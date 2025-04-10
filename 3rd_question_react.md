### First, make sure you have a React project set up using Vite or Create React App.  
### Then create a new component file, for example, `ToggleText.jsx`, and add the following code:

```jsx
import React, { useState } from 'react';

const ToggleText = () => {
  const [show, setShow] = useState(true);

  const toggleText = () => {
    setShow(!show);
  };

  return (
    <div>
      <button onClick={toggleText}>
        {show ? 'Hide' : 'Show'}
      </button>
      {show && <p>Hello World</p>}
    </div>
  );
};

export default ToggleText;
```

### Then import and use the `ToggleText` component inside your main `App.jsx` file:

```jsx
import React from 'react';
import ToggleText from './ToggleText';

function App() {
  return (
    <div>
      <h1>Toggle Example</h1>
      <ToggleText />
    </div>
  );
}

export default App;
```

### Finally, run your React app using:

```bash
npm run dev
```

### You will see a Show/Hide button that toggles the visibility of the text "Hello World".
