<!DOCTYPE html>
<html>
<head>
  <title>Click Rush</title>
  <style>
    body { text-align: center; font-family: Arial; }
    #btn { font-size: 30px; padding: 20px; }
  </style>
</head>
<body>

<h1>Click Rush</h1>
<p>10초 안에 최대한 많이 클릭!</p>
<button id="btn">CLICK!</button>
<p id="score">0</p>
<p id="time">10</p>

<!-- 광고 위치 (상단 or 하단) -->
<div id="ad-top">
  <!-- AdSense 코드 넣기 -->
</div>

<script>
let score = 0;
let time = 10;
let playing = false;

const btn = document.getElementById("btn");

btn.onclick = () => {
  if (!playing) startGame();
  score++;
  document.getElementById("score").innerText = score;
};

function startGame() {
  playing = true;
  let timer = setInterval(() => {
    time--;
    document.getElementById("time").innerText = time;

    if (time <= 0) {
      clearInterval(timer);
      alert("끝! 점수: " + score);

      // 광고 보여주기 위치 (게임 끝난 후)
      showAd();

      reset();
    }
  }, 1000);
}

function reset() {
  score = 0;
  time = 10;
  playing = false;
  document.getElementById("score").innerText = score;
  document.getElementById("time").innerText = time;
}

function showAd() {
  console.log("여기에 광고 노출");
}
</script>

</body>
</html>
