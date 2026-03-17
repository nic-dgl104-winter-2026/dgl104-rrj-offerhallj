# Week 10 - Model View Patterns

Model View patterns are architectural patterns. There are different kinds of Model View Patterns. Web developers use the Model View Controller (MVC) pattern, android developers use Model View ViewModel (MVVM), etc.

## Architecural Patterns
An architecural pattern is a general, reusable solution to a commonly occuring problem in software architecture. For example, when developing a webapp with HTML and CSS, there are conventions regarding how files are named and where they are located in the project heirarchy (differently from how you've learned to set things up in classes):

```
root
|-- front-end (views)
|   |-- home
|   |   |-- index.html
|   |   |-- banner.png
|   |   |-- projects.html
|   |   |-- // . . .
|   |-- academics
|   |   |-- index.html 
|-- styles (styles related to views)
|   |-- home.css
|   |-- footer.css
|-- back-end (interactions)
|   |-- main.js
|   |-- // . . .
etc
```

### Patterns
A pattern is a particular way in which something is done, is organized, or happens. Patterns may be on an individual basis or may be pre-established.
Patterns help create a blueprint for how the project should be structured.

### Abstraction
The main idea of abstraction is that we hide unnecessary data from the end-user so that they are left with a clean app without worrying about the nuts and bolts. This also applies to creating code libraries and stuff.

## MV* Frameworks
### The Model
The Model handles any data-related information. Think of it as the content of the app. It also may take care of the logic in some patterns, or just house the data. The Model may also coordinate queries with the database.

### The View
The View is what the user sees. It's also known as the GUI. The view can also be summarized as the visual representation of the data: when the user interacts with the GUI, the view will display or render the data.

**The interaction between the view and the model is at the heart of MV\* Patterns.**

## MVC
MVC (model view controller) is a pattern used to represent information and data to the user. It is typically used on desktop and mobile web development. This patterns utilizes the following sequence:

1. The user interacts with something in the View; a button, text input, etc.
2. The View delegates the interaction to the Controller, which executes the event.
3. The Controller updates the Model of the interaction, and the Model processes the logic
4. The Model communicates to the View that something has changed
5. Finally, the View is updated from the data received from the Model.

This cycle repeats for each interaction.

### Model
In this patern, the model is the heart of the application, and it completes all work related to data management. The Model's job is to notify the View of the current state.

### View
The View is the user interface. It's job is to observe the model and to pass interactions to the Controller.

### Controller
The Controller prohibits direct connection between the view and the model. It's job is to connect them. Whenever a user wants to see or update a view, the Controller alerts the Model to send the data to the View. This is related to the backend.

## MVP
MVP (Model View Presenter) is derived from MVC, but instead of the Controller being in charge, it's te View Layer. Where the Contoller facilitates in the backend, the Presenter facilitates in the frontend.

### Model and View
The Model and View serve the same purpose in MVP as they do in MVC.

### ViewListener
The ViewListener is an interface used to create methods to connect different, unrelated classes. For example, the ViewListener could define a method called "onButtonClicked()." The Presenter can implement this to communicate with the model and the view. The presenter holds a reference to the View and the Model and adds itself as a Listener to the View. When a button is clicked in the View, it notifies it's Listener (the Presenter) which notifies the Model. This way, neither the View nor the Model needs to be directly aware of the Presenter.

### Architecture
The View contains all of the UI elements. It connects to the Presenter through the Interface and calls the relevant methods on the Presenter when the definied activity is performed. The Presenter then communicates the interaction to the Model, which updates the Presenter when/if any changes are made. The Presenter then communicates the change back to the View.

### MVC vs MVP
MVP is easier to test thatn MVC. MVC is more complex.
MVP is adaptible. MVC is not really suitable for small scope projects.
MVP isolates the code, makeing view model changes easier. It only effects the building blocks of the UI and not how it is presented.

Though MVP is a good pattern, MVC is used mroe often in practice when developing web apps.

## MVVM
### Model
The Model, also known as the DataModel, esposes the data. However, there is an intermediary step between the Model and the ViewModel which is called the Repository. The Repository is the single source of truth. It has access to the data sources and decides where the data is coming from. The data can be of any kind, and they can come from a remote server or a local database. Whenever a ViewModel needs some data, it comes from the Repository. The Repository doesn't know about the ViewModels using its data.

#### Pros:
- Due to the separation of concerns between the ViewModel and the Model, they are easier to test
- The ViewModel is not bound to a specific view
- MVVM reduces the number of interfaces required for MVP
- It makes the code easier to read, mroe scalable, and more maintainable
- It prevents putting extra code inside a View.

#### Cons:
- It is a bit complicated to understand how it works and to distinguish from other patterns
- It can be overkill for smaller apps

MVVM is widely used in mobile app development.

#### Architecture
Views host all activities and fragments.
ViewModel hosts all the LiveData (so I implemented it wrong in my calculator app)
ViewModel communicates with the repository, which fetches data from the database. The Repository, DataSource, Database, etc. make up the Model.