<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Advanced Calculator</title>
    <style>
        body {
            background-color: #3498db;
            color: #fff;
            font-family: 'Arial', sans-serif;
            text-align: center;
            margin-top: 50px;
        }

        #calculator {
            width: 300px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f39c12;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
        }

        input {
            width: 45px;
            height: 45px;
            margin: 5px;
            font-size: 18px;
            color: #fff;
            background-color: #3498db;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        input.operator {
            background-color: #f39c12;
        }

        input.double {
            width: 95px;
        }

        input#display {
            width: 95%;
            margin: 10px auto;
            padding: 10px;
            font-size: 20px;
            text-align: right;
            border: none;
            border-radius: 5px;
        }
    </style>
</head>
<body>

    <div id="calculator">
        <input type="text" id="display" disabled>
        <br>
        <input type="button" value="7" onclick="addToDisplay('7')">
        <input type="button" value="8" onclick="addToDisplay('8')">
        <input type="button" value="9" onclick="addToDisplay('9')">
        <input type="button" value="/" class="operator" onclick="addToDisplay('/')">
        <br>
        <input type="button" value="4" onclick="addToDisplay('4')">
        <input type="button" value="5" onclick="addToDisplay('5')">
        <input type="button" value="6" onclick="addToDisplay('6')">
        <input type="button" value="-" class="operator" onclick="addToDisplay('-')">
        <br>
        <input type="button" value="1" onclick="addToDisplay('1')">
        <input type="button" value="2" onclick="addToDisplay('2')">
        <input type="button" value="3" onclick="addToDisplay('3')">
        <input type="button" value="+" class="operator" onclick="addToDisplay('+')">
        <br>
        <input type="button" value="0" onclick="addToDisplay('0')">
        <input type="button" value="." onclick="addToDisplay('.')">
        <input type="button" value="=" class="double" onclick="calculate()">
        <input type="button" value="C" class="double" onclick="clearDisplay()">
    </div>

    <script>
        function addToDisplay(value) {
            document.getElementById('display').value += value;
        }

        function calculate() {
            try {
                document.getElementById('display').value = eval(document.getElementById('display').value);
            } catch (error) {
                document.getElementById('display').value = 'Error';
            }
        }

        function clearDisplay() {
            document.getElementById('display').value = '';
        }
    </script>

</body>
</html>
