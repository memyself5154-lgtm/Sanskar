<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Be My Valentine 💖</title>

<style>
  body {
    margin: 0;
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    background: linear-gradient(135deg, #ff9a9e, #fad0c4);
    font-family: "Poppins", sans-serif;
  }

  .card {
    background: white;
    padding: 30px 20px 40px;
    border-radius: 20px;
    width: 100%;
    max-width: 350px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  h1 {
    color: #ff4d6d;
    font-size: 1.5rem;
    margin-bottom: 30px;
  }

  .btn-area {
    position: relative;
    height: 120px;
  }

  button {
    padding: 12px 24px;
    border-radius: 30px;
    border: none;
    font-size: 1rem;
    cursor: pointer;
  }

  #yes {
    background: #ff4d6d;
    color: white;
  }

  #no {
    background: #eee;
    color: #333;
    position: absolute;
    left: 50%;
    top: 60px;
    transform: translateX(-50%);
  }

  .msg {
    margin-top: 20px;
    min-height: 24px;
    color: #ff4d6d;
    font-weight: 500;
  }

  .result {
    display: none;
    margin-top: 20px;
  }

  .result img {
    width: 100%;
    border-radius: 15px;
  }
</style>
</head>

<body>

<div class="card">
  <h1>Sanskar, will you be my Valentine? 💘</h1>

  <div class="btn-area">
    <button id="yes">Yes 💖</button>
    <button id="no">No 😒</button>
  </div>

  <div class="msg" id="msg"></div>

  <div class="result" id="result">
    <h2>YAYYYYY 💕</h2>
    <img src="https://media.giphy.com/media/MDJ9IbxxvDUQM/giphy.gif">
    <p>You’re stuck with me now 😌💖</p>
  </div>
</div>

<script>
  const noBtn = document.getElementById("no");
  const msg = document.getElementById("msg");
  const yesBtn = document.getElementById("yes");
  const result = document.getElementById("result");

  const messages = [
    "Please accept 🥺",
    "You are already mine 😌",
    "No is not allowed 😤",
    "Stop running from love 😭",
    "My heart chose you 💘",
    "Say yes before I cry 😭💖"
  ];

  let index = 0;

  function moveNo() {
    const x = Math.random() * 220 - 110;
    const y = Math.random() * 40 - 20;

    noBtn.style.transform = `translate(${x}px, ${y}px)`;
    msg.textContent = messages[index % messages.length];
    index++;
  }

  // Works on mobile + desktop
  noBtn.addEventListener("mouseenter", moveNo);
  noBtn.addEventListener("click", moveNo);
  noBtn.addEventListener("touchstart", moveNo);

  yesBtn.addEventListener("click", () => {
    result.style.display = "block";
    msg.textContent = "Best choice ever 😍";
    yesBtn.style.display = "none";
    noBtn.style.display = "none";
  });
</script>

</body>
</html>
