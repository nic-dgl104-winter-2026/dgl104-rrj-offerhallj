# Week 11 - Object Oriented Programming
Software development has gone through many evolutions over the years. These layers were built one upon the other, with each layer representing an improvement over the previous one.

Machine Language > Assembly Language > Procedural Programming > Object Oriented Programming

Since the Invention of the computer, many programming approaches have been tried, including modular programming, top-down programming, botom-up programming, structured programming, etc. The motivation in each case has been to handle the increaseing complexity of programs. 

**Structured Programming** is a powerful tool that enables programmers to write moderately complex programs fairly easily.

With the advent of languages like C, structured programming has become very popular. 

**Object Oriented Programming (OOP)** is an approach to programming where organization and development attempt to eliminate some of the pitfalls of conventional programming methods by incorporating the best of sturcured programming with several new concepts.

## Procedure-Oriented Programming (POP)
Conventional programming using high level languages is commonly known as procedure-oriented (or procedural) programming. In POP, the problem is viewed as a sequence of things to be done, such as reading, calculating, printing, etc. A number of functions are writtent to accomplish these tasks.

POP consists of writing a lost of instructions for the computer to follow and organizing these instructions into groups of functions. 

POP uses global variables to make data accessible to these functions.

#### Disadvantages of Global Data
- Global data is more vunerable to inadvertant changes
- In large programs, it is difficult to identify which data is used by which function
- When we need to revise an external data structure, we should also revise all functions that access the data

POP does not always model real-world problems because the functions are action-oriented and do not really correspond to the elements of the problem.

#### Characteristics of POP
- Emphasis on algorithms (doing things)
- Large programs are divided into smaller programs known as "functions"
- Most of the functions hare global data
- Data moves openly around the system from function to function
- Functions transform data from one form to another
- Employs top-down approach to program design

## Object-Oriented Programming (OOP)
The major motivating factor in the invention of OOP was to mitigate some of the flaws encountered from the procedural approach.

OOP treats data as a critical element of the program and does not allow it to flow freely around the system. It ties data more closely to the functions that operate on it and protect it from accidental modification froun outside functions.

OOP allows us to decompose a problem in to a number of objects and then build data and functions around these entities. 

OOP provides a structure for modularizing programs bycreating partitioned memory areas for data and methods which can be used as a template for creating copies of such modules on demand.

OOP simplifies handling the data and managing the complexity of the program.

#### Characteristics of OOP
- Emphasis on data rather than procedure
- Programs are divided into objects
- Data structures are designed such that they characterize the objects
- Functions that operate on the data of an object are tied together in the data structure
- Data is hidden and cannot be accessed by external functions
- Objects may communicate with each other through functions
- New data and functions can be easily added whenever necessary
- Follows botom-up approach, in that classes are designed first, 'below' main(), and then are utilized by the program

## Basic Concepts of OOP
- Classes and Objects (already discussed)
- Data Abstraction
- Data Encapsulation
- Inheritance
- Polymorphism
- Dynamic binding
- Message Passing

*Note: a Class is a datatype, whereas an object is an instance of a class object.*

### Data Encapsulation and Abstraction
Data Encapsulation is the wrapping of data and functions in a single unit (class). The data is not accessible to the outside world and only those functions which are wrapped in the class can access it. Encapulation provides al ayer of security around manipulated data, protecting it from external interference or misuse. 

Abstraction refers to the act of representing essential features without including the background details or explanations. Classes use the concept of abstraction and are defined 

### Inheritance
Inheritance is the process by which objects of one class acquire the properties of objects of another class.

### Polymorphism
Polymorphism is the ability to take more than one form. For example, an operation may exhibit different behaviour in different instances. The behaviour depends on the type of data used in the operation. For example, a Shape super-class with a Draw() method may function differently when inherited by Circle, Box, and Triangle subclasses. 

### Dynamic Binding
Binding refers to the linking of a procedure call to the code that will be executed in response to the call. Dynamic binding means that the code associated with a given procedure call is not known until the time of the call. Using the Draw() example below, a particular object may not know which Draw() method it is going to call until runtime. It just knows it needs a Shape and will call Draw() on whatever Shape it gets.

### Message Communication
An object oriented program consists of a set of objects that communicate with each other. the process of programming in an OOP language involves the following basic steps:
- Creating classes that define objects and behaviour
- Creating objects from those class definitions
- Establishing communication among those objects

Objects communicate with one another by sending and receiving information in much the same way that people pass messages to one another. Message passing involves spspecifying the name of the object, the name of the method, and the information to be sent.

## Differences Between OOP and POP
| POP | OOP |
| --- | --- |
| Emphasizes algorithms and logical structure |  emphasizes data |
| Programs divided into smaller programs known as functions | Programs are divided into objects |
| | Data structures are designed to characterize objects|
| | functions that operate on the data of an object are tied together in the data structure |
| Most functions share global data | Data is hidden and cannot be accessed by external function |
| Data moves openly around the system from function to function / less secure | Data is hidden and cannot be accessed by external functions |
| Functions transorm data from one form to another | New data and functions can be easily added whenever |
| Top-down | Bottom-Up |
