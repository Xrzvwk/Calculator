# Calculator
I made this following a tut(S/O bro code) 

HTML: 
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <div id="calculator">
      <input id="display" readonly />
      <div id="keys">
        <button onclick="appendToDisplay('+')" class="operator-btn">+</button>
        <button onclick="appendToDisplay('7')">7</button>
        <button onclick="appendToDisplay('8')">8</button>
        <button onclick="appendToDisplay('9')">9</button>
        <button onclick="appendToDisplay('-')" class="operator-btn">-</button>
        <button onclick="appendToDisplay('4')">4</button>
        <button onclick="appendToDisplay('5')">5</button>
        <button onclick="appendToDisplay('6')">6</button>
        <button onclick="appendToDisplay('*')" class="operator-btn">*</button>
        <button onclick="appendToDisplay('1')">1</button>
        <button onclick="appendToDisplay('2')">2</button>
        <button onclick="appendToDisplay('3')">3</button>
        <button onclick="appendToDisplay('/')" class="operator-btn">/</button>
        <button onclick="appendToDisplay('0')">0</button>
        <button onclick="appendToDisplay('.')">.</button>
        <button onclick="calculate()">=</button>
        <button onclick="clearDisplay()" class="operator-btn">C</button>
      </div>
    </div>

    <script src="index.js"></script>
  </body>
</html>


STYLE.CSS:
body{
    margin: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}



#calculator{
    font-size: Arial, sans-serif;
    background-color: darkgray;
    max-width: 500px;
    overflow: hidden;

}


#display{
    width: 500px;
    padding: 20px;
    font-size: 5rem;
    text-align: left;
    border: none;
    background-color: lightgrey;
    color: black;
}





#keys{
    display: grid;
    grid-template-columns: repeat(4,1fr); /*Fr = fractional Unit, making the columns equally seperate.*/
    gap: 10px;
    padding: 25px;

}



button{
    height: 100px;
    width: 100px;
    border-radius: 50px;
    border: none;
    background-color: lightblue;
    color: white;
    font-size: 3rem;
    font-weight: bold;
    cursor: pointer;
}


button:hover{
    background-color: darkcyan ;
}

button:active{
    background-color: lightblue;
}

.operator-btn{
    background-color: orange;
}
.operator-btn:hover{
    background-color: darksalmon;
}

.operator-btn:active{
    background-color: black;
}

JAVASCRIPT: 
const display = document.getElementById('display');


function appendToDisplay(input){
    display.value += input;
}



function clearDisplay(){
    display .value = "";
}

function calculate(){
    try{
        display.value = eval(display.value);
    }
    catch(error){
        display.value = "Error bruh";
    }
    

}
