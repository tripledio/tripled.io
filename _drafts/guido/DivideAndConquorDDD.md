### Introduction

When Eric Evans introduced DDD he gave a name to a lot of concepts professionals where using and crystalized their meaning. We now have a common dictionary when trying to apply DDD. Since the renewed interest in DDD a lot of the DDD concepts are now 'known' to most of the people working in the software industry. Knwon by name but not necessary by meaning. In day to day discussions i often encounter some confusion on the exact meaning of some of the classic well known DDD concepts. Confusion on what they mean exactly, how they relate to each other and what is their practical use. 

This is especially true in the realm of strategic design since a software engineer is typically more drawn to the tactical design patterns. Those patterns where what was picked up by the largest group of developers from the blue book. Because as developers we want to see the code :) and we could see the practical use of the tactical patterns. Later DDD books have tried to correct this by starting with the strategical patterns before delving in to the tactical patterns. With good reason.

The strategic ddd concepts are quite useful and practical. But since they are not immediately visible in code and they apply to a larger area then a single application they appear to be less relevant for the hands on practical software engineer. I also fear that they are often explained to abstract and that their relations aren't immediately clear. 

So in this post i'll make my own humble attempt at explaining some of the DDD strategic design concepts. Hopefully it can clarifies some things and help you applying these patterns trying to solve some of your business problems. Because they are important, relevant and useful.

### Applying a classic strategy

When we are faced with a large complex problem, we typically try to solve it by splitting it up into several smaller problems. Then we can try to solve the smaller, less complex problems. If the problem is still to complex, rinse and repeat... In other words we apply the classic divide and conquer strategy. 

Once we have partitioned the problem, we then would like to conquer the important problems first. Since in this reality time and resources are limited  we need to take that fact into account. Therefor we should to be doing the import work first and foremost. Postponing or perhaps never doing the work that has a low priority. Don't fall into the trap of trying to solve everything and do everything perfect. This will cost a lot of money and increase time to market.

Dividing and conquering is a classic strategy, one that we often use in our daily life as well. It so happens that the tools in our DDD strategic match very well on this strategy. Coincidence? 

### Divide...

###### The Problem space
We start by identifying the area of business problems we are trying the solve. We call this collection of problems the **problem space**.
https://en.wikipedia.org/wiki/Problem_domain
###### The Domain
This problem space resides in a certain **domain**, a business area. A domain is an area where people are working, solving certain problems in the real world. Solving their problem often requires certain deep knowledge of the functional business area, the domain. Therefore there are often **domain experts** associated with a domain. Domain experts are very well versed in solving the problem in that area, that domain.  If a domain does not require deep knowledge, it is an area that probably isn't worth worrying a lot about since anyone can do it. 

For example when the business you our working for is a bank you our in the financial sector. That is your domain. If you own a chain of shopping malls then your domain is in the retail industry. 

The business problems you are trying to solve will be located in that domain. Both examples are actually very large domains that require people  to perform a variety of tasks. You will need different domain experts to cover this wide range of required knowledge.
 
If we see that there are different domain experts each with their own specialized knowledge, that the structure of our organization is split up to solve different problems, this probably means that our domain is too large to reason about. For in reality people have already splitup the 'problem'. So we want to do the same in our division of the problem space.

In short, when we have a large and complex domain, that is divided in the real world, we will also want to further divide our domain into **subdomains**. 

###### The Subdomains
**A subdomain** is basically a domain with is a subset of a larger domain. It again represents a clear area of expertise that is responsible for providing a solution to a certain area of the business. 

Subdomains are a part of your overall business domain. You can usually see the division of your domain into subdomains by looking at the organisational structure. 

In our shopping mall example we will have multiple subdomains. The distribution and delivery of products. The stock inventory. The human resources management of your employees,... 
 
In our ban example we will have a domain that handles mortages, one that handles trading, one that handles savings,... 

![Domain-Subdomain-example]Domain-Subdomain-example(/content/images/2017/02/Domain-Subdomain-example.png)

Once we have broken up our whole business domain into subdomains that reflect the different area of expertise, we can start grouping the domains by their properties.

Note the importance of *dividing* the problem space first before trying to conquer it. If you immediately try to solve a problem without realising its relation to other business area's you might end up solving the wrong problem, solve a problem of small importance or trying to solve a much too large problem.

###### Domain types

Once you understand what you problem is, where it resided exactly, what its relation is to the other domains... then you can start addressing it. 


**A word of caution** In reality you never start with a clean plate. A company, business will constantly evolve. People were doing business long before the term domain was ever coined. So this is not an excuse for big up front design or a strive for perfectly identifying all the domains and their inner relations in great detail. If this was a requirement to apply DDD then DDD would not have been very useful. Don't make DDD an excuse for perfectionism. DDD is perfectly capable for tackling problems in the real world. It is not something academic that only sounds well in books.

