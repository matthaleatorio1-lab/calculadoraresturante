<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Calculadora Archavon</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      background: radial-gradient(circle at top, #1b1f3b, #050510);
      font-family: 'Segoe UI', Tahoma, sans-serif;
      color: #fff;
    }

    .calculator {
      background: rgba(20, 24, 60, 0.9);
      border-radius: 20px;
      padding: 20px;
      width: 320px;
      box-shadow: 0 0 30px rgba(120, 120, 255, 0.25);
    }

    .display {
      width: 100%;
      height: 60px;
      margin-bottom: 15px;
      background: #0b0f2a;
      border-radius: 12px;
      display: flex;
      align-items: center;
      justify-content: flex-end;
      padding: 10px;
      font-size: 1.8rem;
      box-sizing: border-box;
      overflow-x: auto;
    }

    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }

    button {
      height: 55px;
      border: none;
      border-radius: 12px;
      font-size: 1.2rem;
      cursor: pointer;
      background: linear-gradient(145deg, #2a2f6b, #1a1e4f);
      color: #fff;
      box-shadow: inset 0 0 5px rgba(255,255,255,0.1);
      transition: transform 0.1s, box-shadow 0.1s;
    }

    button:hover {
      box-shadow: 0 0 10px rgba(120,120,255,0.4);
    }

    button:active {
      transform: scale(0.95);
    }

    .operator {
      background: linear-gradient(145deg, #6a5acd, #483d8b);
    }

    .equal {
      grid-column: span 2;
      background: linear-gradient(145deg, #9b4dff, #6a0dad);
    }

    .clear {
      background: linear-gradient(145deg, #ff4d6d, #b3002d);
    }
  </style>
</head>
<body>
  <div class="calculator">
    <div id="display" class="display">0</div>
    <div class="buttons">
      <button class="clear" onclick="clearDisplay()">C</button>
      <button onclick="append('%')">%</button>
      <button onclick="append('/')" class="operator">÷</button>
      <button onclick="append('*')" class="operator">×</button>

      <button onclick="append('7')">7</button>
      <button onclick="append('8')">8</button>
      <button onclick="append('9')">9</button>
      <button onclick="append('-')" class="operator">−</button>

      <button onclick="append('4')">4</button>
      <button onclick="append('5')">5</button>
      <button onclick="append('6')">6</button>
      <button onclick="append('+')" class="operator">+</button>

      <button onclick="append('1')">1</button>
      <button onclick="append('2')">2</button>
      <button onclick="append('3')">3</button>

      <button onclick="append('0')">0</button>
      <button onclick="append('.')">.</button>
      <button class="equal" onclick="calculate()">=</button>
    </div>
  </div>

  <script>
    const display = document.getElementById('display');

    function append(value) {
      if (display.innerText === '0') {
        display.innerText = value;
      } else {
        display.innerText += value;
      }
    }

    function clearDisplay() {
      display.innerText = '0';
    }

    function calculate() {
      try {
        display.innerText = eval(display.innerText);
      } catch {
        display.innerText = 'Erro';
      }
    }
  </script>
</body>
</html>
