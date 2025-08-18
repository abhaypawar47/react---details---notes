Backend - Node JS - DAY 01
____________________________________________________________________________________
Node.js Overview:
•	Definition: Node.js is a JavaScript backend development library and a runtime environment used to run JavaScript outside the browser (server-side scripting).
•	Engine: It runs on the Chrome V8 engine.
•	Developers: Created by Ryan Dahl, OpenJS Foundation, Bryan Cantrill.
•	Initial Release: May 27, 2009 (15 years ago).
•	License: MIT License.
•	Programming Languages: Can be used with JavaScript, Python, C, C++, CoffeeScript.
Key Benefits of Node.js:
•	Single-threaded: Uses event looping and a non-blocking mechanism to respond.
•	Super-fast: Codes are executed quickly on the V8 JavaScript Engine.
•	Event-driven: Has a notification system that enables the application server to capture the response of previous API calls.
•	Buffer-less: Data is released in chunks without buffering.
•	Asynchronous: Non-blocking, non-synchronous libraries move to the next API without waiting for the return data of the previous API.
•	Highly-scalable: Servers can handle many requests.
Real-time Applications (RTAs) and Node.js:
•	Node.js is commonly used to develop real-time applications.
•	Its asynchronous, event-driven nature allows it to handle heavy input-output operations, which helps achieve high performance in modern real-time applications.
•	Examples of Real-time Apps: Google Meet (continuous communication), live stream apps.
Concepts Related to Real-time Applications and Data:
•	WebSockets: Used for continuous data flow (requests and responses) and fast communication with a continuous connection.
•	Data Streaming: Smoothing of data, used by Netflix and Amazon for audio/video streaming.
•	Data Pipelining: Transfer of small, continuous data chunks.


Single Page Applications (SPAs):
•	SPAs enable data updating without reloading the browser/page.
•	Examples: NASA, Netflix, Walmart, Twitter.
Microservices Architecture:
•	Concept: Every module has its own service. It's like Amazon, WhatsApp, Instagram.
•	Benefits:
o	Divides an application into parts, with each microservice handled by a team.
o	Allows development of sections as needed without affecting other parts.
o	Lightweight, easy integration with serverless architecture.
o	Easy development.
o	Builds flexible apps.
REST API:
•	A protocol with rules and regulations for building APIs using a REST architecture.
•	Handles data in "chunks."
Callback Functions (in Programming Context):
•	Passing one function to another function as an argument.
•	Executing one function within another function.
Backend Architecture Diagram (using Node.js):
•	Front-end Layer / Client Side: Uses HTML, CSS, JS, React JS. Sends "Req" (requests) to the backend.
•	Backend Layer / Server Side: Uses Node / Express. Processes requests from the front-end and sends "req" to the database. Receives "Res" (responses) from the database and sends "Response" back to the front-end.
•	Database Layer: Uses MySQL / MongoDB. Stores and retrieves data.
Code Snippet Example (Node.js/JavaScript):
---
console.log("Welcome To Node JS Backend JS Library")
console.log(10 + 30)
---


•	A Demo function defined as a constant arrow function that takes two arguments (with default values of 0) and logs their sum:
---
const Demo = (a = 0, b = 0) => {
console.log(a + b)
       ---
•	Calling the Demo function with arguments 100 and 200: 
---
Demo(100, 200)
---

_______________________________________________________________________________
 
Backend - Node JS - DAY 02
____________________________________________________________________________________
1. Creating a Basic HTTP Server in Node.js:
•	Importing http module: const http = require('http'); This line imports the built-in Node.js http module, which is essential for creating an HTTP server.
•	Creating the server: const app = http.createServer((req, res) => { ... }); This creates an HTTP server instance. The createServer method takes a callback function that is executed for every incoming request. This callback receives two arguments: req (request object) and res (response object).
•	Sending a response:
o	res.write("Welcome To Node JS Server"): This line sends a piece of the response body to the client. The content must be a string.
o	res.write("Hello Dear"); and for(let i=0;i<=10;i++) { res.write(${i}) }: This demonstrates writing multiple parts to the response, including a fixed string and numbers from a loop.
o	res.end(): This method signals to the server that all of the response headers and body have been sent, and the response can be considered complete. It's crucial to call res.end() for every response.
•	Listening for incoming requests: app.listen(3000, () => { console.log('Server is Successfully Running localhost:3000') }); This line makes the server listen for incoming connections on port 3000. Once the server starts successfully, a message is logged to the console.
•	---
const http = require('http');
const app = http.createServer((req, res) => {
    res.write("Welcome To Node JS Server\n");
    res.write("Hello Dear\n");
    for (let i = 0; i <= 10; i++) {
        res.write(`${i}\n`);
    }
    res.end();
});
app.listen(3000, () => {
    console.log('Server is Successfully Running at http://localhost:3000');
});
---








2. HTTP - Network Protocol:
•	Purpose: HTTP (Hypertext Transfer Protocol) is a network protocol that enables communication between clients (e.g., web browsers) and servers.
•	Nature: It operates on a Request-Response (Req-Res) protocol model, meaning clients send requests and servers send responses.
•	HTTP Methods: Common HTTP methods (also known as verbs) used for different types of operations are:
o	GET: Retrieves data.
o	POST: Submits data to be processed to a specified resource.
o	PUT: Updates an existing resource (replaces it entirely).
o	PATCH: Applies partial modifications to a resource.
o	DELETE: Deletes a specified resource.
____________________________________________________________________________________
 
Backend - Node JS - DAY 03
____________________________________________________________________________________
1. Building an HTTP Server and Responding with HTML
•	Sending HTML Responses with Headers:
o	To inform the browser that the response is HTML, set the Content-Type header.
res.writeHead(statusCode, { 'content-type': 'text/html' })
o	 is used to set the HTTP status code (e.g., 200 for OK) and response headers.
o	Example:
---
const statusCode = 200;
res.writeHead(statusCode, { 'content-type': 'text/html' });
res.write("<input type='text' placeholder='enter your name'>");
res.write("<h1>Welcome To Node JS Server !!</h1>");
res.end();
---
________________________________________
2. URL Parsing and Routing
•	URL Module:
o	The built-in url package 
var url = require('url'); 
is used to fetch and parse data from a URL.
•	URL Components (URL Decoding):
o	https://: Network protocol.
o	www.google.com: Domain name (assigned an IP address behind the scenes via DNS).
o	DNS (Domain Name System): Converts IP addresses to human-readable names.
o	/search: Pathname.
o	?q=react+jobs+in+pune: Query string (user-entered keywords/parameters).
o	&: Separator for dynamic variables in the query string.
•	Basic URL Routing:
o	Conditional logic (if/else if) is used within the server's request handler to serve different content based on the urlData.pathname.
o	Example:
---
if (urldata.pathname === '/') {
    res.write("<h1>Home Page Node JS URL Routing </h1>");
} else if (urldata.pathname === '/about') {
    // ... respond for about page ...
}
---
________________________________________
3. Modules in Node.js
•	Definition: Each JavaScript file (.js file) is considered a module.
•	Purpose: To achieve reusability, modules need to export their functionalities.
•	Types of Modules:
1.	Built-in Modules: Provided by Node.js itself (e.g., http, url).
2.	User-Defined Modules: Custom modules created by developers.
3.	Third-Party Modules: Modules installed from npm (e.g., Express.js, Nodemon).
________________________________________
4. Development Utilities
•	Nodemon Package: (Implicitly mentioned by the need for "nodemon package" in the prompt)
o	Nodemon is a utility that monitors for any changes in your source code and automatically restarts your server. This greatly enhances development efficiency by eliminating the need for manual server restarts after every code modification.
________________________________________
5. Middleware 
•	(Mentioned as "middleware" in the prompt, but not detailed in the images)
•	In the context of Node.js (especially with frameworks like Express.js), middleware refers to functions that have access to the request object (req), the response object (res), and the next middleware function in the application’s request-response cycle. These functions can perform tasks like:
o	Executing any code.
o	Making changes to the request and response objects.
o	Ending the request-response cycle.
o	Calling the next middleware in the stack.
____________________________________________________________________________________
 
Backend - Express - DAY 04
____________________________________________________________________________________
Node.js vs. Express.js: A Comparison
Node.js
Node.js is a powerful JavaScript runtime environment.
•	Purpose: Primarily used to build server-side applications, especially event-driven applications with intensive input/output operations.
•	Features:
o	Low-level features.
o	Built on the Google Chrome V8 engine.
o	Written in C, C++, and JavaScript.
o	Acts as a runtime environment for server-side execution.
•	Limitations:
o	Does not provide built-in controllers.
o	Does not provide built-in routing.
o	Does not provide built-in middleware.
o	Requires more coding and development time for complex applications.
Express.js
Express.js is a minimalist web framework for Node.js.
•	Purpose: Used to build web applications following the principles and approaches of Node.js, offering a more streamlined development experience.
•	Relationship to Node.js: It is a framework built on top of Node.js.
•	Features:
o	Offers more features than raw Node.js for web development.
o	Written in JavaScript.
o	Provides built-in routing capabilities.
o	Provides middleware support.
o	Enables faster development.
o	Requires less code to write compared to building applications directly with Node.js.
________________________________________


Express.js: Key Concepts & Development
Framework Overview
Express.js is a complete MVC (Model-View-Controller) framework designed for building full-stack applications.
•	MVC Architectural Pattern:
o	Model: Handles the application's data logic.
o	View: Responsible for the user interface (UI).
o	Controller: Acts as the connection or intermediary between the Model and the View.
Basic Express.js Application Structure
---
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => {
    res.send('Hello World!');
});