----

HERE

#### The Solution space

In the **solution space** we try to conquer the problem. It is the way we are trying to solve the problems from the problem space. 

We can solve a problem by creating a model for it. A *representation* of some business area that helps us solve our problem in the domain. This model is therefor called the domain model. 

different solutions to the divided problems.



### Patterns for dividing the problem



#### Subdomains



### Patterns for solving the problem

#### Bounded Context

A bounded context is, thanks to the (re)popularisation of microservices, one of the more known DDD concepts. A bounded context is a boundary of language where everything inside the boundary has a clear and unambiguous meaning. 

#### Ubiquitous language

The language that is used inside a bounded context and that is known and clear to everyone. Hence ubiquitous.  It is used in conversations between software developers as well as business people, domain experts and hopefully also is present in the software. It is a strict and clear, strict and exact. This language does not come into existence by itself. **Effort needs to be made to define it.** It should be the language used in your typical user stories, use cases.

#### Domain model

Domain models are built to fulfill use cases in a certain subdomain. They are the actual solutions to the problems. They are implemented in the software. 

Ideally they map one on one with a subdomain, solving a specific set of use cases. But in reality this is not always so since not all domain models are created by using DDD techniques. They can span multiple sub domains although this is far from ideal. 

Domain models are dependent on several factors: the team and its structure, the language used, applicable business processes, ... Their dependence on those factors makes it hard to keep the models clean and focussed. More often then not they are based on an unclear language with unclear concepts. 

#### Context map

**TODO**



           /-----------------------\
          /          |              \
Explore  |   Problem | solution      | Model
          \  Space   | Space        /
           \-----------------------/
A use case is a solution for a problem

## Our DDD vocabulary so far
* problem space
* solution space
* domain
* subdomain

## Relations between strategic DDD concepts

#### Domain - subdomain 
A **domain** contains several **subdomains**. Subdomains have a type, an importance attribute that is related to your overal domain and that is dependent on the overal problem you are trying to solve within your domain. 

A **subdomain** can be **core**, **supporting** or **generic** inside your **domain**. A core domain is where you gain your competitive advantage from, a supporting domain is not core but it is specific enough that it warrants custom software. A generic domain is a domain for a problem space that has been solved and is generic enough that you can buy an of the shell product for it.

It is important to note that the type of the subdomain is determined by your domain. What is a generic subdomain in your subdomain will be the core domain of another domain. The generic products you buy have to be written by a business whose core business it is of creating that software.


#### Subdomain - bounded context

A **subdomain** can contain several **bounded contexts**. Ideally a subdomain contains a clean single bounded context.

#### Bounded context - Ubiquitous language

By definitions a **bounded context** is the boundary of a **ubiquitous language**. The language is defined by the context in which it has meaning. 

#### Bounded context - domain model

A bounded context is the language boundary in a subdomain. The ubiquitous language in the context will be used to build our model. So a **domain model** also should exist inside a **bounded context**. Concepts used in the domain model exist in the bounded context. The domain model should **not** use terminology that is outside of the bounded context. 

A model normally will not cover more then one bounded context because this would mean by definition that the application would be ambiguous. One thing could mean different things. Technically this is of course possible and many monolith has fallen into this trap.

#### Domain model - application

An **application** contains typically one **domain model**. Although it can contain more. But it then requires a lot of discipline to keep the models separate. Few applications have managed this and it is one of the reasons that a monolith has such a bad reputation.

## A picture

Below you can find an overview of different combinations and relations between domain, bounded context and models.

![](/content/images/2017/02/Domain-BC-Applications.png)

## Tackling the problem

Below i wrote a very simplistic and naive list in which order the patterns described above could be applied to tackle a problem. The actions that need to be taken or highly dependent on the actual problem at hand. But my goal is to illustrate the difference and the relationship between the different strategic design patterns and how they can be used together.

#### Define the problem space

* define your subdomains
* list the importance of each sub domain
* list the size of the effort to be made for solving each domain
* the sub domain with the highest importance and highest effort size should be your main focus and have the best people

#### Define the solution space

* define the bounded context(s) in the sub domain. Where are the language boundaries?
* Use a context map to map out how the different bounded contexts relate to each other. This is an ongoing effort that should map the reality.

#### Tackle a subdomain

* for the sub domain that you will tackle define the ubiquitous language. This is an ongoing effort
* **If worth the effort** implement a domain model inside the bounded context using the tactical patterns. How you implement the bounded context is again dependent on the importance of the sub domain.
