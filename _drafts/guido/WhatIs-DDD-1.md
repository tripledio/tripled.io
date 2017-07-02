---
layout: post
author: guido
header-img: "img/about-bg.jpg"
---
What is Domain Driven Design
-----------------------------

Domain driven design, or DDD in short, has in recent years come back into the spotlights with the rise of the microservices architecture. But what is DDD exactly? [According to the ddd community](http://dddcommunity.org/learning-ddd/what_is_ddd/) 
> Domain-driven design (DDD) is an **approach** to developing software for complex needs by deeply connecting the implementation to an evolving model of the core business concepts.

While the above is true, it sounds to abstract and complex to my ears. So lets break it down.

#### Domain

A business domain is an area where certain business problems are being addressed. It has a certain expertise associated with it. A business domain has goals, problems associated with it.

#### Driven

Indicating the relation between the domain and the design. The domain is the driving force.

#### Design

The **D** stands for design, not development. This may seem trivial but it is not. We want to intentionally 
*design* our software.

##DDD

So given the above definitions i will give you my definition of DDD.

>Domain driven design is the **goal** of **designing** tailor made solutions for specific problems in different business **domains*.

It is about striving to **designing** _quality software_ where the **driving** force is a specific **domain**. To me DDD is a goal something we want to achieve. There are many different techniques to achieve this goal. But the technique in itself isn't the goal. Nor does the technique in itself guarantee that the goal will be reached.

The DDD community also states that

> Domain-driven design is not a technology or a methodology. DDD provides a structure of practices and terminology for making design decisions that focus and accelerate software projects dealing with complicated domains.

I agree with the above. DDD is not  a technology. A technology or methodology is a means to an end. DDD is the end goal. Withing the DDD community there are several practices, techniques, terminology that can help us achieve that goal. But these are subject to change when we discover something better. 


Why Domain Driven Design?
------------------
So why should we try to achieve that goal? Why would you want DDD?

DDD enables us to solve complex business problems in an elegant and sustainable manner. Because each solution is designed specifically to tackle a given problem. The solutions are also tailor made for the business domain which allows for a much greater flexibility in creating and adding new features. Separating the different problems in the different domains from each other DDD enables us to really tackle the most important _domain_ problems. 

Remember:

>Design is inevitable. The alternative to _good_ design is _bad_ design. Not _no_ design.

The goal is to have quality software _where it matters the most_. DDD contains techniques for identifying which problems are worth tackling first, which we can postpone or which aren't worth solving at all. 

##Conclusion

I hope to have elaborated in this short post what DDD is for me. I intentionally didn't dive into the many different concepts,techniques that exist within the DDD community. I thought it was important to first make a clear distinction between the goal and the means to achieve that goal.