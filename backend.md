Node JS DAY 01
___________________________________________________________________________
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
A simple JavaScript code snippet showing:
•	console.log("Welcome To Node JS Backend JS Library")
•	console.log(10 + 30)
•	A Demo function defined as a constant arrow function that takes two arguments (with default values of 0) and logs their sum:
JavaScript
const Demo = (a = 0, b = 0) => {
  console.log(a + b)
}
•	Calling the Demo function with arguments 100 and 200: Demo(100, 200)
 
Day 02 
___________________________________________________________________________
1. Creating a Basic HTTP Server in Node.js:
•	Importing http module: const http = require('http'); This line imports the built-in Node.js http module, which is essential for creating an HTTP server.
•	Creating the server: const app = http.createServer((req, res) => { ... }); This creates an HTTP server instance. The createServer method takes a callback function that is executed for every incoming request. This callback receives two arguments: req (request object) and res (response object).
•	Sending a response:
o	res.write("Welcome To Node JS Server"): This line sends a piece of the response body to the client. The content must be a string.
o	res.write("Hello Dear"); and for(let i=0;i<=10;i++) { res.write(${i}) }: This demonstrates writing multiple parts to the response, including a fixed string and numbers from a loop.
o	res.end(): This method signals to the server that all of the response headers and body have been sent, and the response can be considered complete. It's crucial to call res.end() for every response.
•	Listening for incoming requests: app.listen(3000, () => { console.log('Server is Successfully Running localhost:3000') }); This line makes the server listen for incoming connections on port 3000. Once the server starts successfully, a message is logged to the console.
2. HTTP - Network Protocol:
•	Purpose: HTTP (Hypertext Transfer Protocol) is a network protocol that enables communication between clients (e.g., web browsers) and servers.
•	Nature: It operates on a Request-Response (Req-Res) protocol model, meaning clients send requests and servers send responses.
•	HTTP Methods: Common HTTP methods (also known as verbs) used for different types of operations are:
o	GET: Retrieves data.
o	POST: Submits data to be processed to a specified resource.
o	PUT: Updates an existing resource (replaces it entirely).
o	PATCH: Applies partial modifications to a resource.
o	DELETE: Deletes a specified resource.
 
