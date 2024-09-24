---
layout: page
title: Calculator
description: Calculator
permalink: /calc/
---
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Stylish Calculator</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
            background-color: #f7e7f0;
            margin: 0;
        }
        #calculator {
            background-color: #ffffff;
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            padding: 20px;
            width: 300px;
        }
        input {
            width: 100%;
            height: 50px;
            font-size: 24px;
            padding: 10px;
            border-radius: 5px;
            border: 1px solid #ccc;
            margin-bottom: 10px;
            text-align: right;
        }
        button {
            width: 23%;
            height: 50px;
            font-size: 20px;
            margin: 5px 1%;
            border-radius: 5px;
            border: none;
            background-color: #6a5acd;
            color: white;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        button:hover {
            background-color: #483d8b;
        }
        button:active {
            background-color: #3b3b8c;
        }
        .clear {
            background-color: #ff1493;
        }
        .clear:hover {
            background-color: #db007a;
        }
        .equal {
            background-color: #28a745;
        }
        .equal:hover {
            background-color: #218838;
        }
    </style>
</head>
<body>

<div id="calculator">
    <input type="text" id="result" disabled>
    <div>
        <button class="clear" onclick="clearResult()">C</button>
        <button onclick="appendToResult('7')">7</button>
        <button onclick="appendToResult('8')">8</button>
        <button onclick="appendToResult('9')">9</button>
        <button onclick="appendToResult('/')">/</button>
    </div>
    <div>
        <button onclick="appendToResult('4')">4</button>
        <button onclick="appendToResult('5')">5</button>
        <button onclick="appendToResult('6')">6</button>
        <button onclick="appendToResult('*')">*</button>
    </div>
    <div>
        <button onclick="appendToResult('1')">1</button>
        <button onclick="appendToResult('2')">2</button>
        <button onclick="appendToResult('3')">3</button>
        <button onclick="appendToResult('-')">-</button>
    </div>
    <div>
        <button onclick="appendToResult('0')">0</button>
        <button class="equal" onclick="calculateResult()">=</button>
        <button onclick="appendToResult('+')">+</button>
    </div>
</div>

<script>
    function appendToResult(value) {
        document.getElementById('result').value += value;
    }

    function clearResult() {
        document.getElementById('result').value = '';
    }

    function calculateResult() {
        try {
            const result = eval(document.getElementById('result').value);
            document.getElementById('result').value = result;
        } catch (e) {
            document.getElementById('result').value = 'Error';
        }
    }
</script>

</body>
</html>
