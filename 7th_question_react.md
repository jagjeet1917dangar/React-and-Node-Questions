### First, make sure you have a React project set up using Vite or Create React App.  
### Then create a new component file, for example, `LoginForm.jsx`, and add the following code:

```jsx
import React, { useState } from 'react';

const LoginForm = () => {
  const [email, setEmail] = useState('');
  const [password, setPassword] = useState('');
  const [error, setError] = useState('');

  const handleSubmit = (e) => {
    e.preventDefault();

    if (!email || !password) {
      setError('Both fields are required.');
    } else {
      setError('');
      console.log('Form submitted:', { email, password });
    }
  };

  return (
    <div>
      <h2>Login Form</h2>
      <form onSubmit={handleSubmit}>
        <input
          type="email"
          placeholder="Email"
          value={email}
          onChange={(e) => setEmail(e.target.value)}
        />
        <br />
        <input
          type="password"
          placeholder="Password"
          value={password}
          onChange={(e) => setPassword(e.target.value)}
        />
        <br />
        <button type="submit">Login</button>
        {error && <p style={{ color: 'red' }}>{error}</p>}
      </form>
    </div>
  );
};

export default LoginForm;
```

### Then import and use the `LoginForm` component inside your main `App.jsx` file:

```jsx
import React from 'react';
import LoginForm from './LoginForm';

function App() {
  return (
    <div>
      <h1>Simple Login Validation</h1>
      <LoginForm />
    </div>
  );
}

export default App;
```

### Finally, run your React app using:

```bash
npm run dev
```

### You will see a login form that validates the email and password fields before submission.
