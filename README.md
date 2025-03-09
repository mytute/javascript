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
* X-Frame-Options: Prevents clickjacking attacks.  
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

