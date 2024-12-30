<style>
  @keyframes move {
    0% { transform: translate(0, 0); }
    50% { transform: translate(100px, 100px); }
    100% { transform: translate(0, 0); }
  }

  .moving-box {
    width: 50px;
    height: 50px;
    background-color: #4CAF50;
    animation: move 3s infinite;
  }
</style>

<div class="moving-box"></div>
