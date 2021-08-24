---
layout: post
title: Creating Slick Color Palette APIs
tags: [swift, programming, featured]
---

The work of writing maintainable code is an ongoing endeavor and some of my favorite problems to solve are ones that build maintainable systems. Maintainable systems are ones you can learn once, easily manipulate, and ideally take from project to project. My favorite part of building maintainable systems is that it minimizes the amount of work I need to do when starting a new project, and like it is for many programmers hitting ⌘ + ⇪ + N to start a new project is one of the most satisfying feelings in the world for me.

A color palette is something every well-designed app needs, and it turns out there are a lot of ways to solve this problem. If you don't yet have a good sense for how to construct a color palette, I highly recommend [this post by Refactoring UI](https://www.refactoringui.com/previews/building-your-color-palette) that explains the fundamentals of a good color palette. Generating a good color palette can be tricky if you’re new to the practice and can require some trial and error, so if you’d like a shortcut a tool like [Coolors](https://coolors.co) is a great starting point.

I've spent years iterating on approaches to codifying color palettes in my iOS and macOS apps, seeking to create one that’s flexible, scales well, and is easy to understand, landing on the version we’ll explore below. We'll be able to leverage asset catalogs, create a clear sense of hierarchy, provide statically typed semantic colors, even take advantage of the built in features of SwiftUI. As a bonus, if you're working with designers, your palette will be so straightforward to modify that a designer can submit a pull request to change colors without ever involving you.

---

Considering we'll be leveraging asset catalogs, the first step should be pretty intuitive, we should create an asset catalog to hold our color palettes.

![An image displaying an asset catalog in a folder called Resources]({{ site.url }}/assets/img/color-palette-resources-folder.jpg)

As I was piecing together different instructions and ideas this second step confused me, so I'll spare you the misery. You're going to want to make a different folder for each color palette you create, and you can do that by right clicking in the asset catalog and selecting *New Folder*.

![An image displaying a New Folder option when you right click inside of an empty asset catalog]({{ site.url }}/assets/img/color-palette-right-click.jpg)

Now it's time to create our color palettes. I'm showing you the Night palette I created for my app, and below it are Spring, Summer, and Winter. Each palette has the same name but all of the colors are named the same, each palette will have colors named background-alt, primary, quaternary, etc.

![An image displaying four color palettes from my app]({{ site.url }}/assets/img/color-palette-asset-catalog.jpg)

**Do not miss this incredibly important step, guide your eyes towards the pink arrow on the right side of the image.** You must select the folder you're adding colors to and check the **Provides Namespace checkbox**. This is what will enable our code to have a clear and consistent naming structure, matching the folder’s name to our theme’s name.

---

Now that we've got our asset catalogs setup, we're ready to write some code. We'll start by constructing a new `Palette` struct, and populating it with some `Color`s that we'll reference across our app.

```swift
extension Color {

    struct Palette {
        let name: String

        var mainBackground: Color {
            self.assetCatalogColor(named: "background-main")
        }

        var midBackground: Color {
            self.assetCatalogColor(named: "background-mid")
        }

        var alternativeBackground: Color {
            self.assetCatalogColor(named: "background-alt")
        }

        var primaryText: Color {
            self.assetCatalogColor(named: "text-primary")
        }

        var alternativeText: Color {
            self.assetCatalogColor(named: "text-alt")
        }

        var primary: Color {
            self.assetCatalogColor(named: "primary")
        }

        var secondary: Color {
            self.assetCatalogColor(named: "secondary")
        }

        var tertiary: Color {
            self.assetCatalogColor(named: "tertiary")
        }

        var quaternary: Color {
            self.assetCatalogColor(named: "quaternary")
        }
    }
}
```

This is a pretty standard palette and should cover most of the use cases you'll encounter in building an app. You can modify it to your needs, but the important thing is that the colors you choose need to match the names of the colors you declared in your asset catalog. But what is this `assetCatalogColor` function?

```swift
private func assetCatalogColor(named semanticColor: String) -> Color {
    #if os(macOS)
        return Color(NSColor(named: "\(self.name)/\(semanticColor)")!)
    #else
        return Color(UIColor(named: "\(self.name)/\(semanticColor)")!)
    #endif
}
```

The `assetCatlogColor` function lives in `Color.Palette`, and it takes advantage of our namespaced folder structure to pull out colors from the asset catalog. `self.name` is the name of our theme, and `semanticColor` is the name of the color we're pulling out, such as `primary`, `secondary`, or `background-main`. Combining the two with a `/`, we'll get the `primary`, `secondary`, or `background-main` color from our current theme. All that's left is to define the themes we'll be constructing.

```swift
extension Color.Palette {

    static let spring = Color.Palette(name: "Spring")
    static let summer = Color.Palette(name: "Summer")
    static let autumn = Color.Palette(name: "Autumn")
    static let winter = Color.Palette(name: "Winter")
    static let day = Color.Palette(name: "Day")
    static let dusk = Color.Palette(name: "Dusk")
    static let night = Color.Palette(name: "Night")

}
```

Constructing themes is pretty easy. All you have to do is instantiate a `Color.Palette` object with a name. That name must match the folder name, so in my app the theme name for `Night` will be `Night` because the folder we chose for that theme was `"Night"`.

---

Now that we have a color palette created, we should probably start using it. If you're using UIKit you'll likely have built your palette atop `UIColor` instead of `Color` and used `.palette.primaryText` wherever a `UIColor` is expected.

But if we're building our app in SwiftUI, we can go the extra mile with just a few lines of code to leverage the `Environment`, making our palette easily accessible and SwiftUI-friendly.

```swift
private struct ColorPaletteKey: EnvironmentKey {
    // We need to default to a theme so without any particular preference let's pick `day`
    static let defaultValue = Color.Palette.day
}

extension EnvironmentValues {
    var preferredColorPalette: Color.Palette {
        get {
            return self[ColorPaletteKey.self]
        }
        set {
            self[ColorPaletteKey.self] = newValue
        }
    }
}
```

This creates the `preferredColorPalette` property in our `Environment`. If you're not sure how the `Environment` works there are a lot of great resources on the internet like [this post by Keith Harrison](https://useyourloaf.com/blog/swiftui-custom-environment-values/).

```swift
struct HeaderView: View {

	@Environment(\.preferredColorPalette) private var palette

	var body: View {
		Text("Hello World")
			.foregroundColor(palette.primaryText)
	}

}

```

Now accessing our colors is a nothing more than two lines of code, how slick is that?

---

Hope I didn't wear you out, there's a lot here, but when you throw it into Xcode you'll see that it's pretty easy to digest. After a few iterations I'm really happy with this solution and have been using it in my personal apps for a while now. It allows us to easily add or change colors, have a visual representation of our colors, with minimal code, and a pretty slick API.

But no code is perfect (except for [mergesort](https://en.wikipedia.org/wiki/Merge_sort)), so I'm always looking for improvements. I'm excited to hear your thoughts or [suggestions](https://twitter.com/mergesort), so don't be shy about reaching out.