<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fuel Cost Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        #calculator {
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            padding: 20px;
            text-align: center;
        }
        button {
            padding: 10px 20px;
            margin-top: 10px;
            background-color: #4caf50;
            color: #fff;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div id="calculator">
        <h2>Fuel Cost Calculator</h2>
        <label for="mileage">Mileage (km/l):</label>
        <input type="number" id="mileage" step="any" required><br>

        <label for="fuelPrice">Fuel Price (INR/l):</label>
        <input type="number" id="fuelPrice" step="any" required><br>

        <label for="distance">Distance (km):</label>
        <input type="number" id="distance" step="any" required><br>

        <button onclick="calculateCost()">Calculate Cost</button>

        <h3 id="result"></h3>
    </div>

    <script>
        function calculateCost() {
            var mileage = document.getElementById('mileage').value;
            var fuelPrice = document.getElementById('fuelPrice').value;
            var distance = document.getElementById('distance').value;

            if (mileage && fuelPrice && distance) {
                var cost = (distance / mileage) * fuelPrice;
                document.getElementById('result').innerHTML = 'Cost of petrol: ' + cost.toFixed(2) + ' INR';
            } else {
                document.getElementById('result').innerHTML = 'Please fill in all fields.';
            }
        }
    </script>
</body>
</html>
