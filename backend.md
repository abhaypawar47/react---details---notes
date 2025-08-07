## Day 1: Node.js Overview

### Key Concepts
- **Definition**: JavaScript runtime for server-side scripting (Chrome V8 engine)
- **Created by**: Ryan Dahl, OpenJS Foundation (2009)
- **License**: MIT License
- **Languages**: JavaScript, Python, C++, etc.

### Benefits
- Single-threaded with event looping
- Fast execution (V8 Engine)
- Event-driven architecture
- Asynchronous & non-blocking I/O
- Highly scalable

### Real-Time Applications
- **Examples**: Google Meet, live streaming
- **Technologies**:
  - WebSockets (continuous connection)
  - Data Streaming (Netflix/Amazon)
  - Data Pipelining (chunked transfers)

### Architectures
```javascript
// Simple Node.js Example
const Demo = (a = 0, b = 0) => {
  console.log(a + b)
}
Demo(100, 200)
```

---

## Day 2: HTTP Server Basics

### Core Components
```javascript
const http = require('http');

const app = http.createServer((req, res) => {
  res.write("Welcome To Node JS Server");
  res.end();
});

app.listen(3000, () => {
  console.log('Server running on port 3000');
});
```

### HTTP Methods
| Method | Purpose          |
|--------|------------------|
| GET    | Retrieve data    |
| POST   | Submit data      |
| PUT    | Update resource  |
| DELETE | Remove resource  |

---

## Day 3: Advanced Server Concepts

### HTML Responses
```javascript
res.writeHead(200, { 'content-type': 'text/html' });
res.write("<h1>Welcome</h1>");
```

### URL Routing
```javascript
const url = require('url');
const urldata = url.parse(req.url, true);

if (urldata.pathname === '/about') {
  // Handle about route
}
```

### Module Types
1. Built-in (http, url)
2. User-defined
3. Third-party (Express, Nodemon)

---

## Day 4: Express.js Fundamentals

### Comparison: Node.js vs Express
| Feature        | Node.js       | Express.js       |
|---------------|---------------|------------------|
| Routing       | Manual        | Built-in         |
| Middleware    | Not included  | Supported        |
| Development   | More code     | Less code        |

### Basic Express App
```javascript
const express = require('express');
const app = express();

app.get('/', (req, res) => {
  res.send('Hello World!');
});

app.listen(3000);
```

---

## Day 5: Template Engines & JSON

### EJS Setup
1. Install: `npm i ejs`
2. Create `views/` folder
3. Render templates:
```javascript
res.render('home.ejs', { data: user });
```

### JSON Responses
```javascript
app.get('/api', (req, res) => {
  res.json({ id: 1, name: "John" });
});
```

---

## Day 6: EJS Deep Dive

### Template Syntax
```ejs
<% if (user.loggedIn) { %>
  <p>Welcome <%= user.name %></p>
<% } %>
```

### Passing Data
```javascript
// Server
res.render('profile', { user: userData });

// EJS
<h2><%= user.email %></h2>
```

---

## Day 7: Form Handling

### GET vs POST
| Aspect        | GET            | POST            |
|---------------|----------------|-----------------|
| Data Location | URL            | Request Body    |
| Security      | Less secure    | More secure     |
| Data Limits   | ~8MB           | Unlimited       |

### POST Handler
```javascript
app.post('/submit', (req, res) => {
  console.log(req.body);
  res.send('Form received!');
});
```

---

## Day 8: MongoDB Integration

### Connection Setup
```javascript
// db.js
mongoose.connect('mongodb://localhost:27017/company')
  .then(() => console.log('DB Connected!'))
  .catch(err => console.error(err));
```

### Schema Definition
```javascript
// models/user.js
const userSchema = new mongoose.Schema({
  username: String,
  useremail: { type: String, unique: true }
});

module.exports = mongoose.model('User', userSchema);
```

### HTTP Status Codes
| Code | Meaning               |
|------|-----------------------|
| 200  | OK                    |
| 201  | Created               |
| 400  | Bad Request           |
| 404  | Not Found             |
| 500  | Server Error          |

---

## Middleware Types
1. Built-in (`express.static()`)
2. Custom middleware
3. Third-party (`body-parser`)

### Essential Middleware
```javascript
app.use(express.json());
app.use(express.urlencoded({ extended: true }));
app.use(express.static('public'));
```
