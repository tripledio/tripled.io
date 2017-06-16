---
layout: post
author: domenique
disqus: false
---

*SOLID*,  The famous acronym coined by Micheal Feathers describing the first five principles of object oriented design composed by Robert C. Martin a.k.a Uncle Bob. What most people tend to forget is that **SOLID describes only five of the in total eleven principles of object oriented design**. These principles date all the way back to 1995, yes Uncle Bob is really that old :)

This post will briefly describe the well known SOLID prinicples, afterwich we will dive deeper into the 6 other, lesser known principles. This post will ultimately become a series, so do check back for follow-up articles.

## SOLID Principles

The SOLID principles are the first five principles of object oriented design and focus around class design. 

* **S**ingle responsibility principle
* **O**pen closed principle
* **L**iskov substition principle
* **I**nterface segration principle
* **D**ependency inversion principle

## Single responsibility principle
<iframe width="560" height="315" src="https://www.youtube.com/embed/2k1uOqRb0HU" frameborder="0" allowfullscreen></iframe>

**SRP**(Single Responsibility Principle) dictates that a class should have only **one reponsibility and this reponsibility should be fully encapsulated by the class**.

In the context of **SRP**, Uncle bob refers to a responsibility as being *a reason for change*. He concluded that if you can find more then one **motive for changing** a class, then that class has more then one responsibility. Failing to adhere to this principle could result in *rigidity* because clients of your class will be **forced to change for reasons they shouldn't**, on the other hand, applying this principle without looking carefully at the context of your application can have a negative effect and introduce needless complexity. 
> The Single Responsibility Principle is one of the simplest of the principles, and one of the hardest to get right. Con-joining responsibilities is something that we do naturally. Finding and separating those responsibilities from one another is much of what software design is really about. Indeed, the rest of the principles we will discuss come back to this issue in one way or another.
> 
> -- Uncle Bob

## Open closed principle

## Liskov substition principle

## Interface segration principle

## Dependency inversion principle