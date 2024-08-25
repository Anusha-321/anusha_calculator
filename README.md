<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Anusha Calculator</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
            margin: 0;
            font-family: Arial, sans-serif;
        }

        .calculator {
            border: 2px solid #122a67;
            border-radius: 10px;
            padding: 20px;
            background-color: #fff;
            box-shadow: 0px 0px 15px rgba(0, 0, 0, 0.3);
            width: 300px;
        }

        #output {
            color: black;
            border-radius: 5px;
            width: 100%;
            height: 50px;
            background-color: #e6e6e6;
            border: solid black 1px;
            font-size: 24px;
            text-align: right;
            padding: 10px;
            box-sizing: border-box;
            margin-bottom: 10px;
        }

        .button-row {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
        }

        .btn_value {
            height: 60px;
            width: 60px;
            margin: 5px;
            outline: none;
            background-color: #122a67;
            color: white;
            border: solid black 1px;
            border-radius: 10px;
            font-size: 20px;
            cursor: pointer;
            transition: background-color 0.2s, box-shadow 0.2s;
        }

        .btn_value:hover {
            background-color: #1e3a8a;
        }

        .btn_value:active {
            background-color: #1a2a5f;
            box-shadow: inset 0px 0px 5px #c1c1c1;
        }

        .btn_value-wide {
            height: 60px;
            width: 130px;
            margin: 5px;
            background-color: #d9534f; 
            color: white;
            border-radius: 10px;
            font-size: 20px;
        }

        .btn_value-wide:hover {
            background-color: #c9302c;
        }

        .btn_value-wide:active {
            background-color: #a61c1c;
            box-shadow: inset 0px 0px 5px #c1c1c1;
        }
    </style>
</head>

<body>
    <div class="calculator">
        <input type="text" id="output" placeholder="Enter Number for calculation" readonly />
        <div class="button-row">
            <input type="button" value="Del" class="btn_value-wide" onclick="deleteLastCharacter()" />
            <input type="button" value="C" class="btn_value" onclick="inputClr()" />
        </div>
        <div class="button-row">
            <input type="button" class="btn_value" value="1" onclick="concatenateValue('1')" />
            <input type="button" class="btn_value" value="2" onclick="concatenateValue('2')" />
            <input type="button" class="btn_value" value="3" onclick="concatenateValue('3')" />
            <input type="button" class="btn_value" value="/" onclick="concatenateValue('/')" />
        </div>
        <div class="button-row">
            <input type="button" class="btn_value" value="4" onclick="concatenateValue('4')" />
            <input type="button" class="btn_value" value="5" onclick="concatenateValue('5')" />
            <input type="button" class="btn_value" value="6" onclick="concatenateValue('6')" />
            <input type="button" class="btn_value" value="-" onclick="concatenateValue('-')" />
        </div>
        <div class="button-row">
            <input type="button" class="btn_value" value="7" onclick="concatenateValue('7')" />
            <input type="button" class="btn_value" value="8" onclick="concatenateValue('8')" />
            <input type="button" class="btn_value" value="9" onclick="concatenateValue('9')" />
            <input type="button" class="btn_value" value="+" onclick="concatenateValue('+')" />
        </div>
        <div class="button-row">
            <input type="button" class="btn_value" value="0" onclick="concatenateValue('0')" />
            <input type="button" class="btn_value" value="." onclick="concatenateValue('.')" />
            <input type="button" class="btn_value" value="*" onclick="concatenateValue('*')" />
            <input type="button" class="btn_value" value="=" onclick="performCalculation()" />
        </div>
    </div>

    <script>
        function concatenateValue(value) {
            document.getElementById("output").value += value;
        }

        function performCalculation() {
            try {
                let expression = document.getElementById("output").value;
                let result = eval(expression);
                document.getElementById("output").value = result;
            } catch (err) {
                document.getElementById("output").value = 'Error';
            }
        }

        function inputClr() {
            document.getElementById("output").value = "";
        }

        function deleteLastCharacter() {
            let currentValue = document.getElementById("output").value;
            document.getElementById("output").value = currentValue.slice(0, -1);
        }
    </script>
</body>

</html>
