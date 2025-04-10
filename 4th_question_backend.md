### First we have to Create a new folder and run `npm init -y`.  
### Then install Express by running `npm install express` in the terminal.  
### Create a JavaScript file and add this code:

```js
const express = require('express');
const app = express();
const PORT = 3000;

app.use(express.json());

let users = [
  { id: 1, name: 'Alice', email: 'alice@example.com' },
  { id: 2, name: 'Bob', email: 'bob@example.com' },
  { id: 3, name: 'Charlie', email: 'charlie@example.com' }
];

app.get('/users', (req, res) => {
  res.json(users);
});

app.get('/users/:id', (req, res) => {
  const userId = parseInt(req.params.id);
  const user = users.find(u => u.id === userId);

  if (user) {
    res.json(user);
  } else {
    res.status(404).json({ message: 'User not found' });
  }
});

app.listen(PORT, () => {
  console.log(`Server is running on http://localhost:${PORT}`);
});
```

### And then you have to run the `node filename.js` command to start the server.

### After that, open your browser or Postman and go to `http://localhost:3000/users/2`

### If the user with that ID exists, it will return the user data; otherwise, it will return:

```json
{
  "message": "User not found"
}
