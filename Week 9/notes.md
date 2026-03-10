# Week 9

## Application Development Coding Process
Creating an Task Management System using a webstack (I'll have to look into that).

Ensure you include code documentation and project documentation. 

Develop a user requirement for the application as well

Code review can be conducted by you or by a peer. Document before you refactor.

Document any errors you encounter when debugging. **This should be done using GitHub actions**.

https://stackoverflow.com/questions/667781/what-is-the-difference-between-mvc-and-mvvm

## Design Patterns
A design pattern is a reusable fragment of code which we utilize as a solution to a specific problem. 

What is the purpose of learning design patterns? 

## Video
Design patterns are accepted solutions to common well-known or well-definied problems

Based on OOP principles
- Program to an interface, not an implementation
- Favor 'object composition' over 'class inheritance'

Most commonly used designed patterns were createed with OOP paradigm in mind.

### In OOP, we rely on the inheritance chain to share data and behaviour

In the typical OOP approach, we write inherited classes that are meant to interact in some way. But this can make it difficult to determine where methods should live.

Programming to an interface means to write a shared "contract" for implementations

An interface is an abstract definition of some behaviour that you want your objects to implement. This has the benefit of keeping your class definitions clean an making testing easier.

### Composition over inheritance
Relying solely on inheritance chains for behaviour can be limited and can lock you into dangerous patterns that produce brittle or over-engineered code.

Object composition allows data and behaviour from related objects to be composed into more complex objects that meet behaviour requirements

This is related to the idea of function composition and higher-order functions in functional programming paradigms

Deisng patters are typically categorized into three solution-based classifications:
- Creational Patterns - used for creating objects (sometimes many objecs) in a predictable way
- Structural patterns - used for composing classes into larger structures with more complex behaviour
- Behavioural patterns - used to support common communication patterns between ddistinct objects.

Wikipedia has an exhaustive list of accepted patterns. It also contains a fourth category of Concurrency patterns. 

### The Singleton Pattern
Responsible for managing a common resource or program state. Used when you only ever need on instance of a particular class

This is a creational pattern. It is typically globally available.

The class definition makes creating instances of the class imposible via:
- private constructors
- public GetInstance() method that returns a static instance

### The Observer Pattern
Notifies observers of state changes to that they can update correctly.

Responsibility: subjects keep a list of observers; observers subscribe and unsubscribe to subjects

This is a behavioural pattern. Notifications ae one-to-many. Subjects don't care how many observes they have, but keep a full list.

Observers have the responsibility of subscribing to subjects. Ideally, subject and observers are loosely coupled.

### Design patterns are not bullet proof solutions to all problems.

Some have stated that design patterns are really 'kludge' solutions to missing features in programming languages (i.e., kotlin's object keyword makes the singleton pattern obsolete)

Design paterns are paradigmatic by nature - the common design patterns won't naturally fit other programming paradigms.

When you have a hammer, everything looks like a nail -- don't overuse design patterns, as they may not be the best solution in every scenario.

### Anti-Patterns
Common patterns that you should avoid. Can be language specific, so it can be difficult to have a good grasp on all anti-patterns.

Sometimes thought of as "solutions" but do not always apply all the benefits one would expect.

The best way to avoid anti-patterns are:
- Code review
- Style guides
- Idiomatic code

