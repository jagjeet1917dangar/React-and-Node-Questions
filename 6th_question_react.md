### First, make sure you have a React project set up using Vite or Create React App.  
### Then create a new component file, for example, `UserList.jsx`, and add the following code:

```jsx
import React, { useEffect, useState } from 'react';

const UserList = () => {
  const [users, setUsers] = useState([]);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    fetch('https://jsonplaceholder.typicode.com/users')
      .then((response) => {
        if (!response.ok) {
          throw new Error('Failed to fetch users');
        }
        return response.json();
      })
      .then((data) => {
        setUsers(data);
        setLoading(false);
      })
      .catch((err) => {
        setError(err.message);
        setLoading(false);
      });
  }, []);

  if (loading) {
    return <p>Loading users...</p>;
  }

  if (error) {
    return <p>Error: {error}</p>;
  }

  return (
    <div>
      <h2>User List</h2>
      <ul>
        {users.map((user) => (
          <li key={user.id}>
            {user.name} ({user.email})
          </li>
        ))}
      </ul>
    </div>
  );
};

export default UserList;
```

### Then import and use the `UserList` component inside your main `App.jsx` file:

```jsx
import React from 'react';
import UserList from './UserList';

function App() {
  return (
    <div>
      <h1>Users from API</h1>
      <UserList />
    </div>
  );
}

export default App;
```

### Finally, run your React app using:

```bash
npm run dev
```

### You will see a list of users fetched from the API, or a loading/error message depending on the state.
