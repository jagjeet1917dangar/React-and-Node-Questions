### First we have to Create a new folder and run npm init -y.
### Then install Express by running npm install express in the terminal.
### Create a JavaScript file and add this code.

```
const express = require('express');
const app = express();
const PORT = 3000;

const users = [
  { id: 1, name: 'Alice', email: 'alice@example.com' },
  { id: 2, name: 'Bob', email: 'bob@example.com' },
  { id: 3, name: 'Charlie', email: 'charlie@example.com' }
];

app.get('/users', (req, res) => {
  res.json(users);
});

app.listen(PORT, () => {
  console.log(`Server is running on http://localhost:${PORT}`);
});
```

### And then you have to run the node filename.js command to start the server.