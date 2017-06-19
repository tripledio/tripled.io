Why Domain Driven Design?
------------------
Domain driven design is an approach for **designing** _quality software_ where the **domain** is the **driving** force. It enables us to solve complex business problems in an elegant and sustainable manner. 

DDD is not a development strategy in itself. It is a design strategy that also uses several software development techniques. 

Properly designed solutions allow for a much greater flexibility in creating and adding features. Enabling us to really tackle the most important _domain_ problems. 

>Design is inevitable. The alternative to _good_ design is _bad_ design. Not _no_ design.

The goal is to have quality software _where it matters the most_. DDD contains techniques for identifying which problems are worth tackling first, which we can postpone or which aren't worth solving at all. 

Domains 
------------------
A domain is an area of expertise where certain problems are addressed. So the domain complexity is the complexity of the business problems, the problems that are solved by business experts.  

Not all domains have the same complexity or the same relevance to the business enterprise. Every enterprise typically needs to tackle multiple problems. But not all of these problems have the same share in the competitive advantage of the enterprise.
 
So the relationship of a domain to the enterprise determines if a domain is core, generic or supporting. 

A core domain is where your competitive advantage lies. Here you will want to _design_ the best solution by creating a _model_. 

A generic domain is a domain that many other business have, like accounting. Typically you can buy an off the shelve solution for this.

A supporting domain supports your core domain. It is a necessity but not important enough to exists on its own. (Yet)

A Chess based example
-----------------------

I'll illustrate some basic DDD concepts with a chess production company - AllGambit. Since i'm not only a software engineer but also a chess player. I know, i know. Talk about clichés. 

AllGambit has multiple chess related offerings. They produces chess content in collaboration with payed Grandmasters. The content can be viewed online according to a subscription model. Of course they also provide an online playing platform where chess players can play chess against each other in all kinds of format. 

With this the AllGambit enterprise already consists out of several domains. 

**Standard chess Domain**

Essential is the online playing platform. Where we want to allow players to play chess against each other on a platform that is so great they are willing to pay for it. This is a **core domain**. The basic functionality everyone expects and the most used. 

**Bughouse Domain**

AllGambit wants to make chess a fun social event so they want to offer full feature packed bughouse chess where friends can easily gang up against each other. They really want to make the difference here. So this is another **core domain**.

**Cheating detection domain**

AllGambit also needs to take care of cheating detection. This is often the reason why people will walk away from a platform. So ALLGambit wants their cheating detection software to be top notch. This is not an easy thing and requires its own expertise. This is a **supporting domain**. But an important one.

**Content creation domain**

Quality chess content is a convincing way to get customers to subscribe. So we need quality content by hiring grandmasters. This is a **core domain** but not one that can be solved by software.

**Content delivery domain**

Our online content of course needs to be easily accessible. We want to pay those grandmasters according to the nr of followers and interactions they have with our customers. This is a **generic domain**. It is important but there are plenty of video and chat platforms out there.

**Subscription domain**

It needs to be easy and secure for customers to subscribe to the AllGambit platform. But this is a problem that already has been solved so that makes it **generic domain**.

**Bookkeeping domain**

We need to keep track of the money of course. Paying our grandmasters, employees and tracking all the bug bucks we make from our customers. Obviously a **generic domain** that can be handled by off the shelf software.

Domain models
-------------------------
In order to solve the domain problems in reality we will create domain models. A _domain model_ is a simpler representation of a domain in reality. It is a simplification of reality where we have removed irrelevant parts. We just want to keep the useful properties that can help us in solving the business problem. 

>A domain model is a _strict_, watered down version of reality. What it has lost in richness, it has gained in strictness.

Models are distilled. They do not appear out of thin air, complete and correct. Reality can be represented in many different ways so there are many different models possible. 
>The goal is to distill a model that is the most usefull for solving the business problem. 

Domain models need to capture a deep understanding of the domain and its problems. A common saying in the DDD community is _throw away the model_. Recognising that the next model will be better because we have gained a better understanding of the problem to solve. If this sounds like waste to you remember that we are writing **soft**ware. It is intended to be easy to change. Otherwise we would make it into hardware. The complexity of software development often lies in designing an appropriate model. 

