<script>
      let display = "";
  let operator = "";
  let operatorClicked = false;
  let resultDisplayed = false;

  function handleClick(e) {
    let button = e.target.innerHTML;
    if (button >= "0" && button <= "9" || button === ".") {
      if (resultDisplayed) {
        display = button;
        resultDisplayed = false;
      } else {
        display += button;
      }
    } else if (button === "C") {
      display = "";
      operator = "";
      operatorClicked = false;
    } else if (button === "CE") {
      display = display.slice(0, -1);
    } else if (button === "+" || button === "-" || button === "*" || button === "/") {
      operator = button;
      operatorClicked = true;
      display += button;
    } else if (button === "=") {
      let num1 = parseFloat(display.split(operator)[0]);
      let num2 = parseFloat(display.split(operator)[1]);
      if (operator === "+") {
        display = num1 + num2;
      } else if (operator === "-") {
        display = num1 - num2;
      } else if (operator === "*") {
        display = num1 * num2;
      } else if (operator === "/") {
        if (num2 === 0) {
          display = "Cannot divide by 0";
        } else {
          display = num1 / num2;
        }
      }
      operator = "";
      resultDisplayed = true;
    }
  }
</script>


<style>
 body {
  background-color: #f1f1f1;
  font-family: Arial, sans-serif;
}

.popup-button {
    position: fixed;
    right: 20px;
    bottom: 20px;
    width: 50px;
    height: 50px;
    background-color: #ddd;
    border-radius: 50%;
    box-shadow: 0px 0px 10px #999;
    text-align: center;
    /* transition: all 0.2s ease-in-out; */
    animation: rotate 0.8s infinite;

}
@keyframes rotate {
    from {transform: rotate(0deg);}
    to {transform: rotate(360deg);}
}
/* .popup-button:hover {
    transform: scale(1.1);
    background-color: #ccc;
} */
.popup-button a {
    display: block;
    width: 100%;
    height: 100%;
    line-height: 50px;
    color: #333;
    text-decoration: none;
}
.popup-button a i {
    font-size: 30px;
}

header {
  background-color: #020d1d;
  color: white;
  text-align: center;
  padding: 1em;
}

.container {
  max-width: 600px;
  margin: 0 auto;
  padding: 1em;
}

.calculator {
    margin: 0 auto;
    border: 1px solid #ccc;
    border-radius: 5px;
    padding: 10px;
    background: linear-gradient(to bottom, #f1f1f1, #e5e5e5); /* Add a background gradient */
    box-shadow: 2px 2px 10px #ccc; /* Add a subtle box-shadow to give the calculator a 3D effect */
}

#display {
    width: 100%;
    font-size: 1.5em;
    text-align: right;
    padding: 5px;
    margin-bottom: 10px;
    border: none;
    background-color: #f1f1f1;
    transition: background-color 0.3s ease-in-out; /* Use a CSS transition to smoothly animate the background color when a button is pressed */
    text-shadow: 1px 1px #ccc; /* Add a subtle text-shadow to give the text a 3D effect */
}

.buttons {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
}

.buttons button {
    width: 25%;
    padding: 10px 0;
    font-size: 1.5em;
    color: #555;
    border: none;
    background-color: #f1f1f1;
    cursor: pointer;
    transition: background-color 0.3s ease-in-out, color 0.3s ease-in-out; /* Use a CSS transition to smoothly animate the background color and text color when a button is pressed */
    box-shadow: 2px 2px 5px #ccc; /* Add a subtle box-shadow to give the buttons a 3D effect */
}

.buttons button:hover {
    background-color: #e5e5e5; /* Change the background color of the button when the cursor is over it */
    color: #333; /* Change the text color of the button when the cursor is over it */
}

.operator {
    background-color: #ff9f43;
    color: #fff;
}


/* Media Query for responsive design */
@media only screen and (max-width: 600px) {
  .calculator {
    width: 90%; /* Change the width of the calculator on small screens */
  }
}


</style>




<head>
  <title>Responsive Multipage Education Website Using HTML, CSS & JavaScript</title>
  <!-- ICONSCOUT CDN-->
  <link rel="stylesheet" href="https://unicons.iconscout.com/release/v2.1.6/css/unicons.css">
    <title>My Calculator</title>
  </head>
    <header>
      <h1> Calculator</h1>
    </header>
    <body>
    <div class="container">
    <div class="calculator">
      <input type="text" id="display" bind:value={display} disabled>
      <div class="buttons">
        <button class="operator" on:click={handleClick}>C</button>
        <button class="operator" on:click={handleClick}>CE</button>
        <button class="operator" on:click={handleClick}>/</button>
        <button class="number" on:click={handleClick}>7</button>
        <button class="number" on:click={handleClick}>8</button>
        <button class="number" on:click={handleClick}>9</button>
        <button class="operator" on:click={handleClick}>*</button>
        <button class="number" on:click={handleClick}>4</button>
        <button class="number" on:click={handleClick}>5</button>
        <button class="number" on:click={handleClick}>6</button>
        <button class="operator" on:click={handleClick}>-</button>
        <button class="number" on:click={handleClick}>1</button>
        <button class="number" on:click={handleClick}>2</button>
        <button class="number" on:click={handleClick}>3</button>
        <button class="operator" on:click={handleClick}>+</button>
        <button class="number" on:click={handleClick}>0</button>
        <button class="number" on:click={handleClick}>.</button>
        <button class="operator" on:click={handleClick}>=</button>
      </div>
    </div>
    <div class="close_all">
      <button id="close_all" class="popup-button"><a href="/"><i class="uil uil-multiply"></i></a></button>
    </div>
  </div>
</body>