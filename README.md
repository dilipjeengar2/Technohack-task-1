# Technohack-task-1
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator program</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f4f4f4;
        }

        #calculator {
            width: 300px;
            border: 1px solid #ccc;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            background-color: #fff;
        }

        input {
            width: calc(100% - 10px);
            padding: 15px;
            box-sizing: border-box;
            font-size: 18px;
            border: none;
            outline: none;
            text-align: right;
        }

        button {
            width: 23.5%;
            padding: 15px;
            box-sizing: border-box;
            font-size: 18px;
            cursor: pointer;
            border: none;
            outline: none;
            background-color: #f2f2f2;
        }

        button:hover {
            background-color: #ddd;
        }

        button.operator {
            background-color: #4CAF50;
            color: white;
        }

        button.operator:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <div id="calculator">
        <input type="text" id="display" readonly>
        <button onclick="appendToDisplay('7')">7</button>
        <button onclick="appendToDisplay('8')">8</button>
        <button onclick="appendToDisplay('9')">9</button>
        <button class="operator" onclick="appendToDisplay('/')">/</button>
        
        <button onclick="appendToDisplay('4')">4</button>
        <button onclick="appendToDisplay('5')">5</button>
        <button onclick="appendToDisplay('6')">6</button>
        <button class="operator" onclick="appendToDisplay('*')">*</button>
        
        <button onclick="appendToDisplay('1')">1</button>
        <button onclick="appendToDisplay('2')">2</button>
        <button onclick="appendToDisplay('3')">3</button>
        <button class="operator" onclick="appendToDisplay('-')">-</button>
        
        <button onclick="appendToDisplay('0')">0</button>
        <button onclick="clearDisplay()">C</button>
        <button class="operator" onclick="calculate()">=</button>
        <button class="operator" onclick="appendToDisplay('+')">+</button>
        
        <button class="operator" onclick="calculatePercentage()">%</button>
    </div>

    <script>
        function appendToDisplay(value) {
            document.getElementById('display').value += value;
        }

        function clearDisplay() {
            document.getElementById('display').value = '';
        }

        function calculate() {
            try {
                document.getElementById('display').value = eval(document.getElementById('display').value);
            } catch (error) {
                document.getElementById('display').value = 'Error';
            }
        }

        function calculatePercentage() {
            try {
                document.getElementById('display').value = eval(document.getElementById('display').value) / 100;
            } catch (error) {
                document.getElementById('display').value = 'Error';
            }
        }
    </script>
</body>
</html>
