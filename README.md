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
