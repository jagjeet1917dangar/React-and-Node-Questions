### First, make sure you have a React project set up using Vite or Create React App.  
### Then create a new component file, for example, `TodoList.jsx`, and add the following code:

```jsx
import React, { useState } from 'react';

const TodoList = () => {
  const [task, setTask] = useState('');
  const [todos, setTodos] = useState([]);

  const handleAdd = () => {
    if (task.trim() !== '') {
      setTodos([...todos, task]);
      setTask('');
    }
  };

  const handleDelete = (index) => {
    const updatedTodos = todos.filter((_, i) => i !== index);
    setTodos(updatedTodos);
  };

  return (
    <div>
      <h2>Todo List</h2>
      <input
        type="text"
        value={task}
        onChange={(e) => setTask(e.target.value)}
        placeholder="Enter a task"
      />
      <button onClick={handleAdd}>Add</button>

      <ul>
        {todos.map((todo, index) => (
          <li key={index}>
            {todo}
            <button onClick={() => handleDelete(index)}>Delete</button>
          </li>
        ))}
      </ul>
    </div>
  );
};

export default TodoList;
```

### Then import and use the `TodoList` component inside your main `App.jsx` file:

```jsx
import React from 'react';
import TodoList from './TodoList';

function App() {
  return (
    <div>
      <h1>React Todo App</h1>
      <TodoList />
    </div>
  );
}

export default App;
```

### Finally, run your React app using:

```bash
npm run dev
```

### You will see a simple todo list UI with an input field, Add button, and Delete option for each task.
