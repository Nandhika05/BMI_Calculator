# Ex06 BMI Calculator
## Date: 10-11-2025

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
## App.js
```
import React, { useState } from "react";
import "./App.css";

function App() {
  const [height, setHeight] = useState("");
  const [weight, setWeight] = useState("");
  const [bmi, setBMI] = useState(null);
  const [message, setMessage] = useState("");

  const calculateBMI = () => {
    if (height > 0 && weight > 0) {
      const heightInMeters = height / 100;
      const bmiValue = (weight / (heightInMeters * heightInMeters)).toFixed(2);
      setBMI(bmiValue);

      if (bmiValue < 18.5) setMessage("Underweight 😕");
      else if (bmiValue >= 18.5 && bmiValue < 24.9) setMessage("Normal weight ✅");
      else if (bmiValue >= 25 && bmiValue < 29.9) setMessage("Overweight ⚠️");
      else setMessage("Obese ❌");
    }
  };

  return (
    <div className="container">
      <h1>BMI Calculator</h1>

      <div className="input-group">
        <label>Height (cm)</label>
        <input
          type="number"
          value={height}
          onChange={(e) => setHeight(e.target.value)}
        />
      </div>

      <div className="input-group">
        <label>Weight (kg)</label>
        <input
          type="number"
          value={weight}
          onChange={(e) => setWeight(e.target.value)}
        />
      </div>

      <button onClick={calculateBMI}>Calculate</button>

      {bmi && (
        <div className="result">
          <h2>Your BMI: {bmi}</h2>
          <p>{message}</p>
        </div>
      )}
    </div>
  );
}

export default App;

```

## App.css
```
~body {
  font-family: Arial, sans-serif;
  background: #f0f0f5;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
}

.container {
  background: #fff;
  padding: 20px;
  width: 350px;
  border-radius: 10px;
  box-shadow: 0px 0px 10px rgba(0,0,0,0.15);
  text-align: center;
}

.input-group {
  margin: 15px 0;
  text-align: left;
}

input {
  width: 100%;
  padding: 8px;
  margin-top: 5px;
  border: 1px solid #999;
  border-radius: 5px;
}

button {
  width: 100%;
  padding: 10px;
  background: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
  margin-top: 10px;
}

button:hover {
  background: #0056b3;
}

.result {
  background: #e8f5e9;
  margin-top: 20px;
  padding: 10px;
  border-radius: 5px;
}

```
## OUTPUT

<img width="1365" height="690" alt="image" src="https://github.com/user-attachments/assets/0a1d98f2-3ebc-4b0c-8219-4c80b22b1a61" />


## RESULT
The program for creating BMI Calculator using React Router is executed successfully.
