# ⏱ Stopwatch Application
## AIM
A simple stopwatch built using **HTML, CSS, and JavaScript**.
## DESCRIPTION

A modern, responsive Stopwatch Application built using **HTML, CSS, and JavaScript**.

This project is a simple yet elegant stopwatch with a clean user interface and smooth functionality.
It can Start, Pause, and Reset, and displays time in the format MM : SS : MS (minutes, seconds, milliseconds).


## Features
- **Start** the stopwatch
- **Pause** the stopwatch without resetting
- **Reset** the stopwatch back to `00 : 00 : 00`
- Displays time in the format **MM : SS : MS**
- Smooth and responsive UI
- Modern design with glassmorphism and digital font



## Technologies Used
- **HTML5** – structure of the app  
- **CSS3** – styling with gradients, shadows, glassmorphism, animations  
- **JavaScript (ES6)** – stopwatch functionality using `setInterval`  

## CODE
### index.html
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Modern Stopwatch</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="container">
    <h1>⏱Sanjay's Stopwatch</h1>
    <div class="stopwatch">
      <div class="time" id="display">00 : 00 : 00</div>
      <div class="buttons">
        <button id="start">Start</button>
        <button id="pause">Pause</button>
        <button id="reset">Reset</button>
      </div>
    </div>
  </div>

  <script src="script.js"></script>
</body>
</html>

```

### style.css
```

@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@500&display=swap');

body {
  margin: 0;
  font-family: Arial, sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
}

.container {
  text-align: center;
  color: #fff;
}

h1 {
  font-size: 2rem;
  margin-bottom: 20px;
  letter-spacing: 1px;
}

.stopwatch {
  background: rgba(255, 255, 255, 0.1);
  padding: 40px;
  border-radius: 20px;
  backdrop-filter: blur(12px);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.4);
  display: inline-block;
}

.time {
  font-family: 'Orbitron', monospace;
  font-size: 3.5rem;
  margin-bottom: 25px;
  color: #00ffcc;
  text-shadow: 0 0 12px rgba(0, 255, 200, 0.8);
}

.buttons {
  display: flex;
  justify-content: center;
  gap: 15px;
}

button {
  font-size: 1rem;
  padding: 12px 25px;
  border: none;
  border-radius: 10px;
  cursor: pointer;
  font-weight: bold;
  transition: all 0.3s ease;
}

#start {
  background: #28a745;
  color: white;
}

#pause {
  background: #ffc107;
  color: black;
}

#reset {
  background: #dc3545;
  color: white;
}

button:hover {
  transform: translateY(-2px) scale(1.05);
  box-shadow: 0 5px 15px rgba(0,0,0,0.3);
}

button:active {
  transform: scale(0.95);
}

```
### script.js
```
let minutes = 0, seconds = 0, milliseconds = 0;
let timer;
let running = false;

const display = document.getElementById("display");
const startBtn = document.getElementById("start");
const pauseBtn = document.getElementById("pause");
const resetBtn = document.getElementById("reset");

function updateDisplay() {
  let m = minutes < 10 ? "0" + minutes : minutes;
  let s = seconds < 10 ? "0" + seconds : seconds;
  let ms = milliseconds < 10 ? "0" + milliseconds : milliseconds;
  display.textContent = `${m} : ${s} : ${ms}`;
}

function startTimer() {
  if (!running) {
    running = true;
    timer = setInterval(() => {
      milliseconds++;
      if (milliseconds === 100) {
        milliseconds = 0;
        seconds++;
      }
      if (seconds === 60) {
        seconds = 0;
        minutes++;
      }
      updateDisplay();
    }, 10);
  }
}

function pauseTimer() {
  running = false;
  clearInterval(timer);
}

function resetTimer() {
  running = false;
  clearInterval(timer);
  minutes = 0;
  seconds = 0;
  milliseconds = 0;
  updateDisplay();
}

startBtn.addEventListener("click", startTimer);
pauseBtn.addEventListener("click", pauseTimer);
resetBtn.addEventListener("click", resetTimer);

updateDisplay();

```
## Output
<img width="1898" height="893" alt="image" src="https://github.com/user-attachments/assets/bf64f17f-bcdc-443e-b422-ee5e09d471dd" />
#### start
<img width="1919" height="894" alt="image" src="https://github.com/user-attachments/assets/3c8f301e-bba9-4cf7-ba21-32e09263e201" />
#### pause
<img width="1919" height="913" alt="image" src="https://github.com/user-attachments/assets/eac4a7bd-a73b-4497-ab10-dd23db30ce47" />
#### reset
<img width="1918" height="901" alt="image" src="https://github.com/user-attachments/assets/7d0daa63-9d1d-4e4f-88f5-e4f9f63be336" />


