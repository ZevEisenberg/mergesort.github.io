---
layout: post
title: Designing A High Signal Interview Process
tags: [industry, programming, featured]
---

Crafting a great interview process is difficult[^1], especially for software development where a company is often trying to assess years of specialized knowledge and potential in only a few hours. The best interviews are said to feel like a discussion amongst peers, where each side is providing the other with signal about what it will be like to work together. Candidates share signals about their experience and thought process, while interviewers help provide signal and insight about a company’s values, the working environment, the state of a company, and more.

The interview process for a job in a highly collaborative environment should be highly collaborative, providing a lot of feedback and insights for both sides along the way. The interview I am imagining is nimble and fair, mimicking the day to day work of a software developer in only 3-4 hours over four rounds. Any shorter and it may be hard to glean enough understanding of who a candidate is. If it goes much longer then that it'll be unfair to candidates who can't dedicate a whole day (or two) to interviewing with your company, and will be an increasingly expensive amount of resources to expend as your company grows.

### Transparency

There aren't any benefits to being secretive about the process so I recommend letting a candidate know ahead of time what to expect from their day with you, beginning the process from a perspective of mutual respect. Given a relatively short time constraint the ideal process would seek to emulate the product lifecycle at your company, with time at the end to fill in any gaps you and the candidate may have. The highest-value work that can be done in that time is to build a **small** feature end to end with partners who will be working day to day with this developer.

### The Product Design Round

The first part of most product development lifecycles is one that focuses on communication and iteration, taking a whole world of possibilities and whittles it down to a tangible output. That’s what we’ll aim to accomplish by pairing up the candidate with a product manager or designer, to discuss the feature they’ll be building together.

The product design portion of the interview would start by walking through the scenario the company finds themselves in, the constraints they have, the customer needs, and anything else that is necessary to consider for what we’ll be building. Acting as partners both sides would work together to develop the context and thoughts into an idea, ultimately leading the candidate towards a defined version of the idea that they’ve worked together to build. There should be enough wiggle room to let a candidate's creativity shine through (which is in itself a useful signal), but ultimately by the end of the interview there will be a defined spec and designs of what needs to be built so the candidate can be prepared for their second interview.

If you don’t reach a well-defined spec through collaboration that’s not necessarily a dealbreaker, not all engineers shine at product design. If you haven’t reached consensus on what a good product spec would look like, you should pause with about 10 minutes to left to discuss what an ideal solution is. This will allow the candidate to familiarize themselves with the solution they’ll be building in the following interview, and it will also clue you into other important signals such as communication skills, how they collaborate in situations that have ambiguity, and their ability to respond to feedback (positive and negative).

### The Cross-Discipline Round

Depending on if you're a front-end or a backend engineer, your second interview will be with a partner from the alternative team. (A backend developer would be asked to discuss the front-end portion in the second interview, and a front-end developer would be asked to discuss the backend needs.) In this case we’ll assume that a front-end engineer is being interviewed, so the discussion would involve your team’s backend engineer, centering around high-level architecture, API design, and other ways that a client would interact with a hypothetical backend.

This interview would not be a coding interview, it would be a high-level discussion with a technical partner. The pair would discuss how the feature should work end to end, not asking a front-end engineer to understand the specific implementation details but to know where the front-end and backend would interact with each other. Knowing what SQL queries are occurring under the hood isn't as valuable day to day for a front-end engineer, but having a good idea for what a solid API looks like or how JSON should be shaped for the necessary data is highly beneficial. By the end of the interview the candidate should walk away with a fully fleshed out spec, one that makes sense for the problem they're looking to solve.

### The Proficiency Round

This is the interview where a candidate will implement the feature we've designed and spec'd out. Much like in the first two interviews it’s important to establish early on that the candidate knows that the developer across the table is their partner and is there to help, answering questions, even pair programming if necessary. We want to get a feel for the kind of code a candidate writes, but we also want to minimize the context necessary to solve a problem. It's difficult to write code on demand, especially when there's a time constraint. To balance those requirements we won’t drop the candidate into a huge code base, and will use common platform/framework conventions so they feel as familiar as possible.