Day 03 
___________________________________________________________________________
Node.js Server Development & Concepts
This summary covers creating HTTP servers in Node.js, handling HTML responses, URL parsing and routing, understanding modules, and an introduction to middleware.
________________________________________
1. Building an HTTP Server and Responding with HTML
•	Core Server Creation:
o	The http module is fundamental for creating servers: const http = require('http');
o	A server instance is created using http.createServer((req, res) => { ... });.
•	Sending Basic Responses:
o	res.write("<b>Welcome To Node JS Server !!</b>") sends string content to the client.
o	res.end() signals the completion of the response.
•	Sending HTML Responses with Headers:
o	To inform the browser that the response is HTML, set the Content-Type header.
o	res.writeHead(statusCode, { 'content-type': 'text/html' }) is used to set the HTTP status code (e.g., 200 for OK) and response headers.
o	Example:
JavaScript
const statusCode = 200;
res.writeHead(statusCode, { 'content-type': 'text/html' });
res.write("<input type='text' placeholder='enter your name'>");
res.write("<h1>Welcome To Node JS Server !!</h1>");
res.end();
•	Listening for Connections:
o	The server listens on a specified port and host: app.listen(PORT, () => { console.log(Server is running on http://HOST:{PORT}) });
o	It's good practice to define PORT and HOST as constants (e.g., const PORT = 3000; const HOST = '127.0.0.1';).
________________________________________




2. URL Parsing and Routing
•	URL Module:
o	The built-in url package (var url = require('url');) is used to fetch and parse data from a URL.
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
JavaScript
if (urldata.pathname === '/') {
    res.write("<h1>Home Page Node JS URL Routing </h1>");
} else if (urldata.pathname === '/about') {
    // ... respond for about page ...
}
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
5. Middleware (Brief Introduction)
•	(Mentioned as "middleware" in the prompt, but not detailed in the images)
•	In the context of Node.js (especially with frameworks like Express.js), middleware refers to functions that have access to the request object (req), the response object (res), and the next middleware function in the application’s request-response cycle. These functions can perform tasks like:
o	Executing any code.
o	Making changes to the request and response objects.
o	Ending the request-response cycle.
o	Calling the next middleware in the stack.
 
Day 04
___________________________________________________________________________
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
The core of an Express.js application involves setting up the server, defining routes, and listening for requests.
JavaScript
// Import the Express.js module
const express = require('express');

// Create an Express application instance
const app = express();

// Define the port number the server will listen on
const port = 3000;

// Define a route for the root URL ('/')
// When a GET request is made to '/', it sends "Hello World!" as a response
app.get('/', (req, res) => {
    res.send('Hello World!');
});

// Start the server and listen on the specified port
app.listen(port, () => {
    // Log a message to the console once the server starts
    console.log(`Example app listening on port ${port}`);
});





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
JavaScript
// This middleware will be executed for any request that hasn't been matched by previous routes.
// The '*' indicates it will match any path.
app.use((req, res) => {
    res.send("404 Not Found"); // Send a 404 message
});
 
Day 05
___________________________________________________________________________
Rendering JSON Data (Objects & Arrays)
In Express.js, you can send JSON data as a response from your server. This is useful for building APIs that serve data to the client.
Example: Sending an Object
You can define an object and send it directly as a response using res.send(). Express will automatically stringify the object into JSON.
JavaScript
app.get('/about', (req, res) => {
    const obj = {
        id: 1,
        name: "Pratik",
        skill: "HTML",
        email: 'pratik@gmail.com'
    };
    res.send(obj); // Sends the object as JSON
});
Example: Sending an Array
Similarly, you can send an array, and Express will convert it to JSON.
JavaScript
app.get('/about', (req, res) => {
    const arr = ["HTML", "CSS", "JS"];
    res.send(arr); // Sends the array as JSON
});
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
Bash
npm i ejs
Step 2: Create a views Folder (and project structure)
For larger, more readable, manageable, and easily developed applications, it's crucial to have a well-organized folder structure. By convention, template files (like EJS files) are placed in a views directory.
Step 3: Use the res.render() Method
Instead of sending raw HTML or JSON with res.send(), you use res.render() to render an EJS template.
JavaScript
// Example in your index.js
app.get('/', (req, res) => {
    res.render('home.ejs'); // Renders the 'home.ejs' file located in the 'views' folder
});



Step 4: Create EJS Pages (e.g., home.ejs)
Inside your views folder, create your EJS files. These files will look like standard HTML but can include EJS specific syntax.
Example: home.ejs
HTML
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
Step 5: Data Traversing (Passing Dynamic Data from index.js to EJS)
The power of template engines lies in passing dynamic data from your server-side Express application to your EJS templates.
You pass data as a second argument to the res.render() method, typically an object where keys become variables accessible within the EJS template.
JavaScript
app.get('/about', (req, res) => {
    const obj = {
        data: 'user' // 'user' is the dynamic data we want to pass
    };
    res.render('about.ejs', obj); // Passes the 'obj' data to 'about.ejs'
});








EJS Syntax for Data Display and Logic
EJS uses specific tags to embed JavaScript logic and display data within HTML:
•	Logical Code:
Code snippet
<% EJS Syntax to write logical code %>
Used for control flow (if/else, loops) or defining variables that don't directly output to HTML.
•	Text Data Display:
Code snippet
<%= As a Text display data %>
Used to output data as plain text. This automatically escapes HTML characters, preventing XSS vulnerabilities.
•	HTML Data Display (Unescaped):
Code snippet
<%- As A HTML Display Data %>
Used to output data as raw HTML. Be cautious when using this, as it can introduce XSS vulnerabilities if the data is not sanitized.
•	Including External EJS Files:
Code snippet
<%- include('external.ejs') %>
Used to embed content from another EJS file into the current template, promoting reusability.
 
Day06
___________________________________________________________________________
EJS Syntax and Data Rendering
EJS (Embedded JavaScript) allows you to embed JavaScript code directly within your HTML templates, making them dynamic.
Example: about.ejs with Dynamic Data
This example demonstrates how to loop through data and apply conditional logic within an EJS template.
HTML
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
 
Passing Data to EJS Templates:
To render an EJS file with dynamic data, you pass an object to res.render(). The keys of this object become accessible variables within your EJS template.
JavaScript
app.get("/about", (req, res) => {
    // Array of user objects to be passed to the EJS template
    const user = [
        {
            id: 1,
            user: "user 1",
            umail: "a@gmail.com"
        },
        {
            id: 2,
            user: "user 2",
            umail: "b@gmail.com"
        },
        {
            id: 3,
            user: "user 3",
            umail: "c@gmail.com"
        }
    ];

    // Create an object to hold the data that will be passed to the EJS template
    const obj = { data: user };

    // Render the 'about.ejs' template, passing the 'obj' as data
    res.render("about.ejs", obj);
});
________________________________________
 
Express.js + EJS Template Engine vs. Express + React (Full-Stack with Client-Side Rendering)
Here's a comparison to help determine which approach is better for different scenarios:
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
 
Day 7 : Form Handling in Express.js
___________________________________________________________________________
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
JavaScript
app.get('/saveform', (req, res) => {
    var urldata = url.parse(req.url, true);
    res.send(urldata); // Sends the parsed URL data as a response
});
•	HTML Form (GET):
HTML
<form action="" method="get">
    <label for="">Enter Your Name:</label>
    <input type="text" name="username" id="username" placeholder="enter your name">
    <label for="">Enter Your Email:</label>
    </form>
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
JavaScript
app.post('/saveform', (req, res) => {
    res.send(req.body); // Sends the data from the request body as a response
});
•	Middleware for POST Method:
o	To properly access data sent via POST, middleware like express.urlencoded() (for URL-encoded data) or express.json() (for JSON data) or multer (for multipart/form-data for file uploads) is required to parse the request body.
IV. Key Differences & Summary
Feature	GET Method	POST Method
Data Pass	Through URL	Through Body
Security	Not Secure (Visible Data)	Secure (Hidden Data)
Data Volume	Limited (Small amount, up to 8MB)	Unlimited (Large amount, including files)
Usage	Non-sensitive data, retrieving information	Sensitive data (personal, financial), submitting forms, file uploads
Data Access	req.query (after url.parse)	req.body (requires middleware for parsing)

Overall Form Handling Considerations:
•	action attribute: Specifies where to send the form data.
•	method attribute: Defines the HTTP method (GET or POST) to be used.
•	name attribute: Crucial for identifying form fields and storing data in a database.
•	id attribute: Useful for client-side logical work and data fetching (e.g., JavaScript manipulation)
day 8 : node mongo connection
___________________________________________________________________________
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
Middleware
Middleware functions are functions that have access to the request object (req), the response object (res), and the next middleware function in the application’s request-response cycle. They are typically used for tasks like parsing data, logging, or serving static files.



•	Serving Static Files:
app.use(express.static('public/'))
o	This line of code sets up middleware to serve static files (like CSS, JavaScript, images) from a directory named public. When a browser requests a file, Express will look for it in this directory first.

•	URL-Encoded Data Parsing:
app.use(express.urlencoded({ extended: true }))
o	This middleware parses incoming request bodies with URL-encoded payloads. It's crucial for handling data submitted from an HTML form (e.g., a POST request with a content type of application/x-www-form-urlencoded).
o	extended: true allows for rich objects and arrays to be encoded into the URL-encoded format, using the qs library. false uses the built-in Node.js querystring library.
o	
•	JSON Data Parsing:
app.use(express.json())
o	This middleware is essential for parsing incoming request bodies with JSON payloads. This is commonly used in REST APIs where data is sent from the client to the server in JSON format (e.g., application/json). The parsed data is then available on req.body.
Routing
•	Root Route (/)
app.get('/', (req, res) => {
    res.send('Welcome To Express Server');
    res.render('form.ejs');
});
o	This is a route handler for a GET request to the root URL (/).
o	It sends a string response and renders an EJS template (form.ejs).
o	Note: It's important to know that res.send() and res.render() both terminate the request-response cycle. You should not call both in the same handler. The code as shown would only execute the first one (res.send) and the second one would fail. You would typically choose one or the other.


•	POST Route for Form Submission (/saveform)
app.post('/saveform', (req, res) => {
    res.send("<h1>Form Is Submitted !!</h1>");
});
o	This is a route handler for a POST request to the /saveform URL.
o	The app.post() method indicates that this route will handle data submissions, such as from an HTML form.
o	It sends back a simple HTML heading to the client, confirming the form submission.
o	In a real application, you would access the submitted form data using req.body and then process it (e.g., save it to a database like MongoDB).
___________________________________________________________________________
 
Node.js and MongoDB Connection with Mongoose
___________________________________________________________________________
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
________________________________________



Step 3: Importing and Using the Model
Now that you have your connection and model defined, you can import the model into your main server file to perform database operations.
1.	Import the Model:
o	In index.js, import the user model you created.
Code Example (index.js):
// import model
const user = require('./models/user');
2.	Inserting Data:
o	Inside a route handler (e.g., a POST request to /saveform), you can create a new document based on your model and save it to the database.
o	The new user() constructor takes the data you want to save.
o	The .save() method then persists this data to the MongoDB collection.
Code Example (index.js - POST route):
app.post('/saveform', (req, res) => {
    // ... (assuming you have express.json() middleware)
    const result = new user(req.body); // create new user document from request body
    result.save(); // save the document to the database
    res.send(result); // respond with the saved document
});
3.	Verification:
o	After the save operation, you can check your MongoDB database (using a tool like MongoDB Compass or the MongoDB Shell) to confirm that the data has been inserted correctly. The new document should be visible in the users collection within your company database.

