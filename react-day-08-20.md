🗓️ Day 8 - React Notes
✅ 1. Importing Bootstrap in React (Vite) App
Bootstrap can be added to a Vite-powered React app in a few simple steps:

📌 Step-by-step:
Install Bootstrap via npm

npm install bootstrap
Import Bootstrap in main.jsx


import 'bootstrap/dist/css/bootstrap.min.css';
(Optional) If using Bootstrap’s JS components


import 'bootstrap/dist/js/bootstrap.bundle.min.js';
Now you can use Bootstrap classes like btn btn-primary, container, card, etc., in your JSX.

📝 Example:
jsx
Copy
Edit
<button className="btn btn-success">Click Me</button>
✅ 2. .map() Method in React
📌 Purpose:
Used to render lists dynamically in React.

🔧 Syntax:
jsx
Copy
Edit
array.map((item, index) => {
  return (
    <Element key={index}>{item.property}</Element>
  );
});
📝 Example:
jsx
Copy
Edit
const names = ['Abhay', 'Nandini', 'Priya'];

function NameList() {
  return (
    <ul>
      {names.map((name, index) => (
        <li key={index}>{name}</li>
      ))}
    </ul>
  );
}
⚠️ Important:
Always use key prop with unique value to avoid rendering issues.

map() does not change the original array, it returns a new one.⚜️⚜️