>If your software is hard to change, something has gone wrong. It is probably high time to start paying of your technical debt.  

An interesting aspect of modeling out a problem is that a model creates a _language_. And language makes for a very useful tool in tackling problems.

  

Ubiquitous language 
-------------------------- 
We want the model to be strict and as a result we need the language used to define the model to be _Ubiquitous_. This simply means that we need all the parties involved in a given domain to speak the same language. This will avoid any misunderstanding and allow us to create a _clear_ and powerful domain model. 

>The model should act as the Ubiquitous language.

In practice you should use the words from the domain model in any requirements document. There should be a clear, concise document that describes the language with clear definitions.

>If something is hard to define, it is hard to code

So take your time to get your definitions right. It things are not clear, speak up.

Bounded Context
--------------------

An ubiquitous language is not omnipresent. It is impossible and inadvisable to have one language, one model for the whole company. There is a _boundary_to the model, to language meaning. 

Depending on the context the meaning of something may change. In our AllGambit example, starting a game in our _standard chess domain_ is completely different then starting a game in our _bughouse domain_. 

It is important to explicitly define the _context_in which a model applies and what its _boundary_ is. This is called a bounded context in DDD. The boundary for a context, the boundary in which the model, language applies. It is one of the big buzz words from DDD. 

Having multiple bounded contexts is important. Having multiple models that try to solve their problem well without being muddled with other concerns will make for much better solutions.

>Do not use one model to rule them all

In the AllGambit example it could be said that normal chess is a simple case of bughouse chess. You simply have no team mates. But this would complicate the model for chess tremendously. Better to tackle them as two separate domains. So that the standard chess playing model can be crystal clear and not impacted form the complexity of the bughouse chess domain.


Implementing a domain model
---------------------
Creating a software solution comes with lot of technical complexity. It is however important that the technical concerns have minimal impact on the _design_ of the _model_ that will solve the domain complexity. 

Technical concerns should not drive the solution of the problem. These are just the tools used. And while it is important to know how to use your tools well, they are obviously not the goal.

In DDD unambiguity is key. Things need to be clear. A wel known saying in DDD is : _"Make the implicit Explicit"_ Don't let the domain be a second class citizin in your code base. Modelling and designing is of the utmost important. If things aren't explicit, they will need to happen somewhere implicit. 

Therefore let the clear language of the domain model be used in the code. Separate the model clearly from the technical infrastructure.

DDD contains something for everyone...
----------------------------------------
##### For the business
DDD will give you a better understanding of your own domain. Because the model created needs to be strict, a lot of concepts will need to be made explicit.

The ubiquitous language will ensure that you can communicate directly with all the members of the team. Concrete business concerns, feature request can and should be discussed with everyone.

DDD will give you a solution that solves your actual problems. It will enable you to try out useful features and new concepts you didn't even know about.

A good model, tailor made to your problem will give you a big competitive advantage. It will enable you to go fast there where it matters.

 
##### For product owners
It will give you a clear language to communicate with the business and the software engineers. The model will give you a better insight what the problem domain is all about and which features should take priority.

But be careful not to be the middle man that blocks access from the software engineers to the the end users that will use the software. Close collaboration is required to really understand the problem that requires solving. Information on the real needs can only be gathered on the business work floor. Not through a middle man or manager.  So make sure not to become that middle man.

##### For software engineers

Remember that the choice is to have a good or bad design. So let us take the time to _think_ before we code. Once a model and design is clear, programming the model is the "easy" part. 

>It is not because engineers aren't coding that they aren't working.

The _designed_ solutions should be _driven_ by the _domain_. Not by the data or by the technical frameworks. 

That a domain model is a watered down version simply means we have removed the irrelevant parts. 

>We are driven by the domain meaning of concepts, **NOT** by their data representation.


Conclusion
--------------------
There is much more to DDD then the basics we've just covered. A lot of different techniques, technical and non technical. Apart from the patterns we discussed, DDD also specifies several other patterns. These range from tools for better collaboration like Event Storming to tactical design patterns for software development like aggregates, value objects... 

But that's a story for another day.

I hope to have contributed a little bit to a better understanding of what DDD is.