<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Will You Be My Valentine? 💘</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: linear-gradient(135deg, #ffe6e6, #ffd6d6);
      text-align: center;
      overflow: hidden;
    }

    .card {
      background: white;
      padding: 30px;
      border-radius: 20px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.2);
      width: 90%;
      max-width: 450px;
    }

    h1 {
      font-size: 28px;
      color: #ff4d6d;
    }

    button {
      padding: 14px 30px;
      font-size: 18px;
      border: none;
      border-radius: 40px;
      cursor: pointer;
      transition: all 0.2s ease;
    }

    #yesBtn {
      background: #ff4d6d;
      color: white;
      margin-right: 15px;
    }

    #noBtn {
      background: #adb5bd;
      color: white;
      position: absolute;
    }

  </style>
</head>
<body>

  <!-- 🎵 Romantic Music -->
  <audio id="music" loop autoplay>
    <source src="perfect.mp3" type="audio/mpeg">
    Your browser does not support the audio element.
  </audio>

  <div class="card" id="card">
    <h1>Sanskar, will you be my Valentine? 💘</h1>

    <img id="mainGif" src="https://pixabay.com/gifs/cat-love-kiss-heart-133/" alt="Cute romantic cats kissing">

    <div class="buttons">
      <button id="yesBtn" onclick="yesClicked()">Yes 💖</button>
      <button id="noBtn">No 😢</button>
    </div>
  </div>

  <script>
    // Move the NO button to random positions when hovered
    const noBtn = document.getElementById("noBtn");
    noBtn.addEventListener("mouseover", () => {
      const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
      const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
      noBtn.style.left = x + "px";
      noBtn.style.top = y + "px";
      noBtn.style.transform = `translate(0, 0)`;
    });

    // YES button behavior
    function yesClicked() {
      document.getElementById("mainGif").src = 
        "https://media.tenor.com/3VjI4wXhGt8AAAAC/celebration-love.gif"; // celebration GIF
      document.getElementById("card").innerHTML = `
        <h1>Yay! 😍 You said YES!</h1>
        <img src="https://media.tenor.com/3VjI4wXhGt8AAAAC/celebration-love.gif" alt="Celebration GIF" style="width:100%;border-radius:18px;">
        <p>Love you forever 💕</p>
      `;
    }
  </script>

</body>
</html>

