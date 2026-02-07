<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Valentine Surprise for Sanskar</title>
  <link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Roboto&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Roboto', sans-serif;
      background: linear-gradient(120deg, #ff9a9e, #fad0c4);
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      text-align: center;
      color: #fff;
      overflow: hidden;
    }

    .container {
      background: rgba(255, 255, 255, 0.15);
      padding: 40px;
      border-radius: 20px;
      box-shadow: 0 8px 20px rgba(0,0,0,0.3);
      max-width: 500px;
      position: relative;
    }

    h1 {
      font-family: 'Pacifico', cursive;
      font-size: 2.5em;
      margin-bottom: 20px;
    }

    p {
      font-size: 1.3em;
      margin-bottom: 30px;
    }

    button {
      font-size: 1.2em;
      padding: 10px 25px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      margin: 10px;
      transition: transform 0.2s, background 0.2s;
    }

    #yesBtn {
      background: #ff6f91;
      color: white;
    }

    #yesBtn:hover {
      transform: scale(1.1);
      background: #ff4971;
    }

    #noBtn {
      background: #f7d794;
      color: #333;
      position: absolute;
    }

    #message {
      display: none;
      margin-top: 20px;
      font-size: 1.5em;
      color: #fff;
      animation: fadeIn 1s ease-in-out forwards;
    }

    @keyframes fadeIn {
      from {opacity: 0;}
      to {opacity: 1;}
    }

    .heart {
      color: #ff214f;
      animation: heartbeat 1s infinite;
    }

    @keyframes heartbeat {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.3); }
    }

    img {
      margin-top: 20px;
      width: 250px;
      border-radius: 15px;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>💌 Hey Sanskar!</h1>
    <p>Will you be my Valentine?</p>
    <button id="yesBtn">Yes ❤️</button>
    <button id="noBtn">No 😢</button>
    <div id="message">
      <p>I knew you would say yes! <span class="heart">💖</span></p>
      <p>I love you 😘</p>
      <img src="https://pixabay.com/gifs/kissing%20cats%20kissing%20love%20cat-3128662/" alt="Cute kitten kissing GIF">
    </div>
  </div>

  <script>
    const yesBtn = document.getElementById('yesBtn');
    const noBtn = document.getElementById('noBtn');
    const container = document.querySelector('.container');
    const message = document.getElementById('message');

    // Show message on Yes click
    yesBtn.addEventListener('click', () => {
      message.style.display = 'block';
      yesBtn.style.display = 'none';
      noBtn.style.display = 'none';
    });

    // Make No button dodge the cursor
    noBtn.addEventListener('mouseenter', () => {
      const containerRect = container.getBoundingClientRect();
      const btnWidth = noBtn.offsetWidth;
      const btnHeight = noBtn.offsetHeight;

      // Random position inside container
      const maxX = containerRect.width - btnWidth;
      const maxY = containerRect.height - btnHeight;

      const randomX = Math.floor(Math.random() * maxX);
      const randomY = Math.floor(Math.random() * maxY);

      noBtn.style.left = randomX + 'px';
      noBtn.style.top = randomY + 'px';
    });
  </script>
</body>
</html>
