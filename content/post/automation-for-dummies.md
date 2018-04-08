---
title: "Automation for Dummies"
date: 2017-10-29T23:00:14+07:00
draft: false
---

![Geeks and repetetive tasks](/images/geeks-and-tasks.jpg)

I have a very horrible thing to admit here, I was a manual QA engineer then I first started out in IT. I was repeatedly clicking those buttons, again and again... we had a smoke test that took a whole day to check. So every 2 weeks I was losing my own time clicking those interface buttons in a similar way, just to check if system was fully functional. After that point in my carrier, I picked python and started automating all those routines. I dedicated a lot of my time to never do repetitive tasks again. And here are most important give away's I have so far to simplify your life with a software project:


### You still need to check things manually

Hate to break it to you. But your 'automation' is only able to check narrow set of rules to consider system in a valid state. You still need to check out things manually. Automating some of most common routine is a best thing you can do. Some ideas to automate:

- Use Procfile's and be able to launch environment very close to production with one command

- Have a reasonable copy from production database (but don't forget to sanitize some of the data, just in case)

- Anything else that takes a lot of your time, but you have to it regularly

### You don't need to have a 100% coverage

Let's face it, it would be very nice to have a 100% code coverage to feel safe and good. But in the real world, we're very unlikely to invest so much effort into covering existing code base fully. There is no sense - churn is low, complexity could be low as well - it works, your unlikely to fix it, don't write any tests for it.

### Integration testing is a scam

People really want to find shortcuts in everything. And it is fantastic, but there is always a catch. If you never did any automated testing before, probably the only metric you know about is test coverage. And that metric leads you towards very incorrect actions -- usually it is integration testing. You'll be hyped up about the fact that it covers all your code so fast -- since it covers all layers of your application. But it come with a huge costs -- those tests require you to investigate, understand where something went wrong, they are very fragile and they are ridiculously slow.  I think mister J.B.R can tell a better story about them then i do:

<iframe width="560" height="315" src="https://www.youtube.com/embed/VDfX44fZoMc" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

### Automated testing is also a production code, you need to maintain it too

Don't over do it, like seriously - don't test things just because it's easy to do. You can't really justify testing all possible scenarios, in a situation then your system uses code in a very limited scope. You also need to be sure that your automated testing is easy to read, so it could double down as documentation/example of usage.

### Have a bug - write a test that reproduces it

Most reasonable way to start off testing for a big project - automating all the bugs you have."Bug" is a a great justification that this particular functionality is critical enough for business to care. It happens second time - business will raise this issue again! So it is as simple as that, write test for it!

### Fail really loudly

I have to admit, that a lot of mistakes happen due to some miss configuration. But somehow, a lot of software that people write try to keep running without satisfied dependencies. It seems obvious, but it is not - a lot of companies don't get it right. If you can't guarantee that your system will function properly without Redis being properly configured -- BLOW UP YOUR APP, don't give it a chance to run! 