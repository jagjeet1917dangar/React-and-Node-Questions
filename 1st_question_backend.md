### First we have t0 Create a new folder and run npm init -y.
### And then we have to run command npm install express in the terminal.
### Create a javascript file and add this code.

``` 
const express = require('express');
const app = express();
const PORT = 3000;

app.get('/', (req, res) => {
  res.send('Server is running');
});

app.listen(PORT, () => {
  console.log(`Server is running on http://localhost:${PORT}`);
});
```
### And then you have to run the node filename.js command to run the server.
