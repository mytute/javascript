# React js    

1.  HOC

* Simple Definition   
"A Higher-Order Component (HOC) is like a wrapper function that takes a component and adds extra features to it, without changing its original structure."

* Explain the Purpose  
"HOCs are useful for reusing logic across multiple components. Instead of writing the same code in every component, we create an HOC that applies the logic wherever needed."

* Common Use Case
"A common example is authentication. If we want to protect multiple pages, instead of writing login checks inside each page, we create an HOC that wraps those pages and ensures only logged-in users can access them."

2. Redux

* Simple Definition  
"Redux is a state management tool that helps manage and share data across multiple components in a React app."
* Core Concept
Redux follows a unidirectional data flow. Components send requests (actions), a function (reducer) updates the state, and the new state is stored in a central place (store). This ensures consistent data across the app.

1. store.js (Centralized State Storage)

    Creates and configures the Redux store.
    Combines reducers and applies middleware (if needed).

2. reducers/ (Handles State Updates)

    index.js → Combines multiple reducers.
    [feature]Reducer.js → Each feature (e.g., auth, cart, users) has its own reducer file.

3. actions/ (Defines Actions)

    [feature]Actions.js → Defines functions that dispatch actions to update state.


3. How to Explain Virtual DOM in an Interview (Without Code)

🔹 Step 1: Define It Simply
"Virtual DOM is a lightweight copy of the real DOM that helps React update the UI efficiently."

🔹 Step 2: Use a Real-Life Analogy
"Imagine you are editing a document. Instead of printing a new copy for every small change, you make edits on a draft first, compare the changes, and then update only the necessary parts in the final version. The Virtual DOM works similarly—it updates changes in memory first and then applies only the needed updates to the real DOM."

🔹 Step 3: Explain the Benefit
"Updating the real DOM directly is slow. The Virtual DOM makes changes faster by reducing unnecessary updates, improving performance, and making React apps smoother."  


4. SOLID
   
S - Single Responsibility Principle
"A class should have only one responsibility or reason to change, meaning it should do just one thing well."   

O - Open/Closed Principle
"Software should be open for extension but closed for modification, meaning we can add new functionality without changing existing code."

L - Liskov Substitution Principle
"Objects of a superclass should be replaceable with objects of a subclass without affecting the correctness of the program."   
subtyps must be substitutable for their base types  

I - Interface Segregation Principle
"Clients should not be forced to implement interfaces they don't use. Split large interfaces into smaller, more specific ones."
the dependency of one class to another on should depend on the smapplest possible interface.  

D - Dependency Inversion Principle
"High-level modules should not depend on low-level modules. Both should depend on abstractions. This promotes loose coupling."    

5.  The Four Main Principles of OOP:  

    Encapsulation:
        What it is: Wrapping data (variables) and methods (functions) into a single unit called a class.
        Purpose: Protects the internal state of an object from unintended interference and misuse. It allows you to control how data is accessed or modified.
        Example: You can hide the internal details of an object, exposing only the necessary functionality.

    Abstraction:
        What it is: Hiding the complex implementation details and showing only the essential features of an object.
        Purpose: Simplifies the interaction with objects by reducing complexity.
        Example: A car object exposes a drive() method without needing to know the internal workings of the engine or wheels.

    Inheritance:
        What it is: A way to create a new class based on an existing class by inheriting its properties and methods.
        Purpose: Allows for code reusability and hierarchical relationships between classes.
        Example: A Dog class can inherit from an Animal class, gaining its properties like name and age, and adding its own behavior like bark().

    Polymorphism:
        What it is: The ability of an object to take on many forms, allowing methods to behave differently based on the object that is calling them.
        Purpose: Enables flexibility in how methods are used and helps in creating more generic code.
        Example: A shape class with a method draw() can have different implementations in the Circle and Square classes, both responding to draw() differently.
