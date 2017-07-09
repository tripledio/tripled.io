---
layout: post
author: kris
header-img: "img/devops.jpg"
disqus: true
---
# DevOps: Continous Delivery

## History
I'm a *developer*, and have often been in the situation where I needed to work with the classical form of an *operations department*. That basically boils down to:

1. Write code for [3-36] months;
2. Plan meeting with ops;
3. Throw some artifact over the mythical wall separating the men from the boys (either side presumes they are the men);
4. Wait until first failure to start fingerpointing, either way it will point to the other side.

While this has led to many succes scenario's, I have had some better experiences with "DevOps". Unfortunatly DevOps has gone down the same path as Agile. The original intent might have been completely lost during another buzzword bingo meeting. So lets start from the beginning.

![These were once operators too](/img/operator.jpg) 

## Continous Integration
Has been around for a bit longer, and is generally accepted amongst most of the developers. This means the code from John and the code from Dave meet in whatever sourcecode repository that you are using *as fast as possible*. Then it should get picked up by a build server so that there is valuable feedback about the integration: compilation, test reports, etc.

### Details
Branching strategy, or even trunk based development. Both can work, but it all depends on your team. 

#### Feature branching works when:
* Features don't stay open longer than needed, developers drive integration, kanban helps here;
* Changes from the integration branch are distributed on each open branch quickly.

#### Trunk based development works when:
* Developers are good enough to do small increments;
* Architecture allows this;
* Code reviews are pre-commit (pairing);
* You don't have people withholding work on their local machine for days,weeks,etc because it's not done yet.

All-in-all, these days, with most teams, I'd go for the feature branching. It gives you more strategies to play with.

## Continous Delivery
This is where software developers usually fall short. We integrate code as quickly as possible and then it just sits there, gathering dust while developers add more and more features. I sometimes make the comparison of: what if amazon just shipped once a quarter, how would that warehouse look. So we should probably try to not keep everything in the warehouse until christmas, and get things out there, with customers, as soon as possible, they already payed for the code, invested time in talking and discussing the feature, getting it to them as soon as possible feels like the right thing to do.

![Loaded with unreleased features](/img/warehouse.jpg)

#### But wait, I have *environments*
Sure, production is one of them, everybody has that one. Then depending on the terminology you have a UAT, an ITT, a DEV, etc. We usually have them set up, because they were set up manually. As soon as everything has been automated, environments can be created and destroyed as needed. You can have one per feature branch. It can be validated by your product owner. As soon as the branch dies, the evironment disappears. Your environment will turn into your *shortest possible* feedback cycle.

Usually environments are coupled with a set of data. Sometimes it's one they once copied from production for load and/or performance testing. Another automatable task. It's a separate responsability to be able to export/import data from/to any environment. That's sounds an awefull lot like a possible backup strategy as well.

![An example pipeline](/img/pipeline.png)

### Mindset of *complete automation*
What all continous delivery pipelines have in common is that people are no longer required to get something up and running. You write code and sit-back until it's up&running somewhere. The trick here is mindset. Any task that a person in your team has to perform should be automated. The scripts should be versioned inside a version control system, just like code. 

This also prevents other problems, specific information that resides with only one developer is now availabe in a git repo, just like code. This opens up any task to the same process you might have in place for code quality, like code-reviews.

## Recap
So, CD is not possible without CI. It's the next step. There are plenty of technologies that can be used. And any deployment platform should have an automated option, even if it's remotely ssh'ing in and executing the commands from a script under source control. Since people hire us to solve their problems in an efficient automated manner, these techniques should be applied to our own job.

The fact that going to production, or creating/updating multiple *environments* a day means it can't hurt you as much as doing this only 4 times a year. It means you can't have one deployment taking 3 days. 

### Is this DevOps?
It's part of it. But it's a lot more, the *you build it, you ship it* means that you also manage more aspects: monitoring, tracing, log management, failure management, circuit breakers, backups, etc. But I would prefer to start from a CD pipeline, since that would be a basis to rolling out all these aspects. Your infrastructure, formally described declaratively.

My hope is that in a couple of years all apps will be available instantly, that adding infrastructure is a matter of adding some container in a compose file. That would free up time and allow developers to focus more on writing quality code rather then sitting in meeting rooms talking about all the manual steps needed to deploy our applications.

I'd like to remind people about what was said about manual testing. For me this is equally true for any manual task during software development.

>Manual testing is immoral. Not only is it high stress, tedious, and error prone; it’s just wrong to turn humans into machines. If you can write a script for a test procedure, then you can write a program to execute that procedure. That program will be cheaper, faster, and more accurate than a human, and will free the human to do what humans to best: create!
