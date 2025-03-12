<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Attendance Calculator</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f4f4f4;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            color: #333;
        }

        .calculator {
            background-color: #fff;
            border-radius: 12px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
            padding: 40px;
            width: 400px;
            text-align: center;
        }

        h1 {
            color: #007bff;
            margin-bottom: 30px;
            font-size: 28px;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.1);
        }

        .input-group {
            margin-bottom: 25px;
            text-align: left;
        }

        label {
            display: block;
            margin-bottom: 8px;
            color: #555;
            font-weight: 600;
        }

        input[type="number"] {
            width: calc(100% - 22px);
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            transition: border-color 0.3s ease;
        }

        input[type="number"]:focus {
            border-color: #007bff;
            outline: none;
            box-shadow: 0 0 8px rgba(0, 123, 255, 0.2);
        }

        button {
            background-color: #007bff;
            color: white;
            padding: 12px 25px;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        button:hover {
            background-color: #0056b3;
        }

        #result {
            margin-top: 30px;
            font-size: 18px;
            font-weight: 600;
            color: #4CAF50;
            padding: 15px;
            background-color: #e8f5e9;
            border-radius: 8px;
            box-shadow: inset 0 2px 4px rgba(0, 0, 0, 0.1);
        }

        .info {
            margin-top: 20px;
            font-size: 12px;
            color: #777;
        }
    </style>
</head>

<body>
    <div class="calculator">
        <h1>Attendance Calculator</h1>
        <div class="input-group">
            <label for="attended">Classes Attended:</label>
            <input type="number" id="attended" placeholder="Enter attended classes">
        </div>
        <div class="input-group">
            <label for="total">Total Classes:</label>
            <input type="number" id="total" placeholder="Enter total classes">
        </div>
        <button onclick="calculateAttendance()">Calculate</button>
        <div id="result"></div>
        <div class="info">This calculator displays the percentage of classes you have attended.</div>
    </div>

    <script>
        function calculateAttendance() {
            const attended = parseFloat(document.getElementById("attended").value);
            const total = parseFloat(document.getElementById("total").value);

            if (isNaN(attended) || isNaN(total) || total === 0) {
                document.getElementById("result").textContent = "Please enter valid numbers.";
                return;
            }

            const percentage = (attended / total) * 100;
            document.getElementById("result").textContent = `Attendance: ${percentage.toFixed(2)}%`;
        }
    </script>
</body>

</html>
