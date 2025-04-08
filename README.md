# SmartTripBudget
/SmartTripBudget
  ├── index.html
  ├── style.css
  ├── script.js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Travel Budget Calculator</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Travel Budget Calculator</h1>
    <form id="calculator">
        <label for="income">Yearly Income ($):</label>
        <input type="number" id="income" name="income" required><br><br>

        <label for="family-size">Family Size:</label>
        <input type="number" id="family-size" name="family-size" required><br><br>

        <label for="travel-style">Travel Style:</label>
        <select id="travel-style" name="travel-style">
            <option value="budget">Budget</option>
            <option value="luxury">Luxury</option>
            <option value="adventure">Adventure</option>
        </select><br><br>

        <button type="button" onclick="calculate()">Calculate</button>
    </form>
    <h2>Results:</h2>
    <p id="results">Enter your details to see the results.</p>
    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 20px;
    background-color: #f4f4f4;
}

h1 {
    color: #333;
}

form {
    background: #fff;
    padding: 15px;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
}

label {
    display: block;
    margin: 10px 0 5px;
}

input, select, button {
    width: 100%;
    padding: 10px;
    margin-bottom: 15px;
}

button {
    background-color: #007BFF;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}
function calculate() {
    const income = document.getElementById('income').value;
    const familySize = document.getElementById('family-size').value;
    const travelStyle = document.getElementById('travel-style').value;

    // Example calculations
    let budgetPercentage = travelStyle === 'budget' ? 0.2 : travelStyle === 'luxury' ? 0.5 : 0.3;
    let yearlyTravelBudget = income * budgetPercentage;
    let costPerTrip = yearlyTravelBudget / 3; // Assume 3 trips per year as a baseline.

    // Display results
    document.getElementById('results').innerText = 
        `Yearly Travel Budget: $${yearlyTravelBudget.toFixed(2)}\nCost per Trip: $${costPerTrip.toFixed(2)}\nYou can afford approximately ${Math.floor(income / costPerTrip)} trips per year.`;
}
