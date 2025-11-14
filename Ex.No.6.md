# Ex06 BMI Calculator
## Date: 12-11-2025

## AIM
To create a BMI calculator using React Router 

## ALGORITHM
### STEP 1 State Initialization
Manage the current page (Home or Calculator) using React Router.

### STEP 2 User Input
Accept weight and height inputs from the user.

### STEP 3 BMI Calculation
Calculate the BMI based on user input.

### STEP 4 Categorization
Classify the BMI result into categories (Underweight, Normal weight, Overweight, Obesity).

### STEP 5 Navigation
Navigate between pages using React Router.

## PROGRAM
App.jsx
```
import React, { useState } from "react";
import "./App.css";

function App() {
  const [weight, setWeight] = useState("");
  const [height, setHeight] = useState("");
  const [bmi, setBmi] = useState(null);
  const [category, setCategory] = useState("");

  const calculateBMI = () => {
    if (!weight || !height) {
      alert("Please enter both weight and height!");
      return;
    }

    const heightInMeters = height / 100;
    const result = (weight / (heightInMeters * heightInMeters)).toFixed(2);
    setBmi(result);

    if (result < 18.5) setCategory("Underweight");
    else if (result >= 18.5 && result < 24.9) setCategory("Normal weight");
    else if (result >= 25 && result < 29.9) setCategory("Overweight");
    else setCategory("Obesity");
  };

  const resetForm = () => {
    setWeight("");
    setHeight("");
    setBmi(null);
    setCategory("");
  };

  return (
    <div className="container">
      <h1>BMI Calculator</h1>
      <p>
        Enter your weight and height below to calculate your Body Mass Index (BMI)
      </p>

      <div className="input-group">
        <label>Weight (kg):</label>
        <input
          type="number"
          value={weight}
          onChange={(e) => setWeight(e.target.value)}
          placeholder="Enter weight"
        />
      </div>

      <div className="input-group">
        <label>Height (cm):</label>
        <input
          type="number"
          value={height}
          onChange={(e) => setHeight(e.target.value)}
          placeholder="Enter height"
        />
      </div>

      <div className="button-group">
        <button onClick={calculateBMI}>Calculate</button>
        <button onClick={resetForm} className="reset">Reset</button>
      </div>

      {bmi && (
        <div className="result">
          <h3>Your BMI: {bmi}</h3>
          <h4>Category: {category}</h4>
        </div>
      )}
    </div>
  );
}

export default App;

```
App.css
```
body {
  font-family: Arial, sans-serif;
  background: #f2f4f7;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.container {
  background: white;
  padding: 40px;
  border-radius: 12px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  text-align: center;
  width: 350px;
}

h1 {
  color: #333;
}

p {
  font-size: 14px;
  color: #666;
  margin-bottom: 20px;
}

.input-group {
  margin: 15px 0;
  text-align: left;
}

.input-group label {
  font-weight: bold;
  display: block;
  margin-bottom: 5px;
  color: #333;
}

.input-group input {
  width: 100%;
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 6px;
  font-size: 14px;
}

.button-group {
  margin-top: 20px;
}

button {
  background: #4caf50;
  color: white;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 6px;
  cursor: pointer;
  font-size: 15px;
}

button:hover {
  background: #45a049;
}

button.reset {
  background: #f44336;
}

button.reset:hover {
  background: #d73226;
}

.result {
  margin-top: 20px;
  background: #e8f5e9;
  padding: 15px;
  border-radius: 8px;
}

.result h3,
.result h4 {
  margin: 5px 0;
  color: #333;
}

```


## OUTPUT

<img width="967" height="525" alt="Screenshot 2025-11-14 155114" src="https://github.com/user-attachments/assets/434d3509-1ec2-4766-94cf-f9c561a22ff7" />



## RESULT
The program for creating BMI Calculator using React Router is executed successfully.
