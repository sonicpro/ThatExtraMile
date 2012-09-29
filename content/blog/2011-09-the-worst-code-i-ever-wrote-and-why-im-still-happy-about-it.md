My last 2 years in high school, I was lucky enough to have 13 hours of programming-related classes every week. Those classes covered a few languages, but the most of it was spent on C/C++ (and nothing advanced either… mostly basic stuff) and Visual Basic. We thought we learned a lot, and I guess from a purely syntactical point of view that may have indeed been true. But we didn't really learn a lot about the differences between good code and bad code. 

We mostly cared about getting our assignments working. When you completed an assignment, you moved on to the next one and none of the code of the previous assignment really mattered anymore. Maintainability or even readability were things that never even occurred to us. Maybe a few of the teachers tried to tell us about it at some point, but it certainly didn't stick. 

In the final year, we could pick a project to work on for the majority of the year. There were no limits on the assignment, so most people picked something that interested them. I was pretty interested in manager/simulation games, so I figured I'd just build my own Formula 1 manager game. The player would get full control over a F1 team, which in my game meant: 

* picking the suppliers for tires, fuel and engines, all of which had varying levels of quality and costs associated with it
* hiring a chief-designer, chief-mechanic and drivers, all of which had a specified talent level and negotiations took the results of the team's previous year into account, as well as the results of the potential hire's previous team, which influenced prices and negotiation tactics.
* landing sponsors, some of which were more than happy to sponsor your team depending on last year's results, or wouldn't even answer your calls and they all had varying budgets as well

I came up with a pretty good formula to simulate realistic race results based on all these factors as well as a dose of luck, or bad luck. If you played for a few seasons, the decisions you made all added up nicely, and gradually. When the project was due, it all worked. Since I loved playing those kind of games, I tested it very extensively by playing it regularly. When issues came up, I'd fix them. When I thought of improvements, I implemented them. I delivered something that worked, and that was large enough in scope and complexity to be impressive for a school project.

But the codebase was truly atrocious. I wasn't using proper structures for either data or behavior and I ended up with a shitload of extensive multi-dimensional arrays. All of my types were in those arrays, as I just didn't know yet that they should've been types of their own. Of course, I listed all of the indices on pieces of paper so I'd know which data properties corresponded with each index. Behavior was all implemented in the UI layer. I was using VB5 at the time, which didn't really encourage me to seek out nicer ways to structure my code. I copy/pasted large gobs of code whenever I needed to reuse something. And of course, whenever I had to make a change, I needed to do it in multiple places. Quite a few places in most cases even. I was using flat files to store data, so I didn't have the opportunity to make a horrendous mess out of a SQL-based data layer but if I had used a database, my usage of it would've surely been epic.

I got a very good grade for the project, and while I was happy to see that all of my hard work was rewarded, it did kinda scare me that a codebase that was so brittle and so painful could actually work, and work well even. It was my first encounter with what is by far the biggest problem with software development to this day: *if you keep adding code, sooner or later it might actually work*. Luckily, this was just a school project. But can you imagine if this were a project done by a professional company? That codebase would've cost money to develop, and the company would actually have a working project, no matter how expensive it would've been to keep working on it. At the time, I couldn't imagine a company in such a situation that would say: "ah, it sucks… we need to start over". And I think we all know that very few companies would actually do that.

I love that horrendous codebase for the lessons it taught me so early on. I learned a lot about what you shouldn't do when you're developing something that's supposed to stick around for a while, and I'm glad I learned it without it costing a lot of money. Of course, that doesn't mean that every single thing I've written since is all roses and peaches, but it put me on the path of trying to continuously improve as a developer, not only in what I was able to do with code, but also as to how clear I could make it to others. 

Note: I no longer have that codebase unfortunately. Really wish I did, if only because it'd be pretty funny going through it after all these years.