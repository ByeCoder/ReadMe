<canvas id="gameCanvas" width="300" height="300"></canvas>
<script>
  var canvas = document.getElementById('gameCanvas');
  var ctx = canvas.getContext('2d');

  var snake = [{ x: 50, y: 50 }];
  var direction = 'right';

  function drawSnake() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    snake.forEach(function(segment) {
      ctx.fillStyle = 'green';
      ctx.fillRect(segment.x, segment.y, 10, 10);
    });
  }

  function updateSnake() {
    var head = Object.assign({}, snake[0]);
    if (direction === 'right') head.x += 10;
    else if (direction === 'left') head.x -= 10;
    else if (direction === 'up') head.y -= 10;
    else if (direction === 'down') head.y += 10;
    snake.unshift(head);
    snake.pop();
  }

  function gameLoop() {
    drawSnake();
    updateSnake();
  }

  setInterval(gameLoop, 100);

  window.addEventListener('keydown', function(e) {
    if (e.key === 'ArrowRight') direction = 'right';
    else if (e.key === 'ArrowLeft') direction = 'left';
    else if (e.key === 'ArrowUp') direction = 'up';
    else if (e.key === 'ArrowDown') direction = 'down';
  });
</script>