app.listen(port, () => {
    console.log(`Example app listening on port ${port}`);
});
---
1.	Import Express.js Module
o	const express = require('express');
o	Loads the Express framework for building the web application.
2.	Create an Application Instance
o	const app = express();
o	Creates an Express app object to define routes and handle requests.
3.	Set the Port Number
o	const port = 3000;
o	Defines the port on which the server will run.
4.	Define a Route for the Root URL ('/')
o	app.get('/', (req, res) => { res.send('Hello World!'); });
o	Handles HTTP GET requests to '/' and responds with "Hello World!".
5.	Start the Server
o	app.listen(port, () => { console.log(\Example app listening on port ${port}`); });`
o	Makes the server listen for incoming requests on port 3000 and logs a message when running.
---
Development Steps for an Event-Driven App with Express.js
1.	Initialize Node.js Project:
o	Navigate to your project folder (e.g., DAY 1 FOLDER).
o	Run npm init -y to initialize a package.json file with default settings (auto-config).
2.	Install Express.js:
o	Run npm i express to install the Express.js package and add it to your project's dependencies.
3.	Create index.js (or your main application file):
o	Create a file named index.js (or another appropriate name) to write your Express.js application code.
Fallback Routing in Express.js
Express.js allows you to define a "fallback" route that catches all requests that haven't been handled by specific routes. This is commonly used for handling 404 "Not Found" errors.
This middleware will be executed for any request that hasn't been matched by previous routes. The '*' indicates it will match any path.
---
app.use((req, res) => {
    res.send("404 Not Found");
});
---

_______________________________________________________________________________
 
Backend - Express - DAY 05
____________________________________________________________________________________
Rendering JSON Data (Objects & Arrays)
In Express.js, you can send JSON data as a response from your server. This is useful for building APIs that serve data to the client.
Example: Sending an Object
You can define an object and send it directly as a response using res.send(). Express will automatically stringify the object into JSON.
---
app.get('/about', (req, res) => {
    const obj = {
        id: 1,
        name: "Pratik",
        skill: "HTML",
        email: 'pratik@gmail.com'
    };
    res.send(obj); // Sends the object as JSON
});
---
Example: Sending an Array
Similarly, you can send an array, and Express will convert it to JSON.
---
app.get('/about', (req, res) => {
    const arr = ["HTML", "CSS", "JS"];
    res.send(arr); //Sends the array as JSON
});
---
________________________________________

 
Template Engines (Server-Side Rendering - SSR)
A template engine in Express.js is used to generate HTML dynamically by combining templates with data. It enables rendering views on the server side. This allows you to create dynamic web pages where content can change based on server-side data.
Popular Template Engines for Express include:
•	Pug (formerly Jade): Known for its clean and minimalistic syntax.
•	EJS (Embedded JavaScript): Uses regular JavaScript for embedding code directly within HTML templates.
•	Handlebars: Extensible with helpers, focuses on logic-less templates, and uses whitespace-sensitive syntax.
•	Mustache: Simple and logic-less, designed to work across various platforms.
Using EJS (Embedded JavaScript) - Steps & Concepts
EJS is a popular choice for its simplicity and use of familiar JavaScript syntax within HTML.
Step 1: Install EJS
Before using EJS, you need to install it in your project:
---
npm i ejs
---
Step 2: Create a views Folder (and project structure)
For larger, more readable, manageable, and easily developed applications, it's crucial to have a well-organized folder structure. By convention, template files (like EJS files) are placed in a views directory.
Step 3: Use the res.render() Method
Instead of sending raw HTML or JSON with res.send(), you use res.render() to render an EJS template.
---
app.get('/', (req, res) => {
    res.render('home.ejs'); //Renders the 'home.ejs' file located in the 'views' folder
});
---



Step 4: Create EJS Pages (e.g., home.ejs)
Inside your views folder, create your EJS files. These files will look like standard HTML but can include EJS specific syntax.
Example: home.ejs
---
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
</head>
<body>
    <h1>Hello ejs package</h1>
</body>
</html>
---
Step 5: Data Traversing (Passing Dynamic Data from index.js to EJS)
The power of template engines lies in passing dynamic data from your server-side Express application to your EJS templates.
You pass data as a second argument to the res.render() method, typically an object where keys become variables accessible within the EJS template.
---
app.get('/about', (req, res) => {
    const obj = {
        data: 'user' //'user' is the dynamic data we want to pass
    };
    res.render('about.ejs', obj); //Passes the 'obj' data to 'about.ejs'
});
---







EJS Syntax for Data Display and Logic
EJS uses specific tags to embed JavaScript logic and display data within HTML:
•	Logical Code:
<% EJS Syntax to write logical code %> 
Used for control flow (if/else, loops) or defining variables that don't directly output to HTML.
•	Text Data Display:
<%= As a Text display data %>
Used to output data as plain text. This automatically escapes HTML characters, preventing XSS vulnerabilities.
•	HTML Data Display (Unescaped):
<%- As A HTML Display Data %>
Used to output data as raw HTML. Be cautious when using this, as it can introduce XSS vulnerabilities if the data is not sanitized.
•	Including External EJS Files:
<%- include('external.ejs') %>
Used to embed content from another EJS file into the current template, promoting reusability.
____________________________________________________________________________________
 
Backend - Express - DAY 06
____________________________________________________________________________________
EJS Syntax and Dynamic Data Rendering
Example: about.ejs with Dynamic Data : This example demonstrates how to loop through data and apply conditional logic within an EJS template.
---
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
</head>
<body>
    <h1>This is about</h1>
    <hr />

    <% data.map(function(user, index) { %>
        <h2>User ID: <%= user.id %></h2>
        <h2>User Name: <%= user.user %></h2>
        <h2>User Email: <%= user.umail %></h2>
        <hr />
    <% }); %>

    <% var age = 20; %>
    <% if (age >= 20) { %>
        <h2>Age is more than 18</h2>
    <% } %>
</body>
</html>
---

•	The normal HTML part (<h1>, <hr>, etc.) is static and always appears in the browser.
•	The <% data.map(function(user, index) { %> ... <% }); %> part loops over the data array sent from the server and inserts each user’s ID, Name, and Email into the page.
•	<%= ... %> is used to output values into the HTML (it escapes HTML by default to prevent XSS).
•	<% ... %> is used to run JavaScript logic without printing anything, like loops and if conditions.
•	At the end, age is set to 20, and the if statement checks if (age >= 20) to conditionally show "Age is more than 18".

In short: EJS lets you mix JavaScript directly in your HTML to render data dynamically from the server.
---

 
Passing Data to EJS Templates:
To render an EJS file with dynamic data, you pass an object to res.render(). The keys of this object become accessible variables within your EJS template.
---
app.get("/about", (req, res) => {
    const user = [
        { id: 1, user: "user 1", umail: "a@gmail.com" },
        { id: 2, user: "user 2", umail: "b@gmail.com" },
        { id: 3, user: "user 3", umail: "c@gmail.com" }
    ];

    const obj = { data: user };
    res.render("about.ejs", obj);
});
---

•  Define the Route
•	app.get("/about", (req, res) => { ... }); defines a GET route for the URL /about.
•  Create User Data
•	An array user is created containing multiple objects, each representing a user with properties: id, user (name), and umail (email).
•  Wrap Data in an Object
•	The array is wrapped inside an object obj with the key data, which will be passed to the EJS template.
•  Render the EJS Template
•	res.render("about.ejs", obj); renders the about.ejs template and injects the obj data into it.
•  Dynamic HTML Rendering
•	The template can now access data and dynamically display the list of users on the webpage.
•  Purpose
•	This demonstrates how Express passes server-side data to EJS for dynamic content generation.
---
 
Express.js + EJS Template Engine vs. Express + React 
Express + EJS Template Engine
•	Pros:
o	Good for server-side rendered (SSR) applications.
o	Dynamically renders views with data sent from the back-end (e.g., database data).
o	Easier to integrate with existing back-end systems and quick to implement.
•	Cons:
o	Lacks the dynamic interactivity and modularity that modern JavaScript frameworks like React provide.
o	The UI may not feel as dynamic or responsive compared to React (as more client-side logic happens with EJS).
•	Use Case:
o	Best for applications that require quick server-side rendering with simple dynamic content but don't need complex client-side interactions.
---------
Express + React (Full-Stack with Client-Side Rendering)
•	Pros:
o	Provides a modern, scalable architecture suitable for large-scale applications.
o	React's client-side rendering allows for rich, dynamic user interfaces and faster page loads.
o	Easy to manage complex state and user interactions in the front-end.
o	React can handle all the UI logic, while Express handles the API and back-end logic.
o	Clear separation of concerns between back-end (Express) and front-end (React).
•	Cons:
o	More complex to set up, especially for beginners.
o	The development process is a bit slower as you need to handle both front-end (React) and back-end (Express) configurations.
o	Requires a build process for React in production.
•	Use Case:
o	Ideal for modern web apps that require dynamic content, reusable components, and a scalable architecture. This setup is suitable for applications like dashboards, interactive platforms, or social media sites.
________________________________________

Middleware in Express.js
Middleware functions are a fundamental part of the Express.js framework, known for their simplicity and flexibility.
•	Definition: Middleware is a request handler that allows you to intercept and manipulate requests and responses before they reach route handlers. It's a function that sits between the server and an application, intercepting requests and responses and performing additional actions before passing them on.
•	Purpose:
o	Connect two applications to work together.
o	Allow you to perform actions when working with forms or submitting forms.
o	Access and modify request (req) and response (res) objects. Middleware functions have access to these objects.
Types of Middleware:
1.	Built-in Middleware:
o	These are functions provided directly by Express.js.
o	Example: express.static()
	Used to serve static files such as images, audio, video, CSS files, and JavaScript files from a specified directory.
	JavaScript
	  const express = require("express");
	  const app = express();
	  const port = 8000;
	
	  // Serve static files from the 'public' directory
	  app.use(express.static("public"));
2.	User-defined Middleware:
o	Custom middleware functions written by developers to perform specific tasks.
3.	Third-party Middleware:
o	Middleware packages developed by the community and installed via npm (e.g., body-parser for parsing request bodies).
____________________________________________________________________________________
 
Backend - Express - DAY 07
____________________________________________________________________________________
I. Introduction to Form Handling
Form handling in web development primarily involves two HTTP methods: GET and POST. These methods are used within HTML <form> tags to send data from a client (browser) to a server.
II. GET Method
•	Data Transmission: Data is passed through the URL as query parameters.
•	Security: Not secure for sensitive information because data is visible in the URL.
•	Data Volume: Suitable for small amounts of data (limited data), typically up to 8MB.
•	Data Types: Primarily used for string and number data.
•	Example URL Structure (GET):
•	http://127.0.0.1:3001/?username=Saurabh&useremail=pratik08sabalex@gmail.com&userpass=1234567890&userskill=JS
•	Express.js Implementation (GET):
---
app.get('/saveform', (req, res) => {
    var urldata = url.parse(req.url, true);
    res.send(urldata); // Sends the parsed URL data as a response
});
---
•	HTML Form (GET):
---
<form action="" method="get">
    <label for="">Enter Your Name:</label>
    <input type="text" name="username" id="username" placeholder="enter        your name">
    <label for="">Enter Your Email:</label>
    </form>
---
•	Data Access (GET):
o	url.parse(req.url, true) is used to fetch and parse URL data.
o	Input fields use name and id attributes:
	name: Used to store data in a database.
	id: Used for logical work and data fetching.


III. POST Method
•	Data Transmission: Data is sent through the body of the HTTP request, not the URL.
•	Security: More secure as data is hidden and not visible in the URL. Ideal for sensitive data like personal or financial information.
•	Data Volume: Can handle a large amount of data, including files, and offers unlimited data transfer.
•	Data Types: Supports strings, numbers, files, and more.
•	Usage:
o	Used for sensitive information (personal info, financial info).
o	Used when sending large amounts of data (e.g., file uploads).
•	enctype Attribute (for file uploads):
o	When uploading files, the <form> tag should include enctype="multipart/form-data".
•	Express.js Implementation (POST):
---
app.post('/saveform', (req, res) => {
    res.send(req.body); // Sends the data from the request body as a response
});
---
•	Middleware for POST Method:
o	To properly access data sent via POST, middleware like 
o	express.urlencoded() (for URL-encoded data) or express.json() (for JSON data) or multer (for multipart/form-data for file uploads) is required to parse the request body.
IV. Key Differences & Summary
Feature	GET Method	POST Method
Data Pass	Through URL	Through Body
Security	Not Secure (Visible Data)	Secure (Hidden Data)
Data Volume	Limited (Small amount, up to 8MB)	Unlimited (Large amount, including files)
Usage	Non-sensitive data, retrieving information	Sensitive data (personal, financial), submitting forms, file uploads
Data Access	req.query (after url.parse)	req.body (requires middleware for parsing)


action: URL to send form data,  method: HTTP method (GET/POST),
name: identifies form fields for data storage , id: used for client-side logic and JavaScript
____________________________________________________________________________________
 
Backend - Express - DAY 08
____________________________________________________________________________________
1. HTTP Status Codes
This section shows common HTTP status codes used to communicate the result of a server request.
Status Code	Meaning	Common Use
200 OK	Success	The request was successful, and the server responded with the requested data.
201 Created	Success	The request has been fulfilled and has resulted in one or more new resources being created. Often used after a successful POST request.
400 Bad Request	Client Error	The server cannot process the request due to something that is perceived to be a client error (e.g., malformed syntax).
401 Unauthorized	Client Error	The client must authenticate itself to get the requested response.
403 Forbidden	Client Error	The client does not have access rights to the content, so the server is rejecting the request.
404 Not Found	Client Error	The server cannot find the requested resource. This is a common error for a typo in the URL.
500 Internal Server Error	Server Error	A generic error message, given when an unexpected condition was encountered and no more specific message is suitable. The problem is on the server side.

2. Express.js Middleware and Routing
This section highlights key pieces of middleware and a basic route handler in an Express.js application.
Middleware: Middleware functions are functions that have access to the request object (req), the response object (res), and the next middleware function in the application’s request-response cycle. They are typically used for tasks like parsing data, logging, or serving static files.



•	Serving Static Files:
app.use(express.static('public/'))
o	This line of code sets up middleware to serve static files (like CSS, JavaScript, images) from a directory named public. When a browser requests a file, Express will look for it in this directory first.
•	URL-Encoded Data Parsing:
app.use(express.urlencoded({ extended: true }))
o	This middleware parses incoming request bodies with URL-encoded payloads. It's crucial for handling data submitted from an HTML form (e.g., a POST request with a content type of application/x-www-form-urlencoded).
o	extended: true allows for rich objects and arrays to be encoded into the URL-encoded format, using the qs library. false uses the built-in Node.js querystring library.
•	JSON Data Parsing:
app.use(express.json())
o	This middleware is essential for parsing incoming request bodies with JSON payloads. This is commonly used in REST APIs where data is sent from the client to the server in JSON format (e.g., application/json). The parsed data is then available on req.body.
•	Root Route (/)
app.get('/', (req, res) => {
    res.send('Welcome To Express Server');
    res.render('form.ejs');
});
o	This is a route handler for a GET request to the root URL (/).
o	It sends a string response and renders an EJS template (form.ejs).
o	Note: It's important to know that res.send() and res.render() both terminate the request-response cycle. You should not call both in the same handler. The code as shown would only execute the first one (res.send) and the second one would fail. You would typically choose one or the other
•	POST Route for Form Submission (/saveform)
app.post('/saveform', (req, res) => {
    res.send("<h1>Form Is Submitted !!</h1>");
});
o	This is a route handler for a POST request to the /saveform URL.
o	The app.post() method indicates that this route will handle data submissions, such as from an HTML form.
o	It sends back a simple HTML heading to the client, confirming the form submission.
o	In a real application, you would access the submitted form data using req.body and then process it (e.g., save it to a database like MongoDB).
____________________________________________________________________________________
 
Backend - Express - DAY 09
____________________________________________________________________________________
Mongoose is an Object Data Modeling (ODM) library for MongoDB and Node.js. It's a beginner-friendly and recommended tool that provides a straightforward way to define schemas and interact with your MongoDB database.
Prerequisites
First, you need to install Mongoose in your project:
> npm install mongoose
________________________________________

Step 1: Database Connection

The first step is to create a connection file that will handle the logic for connecting to your MongoDB database.

1.	Folder Structure:
o	Create a config folder in your project's root directory.
o	Inside the config folder, create a file named db.js.
2.	db.js File Content:
o	In this file, you will require mongoose and use its connect() method to establish a connection.
o	The connection string typically follows the format: mongodb://localhost:27017/your_db_name.
o	Use .then() and .catch() blocks to handle success and failure of the connection attempt.
o	Export the connection object so it can be used in other parts of your application.
Code Example (db.js):
---
const mongoose = require('mongoose');

const connection = mongoose.connect('mongodb://localhost:27017/company')
    .then(() => {
        console.log('DB Connection Successfully !!');
    })
    .catch((err) => {
        console.log('DB Connection Faild');
        console.log(err);
    });
	module.exports = connection;
          ---





3.	Importing the Connection:
o	In your main server file (e.g., index.js), you need to import the connection you just created. This will trigger the connection attempt when your server starts.
Code Example (index.js):
// import DB Connection
const connection = require('./config/db');
________________________________________

Step 2: Schema and Model Design

A Mongoose Schema is the blueprint for your documents. It defines the structure of the data, the types of the fields, and any constraints. A Model is a constructor compiled from the Schema that gives you access to a set of methods for interacting with the database.

1.	Folder Structure:
o	Create a models directory in your root folder.
o	Inside the models folder, create a file for your schema, for example, user.js for a User model.
2.	user.js File Content:
o	Require mongoose and create a new mongoose.Schema object.
o	Define the fields for your document (e.g., username, useremail, userpass, gender).
o	You can also add constraints like type, required, and unique to your fields.
Code Example (user.js):
---
const mongoose = require('mongoose');

// Structured of our document
const userSchema = new mongoose.Schema({
    username: String,
    useremail: {
        type: String,
        required: true,
        unique: true
    },
    userpass: String,
    gender: String
});

// export module as a model
module.exports = mongoose.model('User', userSchema);
---
________________________________________



Step 3: Importing and Using the Model
Now that you have your connection and model defined, you can import the model into your main server file to perform database operations.

1.	Import the Model:
const user = require('./models/user');

2.	Inserting Data:
o	Inside a route handler (e.g., a POST request to /saveform), you can create a new document based on your model and save it to the database.
o	The new user() constructor takes the data you want to save.
o	The .save() method then persists this data to the MongoDB collection.
---
app.post('/saveform', (req, res) => {
    const result = new user(req.body); //create new user document from request body
    result.save(); // save the document to the database
    res.send(result); // respond with the saved document
});
---
3.	Verification:
o	After the save operation, you can check your MongoDB database (using a tool like MongoDB Compass or the MongoDB Shell) to confirm that the data has been inserted correctly. The new document should be visible in the users collection within your company database.

____________________________________________________________________________________
 
Backend - Express - DAY 10
____________________________________________________________________________________
❇️ Project Structure
First, ensure your project follows this file structure. This standard approach keeps your application organized and scalable.
/Express_App
|-- config/
|   |-- db.js               <-- Database connection logic
|-- models/
|   |-- emp.js              <-- Mongoose schema and model
|-- public/
|   |-- style.css           <-- Your CSS file (if you have one)
|-- views/
|   |-- empdata.ejs         <-- The view for displaying employee data
|   |-- home.ejs            <-- The view for the employee registration form
|-- node_modules/
|-- .env                    <-- Environment variables (recommended for production)
|-- package.json
|-- index.js                <-- The main server file
________________________________________
 


❇️ index.js (Main Server File)
const express = require('express');
const app = express();
const HOST = '127.0.0.1';
const PORT = process.env.PORT || 3000;
const conn = require('./config/db');
conn(); // Connect to the database
app.use(express.static('public')); // Serve static files
app.use(express.urlencoded({ extended: true }));
app.use(express.json());
app.set('view engine', 'ejs');
const Emp = require('./models/emp');

// ----- ROUTES ---------------------------------------------------

// GET: Homepage (Registration Form)
app.get('/', (req, res) => {
  res.render('home'); // home.ejs
});
// POST: Save form data to DB
app.post('/saveform', async (req, res) => {
  try {
    const newEmployee = new Emp(req.body);
    await newEmployee.save();
    console.log('Employee saved successfully:', newEmployee);
    res.send('Employee data saved successfully!');
  } catch (error) {
    console.error('Error saving employee data:', error);
    res.status(500).send('Error saving employee data.');
  }});


// GET: Display all employee data
app.get('/empdata', async (req, res) => {
  try {
    const allEmployees = await Emp.find();
    res.render('empdata', { employees: allEmployees });
  } catch (error) {
    console.error('Error fetching employee data:', error);
    res.status(500).send('Error fetching employee data.');
  }
});
// Start server
app.listen(PORT, () => {
  console.log(`Server is up on http://${HOST}:${PORT}`);
});
________________________________________
 




❇️ config/db.js (Database Connection)
const mongoose = require('mongoose');
const dbConnection = async () => {
  try {
    await mongoose.connect('mongodb://localhost:27017/company');
    console.log('DB Connection Done 😊');
  } catch (error) {
    console.log('DB Connection Failed 😞');
    console.error(error);
  }
};
module.exports = dbConnection;
________________________________________
models/emp.js (Mongoose Schema)
const mongoose = require('mongoose');
const Schema = mongoose.Schema;

const empSchema = new Schema({
  empName: { type: String, required: true },
  empEmail: { type: String, required: true, unique: true },
  empPass: { type: String, required: true },
  empPhone: { type: String },
  empRole: { type: String },
  empCTC: { type: Number },
  empAddress: { type: String }
});

// Create a model and export
const Emp = mongoose.model('Emp', empSchema);
module.exports = Emp;
________________________________________
 




❇️ views/home.ejs (Employee Registration Form)

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Employee Registration</title>
    <link rel="stylesheet" href="/style.css">
</head>
<body>
    <div class="container">
        <h2>Employee Registration Form</h2>
        <form action="/saveform" method="post">
            <label for="empName">Employee Name:</label>
            <input type="text" id="empName" name="empName" required>

            <label for="empEmail">Email:</label>
            <input type="email" id="empEmail" name="empEmail" required>

            <label for="empPass">Password:</label>
            <input type="password" id="empPass" name="empPass" required>

            <label for="empPhone">Phone Number:</label>
            <input type="tel" id="empPhone" name="empPhone">

            <label for="empRole">Role:</label>
            <input type="text" id="empRole" name="empRole">

            <label for="empCTC">CTC:</label>
            <input type="number" id="empCTC" name="empCTC">

            <label for="empAddress">Address:</label>
            <textarea id="empAddress" name="empAddress"></textarea>
            
            <button type="submit">Register Employee</button>
        </form>
    </div>
</body>
</html>
________________________________________
 


❇️ views/empdata.ejs (Display Data)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Employee Data</title>
    <link rel="stylesheet" href="/style.css">
</head>
<body>
    <div class="container">
        <h2>All Employee Records</h2>
        <a href="/">Go Back to Registration Form</a>
        <table>
            <thead>
                <tr>
                    <th>ID</th>
                    <th>Name</th>
                    <th>Email</th>
                    <th>Phone</th>
                    <th>Role</th>
                    <th>CTC</th>
                    <th>Address</th>
                </tr>
            </thead>
            <tbody>
                <% employees.forEach((employee, index) => { %>
                    <tr>
                        <td><%= index + 1 %></td>
                        <td><%= employee.empName %></td>
                        <td><%= employee.empEmail %></td>
                        <td><%= employee.empPhone %></td>
                        <td><%= employee.empRole %></td>
                        <td><%= employee.empCTC %></td>
                        <td><%= employee.empAddress %></td>
                    </tr>
                <% }) %>
            </tbody>
        </table>
    </div>
</body>
</html>
_______________________________________________________________________________
 
Backend - Express - DAY 11
___________________________________________________________________________
MongoDB & Express.js CRUD Notes: Delete and Update

1. The Delete Operation
The goal is to click a delete button next to a product, which removes it from the database and refreshes the product list. This involves a user action in the view, a corresponding route in Express, and a database command.

Step 1: The "Delete" Link in the View (productdata.ejs)
In your product list table, each product row has a delete icon. This icon is wrapped in a link (<a> tag) that points to a specific URL for deleting that item.

---
<td>
  <a href="/delete/<%= val._id %>" onclick="return confirm('Are You Sure ?')">
    <i class="fa fa-trash fw-bold text-danger"></i>
  </a>
</td>
---
Explanation:
•	href="/delete/<%= val._id %>": This is the most critical part.
o	It creates a unique URL for each product, for example, /delete/60b8d295f1d2a1234567890.
o	<%= val._id %> is EJS syntax that injects the unique _id of the product from the database into the URL.
•	onclick="return confirm('Are You Sure ?')": This is a client-side JavaScript feature. It shows a confirmation popup to the user before proceeding with the link. This is good practice to prevent accidental deletions.














Step 2: The Express Route for Deletion (index.js)
When the user clicks the delete link, the browser sends a GET request to the server at the specified URL (e.g., /delete/some-id). Your Express app needs a route to handle this.
---
// A route to handle the GET request for deleting an employee
app.get('/delete/:id', async (req, res) => {
    try {
        const id = req.params.id;
        await Emp.findByIdAndDelete(id);
        res.redirect('/empdata');
    } catch (error) {
        console.error(error);
        res.status(500).send("Error deleting employee.");
    }
});
---
Explanation:
1.	app.get('/delete/:id', ...): This defines a route that listens for GET requests on paths that match the pattern /delete/ followed by an ID. The :id part is a URL parameter.
2.	const id = req.params.id;: Express automatically captures the value from the :id part of the URL and makes it available in the req.params object.
3.	await Product.findByIdAndDelete(id);: This is the Mongoose command that communicates with your MongoDB database. It finds one document with the matching _id and removes it.
4.	res.redirect('/productdata');: After successfully deleting the item, you redirect the user back to the main product list page. The browser will then make a new request to /productdata, which will fetch and display the now-updated list of products. This is part of the Post-Redirect-Get (PRG) pattern and is excellent practice.
________________________________________
 
2. The Update (Edit) Operation
The update process is a two-stage operation:
1.	Stage A: Fetch the existing data for an item and display it in an editable form.
2.	Stage B: Submit the modified data from the form to the server to update the database.
Stage A: Showing the Edit Form
Step 1: The "Edit" Link in the View (productdata.ejs)
Similar to the delete link, you need a link that takes the user to the edit page for a specific 
---
<td>
  <a href="/edit/<%= val._id %>">
    <i class="fa fa-edit fw-bold text-success"></i>
  </a>
</td>
---
Step 2: The GET Route to Render the Edit Form (index.js)
This route finds the product's data and passes it to the edit.ejs template so the form can be pre-filled.
---
app.get('/edit/:id', async (req, res) => {
    try {
        // 1. Get the ID from the URL
        const id = req.params.id;

        // 2. Find the product's data using its ID
        const result = await product.findById(id);

        // 3. Render the edit page and pass the product data to it
        res.render('edit.ejs', { data: result });

    } catch (error) {
        console.log(error);
    }
});
---
 
Step 3: The Edit Form (edit.ejs)
The form is pre-populated with the data passed from the res.render call.
---
<form action="/updateform/<%= data._id %>" method="post">
    <div class="col-md-6">
      <label for="productName" class="form-label">Update Product Name</label>
      <input type="text" class="form-control" value="<%= data.productName %>" id="productName" name="productName">
    </div>

    <div class="col-md-6">
      <label for="productPrice" class="form-label">Update Product Price</label>
      <input type="number" class="form-control" value="<%= data.productPrice %>" id="productPrice" name="productPrice">
    </div>

    <button type="submit" class="btn btn-primary">Update Product</button>
</form>
---
Explanation :
1.	value="<%= data.productName %>": This is how you pre-fill the form fields. The data object from your route is used to place the current product name, price, etc., into the value attributes of the input fields.

Stage B: Processing the Submitted Form Data
Step 4: The POST Route to Update the Database (index.js)
This route receives the submitted form data and performs the database update.
---
app.post('/updateform/:id', async (req, res) => {
    try {
        // 1. Get the ID from the URL
        const id = req.params.id;

        // 2. Find the document by ID and update it with the new data from the form
        // req.body contains the submitted form data (e.g., { productName: 'New Name', productPrice: 123 })
        const result = await product.findByIdAndUpdate(id, req.body);

        // 3. Redirect to the product list page
        res.redirect('/productdata');

    } catch (error) {
        console.log(error);
    }
});
---



Explanation:
1.	app.post('/updateform/:id', ...): This route listens for POST requests at the URL specified in the form's action attribute.
2.	req.body: When a form is submitted via POST, Express (with the help of express.urlencoded() middleware) parses the data and makes it available in req.body.
3.	await product.findByIdAndUpdate(id, req.body);: This is the Mongoose command that does the magic. It finds the document with the matching id and updates its fields with the key-value pairs from req.body.
4.	res.redirect('/productdata');: Again, using the PRG pattern, you redirect the user to the product list to see the successful update.
________________________________________
Summary of Key Concepts & Best Practices
1.	Unique URLs for Items: Always use the item's _id as a URL parameter (/:id) for operations targeting a specific document.
2.	Rendering vs. Sending: Use res.render() to build and send a full HTML page with data. Use res.send() or res.json() for API-style responses (sending raw data).
3.	PRG Pattern (Post-Redirect-Get): After a successful POST, PUT, or DELETE request, always res.redirect() to a GET route. This prevents users from accidentally re-submitting the form by refreshing the page.
4.	Mongoose Methods:
o	Delete: Product.findByIdAndDelete(id)
o	Update: Product.findByIdAndUpdate(id, newData)
o	Read (for Edit Form): Product.findById(id)
5.	Form Data Flow: The name attribute of an <input> tag becomes the key in the req.body object on the server. For example, <input name="productName"> becomes req.body.productName.
--------------------------------------------------------------------------------------------------------------------------


 
Backend - Express - DAY 12
____________________________________________________________________________________
Summary Notes: File Uploads in Express.js with Multer
Multer is a Node.js middleware for handling multipart/form-data, which is primarily used for uploading files. It integrates seamlessly with Express to simplify the process of handling file uploads.

1. Installation and Basic Setup
First, you need to install Express and Multer in your project.

npm install express multer

In your main server file (e.g., index.js), you require them.
const express = require('express');
const multer = require('multer');
const app = express();

Other setup like database connection, models, etc.
const profiles = require('./models/profileSchema');

2. Configuring Multer Storage
Multer needs to know where and how to store the files it processes. The most common strategy is multer.diskStorage.
multer.diskStorage() takes an object with two key functions: destination and filename.
•	destination: A function or string that tells Multer in which folder to store the uploaded files.
•	filename: A function that tells Multer what to name the file inside the destination folder.
Example Configuration:

// Configure storage for Multer
const storage = multer.diskStorage({
    destination: function (req, file, cb) {
        // The folder where files will be saved
        cb(null, 'public/uploads/');
    },
    filename: function (req, file, cb) {
        // To ensure unique filenames, prepend the current timestamp to the original filename.
        // This prevents files with the same name from overwriting each other.
        const uniqueSuffix = Date.now() + '-' + Math.round(Math.random() * 1E9);
        cb(null, uniqueSuffix + '-' + file.originalname);
    }
});




// Initialize Multer with the storage configuration
const upload = multer({ storage: storage });
•	Note on Filenames: The snippet Date.now() + "-" + file.originalname is a good practice to avoid name conflicts.

3. CRUD Operations with File Uploads

A. Create (POST Request with a File)---
To create a new record that includes a file, you use the upload middleware in your route definition. upload.single('fieldName') will process a single file from the form field named 'fieldName'.

---
// Route to handle creating a new profile with a picture
// 'userProfile' is the name of the <input type="file" name="userProfile"> in your HTML form.
--
app.post('/profiles', upload.single('userProfile'), async (req, res) => {
    try {
        const newProfile = new profiles({
            name: req.body.name,
            email: req.body.email,
            // req.file contains information about the uploaded file
            // We save the path or filename to the database
            profilePic: req.file.filename 
        });

        await newProfile.save();
        res.status(201).send("Profile created successfully!");

    } catch (error) {
        res.status(500).send("Error creating profile.");
    }
});
--
---
 
B. Read (GET Request and Displaying Data)---
Your frontend code snippet shows how to display the data. You fetch the records from your database and pass them to your template. The image is rendered using the filename stored in the database.
---
<tbody>
  <% data.map((val, index) => { %>
    <tr>
      <td class="text-center"><%= index+1 %></td>
      <td><%= val.userName %></td>
      <td><%= val.userPassword %></td>
      <td>
        <img src="/uploads/<%= val.userProfile %>" alt="Profile" class="rounded-circle border" width="50" height="50">
      </td>
    </tr>
  <% }) %>
</tbody>
Make sure your Express app serves the uploads folder as a static directory: app.use(express.static('public')); or app.use('/uploads', express.static('public/uploads'));
---
________________________________________
C. Delete (DELETE Request) ---
---
const fs = require('fs'); // Require the File System module at the top of your file
const path = require('path'); // Require the Path module

app.delete('/delete/:id', async (req, res) => {
    try {
        const id = req.params.id;

        // 1. Find the profile document to get the filename of the image
        const profileToDelete = await profiles.findById(id);
        
        if (!profileToDelete) {
            return res.status(404).send("<h2>User not found.</h2>");
        }

        const filename = profileToDelete.profilePic; // Assuming 'profilePic' is the field name in your schema
---

// 2. Delete the file from the 'public/uploads' directory
        if (filename) {
            const filePath = path.join(__dirname, 'public/uploads', filename);
            fs.unlink(filePath, (err) => {
                if (err) {
                    console.error("Failed to delete the file:", err);
                    // Decide if you want to stop the process or just log the error
                    // For this example, we will continue to delete the DB record
                } else {
                    console.log("Successfully deleted file:", filePath);
                }
            });
        }
        ---


// 3. Delete the profile document from the database
        await profiles.findByIdAndDelete(id);

        res.status(200).send("<h2>Deleted User Successfully</h2>");

    } catch (err) {
        console.error(err);
        res.status(500).send("<h2>Failed to Delete User</h2>");
    }
});
--------------------------------------------------------------------------------------
D. Edit / Update (PUT or PATCH Request)---
The logic for updating is slightly more complex. You need to handle cases where the user uploads a new file and cases where they only update text fields without changing the existing file.
Recommended UPDATE Route:
JavaScript
// Use PUT for replacing the entire resource, or PATCH for partial updates.
// We still need the upload middleware to handle a potential new file.
---
app.put('/update/:id', upload.single('userProfile'), async (req, res) => {
    try {
        const id = req.params.id;
        
        // Find the existing profile
        const existingProfile = await profiles.findById(id);
        if (!existingProfile) {
            return res.status(404).send('Profile not found');
        }

        // Prepare the update data
        const updateData = {
            name: req.body.name,
            email: req.body.email,
        };
---
// Check if a new file was uploaded
        if (req.file) {
            // A new file is uploaded, so we need to delete the old one.
            const oldFilename = existingProfile.profilePic;
            if (oldFilename) {
                const oldFilePath = path.join(__dirname, 'public/uploads', oldFilename);
                fs.unlink(oldFilePath, (err) => {
                    if (err) console.error("Error deleting old file:", err);
                });
            }






// Add the new filename to our update data
            updateData.profilePic = req.file.filename;
        }

// Update the profile in the database
        await profiles.findByIdAndUpdate(id, updateData, { new: true });
// {new: true} returns the updated doc
        res.status(200).send("Profile updated successfully!");
    } catch (error) {
        console.error(error);
        res.status(500).send("Error updating profile.");
    }
});
________________________________________
Summary of Key Multer Functions (from your image)
•	upload.single('file'): Accepts a single file with the name "file".
•	upload.array('files', 5): Accepts an array of files (max 5) with the name "files".
•	multer.diskStorage(): Configures Multer to save files to disk, allowing you to control the destination and filename.
•	multer.memoryStorage(): Stores files in memory as Buffer objects. Useful for quick image manipulation before saving, but can consume a lot of RAM.
____________________________________________________________________________________
 
Backend - Express – CRUD - Operation
____________________________________________________________________________________

INDEX.JS FILE CODE SNIPPET
---
const express = require("express");
const path = require("path");
const connectDB = require("./config/db");
const Employee = require("./models/emp");

const app = express();
connectDB();

// Middleware
app.use(express.urlencoded({ extended: true })); // for form data
app.set("view engine", "ejs");
app.set("views", path.join(__dirname, "views"));

// Routes

// Page 1: Add form
app.get("/", (req, res) => {
  res.render("add");
});

// Insert employee
app.post("/add", async (req, res) => {
  try {
    const { name, age, email, phone } = req.body;
    await Employee.create({ name, age, email, phone });
    res.redirect("/list");
  } catch (err) {
    res.send("Error: " + err.message);
  }
});

// Page 2: List employees
app.get("/list", async (req, res) => {
  const employees = await Employee.find();
  res.render("list", { employees });
});

// Edit employee (form)
app.get("/edit/:id", async (req, res) => {
  const emp = await Employee.findById(req.params.id);
  res.render("edit", { emp });
});








// Update employee
app.post("/edit/:id", async (req, res) => {
  const { name, age, email, phone } = req.body;
  await Employee.findByIdAndUpdate(req.params.id, { name, age, email, phone });
  res.redirect("/list");
});

// Delete employee
app.get("/delete/:id", async (req, res) => {
  await Employee.findByIdAndDelete(req.params.id);
  res.redirect("/list");
});

// Start server
app.listen(3000, () =>
  console.log("✅ Server started on http://localhost:3000")
);

------

EXPLANATION OF A CODE:

1. Importing required modules
---
const express = require("express");
const path = require("path");
const connectDB = require("./config/db");
const Employee = require("./models/emp");
---
•	express → helps you create a web server easily.
•	path → helps you work with file paths (like telling Express where your views folder is).
•	connectDB → a function you wrote to connect to MongoDB.
•	Employee → your MongoDB model (like a "blueprint" for employee data in the database).
________________________________________
2. Setting up Express
---
const app = express();
connectDB();
---
•	Creates an Express app.
•	Connects to the MongoDB database.
________________________________________






3. Middleware
---
app.use(express.urlencoded({ extended: true })); 
app.set("view engine", "ejs");
app.set("views", path.join(__dirname, "views"));
---
•	express.urlencoded(...) → allows your server to read form data (like when you submit a form).
•	app.set("view engine", "ejs") → tells Express you’ll use EJS templates for rendering HTML.
•	app.set("views", ...) → sets the folder where your EJS files are located.
________________________________________
4. Routes
This is where you define what should happen when users visit different URLs.
(a) Add Employee Page
---
app.get("/", (req, res) => {
  res.render("add");
});
---
👉 When you go to http://localhost:3000/, it shows the add employee form (add.ejs file).
________________________________________
(b) Insert Employee
---
app.post("/add", async (req, res) => {
  const { name, age, email, phone } = req.body;
  await Employee.create({ name, age, email, phone });
  res.redirect("/list");
});
---
👉 When the form is submitted, this route takes the input (name, age, email, phone) and saves it to MongoDB.
👉 After saving, it redirects you to /list to see all employees.
________________________________________
(c) List Employees
---
app.get("/list", async (req, res) => {
  const employees = await Employee.find();
  res.render("list", { employees });
});
---
👉 Fetches all employees from the database.
👉 Passes them to the list.ejs file to display.
________________________________________








(d) Edit Employee (show form)
---
app.get("/edit/:id", async (req, res) => {
  const emp = await Employee.findById(req.params.id);
  res.render("edit", { emp });
});
---
👉 When you go to /edit/employeeID, it finds that employee and shows an edit form (edit.ejs).
________________________________________
(e) Update Employee
---
app.post("/edit/:id", async (req, res) => {
  const { name, age, email, phone } = req.body;
  await Employee.findByIdAndUpdate(req.params.id, { name, age, email, phone });
  res.redirect("/list");
});
---
👉 Updates the employee info in MongoDB.
👉 Then redirects back to the list page.
________________________________________
(f) Delete Employee
---
app.get("/delete/:id", async (req, res) => {
  await Employee.findByIdAndDelete(req.params.id);
  res.redirect("/list");
});
---
👉 Deletes the employee by ID.
👉 Then reloads the list page.
________________________________________
5. Starting the server
---
app.listen(3000, () =>
  console.log("✅ Server started on http://localhost:3000")
);
---
👉 Starts the server at http://localhost:3000.

---------------------------------------------------------------------------------------------------------------------------------
 
CONFIG/DB.JS
---
const mongoose = require("mongoose");

const connectDB = async () => {
  try {
    await mongoose.connect("mongodb://127.0.0.1:27017/company", {
      useNewUrlParser: true,
      useUnifiedTopology: true,
    });
    console.log("✅ MongoDB connected...");
  } catch (err) {
    console.error("❌ DB connection failed:", err);
    process.exit(1);
  }
};

module.exports = connectDB;
---
EXPLANATION OF  A CODE
1. Importing Mongoose
--
const mongoose = require("mongoose");
---
•	mongoose is a library that helps you talk to MongoDB in an easy way.
•	It lets you connect, create schemas/models, and run queries.
________________________________________
2. Creating a Function to Connect DB
---
const connectDB = async () => {
  try {
    await mongoose.connect("mongodb://127.0.0.1:27017/company", {
      useNewUrlParser: true,
      useUnifiedTopology: true,
    });
    console.log("✅ MongoDB connected...");
  } catch (err) {
    console.error("❌ DB connection failed:", err);
    process.exit(1);
  }
};
---
👉 What’s happening here:
•	const connectDB = async () => { ... } → makes a function called connectDB that runs asynchronously (because connecting to DB takes time).
•	mongoose.connect("mongodb://127.0.0.1:27017/company", {...}) → actually connects to the database.




o	mongodb://127.0.0.1:27017/company → this is the connection string:
	127.0.0.1 = your local computer (localhost)
	27017 = default MongoDB port
	company = database name (MongoDB will create it if it doesn’t exist)
o	Options:
	useNewUrlParser: true → makes sure new URL parser is used (avoids warnings).
	useUnifiedTopology: true → uses the new MongoDB engine for better connection handling.
•	If the connection is successful → console.log("✅ MongoDB connected...").
•	If it fails → it shows an error and process.exit(1) stops the app (so you don’t run a broken app without DB).
________________________________________
3. Exporting the Function
---
module.exports = connectDB;
---
•	Makes this function available in other files.
•	Example: in your server.js or app.js, you can call:
const connectDB = require("./config/db");
connectDB();   // starts MongoDB connection
________________________________________
🚀 In short:
•	This file connects your Express app to MongoDB.
•	It tries → connects → shows success.
•	If it fails → shows error and stops the app.
•	Exported so you can use it in your main app file.
--------------------------------------------------------------------------------------------------------------------------------














MODELS/EMP.JS
--
const mongoose = require("mongoose");

const empSchema = new mongoose.Schema({
  name: String,
  age: Number,
  email: String,
  phone: String,
});

module.exports = mongoose.model("Employee", empSchema);

--
1. Import mongoose
const mongoose = require("mongoose");
•	mongoose is an ODM (Object Data Modeling) library for MongoDB.
•	It lets you define schemas (blueprints) for documents and interact with MongoDB using JavaScript objects.
________________________________________
2. Define a schema
const empSchema = new mongoose.Schema({
  name: String,
  age: Number,
  email: String,
  phone: String,
});
•	mongoose.Schema defines the structure of documents inside a MongoDB collection.
•	Here, each Employee document will look like:
{
  "name": "John Doe",
  "age": 25,
  "email": "john@example.com",
  "phone": "1234567890"
}
Fields:
o	name: text/string
o	age: number
o	email: text/string
o	phone: text/string
(You could also add validations like required: true, unique: true, etc., but here it’s kept simple.)
________________________________________





3. Create a model
module.exports = mongoose.model("Employee", empSchema);
•	mongoose.model("Employee", empSchema):
o	First argument "Employee" → model name.
	MongoDB will automatically create/use a collection called employees (lowercase + plural).
o	Second argument empSchema → schema blueprint.
•	The model is like a class in OOP → you can create objects (documents), save them, update them, query them, etc.
____________________________________________________________________________________

VIEWS/ADD.JS
---
<!DOCTYPE html>
<html>
  <head>
    <title>Add Employee</title>
  </head>
  <body>
    <h1>Register Employee</h1>
    <form action="/add" method="POST">
      <label>Name:</label>
      <input type="text" name="name" required /><br />

      <label>Age:</label>
      <input type="number" name="age" required /><br />

      <label>Email:</label>
      <input type="email" name="email" required /><br />

      <label>Phone:</label>
      <input type="text" name="phone" required /><br />

      <button type="submit">Submit</button>
    </form>
  </body>
</html>
---
____________________________________________________________________________________


 
VIEWS/LIST.JS
<!DOCTYPE html>
<html>
  <head>
    <title>Employee List</title>
  </head>
  <body>
    <h1>All Employees</h1>
    <a href="/">➕ Add New Employee</a>
    <table border="1" cellpadding="8">
      <tr>
        <th>Name</th>
        <th>Age</th>
        <th>Email</th>
        <th>Phone</th>
        <th>Actions</th>
      </tr>
      <% employees.forEach(emp => { %>                // MAP METHOD ALTERNATEVELY
      <tr>
        <td><%= emp.name %></td>
        <td><%= emp.age %></td>
        <td><%= emp.email %></td>
        <td><%= emp.phone %></td>
        <td>
          <a href="/edit/<%= emp._id %>">✏️ Edit</a>
          <a href="/delete/<%= emp._id %>">🗑️ Delete</a>
        </td>
      </tr>
      <% }) %>
    </table>
  </body>
</html>
______________________________________________________________________________________

VIEWS/EDIT.JS
<!DOCTYPE html>
<html>
<head>
  <title>Edit Employee</title>
</head>
<body>
  <h1>Edit Employee</h1>
  <form action="/edit/<%= emp._id %>" method="POST">
    <label>Name:</label>
    <input type="text" name="name" value="<%= emp.name %>" required /><br />

    <label>Age:</label>
    <input type="number" name="age" value="<%= emp.age %>" required /><br />

    <label>Email:</label>
    <input type="email" name="email" value="<%= emp.email %>" required /><br />

    <label>Phone:</label>
    <input type="text" name="phone" value="<%= emp.phone %>" required /><br />

    <button type="submit">Update</button>
  </form> </body> </html>
______________________________________________________________________________________
Backend - Express – CRUD – Operation + File
______________________________________________________________________________________

INDEX.JS

---
const express = require("express");
const app = express();
const path = require("path");
const multer = require("multer");
const Emp = require("./models/emp");

// Middleware-----
app.use(express.urlencoded({ extended: true }));
app.use(express.json());
app.use(express.static("public"));
app.set("view engine", "ejs");

// Multer setup for file upload-----
const storage = multer.diskStorage({
  destination: function (req, file, cb) {
    cb(null, "public/uploads/");
  },
  filename: function (req, file, cb) {
    cb(null, Date.now() + "-" + file.originalname);
  },
});
const upload = multer({ storage: storage });

// ---------------------- ROUTES ----------------------

// Page 1: Add employee-----
app.get("/add", (req, res) => {
  res.render("add", { emp: null }); // send emp as null
});

app.post("/add", upload.single("photo"), async (req, res) => {
  const { name, age, email, phone } = req.body;
  const photo = req.file ? req.file.filename : "";
  const emp = new Emp({ name, age, email, phone, photo });
  await emp.save();
  res.redirect("/list");
});

// Page 2: List all employees-----
app.get("/list", async (req, res) => {
  const employees = await Emp.find();
  res.render("list", { employees });
});









// Edit employee-----
app.get("/edit/:id", async (req, res) => {
  const emp = await Emp.findById(req.params.id);
  res.render("add", { emp }); // reuse add.ejs for edit
});

app.post("/edit/:id", upload.single("photo"), async (req, res) => {
  const { name, age, email, phone } = req.body;
  const emp = await Emp.findById(req.params.id);

  emp.name = name;
  emp.age = age;
  emp.email = email;
  emp.phone = phone;

  if (req.file) {
    emp.photo = req.file.filename;
  }

  await emp.save();
  res.redirect("/list");
});

// Delete employee-----
app.get("/delete/:id", async (req, res) => {
  await Emp.findByIdAndDelete(req.params.id);
  res.redirect("/list");
});

// Start server-----
app.listen(3000, () => console.log("Server running on http://localhost:3000"));


--------------------------------------------------------------------------------------

EXPLANATION OF CODE

1. Required modules
---
const express = require("express");
const app = express();
const path = require("path");
const multer = require("multer");
const Emp = require("./models/emp");
---
•	express → web server framework.
•	path → Node’s path utility (not heavily used here).
•	multer → middleware for file uploads.
•	Emp → the Mongoose model you created earlier (empSchema).
________________________________________






2. Middleware setup
---
app.use(express.urlencoded({ extended: true }));
app.use(express.json());
app.use(express.static("public"));
app.set("view engine", "ejs");
---
•	express.urlencoded() → parses form submissions (like <form>).
•	express.json() → parses JSON request bodies (APIs).
•	express.static("public") → serves static files (public/ folder, e.g., CSS, JS, uploaded images).
•	app.set("view engine", "ejs") → sets EJS as the templating engine for rendering HTML pages.
________________________________________
3. Multer configuration (file upload)
---
const storage = multer.diskStorage({
  destination: function (req, file, cb) {
    cb(null, "public/uploads/");
  },
  filename: function (req, file, cb) {
    cb(null, Date.now() + "-" + file.originalname);
  },
});
const upload = multer({ storage: storage });
---
•	Files uploaded through a form will be saved in public/uploads/.
•	Each uploaded file is renamed as:
•	1692283981234-originalfilename.jpg
(timestamp + original filename).
________________________________________
4. Routes
➤ Page 1: Add Employee (GET)
---
app.get("/add", (req, res) => {
  res.render("add", { emp: null }); // renders add.ejs with emp=null
});
---
•	Shows the employee form (add.ejs).
•	emp=null → tells the view we’re creating a new employee (not editing).
________________________________________











➤ Add Employee (POST)
---
app.post("/add", upload.single("photo"), async (req, res) => {
  const { name, age, email, phone } = req.body;
  const photo = req.file ? req.file.filename : "";
  const emp = new Emp({ name, age, email, phone, photo });
  await emp.save();
  res.redirect("/list");
});
---
•	upload.single("photo") → accepts a file from the form field named photo.
•	Creates a new Emp document with submitted details and uploaded photo.
•	Saves it to MongoDB.
•	Redirects to /list page (to see all employees).
________________________________________
➤ Page 2: List Employees
---
app.get("/list", async (req, res) => {
  const employees = await Emp.find();
  res.render("list", { employees });
});
---
•	Fetches all employees from MongoDB.
•	Passes them to list.ejs for display.
________________________________________
➤ Edit Employee (GET)
---
app.get("/edit/:id", async (req, res) => {
  const emp = await Emp.findById(req.params.id);
  res.render("add", { emp }); // reuse add.ejs form for editing
});
---
•	Finds an employee by ID.
•	Renders add.ejs again, but pre-fills the form with employee data for editing.
________________________________________

















➤ Edit Employee (POST)
---
app.post("/edit/:id", upload.single("photo"), async (req, res) => {
  const { name, age, email, phone } = req.body;
  const emp = await Emp.findById(req.params.id);

  emp.name = name;
  emp.age = age;
  emp.email = email;
  emp.phone = phone;

  if (req.file) {
    emp.photo = req.file.filename; // replace old photo if new one uploaded
  }

  await emp.save();
  res.redirect("/list");
});
---
•	Updates employee details.
•	If a new photo is uploaded → replaces old one.
•	Saves updated employee.
•	Redirects back to /list.
________________________________________
➤ Delete Employee
---
app.get("/delete/:id", async (req, res) => {
  await Emp.findByIdAndDelete(req.params.id);
  res.redirect("/list");
});
---
•	Deletes employee by ID.
•	Redirects back to list page.
________________________________________
5. Start Server
---
app.listen(3000, () => console.log("Server running on http://localhost:3000"));
---
•	Starts Express server on port 3000.
____________________________________________________________________________________________

 
---
VIEWS/ADD.EJS
---
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title><%= emp ? 'Edit' : 'Add' %> Employee</title>
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css"
      rel="stylesheet"
    />
  </head>
  <body>
    <div class="container mt-5">
      <h2><%= emp ? 'Edit' : 'Add' %> Employee</h2>
      <form
        action="<%= emp ? '/edit/' + emp._id : '/add' %>"
        method="post"
        enctype="multipart/form-data"
      >
        <div class="mb-3">
          <label>Name</label>
          <input
            type="text"
            class="form-control"
            name="name"
            value="<%= emp ? emp.name : '' %>"
            required
          />
        </div>
        <div class="mb-3">
          <label>Age</label>
          <input
            type="number"
            class="form-control"
            name="age"
            value="<%= emp ? emp.age : '' %>"
            required
          />
        </div>
        <div class="mb-3">
          <label>Email</label>
          <input
            type="email"
            class="form-control"
            name="email"
            value="<%= emp ? emp.email : '' %>"
            required
          />
        </div>
        <div class="mb-3">
          <label>Phone</label>
          <input
            type="text"
            class="form-control"
            name="phone"
            value="<%= emp ? emp.phone : '' %>"
            required
          />
        </div>
        <div class="mb-3">
          <label>Photo</label>
          <input type="file" class="form-control" name="photo" <%= emp ? '' :
          'required' %>> <% if(emp && emp.photo){ %>
          <img src="/uploads/<%= emp.photo %>" width="100" class="mt-2" />
          <% } %>
        </div>
        <button class="btn btn-primary" type="submit">
          <%= emp ? 'Update' : 'Add' %>
        </button>
      </form>
      <a href="/list" class="btn btn-secondary mt-3">View Employees</a>
    </div>
  </body>
</html>



---
EXPLANATION OF A CODE: 
---
🔹 File Structure / Purpose
•	Written in EJS, not plain HTML.
•	The <%= %> tags allow you to inject dynamic values from Node.js (Express).
•	This template is reused for Add Employee and Edit Employee by checking whether an emp object exists.
________________________________________
🔹 Code Breakdown
<title><%= emp ? 'Edit' : 'Add' %> Employee</title>
•	If emp object is provided → Title is Edit Employee.
•	If not → Title is Add Employee.
________________________________________
<h2><%= emp ? 'Edit' : 'Add' %> Employee</h2>
•	Same logic applied to heading.
________________________________________
<form action="<%= emp ? '/edit/' + emp._id : '/add' %>" method="post" enctype="multipart/form-data">
•	Form action changes based on the situation:
o	If editing → /edit/<employee_id>.
o	If adding → /add.
•	enctype="multipart/form-data" → allows file uploads (employee photo).
________________________________________
🔹 Input Fields
Each field is pre-filled if editing, otherwise empty.
Name
<input type="text" class="form-control" name="name" value="<%= emp ? emp.name : '' %>" required />
•	Shows the existing emp.name if editing.
•	Empty input if adding new employee.
Age
<input type="number" class="form-control" name="age" value="<%= emp ? emp.age : '' %>" required />
•	Works the same for age.
Email
<input type="email" class="form-control" name="email" value="<%= emp ? emp.email : '' %>" required />
Phone
<input type="text" class="form-control" name="phone" value="<%= emp ? emp.phone : '' %>" required />
________________________________________

🔹 Photo Upload
<input type="file" class="form-control" name="photo" <%= emp ? '' : 'required' %>>
•	If adding a new employee → Photo is required.
•	If editing → Photo is optional.
<% if(emp && emp.photo){ %>
  <img src="/uploads/<%= emp.photo %>" width="100" class="mt-2" />
<% } %>
•	If editing and a photo already exists, it shows a small preview.
________________________________________
🔹 Submit Button
<button class="btn btn-primary" type="submit">
  <%= emp ? 'Update' : 'Add' %>
</button>
•	Button text changes based on context: Update or Add.
________________________________________
🔹 Navigation
<a href="/list" class="btn btn-secondary mt-3">View Employees</a>
•	Provides a link to go back and view all employees.
-------------------------------------------------------------------------------------------------------------------------------------------

 
VIEWS/LIST.JS
---

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Employee List</title>
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css"
      rel="stylesheet"
    />
  </head>
  <body>
    <div class="container mt-5">
      <h2>All Employees</h2>
      <a href="/add" class="btn btn-success mb-3">Add New Employee</a>
      <table class="table table-bordered">
        <thead>
          <tr>
            <th>Photo</th>
            <th>Name</th>
            <th>Age</th>
            <th>Email</th>
            <th>Phone</th>
            <th>Actions</th>
          </tr>
        </thead>
        <tbody>
          <% employees.forEach(emp => { %>
          <tr>
            <td><img src="/uploads/<%= emp.photo %>" width="80" /></td>
            <td><%= emp.name %></td>
            <td><%= emp.age %></td>
            <td><%= emp.email %></td>
            <td><%= emp.phone %></td>
            <td>
              <a href="/edit/<%= emp._id %>" class="btn btn-primary btn-sm"
                >Edit</a
              >
              <a href="/delete/<%= emp._id %>" class="btn btn-danger btn-sm"
                >Delete</a
              >
            </td>
          </tr>
          <% }) %>
        </tbody>
      </table>
    </div>
  </body>
</html>
---


 
CONFIG/DB.JS:

---
const mongoose = require("mongoose");

mongoose
  .connect("mongodb://127.0.0.1:27017/company", {
    useNewUrlParser: true,
    useUnifiedTopology: true,
  })
  .then(() => console.log("MongoDB connected"))
  .catch((err) => console.log("MongoDB connection error:", err));

module.exports = mongoose;

---

MODELS/EMP.JS
---
const mongoose = require("../config/db");

const empSchema = new mongoose.Schema({
  name: String,
  age: Number,
  email: String,
  phone: String,
  photo: String,
});

module.exports = mongoose.model("Trainee", empSchema);

---
______________________________________________________________________________________






 
Backend - Express – Login Authentication
____________________________________________________________________________________________






