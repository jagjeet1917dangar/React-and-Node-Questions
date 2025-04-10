### First we have to Create a new folder and run npm init -y.
### Then install Express by running npm install express in the terminal.
### Create a JavaScript file and add this code.

```
const express = require('express');
const app = express();
const PORT = 3000;

// Middleware to parse JSON bodies
app.use(express.json());

// In-memory users array
let users = [
  { id: 1, name: 'Alice', email: 'alice@example.com' }
];

// GET route to fetch users
app.get('/users', (req, res) => {
  res.json(users);
});

// POST route to add a new user
app.post('/users', (req, res) => {
  const newUser = req.body;
  users.push(newUser);
  res.status(201).json({ message: 'User added successfully', user: newUser });
});

app.listen(PORT, () => {
  console.log(`Server is running on http://localhost:${PORT}`);
});
```

### And then you have to run the node filename.js command to start the server.
### Use Postman to send a POST request to http://localhost:3000/users with JSON data like this.

```
{
  "id": 2,
  "name": "Bob",
  "email": "bob@example.com"
}
```