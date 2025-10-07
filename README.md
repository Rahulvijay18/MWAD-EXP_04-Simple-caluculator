# MWAD-EXP_04-Simple-caluculator

## Nmae: RAHUL VIJAY V
## Reg No: 212223040164

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

### SimpleCalculator.jsx

```
import React, { useState } from "react";
import "./Calculator.css";

export default function SimpleCalculator() {
  const [input, setInput] = useState("");

  const handleClick = (value) => {
    setInput(input + value);
  };

  const handleClear = () => {
    setInput("");
  };

  const handleBackspace = () => {
    setInput(input.slice(0, -1));
  };

  const handleCalculate = () => {
    try {
      const expression = input.replace(/×/g, "*").replace(/÷/g, "/");
      const result = eval(expression);
      setInput(result.toString());
    } catch {
      setInput("Error");
    }
  };

  return (
    <div className="calculator-container">
      <h2 className="title">Simple Calculator</h2>
      <input type="text" value={input} readOnly className="display" />

      <div className="button-grid">
        {[7, 8, 9, "÷", 4, 5, 6, "×", 1, 2, 3, "-", 0, ".", "=", "+"].map((btn) => (
          <button
            key={btn}
            onClick={() => {
              if (btn === "=") handleCalculate();
              else handleClick(btn.toString());
            }}
            className={btn === "=" ? "button equal" : "button"}
          >
            {btn}
          </button>
        ))}

        <button onClick={handleBackspace} className="button span-two">
          ⌫
        </button>
        <button onClick={handleClear} className="button span-two clear">
          C
        </button>
      </div>
    </div>
  );
}

```

### Calculator.css

```
html, body {
  margin: 0;
  padding: 0;
  width: 100vw;
  height: 100vh;
  background-color: #4f7ccf;
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: Arial, sans-serif;
  overflow: hidden;
}

#root {
  width: 100vw;
  height: 100vh;
  background-color: #4f7ccf;
  display: flex;
  justify-content: center;
  align-items: center;
}

.calculator-container {
  background-color: #a4cff2;
  padding: 20px;
  border-radius: 10px;
  width: 300px;
  max-width: 90vw;
  box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
}

.title {
  text-align: center;
  margin-bottom: 10px;
  color: #333;
}

.display {
  width: 100%;
  height: 40px;
  font-size: 20px;
  text-align: right;
  padding: 5px 10px;
  margin-bottom: 10px;
  border: 2px solid #ccc;
  border-radius: 5px;
  box-sizing: border-box;
  background-color: #fff;
  color: #000;
}

.button-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

.button {
  height: 50px;
  font-size: 18px;
  border: none;
  border-radius: 8px;
  background-color: #ffffff;
  color: #000;
  cursor: pointer;
  font-weight: bold;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
  transition: background-color 0.2s;
}

.button:hover {
  background-color: #e0e0e0;
}

.equal {
  background-color: #4da6ff;
  color: white;
}

.equal:hover {
  background-color: #3399ff;
}

.clear {
  background-color: #ff6b6b;
  color: white;
}

.clear:hover {
  background-color: #ff4c4c;
}

.span-two {
  grid-column: span 2;
}

```

### App.jsx

```
import React from "react";
import SimpleCalculator from "./SimpleCalculator";

function App() {
  return <SimpleCalculator />;
}

export default App;

```
## OUTPUT

<img width="1919" height="907" alt="Screenshot 2025-10-08 005532" src="https://github.com/user-attachments/assets/2f7d395f-9d8a-46da-9f0d-541a6c7aba29" />
<img width="1919" height="895" alt="Screenshot 2025-10-08 005548" src="https://github.com/user-attachments/assets/f143ca03-3b68-47f4-b946-04df3deaa702" />
<img width="1919" height="903" alt="Screenshot 2025-10-08 005629" src="https://github.com/user-attachments/assets/a0b7d48a-59a5-41d6-abe8-0c6021e82dab" />



## RESULT
The program for developing a simple calculator in React.js is executed successfully.
