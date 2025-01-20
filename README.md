<h1 align="center">Hi 👋, I'm Vijay Guhan</h1>
<h3 align="center">A Passionate Full-Stack Developer from India</h3>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=vijayguhan10&label=Profile%20Views&color=0e75b6&style=flat" alt="Profile Views" />
</p>

<p align="center">
  <a href="https://github-profile-trophy.vercel.app/?username=vijayguhan10">
    <img src="https://github-profile-trophy.vercel.app/?username=vijayguhan10&margin-w=10" alt="GitHub Trophies" />
  </a>
</p>

---

- 🔭 I’m the **Founder and CEO** of [Autom Consultancy](https://event-management-swart-kappa.vercel.app)  
  Specializing in **Event Management ERP Solutions**.

- 💬 Ask me about **React, Node.js, Express, MongoDB**.

- 📫 How to reach me: **vijayguhan10@gmail.com**

---

<h3 align="left">🌐 Connect with Me:</h3>
<p align="left">
  <a href="https://www.linkedin.com/in/vijay-guhan-728299283" target="_blank">
    <img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="LinkedIn" height="30" width="40" />
  </a>
</p>

---

<h3 align="left">💻 Languages and Tools:</h3>
<p align="left">
  <a href="https://aws.amazon.com" target="_blank" rel="noreferrer">
    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/amazonwebservices/amazonwebservices-original-wordmark.svg" alt="AWS" width="40" height="40" />
  </a>
  <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript" target="_blank" rel="noreferrer">
    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt="JavaScript" width="40" height="40" />
  </a>
  <a href="https://reactjs.org/" target="_blank" rel="noreferrer">
    <img src="https://reactnative.dev/img/header_logo.svg" alt="React" width="40" height="40" />
  </a>
  <a href="https://nodejs.org" target="_blank" rel="noreferrer">
    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original-wordmark.svg" alt="Node.js" width="40" height="40" />
  </a>
  <a href="https://expressjs.com" target="_blank" rel="noreferrer">
    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/express/express-original-wordmark.svg" alt="Express.js" width="40" height="40" />
  </a>
  <a href="https://www.mongodb.com/" target="_blank" rel="noreferrer">
    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mongodb/mongodb-original-wordmark.svg" alt="MongoDB" width="40" height="40" />
  </a>
  <a href="https://www.typescriptlang.org/" target="_blank" rel="noreferrer">
    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/typescript/typescript-original.svg" alt="TypeScript" width="40" height="40" />
  </a>
  <a href="https://nextjs.org/" target="_blank" rel="noreferrer">
    <img src="https://cdn.worldvectorlogo.com/logos/nextjs-2.svg" alt="Next.js" width="40" height="40" />
  </a>
  <a href="https://git-scm.com/" target="_blank" rel="noreferrer">
    <img src="https://www.vectorlogo.zone/logos/git-scm/git-scm-icon.svg" alt="Git" width="40" height="40" />
  </a>
</p>

---

<h3 align="left">📈 GitHub Stats:</h3>
<p align="center">
  <img align="center" src="https://github-readme-stats.vercel.app/api?username=vijayguhan10&show_icons=true&locale=en&theme=radical" alt="GitHub Stats" />
  <img align="center" src="https://streak-stats.demolab.com/?user=vijayguhan10&theme=radical" alt="GitHub Streak" />
</p>

---

<h3 align="left">🎮 Fun Zone: Play Some Games!</h3>
<p align="center">
  <a href="https://snake-2.vercel.app/" target="_blank">
    <img src="https://img.shields.io/badge/Play%20Snake%20Game-33cc99?style=for-the-badge" alt="Snake Game" />
  </a>
  <a href="https://tetris.vercel.app/" target="_blank">
    <img src="https://img.shields.io/badge/Play%20Tetris-blueviolet?style=for-the-badge" alt="Tetris" />
  </a>
</p>

---

<h3 align="center">💡 "Coding is the closest thing we have to magic." 💡</h3>
<p align="center">
 <!DOCTYPE html>
<html>
<head>
  <title></title>
  <style>
  html, body {
    height: 100%;
    margin: 0;
  }

  body {
    background: black;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  canvas {
    border: 1px solid white;
  }
  </style>
</head>
<body>
<canvas width="400" height="400" id="game"></canvas>
<script>
var canvas = document.getElementById('game');
var context = canvas.getContext('2d');

var grid = 16;
var count = 0;
  
var snake = {
  x: 160,
  y: 160,
  
  // snake velocity. moves one grid length every frame in either the x or y direction
  dx: grid,
  dy: 0,
  
  // keep track of all grids the snake body occupies
  cells: [],
  
  // length of the snake. grows when eating an apple
  maxCells: 4
};
var apple = {
  x: 320,
  y: 320
};

// get random whole numbers in a specific range
// @see https://stackoverflow.com/a/1527820/2124254
function getRandomInt(min, max) {
  return Math.floor(Math.random() * (max - min)) + min;
}

// game loop
function loop() {
  requestAnimationFrame(loop);

  // slow game loop to 15 fps instead of 60 (60/15 = 4)
  if (++count < 4) {
    return;
  }

  count = 0;
  context.clearRect(0,0,canvas.width,canvas.height);

  // move snake by it's velocity
  snake.x += snake.dx;
  snake.y += snake.dy;

  // wrap snake position horizontally on edge of screen
  if (snake.x < 0) {
    snake.x = canvas.width - grid;
  }
  else if (snake.x >= canvas.width) {
    snake.x = 0;
  }
  
  // wrap snake position vertically on edge of screen
  if (snake.y < 0) {
    snake.y = canvas.height - grid;
  }
  else if (snake.y >= canvas.height) {
    snake.y = 0;
  }

  // keep track of where snake has been. front of the array is always the head
  snake.cells.unshift({x: snake.x, y: snake.y});

  // remove cells as we move away from them
  if (snake.cells.length > snake.maxCells) {
    snake.cells.pop();
  }

  // draw apple
  context.fillStyle = 'red';
  context.fillRect(apple.x, apple.y, grid-1, grid-1);

  // draw snake one cell at a time
  context.fillStyle = 'green';
  snake.cells.forEach(function(cell, index) {
    
    // drawing 1 px smaller than the grid creates a grid effect in the snake body so you can see how long it is
    context.fillRect(cell.x, cell.y, grid-1, grid-1);  

    // snake ate apple
    if (cell.x === apple.x && cell.y === apple.y) {
      snake.maxCells++;

      // canvas is 400x400 which is 25x25 grids 
      apple.x = getRandomInt(0, 25) * grid;
      apple.y = getRandomInt(0, 25) * grid;
    }

    // check collision with all cells after this one (modified bubble sort)
    for (var i = index + 1; i < snake.cells.length; i++) {
      
      // snake occupies same space as a body part. reset game
      if (cell.x === snake.cells[i].x && cell.y === snake.cells[i].y) {
        snake.x = 160;
        snake.y = 160;
        snake.cells = [];
        snake.maxCells = 4;
        snake.dx = grid;
        snake.dy = 0;

        apple.x = getRandomInt(0, 25) * grid;
        apple.y = getRandomInt(0, 25) * grid;
      }
    }
  });
}

// listen to keyboard events to move the snake
document.addEventListener('keydown', function(e) {
  // prevent snake from backtracking on itself by checking that it's 
  // not already moving on the same axis (pressing left while moving
  // left won't do anything, and pressing right while moving left
  // shouldn't let you collide with your own body)
  
  // left arrow key
  if (e.which === 37 && snake.dx === 0) {
    snake.dx = -grid;
    snake.dy = 0;
  }
  // up arrow key
  else if (e.which === 38 && snake.dy === 0) {
    snake.dy = -grid;
    snake.dx = 0;
  }
  // right arrow key
  else if (e.which === 39 && snake.dx === 0) {
    snake.dx = grid;
    snake.dy = 0;
  }
  // down arrow key
  else if (e.which === 40 && snake.dy === 0) {
    snake.dy = grid;
    snake.dx = 0;
  }
});

// start the game
requestAnimationFrame(loop);
</script>
</body>
</html>

---

<h3 align="left">📬 Have questions? Feel free to reach out!</h3>
<p align="left">
  📧 Email: vijayguhan10@gmail.com  
  💼 LinkedIn: [Vijay Guhan](https://www.linkedin.com/in/vijay-guhan-728299283)  
</p>
