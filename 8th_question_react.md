### First, make sure you have a React project set up using Vite or Create React App.  
### Then create a new component file, for example, `Accordion.jsx`, and add the following code:

```jsx
import React, { useState } from 'react';

const data = [
  {
    question: 'What is React?',
    answer: 'React is a JavaScript library for building user interfaces.',
  },
  {
    question: 'What is useState?',
    answer: 'useState is a Hook that lets you add React state to function components.',
  },
  {
    question: 'What is JSX?',
    answer: 'JSX is a syntax extension for JavaScript that looks similar to HTML.',
  },
];

const Accordion = () => {
  const [activeIndex, setActiveIndex] = useState(null);

  const toggleAccordion = (index) => {
    setActiveIndex(activeIndex === index ? null : index);
  };

  return (
    <div>
      <h2>FAQ</h2>
      {data.map((item, index) => (
        <div key={index}>
          <h3
            onClick={() => toggleAccordion(index)}
            style={{ cursor: 'pointer' }}
          >
            {item.question}
          </h3>
          {activeIndex === index && <p>{item.answer}</p>}
        </div>
      ))}
    </div>
  );
};

export default Accordion;
```

### Then import and use the `Accordion` component inside your main `App.jsx` file:

```jsx
import React from 'react';
import Accordion from './Accordion';

function App() {
  return (
    <div>
      <h1>Accordion Example</h1>
      <Accordion />
    </div>
  );
}

export default App;
```

### Finally, run your React app using:

```bash
npm run dev
```

### You will see an FAQ-style accordion where clicking a question shows or hides its answer.
