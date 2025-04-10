### First, make sure you have a React project set up using Vite or Create React App.  
### Then create a new component file, for example, `Counter.jsx`, and add the following code:

```jsx
import React, { useState } from 'react';

const Counter = () => {
  const [count, setCount] = useState(0);

  const increment = () => setCount(count + 1);
  const decrement = () => setCount(count - 1);
  const reset = () => setCount(0);

  return (
    <div>
      <h2>Count: {count}</h2>
      <button onClick={increment}>Increment</button>
      <button onClick={decrement}>Decrement</button>
      <button onClick={reset}>Reset</button>
    </div>
  );
};

export default Counter;
```

### Then import and use the `Counter` component inside your main `App.jsx` file:

```jsx
import React from 'react';
import Counter from './Counter';

function App() {
  return (
    <div>
      <h1>React Counter App</h1>
      <Counter />
    </div>
  );
}

export default App;
```

### Finally, run your React app using:

```bash
npm run dev
```

### You will see a simple counter UI with Increment, Decrement, and Reset buttons.
