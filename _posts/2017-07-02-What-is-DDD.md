---
layout: post
author: guido
title: What is domain driven design?
header-img: "img/DDD-books.jpg"
category: DDD
tags: DDD, Software development
excerpt: A clear explanation of what DDD is

---
What is Domain Driven Design (DDD)? 
-----------------------------

Domain driven design, or DDD in short, is a term that was coined by Eric Evans in his [book](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/ref=sr_1_1?ie=UTF8&s=books&qid=1238687848&sr=8-1) of the same title.
With the rise of the microservices architecture **domain driven design** has come back into the spotlights . It can easily be one of the buzz words that they throw at you during a job interview. Or a requirement for a certain job. But what is DDD exactly? 

According to the [ddd community](http://dddcommunity.org/learning-ddd/what_is_ddd/) 

> Domain-driven design (DDD) is an **approach** to developing software for complex needs by deeply connecting the implementation to an evolving model of the core business concepts.

While the above is true, it sounds a bit to abstract and complex to my ears. So lets break it down.

#### Domain

A business domain is an area of the business where certain problems are being addressed. It has a certain expertise associated with it. A business domain has goals and problems associated with it.

#### Driven

Indicating the relation between the domain and the design. The domain is the driving force.

#### Design

The **D** stands for design, not development. This may seem trivial but it is not. We want to intentionally 
*design* our software.

DDD
---

So given the above definitions i will give you my 'own' definition of DDD.


**Domain driven design is the _goal_ of _designing_ tailor made solutions for problems that are specific to given business _domains_.**


To me DDD is about striving to **design** _quality software_ where the **driving** force is a specific **domain**. I see DDD as a goal. Something we want to achieve. While there are many different techniques to achieve this goal, the techniques in itself aren't the goal. Nor does a technique in itself guarantee that the goal will be reached.

The DDD community also states that

> Domain-driven design is not a technology or a methodology. DDD provides a structure of practices and terminology for making design decisions that focus and accelerate software projects dealing with complicated domains.

I fully agree with the above. This fits very well with my definition. DDD is not a technology. A technology or methodology is a means to an end. DDD is the end goal. Within the DDD community there are several practices, techniques, terminology that can help us achieve that goal. But these are subject to change when we possibly discover a better way to achieve our goal.


Why Domain Driven Design?
------------------
So why should we try to achieve that goal? Why would you want DDD? What is so special about wanting to create a solution for a given problem that really fits the domain? 

In short I can guarantee you that a very high percentage of software solutions are not driven by the domain.  More often then not they are driven by the data used to capture the solution. Or by the tools, technologies that are popular at the moment. Which places a huge mortgage on the software from the get go. But that is a subject that definitely deserves a post on its own.

In contrast, DDD enables us to solve complex business problems in an elegant and sustainable manner. Because each solution is designed specifically to tackle a given problem. The solutions are also tailor made for the business domain which allows for a much greater flexibility in creating and adding new features. Separating the different problems in the different domains from each other DDD enables us to really tackle the most important _domain_ problems. 

Remember:

>Design is inevitable. The alternative to _good_ design is _bad_ design. Not _no_ design.

The goal is to have quality software _where it matters the most_. DDD contains techniques for identifying which problems are worth tackling first, which we can postpone or which aren't worth solving at all. 

Conclusion
---

I hope to have elaborated in this short post what DDD is for me. I intentionally did not dive into the many different concepts and techniques that exist within the DDD community. I thought it was important to first make the clear distinction between the goal (DDD) and the means to achieve that goal.