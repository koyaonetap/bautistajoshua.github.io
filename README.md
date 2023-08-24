<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Scientific Calculator</title>
<style>
  #calculator {
    width: 250px;
    margin: 0 auto;
    padding: 20px;
    border-radius: 5px;
  }
  .back-video{
  position: absolute;
  right: 0;
  bottom: 0;
  z-index: -1;
}
.table,td, h2{
  margin: auto;
border-collapse: collapse;
font-size: 25px;
table-layout: fixed;
opacity: 0.5;
color: white;
margin-top: 100px;
}
</style>
</head>
<body>
  <video autoplay loop muted plays-inline class="back-video">
    <source src="video/video.mp4">
</video>
<div id="calculator">
  <h2>Advanced Calculator</h2>
  <input type="text" id="display" readonly>
  <table>
    <tr>
      <td><button onclick="appendToDisplay('+')">+</button></td>
      <td><button onclick="appendToDisplay('-')">-</button></td>
      <td><button onclick="appendToDisplay('*')">*</button></td>
      <td><button onclick="appendToDisplay('++')">++</button></td>
   </tr>
      <tr></tr><td><button onclick="appendToDisplay('%')">%</button></td>
      <td><button onclick="appendToDisplay('^')">^</button></td>
      <td><button onclick="appendToDisplay('/')">/</button></td>
      <td><button onclick="appendToDisplay('--')">--</button></td>
    </tr>
    <tr>
      <td><button onclick="appendToDisplay('7')">7</button></td>
      <td><button onclick="appendToDisplay('8')">8</button></td>
      <td><button onclick="appendToDisplay('9')">9</button></td>
    </tr>
   </tr>
      <td><button onclick="appendToDisplay('4')">4</button></td>
      <td><button onclick="appendToDisplay('5')">5</button></td>
      <td><button onclick="appendToDisplay('6')">6</button></td></tr>
      <tr>  <td><button onclick="appendToDisplay('1')">1</button></td>
      <td><button onclick="appendToDisplay('2')">2</button></td>
      <td><button onclick="appendToDisplay('3')">3</button></td></tr>
    </tr> <td><button onclick="appendToDisplay('0')">0</button></td>
      <td><button onclick="appendToDisplay('.')">.</button></td>
      <td><button onclick="calculateResult()">=</button></td>
      <td><button onclick="clearDisplay()">C</button></td>
    </tr>
  </table>
  <script>
    let displayValue = '';
    function appendToDisplay(value) {
      displayValue += value;
      document.getElementById('display').value = displayValue;
    }
    function calculateResult() {
      try {
        displayValue = eval(displayValue);
        document.getElementById('display').value = displayValue;
      } catch (error) {
        document.getElementById('display').value = 'Error';
      }
    }
    function clearDisplay() {
      displayValue = '';
      document.getElementById('display').value = displayValue; }
  </script>
</body>
</html>
