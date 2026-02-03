<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Haider Ali Calculator</title>

<style>
    body {
        margin: 0;
        padding: 0;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        background: linear-gradient(135deg, #667eea, #764ba2);
        font-family: Arial, sans-serif;
    }

    .calculator {
        background: #1e1e2f;
        padding: 20px;
        border-radius: 15px;
        box-shadow: 0 20px 40px rgba(0,0,0,0.4);
        width: 320px;
    }

    .title {
        text-align: center;
        color: #00ffcc;
        font-size: 22px;
        margin-bottom: 10px;
        font-weight: bold;
    }

    .display {
        width: 100%;
        height: 60px;
        background: #000;
        color: #00ffcc;
        font-size: 28px;
        text-align: right;
        padding: 10px;
        box-sizing: border-box;
        border-radius: 10px;
        margin-bottom: 15px;
        overflow: hidden;
    }

    .buttons {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 10px;
    }

    button {
        height: 60px;
        font-size: 20px;
        border: none;
        border-radius: 10px;
        cursor: pointer;
        transition: transform 0.1s, box-shadow 0.1s;
    }

    button:active {
        transform: scale(0.95);
        box-shadow: inset 0 0 10px rgba(0,0,0,0.5);
    }

    .number {
        background: #2d2d44;
        color: #fff;
    }

    .operator {
        background: #ff8c00;
        color: #fff;
    }

    .equal {
        background: #00c853;
        color: #fff;
        grid-column: span 2;
    }

    .clear {
        background: #e53935;
        color: #fff;
    }

    .zero {
        grid-column: span 2;
    }

    footer {
        margin-top: 20px;
        color: #fff;
        font-size: 14px;
        opacity: 0.85;
    }
</style>
</head>

<body>

<div class="calculator">
    <div class="title">Project-Calculator</div><br/>
    

    <div id="display" class="display">0</div>

    <div class="buttons">
        <button class="clear" onclick="clearDisplay()">C</button>
        <button class="operator" onclick="appendValue('/')">÷</button>
        <button class="operator" onclick="appendValue('*')">×</button>
        <button class="operator" onclick="appendValue('-')">−</button>

        <button class="number" onclick="appendValue('7')">7</button>
        <button class="number" onclick="appendValue('8')">8</button>
        <button class="number" onclick="appendValue('9')">9</button>
        <button class="operator" onclick="appendValue('+')">+</button>

        <button class="number" onclick="appendValue('4')">4</button>
        <button class="number" onclick="appendValue('5')">5</button>
        <button class="number" onclick="appendValue('6')">6</button>
        <button class="number" onclick="appendValue('.')">.</button>

        <button class="number" onclick="appendValue('1')">1</button>
        <button class="number" onclick="appendValue('2')">2</button>
        <button class="number" onclick="appendValue('3')">3</button>
        <button class="equal" onclick="calculate()">=</button>

        <button class="number zero" onclick="appendValue('0')">0</button>
    </div>
</div>

<footer>
    © 2023 Haider Ali. All Rights Reserved.
</footer>

<script>
    let display = document.getElementById("display");

    function appendValue(value) {
        if (display.innerText === "0") {
            display.innerText = value;
        } else {
            display.innerText += value;
        }
    }

    function clearDisplay() {
        display.innerText = "0";
    }

    function calculate() {
        try {
            display.innerText = eval(display.innerText);
        } catch {
            display.innerText = "Error";
        }
    }
</script>

</body>
</html>
