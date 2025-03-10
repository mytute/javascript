# Node js  


1. What is node js  ?  
Node.js is an open-source, cross-platform, back-end Javascript runtime environment that runs on the chrome's V8 engine and execute Javascript code outside a web browser.   
it has also javascript features like event driven and non-blocking.  

2. What is runtime environment ?
A runtime environment is where a program runs. It provides the necessary resources like memory, execution engine, and system APIs.   
For example, Node.js is a runtime environment for JavaScript that allows it to run outside the browser.

3. What is the difference between req.params and req.query ?   
  * req.params: Gets values from URL parameters (route parameters). Used for dynamic routes. (state)     
  Example: GET /user/:id → req.params.id
  * req.query: Gets values from the query string in the URL. Used for optional parameters. (filtaration, sorting )    
  Example: GET /users?name=John → req.query.name

4. What is body-parser & What does it do ?
All http requests are texts and so in order to work with javascript, body of post request need to turn from a string into jason.
"body-parser" do this job as middleware.

5. What security mechanisms are available in NODE ?    
Helmet: A security module that adds HTTP headers for protection.  
  *  X-Frame-Options: Prevents clickjacking attacks.  
  * Cross-Site Scripting (XSS) Protection: Mitigates XSS attacks.   
  * Strict Transport Security (HSTS): Forces HTTPS for secure communication.

6. Difference of Node.js Compared to Other Technologies
  * Non-blocking & Asynchronous: Unlike traditional web servers, Node.js uses an event-driven, non-blocking I/O model, making it fast and efficient.  
  * Single Programming Language: Uses JavaScript for both frontend and backend, simplifying development.  
  * Lightweight & Scalable: Handles many connections efficiently, making it great for real-time apps like chat apps, streaming, and APIs.

7. Why is Node.js Best for Web Development?
  * Fast Performance (Powered by V8 engine)  
  * Handles High Traffic Efficiently  
  * Large Ecosystem (NPM) for easy package management  
  * Perfect for Real-Time Applications like chat, gaming, and APIs

8. How Does Node.js Handle High Traffic Efficiently?  
  * Non-blocking I/O: Handles multiple requests at the same time without waiting.  
  * Event-Driven Architecture: Uses events and callbacks instead of creating multiple threads.  
  * Single-Threaded with Async Processing: Uses a single thread with event loop to manage thousands of connections.  
  * Load Balancing: Can use cluster module to run multiple instances and distribute traffic.  
  * Efficient Resource Utilization: Uses fewer system resources compared to traditional multi-threaded servers.

9. Options to Run Synchronous Processes in JavaScript:
  * use async/await.   
  * use worker thereds for CPU-intensive tasks.  
  * use promises with then() chaining.
  * callback.  

10. Difference Between Promise.all() and Promise.allSettled()
  * Promise.all():
      1. Runs multiple promises in parallel. 
      2. Fails immediately if any promise rejects.  
      ```js
        Promise.all([p1, p2, p3]).then(results => console.log(results))
        .catch(error => console.log(error));
      ```
  * Promise.allSettled()
      1. Runs multiple promises in parallel.   
      2. Waits for all promises to finish, even if some fail.  
      3. Returns an array with status (fulfilled or rejected) for each promise.  
      ```js
        Promise.allSettled([p1, p2, p3]).then(results => console.log(results));
      ```
11. When to Use async/await vs Promises
  * Use async/await:
    1. When you want to write clean, readable, and synchronous-like code for handling asynchronous operations.
    2. Best for sequential operations.  
  * Use Promises (.then()/.catch()):
    1. When working with legacy code or libraries that only support Promises.
    2. When you need fine-grained control over asynchronous operations (e.g., using Promise.all, Promise.race).

12.  Global Objects Provided by Node.js  
    1. global – The global object (similar to window in browsers).  
    2. __dirname – The directory path of the current file.  
    3. __filename – The full path of the current file.  
    4. process – Provides information about the current Node.js process.  
    5. console – Used for logging (console.log()).  
    6. setTimeout() / setInterval() / setImmediate() – Timer functions.  
    7. require() – Used to import modules.  
    8. Buffer – Handles binary data.

13. What is Middleware in Express?
    Middleware in Express.js is a function that runs before the request reaches the final handler. It can modify the request and response or stop the request.   
    use for logging(request), authentication(request), error handling(response), and modifying requests.
    ```js
      app.use((req, res, next) => {
        console.log('Middleware executed');
        next(); // Passes control to the next handler
      });
    ```
