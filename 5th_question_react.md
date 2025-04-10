### First, make sure you have a React project set up using Vite or Create React App.  
### Then create a new component file, for example, `LiveSearch.jsx`, and add the following code:

```jsx
import React, { useState } from 'react';

const LiveSearch = () => {
  const [query, setQuery] = useState('');

  const names = ['Alice', 'Bob', 'Charlie', 'David', 'Eve', 'Frank'];

  const filteredNames = names.filter((name) =>
    name.toLowerCase().includes(query.toLowerCase())
  );

  return (
    <div>
      <h2>Live Search</h2>
      <input
        type="text"
        placeholder="Search names..."
        value={query}
        onChange={(e) => setQuery(e.target.value)}
      />
      <ul>
        {filteredNames.map((name, index) => (
          <li key={index}>{name}</li>
        ))}
      </ul>
    </div>
  );
};

export default LiveSearch;
```

### Then import and use the `LiveSearch` component inside your main `App.jsx` file:

```jsx
import React from 'react';
import LiveSearch from './LiveSearch';

function App() {
  return (
    <div>
      <h1>Live Search Example</h1>
      <LiveSearch />
    </div>
  );
}

export default App;
```

### Finally, run your React app using:

```bash
npm run dev
```

### You will see a search input field that filters the names list as you type.
