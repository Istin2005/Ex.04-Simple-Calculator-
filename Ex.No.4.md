# Ex04 Simple Calculator - React Project
## Date:12-10-2025

## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM

## calculator.js

```
// src/Calculator.js
import React, { useState } from 'react';
import './Calculator.css';

function Calculator() {
  const [input, setInput] = useState('');

  const handleClick = (value) => {
    if (value === '=') {
      try {
        setInput(eval(input).toString());
      } catch {
        setInput('Error');
      }
    } else if (value === 'C') {
      setInput('');
    } else {
      setInput(input + value);
    }
  };

  const buttons = [
    '7', '8', '9', '/', 
    '4', '5', '6', '*', 
    '1', '2', '3', '-', 
    '0', '.', 'C', '+', '='
  ];

  return (
    <div className="calculator">
      <input type="text" value={input} readOnly />
      <div className="buttons">
        {buttons.map((btn, index) => (
          <button key={index} onClick={() => handleClick(btn)}>
            {btn}
          </button>
        ))}
      </div>
    </div>
  );
}

export default Calculator;

```

## calculator css

```
/* src/Calculator.css */
.calculator {
  width: 250px;
  margin: 100px auto;
  padding: 20px;
  background: #f3f3f3;
  border-radius: 12px;
  box-shadow: 0 0 10px rgba(0,0,0,0.1);
  text-align: center;
}

input {
  width: 100%;
  height: 50px;
  font-size: 20px;
  text-align: right;
  margin-bottom: 10px;
  border: none;
  border-radius: 8px;
  padding: 10px;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

button {
  padding: 15px;
  font-size: 18px;
  border: none;
  border-radius: 8px;
  background: #4caf50;
  color: white;
  cursor: pointer;
  transition: 0.3s;
}

button:hover {
  background: #45a049;
}

button:nth-child(16) {
  background: #2196f3;
}

button:nth-child(16):hover {
  background: #0b7dda;
}

```

## app js
```
// src/App.js
import React from 'react';
import Calculator from './Calculator';

function App() {
  return (
    <div>
      <h1 style={{ textAlign: 'center', color: '#333' }}>Simple Calculator</h1>
      <Calculator />
    </div>
  );
}

export default App;

```


## OUTPUT
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a9a269cb-d7b1-4106-85b5-b546fa23cfec" />


## RESULT
The program for developing a simple calculator in React.js is executed successfully.
