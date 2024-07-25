

  <!DOCTYPE html>  
<html lang="en">  
<head>  
    <meta charset="UTF-8">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>Calculator</title>
    <style>
        body {  
    display: flex;  
    justify-content: center;  
    align-items: center;  
    height: 100vh;  
    background-color: #f4f4f4;  
    font-family: Arial, sans-serif;  
}  

.calculator {  
    background: rgb(228, 7, 7);  
    border-radius: 10px;  
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);  
    padding: 20px;  
}  

#result {  
    width: 100%;  
    height: 40px;  
    font-size: 24px;  
    text-align: right;  
    border: 1px solid #02470e;  
    border-radius: 5px;  
    margin-bottom: 10px;  
    padding: 5px;  
}  

.buttons {  
    display: grid;  
    grid-template-columns: repeat(4, 1fr);  
    gap: 10px;  
}  

button {  
    height: 60px;  
    font-size: 20px;  
    background-color: #007bff;  
    color: white;  
    border: none;  
    border-radius: 5px;  
    cursor: pointer;  
    transition: background-color 0.3s;  
}  

button:hover {  
    background-color: #0056b3;  
}
    </style>  
</head>  
<body>  
    <div class="calculator">  
        <input type="text" id="result" disabled>  
        <div class="buttons">  
            <button onclick="clearResult()">C</button>  
            <button onclick="appendToResult('7')">7</button>  
            <button onclick="appendToResult('8')">8</button>  
            <button onclick="appendToResult('9')">9</button>  
            <button onclick="appendToResult('/')">÷</button>  

            <button onclick="appendToResult('4')">4</button>  
            <button onclick="appendToResult('5')">5</button>  
            <button onclick="appendToResult('6')">6</button>  
            <button onclick="appendToResult('*')">×</button>  

            <button onclick="appendToResult('1')">1</button>  
            <button onclick="appendToResult('2')">2</button>  
            <button onclick="appendToResult('3')">3</button>  
            <button onclick="appendToResult('-')">−</button>  

            <button onclick="appendToResult('0')">0</button>  
            <button onclick="appendToResult('.')">.</button>  
            <button onclick="calculateResult()">=</button>  
            <button onclick="appendToResult('+')">+</button>  
        </div>  
    </div>  

    <script src="script.js">
        function appendToResult(value) {  
    document.getElementById('result').value += value;  
}  

function clearResult() {  
    document.getElementById('result').value = '';  
}  

function calculateResult() {  
    const resultField = document.getElementById('result');  
    try {  
        resultField.value = eval(resultField.value) || ""; // eval can be risky, use with caution  
    } catch (error) {  
        resultField.value = "Error";  
    }  
}
    </script>  
</body>  
</html>