14. How to Handle Exceptions in Node.js?
    1. using try...catch   
    ```js
      try {
        let result = riskyFunction();
      } catch (error) {
        console.error('Error occurred:', error);
      }
    ```
    2. Catches unexpected errors.(for Debugging, Preventing Crashes, Monitoring)   
    ```js
      # Catches unexpected errors.  
      process.on('uncaughtException', (err) => {
        console.error('Unhandled Exception:', err);
      });
      process.on('unhandledRejection', (reason, promise) => {
        console.error('Unhandled Rejection:', reason);
      });
    ```
15. Difference Between npm and Yarn  
    | Feature                  | npm (Node Package Manager)                     | Yarn                              |
    |--------------------------|-----------------------------------------------|-----------------------------------|
    | **Speed**                | Slower (older versions), improved in v5+      | Faster due to parallel downloads  |
    | **Security**             | Uses `package-lock.json`                      | Uses `yarn.lock` (more strict)    |
    | **Offline Support**       | Limited caching                               | Better offline caching            |
    | **Dependency Resolution**| Installs dependencies sequentially            | Installs dependencies in parallel |
    | **CLI Commands**         | `npm install`, `npm run`                      | `yarn add`, `yarn run`            |
    | **Default Package Manager** | Comes with Node.js                         | Needs separate installation       |


16. Different Types of Functions in JavaScript
    1. Function Declaration (Function Definition)  
       * Declared with the function keyword.  
       * Can be hoisted (used before declaration).  
         ```js
         function greet() {
            return "Hello!";
          }
          console.log(greet()); // Hello!
         ```
    2. Function Expression  
       * Assigned to a variable.  
       * Not hoisted (cannot be used before declaration).  
         ```js
         const greet = function() {
            return "Hello!";
          };
          console.log(greet()); // Hello!
         ```
    3. Arrow Function  
       * Shorter syntax, does not have its own this.  
       * Cannot be used as a constructor.  
         ```js
         const greet = () => "Hello!";
         console.log(greet()); // Hello!
         ```
    4. Immediately Invoked Function Expression (IIFE)  
       * Runs immediately after being defined.   
       * Used to avoid polluting the global scope.  
         ```js
         (function() {
            console.log("IIFE executed!");
          })();
         ```
    5. Generator Function  
       * Uses function* and yield to pause and resume execution.  
         ```js
         function* generator() {
            yield 1;
            yield 2;
          }
          const gen = generator();
          console.log(gen.next().value); // 1

         ```
    6. Constructor Function  
       * Used to create objects.  
         ```js
         function Person(name) {
            this.name = name;
          }
          const person1 = new Person("John");
          console.log(person1.name); // John
         ```

17.  Difference Between Dependency and DevDependency
  * Dependencies (dependencies):
    1. Required for the app to run.
    2. Used in production.
       Example: Express for handling requests. (npm install package-name)  

  * DevDependencies (devDependencies):
    1. Needed only for development (not in production). (npm install package-name --save-dev)  
       Example: Jest for testing.

18 Explain Authrization, Authenticaion process   

  1. Authentication Flow:   
     
    User Login:
        User provides username and password.
    Backend:
        Backend checks credentials and if valid, generates:
            Access Token (short-lived, e.g., 15 minutes).
            Refresh Token (long-lived, e.g., 7 days).
    Frontend:
        Stores the access token and refresh token (usually in localStorage or HTTP-only cookies).  
        
  2. Access Token Flow (Using Access Token to Access Resources):

    User Makes API Request:
        Frontend sends access token in the Authorization header (Bearer <access_token>).
    Backend:
        Verifies the access token for validity.
        If valid, proceeds with the request and returns data.
        If expired, sends a 401 Unauthorized response.

  3. Refresh Token Flow (Handling Expired Access Token):

    Access Token Expired:
        Frontend detects that the access token has expired (e.g., 401 response).
    Frontend Requests New Access Token:
        Frontend sends the refresh token to a dedicated /refresh-token endpoint.
    Backend:
        Verifies the refresh token for validity.
        If valid, generates a new access token and sends it back to the frontend.
        If the refresh token is expired/invalid, it sends a 401 Unauthorized response and the user is logged out.  
        
  4. User Session Flow (Maintaining Session):

    Access Token:
        Short-lived (used for API requests).
    Refresh Token:
        Long-lived (used to get a new access token when expired).
    Frontend:
        Continuously sends the access token for API calls.
        When expired, it exchanges the refresh token for a new access token.
        If both tokens expire, the user is asked to log in again.




  
event loop   
