## READ THE OOP DOCUMENTATION
**Write a summary on how you envision applying Object-Oriented Programming (OOP) in your programming assignment, including relevant examples.**

The most obvious use of OOP in the programming assignment will be the Task object. I plan to create a Task class which will hold the relevant details associated with the task (title, date created, due date, completion status, etc.), and will instantiate new instances whenever a new task is created by the user. Any modifcation of a task will be done using methods in the class. Tasks will be kept in a List and can be easily added or removed from it. If I decide to add variants of the Task class (perhaps I could implement simple tasks as well as complex, multi-step tasks) I could create additional classes which inherit from the base class. 

Since I'm planning to develop this project in Javascript, Task may be the only object tht I create (unless the assignment requires a specific number). However, if I were doing this in another programming language, like C#, I would probbly also create a singleton TaskManager class which holds the Task list and performs any deletion or insertion operations into it. 


## FOLLOW-UP QUESTIONS AND REFLECTIONS
**Determine if your chosen programming language is OOP capable. To what extent does it support OOP? Fully, or partially? Does it support any other paradigms? Wikipedia has a good list of multi-paradigmatic programming languages.**

As mentioned above, the language I will be using for the assignment is Javascript. As far as I'm aware, Javascript is fully OOP capable, though, unlike some other OOP languages (C#, for example), Javascript doesn't enforce the use of classes. Instead, the language is often used with a more procedure-oriented approach.

Javascript also supports functional, imperative, and reflective programming paradigms, and patially supports concurrent programming.