Our top priority will be to build something that works, acknowledging the tradeoffs that were made along the way, and talking through where improvements could have been made (if there's room for improvement). The output we want to see is a working solution to match the spec we’ve built upon in prior exercises, if this were a test this would be where the candidate shows their work. The best candidates will be the ones that not only have a good solution to the problem, but also communicate well in the process of building it.

### The Calibration Round

If you’ve ever walked out of an interview hoping the first person you met hours ago didn’t misunderstand a slip of the tongue or an unclear thought, you know how awful it can be to sit with that feeling for 24, 48, or even 72 hours as you wait for a response. Sometimes a company feels like if they had only spent a little more time with a candidate they would have gotten the signal they need to make a solid hire or no hire decision. It's much better for both sides to figure any open questions before a candidate leaves the office, so that’s what this interview accomplishes. This interview is a candidate’s opportunity to ask questions they have for the company, and a company’s opportunity to get answers to any open questions they may still have about the candidate. 

Before starting this interview let a candidate know that the three interviewers they met will be taking 10-15 minutes to try and figure out what questions they have. It’s been a stressful couple of hours so do whatever you can to ease the candidate’s nerves. Assure and reassure them that this is a normal part of the process no matter how well they did, it’s not always feasible to answer all the questions you may have about a candidate in a short period of time. But also let them know that you want both sides to feel confident they know what working with the other side is like, this is a big decision to make. The extra interview session is bidirectional, the candidate will have plenty of time to have their questions answered as well.

Offer some water, let them use the restroom, ask them if they want to take a few minutes to themselves or even offer an employee for them to hang out with, whatever they want after a long day. At first this short gap may seem anxiety provoking, almost like sitting through judgment day, but as long as a candidate knows upfront about the process and motivation it should be a lot less uneasy than days of wondering about how an interview went without an opportunity to correct the record.

Due to the imbalanced dynamics of this experience time-boxing your team to 15 minutes of discussion is a must. In this time a team should be coordinating to figure out what open questions remain, your goal is to figure out if you have enough signal to make a decision, and if not what needs to be asked to get enough signal. You can dive in more to the solutions a candidate came up with, discuss proper leveling, interpersonal dynamics, and whatever else matters to your team.

----------

If the interviewers agree that the candidate did well and don’t have any open questions then this last interview will be short. Provide the candidate with 15-30 minutes to ask about whatever they may want to know, and then let them go destress.

If you’re still looking for more signal then the process will be extended a bit longer, accounting for the questions you want to answer. The candidate will still have 15-30 minutes to learn more about your company, but you’ll also have 30-45 minutes to learn more about the candidate. You may want to clarify a response the candidate gave, which is easy to do with them still here. If you didn't get a good read on their product design skills, have an exercise prepared where they'll need to go in depth a little more. If it was the high level architecture discussion then ask them to design a slightly more complicated system. If you weren't sure about their feature development, work to expand upon what you built in the last session. Like every interview process both sides are trying to leave with as few open questions as possible, so use this time to close out any open doors.

### Following Up

While a high signal interview process is unsurprisingly about getting a lot of signal in a short period of time, it’s also one that aims to have candidates and companies be respectful to each other in the process. A good interview process is only made better when a candidate receives an answer in a timely manner.

Once the interview has wrapped up it's ok to take some time to figure out your thoughts, but don’t take too long. If the process went as expected the interviewers should have a good idea about whether they want to hire a candidate after the third interview, so all that’s left is to figure out the specifics. It’s not unreasonable to come out of an interview to pressing work but it’s important to close this loop, try to make an official call by the end of the day (or early the next day if the interview took place in the afternoon) so the candidate will remember this process favorably no matter the result.

And that's it. This process is quick, has depth to it, and provides a much more accurate feel for what working with a person is like than a whiteboarding exercise. It's a flexible enough approach that you can tailor the interviews to your company's needs, and I would highly recommend doing so, reevaluating what's working and what isn't. We should always be reevaluating our interview processes because talent evaluation isn't easy and needs change as a company and the industry move forward, so if you have ideas for improvement I’d love for you to [share them](https://twitter.com/mergesort) with me.

---

This post was surprisingly difficult to write in a clear and concise manner without making a formal write up feel so formal, and not losing the message by being too informal. It really took a village so thank you to the plethora of people who helped by providing feedback and editing my drafts, most notably [Tamar Nachmany](https://twitter.com/tamarshmallows), [Amro Mousa](https://twitter.com/amdev), and [Brian Michel](https://twitter.com/brianmichel).

[^1]: 

    There are a lot of tradeoffs when it comes to interviewing around preference, fairness, complexity, bias, and more. **To be upfront I won't cover any of that in this post**, but know that they were considered, and some are listed in the appendix below. I have another post planned about how every interview process is flawed and biased, but for now the most important thing to keep in mind is that every interview process, whether it's a take home project or writing code on a whiteboard provides both sides signal, but comes with tradeoffs. Tradeoffs are a necessity because there’s no fair way to evaluate in only a few hours what working with a candidate or a company will look like for the next few years, so it's important to acknowledge as a company which tradeoffs you're willing to make.

    **Caveats, Disclaimers, and Footnotes**
    
    1. This is written from the perspective of a company, but all of these considerations are just as important to a candidate understanding a company they hope to work at for a long time.

    2. Hiring criteria differs, for example sometimes you need to hire the best applicant available vs. hiring someone who can do the role, so you should be flexible and define that ahead of time.

    3. This may not work for your startup, this may not work for a big tech company! But I believe it's a process worth considering if your company is one where engineering, product, design, and other organizational functions are expected to work well together.

    4. Assume that this is an on-site interview, something that may be less common right now, especially with the rise of remote work. The process should still be doable in a remote setting, but there may be some adaptations necessary.
