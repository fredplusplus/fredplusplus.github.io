---
layout: post
title: "Ship it today v.s. Refactoring"
description: ""
category: Geek
tags: [Product Management]
---
{% include JB/setup %}
I came across an interesting disucssion today about the balance of shipping product ASAP versus taking time to refactor code.

The discussion is essentially around the balance of time and cost. PMs obviously want to release a feature as soon as it works. The longer it waits, the more risky it becomes.
+ More time means more cost.
+ Competitors may catch up.
+ Customers are waiting.

From the developer side, everybody wants to release ASAP. But the definition of "product finish" is quite different on this side. Developers not only wants to make a product work, the code must also be rubust, and well tested. Unfortunately it usually means more time, sometimes even cutting feature. Why don't we want to release once we see the code working?
+ Need regression test
+ Need feature test
+ Need proper code review/best practices
+ Validate there is no hack in code

As a developer, I constantly get requests from our PMs asking why something simple as adding one message cannot be launched in 2 hours. Here is why. All the code is generic, adding a message here equals adding a message everywhere the codebase covers. Yes, adding a line here will get what you want. But I need to make sure everybody is expecting the same message. If somebody says they don't want to have this message, I need to implement some kind of check to suppress it under certain condition. So on and so forth. And whenever a request like this comes to me, I need to evaluate whether my system is the best place to handle it. Sometimes I can do it doesn't mean I will do it (and many people just don't get it) . To summarize, implementing a feature is never as simple as it looks like.

So, why do developers need to worry about any of these? Because developers are ultimately responsible for the successful launch of a new product, and all the future maintenance. One may think it's not a big deal to add a hack and take it out 3 weeks later. But trust me, when you think you will take out a hack in 3 weeks, it never happens. Over time, code is trashed with patch/hack/magic, and nobody knows why it works/doesn't work. Imagine my frustration when I get a 2AM page!

Every company, every teams eventually will run into a decision on whether they should just release a half-backed product due to time pressure, or delay the product and follow best code practices. Well, my vote is ALWAYS to follow best practices and eliminate any hack. The biggest problem for me is to get the invaluable time in order to write the right code. Here is something I always remind myself:
> I spend 90% time to complete the first 90% of the project, then I spend another 90% to complete the last 10%.
So you see, when I think I need 1 week to write a feature, it will take me two. The time includes designing, implementing, unit testing, integration test, release, monitoring, supporting, etc. Testing and following best practices are essential parts of writing a feature and not optional, so they need to be included as part of the product cost. If the extended time means product can't launch in time, so be it.
   