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

app.delete('/users/:id', (req, res) => {
  const userId = parseInt(req.params.id);
  const initialLength = users.length;
  users = users.filter(u => u.id !== userId);

  if (users.length < initialLength) {
    res.status(204).send();
  } else {
    res.status(404).json({ message: 'User not found' });
  }
});

app.listen(PORT, () => {
  console.log(`Server is running on http://localhost:${PORT}`);
});
```

### And then you have to run the `node filename.js` command to start the server.

### Use Postman to send a DELETE request to `http://localhost:3000/users/2`

### If the user is successfully deleted, the response will have:

**Status Code:** `204 No Content` (no body)

### If the user is not found, it will return:

```json
{
  "message": "User not found"
}
```
