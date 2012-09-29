I recently read Rob Conery's "<a href="http://blog.wekeroad.com/blog/what-should-microsoft-do-for-net-open-source/">What Should Microsoft Do For .NET Open Source</a>" post where he invites people to answer the question he poses in his post.  Obviously, I could not resist posting my thoughts and views on this.

Before I start, I would like to state that I appreciate all of Microsoft's recent efforts to move to a more open development model.  I think they've done a pretty good job already but nothing's perfect and there's always room for improvement.  So let's just get to the list of things that I would love to see from Microsoft with regards to dealing with Open Source Software in the .NET world.

First of all, I'd like to see a completely transparent development model.  I love the fact that ASP.NET MVC is released under an Open Source License, but it would be better if everyone could track the development.  With that I mean access to the internal bug/issue tracker and source code repository.  I want to know what problems are known, and how they are being dealt with.  I want to see the progress in the code.  I want the ability to either run off the trunk, or to merge specific pieces of the trunk into a released version if that enables me to avoid problems that I might run into with an officially released version.  Getting the source code to a released version is (IMO) only a small part of what Open Source development is all about.

I also want them to be open to outside contributions.  I truly hate running into annoying little bugs that won't be fixed until the next major version (which sometimes takes a year or 2 to come out) but which could be avoided with a simple patch.  Allow people to contribute patches and you'd be amazed at the amount of goodwill and support you'll create among a vocal group of users.  Obviously, this only works when the development model in general is as open as I mentioned earlier.  Nobody is going to submit patches based on a released version if the actual trunk might already contain fixes or has been modified heavily after the latest release.  And being able to patch a released version for your own use isn't always a viable option to most people since you really don't want to deal with having to merge the patch when newer versions are released (and all the regression testing that comes with it).

Microsoft should also play nice with other Open Source projects.  Sure, they included JQuery with ASP.NET MVC which is a good move.  But there are a lot of examples where they developed some library or framework for which a generally accepted Open Source alternative was already present.  I still cringe whenever I'm forced to use MSTest (which to this day is still a pretty crappy testing framework IMHO) while they could've just as easily supported NUnit's development.  And if you're not happy with NUnit, consider the state of MSTest before you complain about my choice of NUnit over say... MBUnit or any of the other testing frameworks.  Does anyone remember NDoc? Was Sandcastle really necessary or would it have made more sense to just invest some effort into NDoc instead of starting from scratch?  My biggest issue with this is that Microsoft's alternatives can often be used without resistance in certain workplaces, just because it's from Microsoft.  It doesn't even matter if there are actually better Open Source alternatives available... In Microsoft we trust, thus Microsoft you'll use.  Not always the smartest choice, as I'm sure many of you will agree with.

Would it really be so bad for Microsoft if they would just assign some developers to help out with projects that already exist?  We now generally have to wait until the third version of any Microsoft product before we really get great quality, while in some cases, a high-quality Open Source alternative was already available from the start.  This often leads to about 3 to 4 years of crappy releases that many people will adopt solely because it's from Microsoft and because "it'll improve in the next versions".   Even if you don't want to assign developers to Open Source projects, it might already be very useful to provide helpful things such as servers, bandwidth, anything that could help out.  Hell, references in official Microsoft documentation on MSDN would already be a huge step up.

There also needs to be some kind of PR cleanup campaign for all of the FUD that Microsoft has spread about Open Source software in general in the past few years.  While it can be argued that that FUD was mainly targeted at GPL software, to many managers in big companies the message came across as "Do not use Open Source because it's a legal minefield".   That is a misconception that many .NET developers are still fighting on a daily basis which isn't good for anyone.

Then there is the issue of support.  I'm not going to repeat myself so I'll just link to a previous post of mine which covers that topic: <a href="/blog/2009/03/support-of-commercial-software-vs-open-source-software/">Support Of Commercial Software vs Open Source Software</a>.  

And as for the host of legal aspects that Microsoft is probably afraid of, I would suggest looking into the reasons why other (large) companies are able to be cooperative citizens within the Open Source world without legal troubles.  Hell, commercial software can be a legal minefield as well so is the Open Source world truly worse?  Maybe they should ask companies like IBM... surely they have plenty of experience in both cases.

Do I expect or even want Microsoft to open source everything in the .NET world? No.  But I would definitely appreciate it if Microsoft would play nice with other Open Source projects, be a more active participant and be open to outside participation as well.  I'm sure I won't be the only one who thinks so.