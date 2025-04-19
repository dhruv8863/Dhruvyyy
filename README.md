<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>I'm Sorry, Sushiii</title>
  <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Roboto&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body, html {
      height: 100%;
      font-family: 'Roboto', sans-serif;
      color: white;
      overflow: hidden;
    }

    video#bgVideo {
      position: fixed;
      top: 0;
      left: 0;
      object-fit: cover;
      width: 100%;
      height: 100%;
      z-index: -1;
    }

    .overlay {
      position: absolute;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.5);
      z-index: 0;
    }

    .container {
      position: relative;
      text-align: center;
      padding: 100px 20px;
      z-index: 1;
    }

    h1 {
      font-family: 'Great Vibes', cursive;
      font-size: 4em;
      margin-bottom: 20px;
      opacity: 0;
      animation: fadeIn 2s ease-in forwards;
      animation-delay: 1s;
    }

    p, .letter p {
      font-size: 1.4em;
      max-width: 700px;
      margin: 0 auto;
      opacity: 0;
      animation: fadeInText 3s ease-in forwards;
      animation-delay: 2s;
      white-space: nowrap;
      overflow: hidden;
      display: inline-block;
      border-right: .15em solid orange;
    }

    .letter {
      margin-top: 60px;
      background: rgba(255, 255, 255, 0.1);
      border-radius: 20px;
      padding: 30px;
      max-width: 800px;
      margin-left: auto;
      margin-right: auto;
      font-size: 1.2em;
      line-height: 1.6em;
      opacity: 0;
      animation: fadeInText 4s ease-in forwards;
      animation-delay: 5s;
    }

    .heart {
      position: absolute;
      width: 20px;
      height: 20px;
      background: pink;
      transform: rotate(45deg);
      animation: float 10s infinite;
    }

    .heart::before,
    .heart::after {
      content: '';
      position: absolute;
      width: 20px;
      height: 20px;
      background: pink;
      border-radius: 50%;
    }

    .heart::before {
      top: -10px;
      left: 0;
    }

    .heart::after {
      left: -10px;
      top: 0;
    }

    @keyframes float {
      0% {
        transform: translateY(0) rotate(45deg);
        opacity: 1;
      }
      100% {
        transform: translateY(-100vh) rotate(45deg);
        opacity: 0;
      }
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    @keyframes fadeInText {
      0% {
        width: 0;
      }
      100% {
        width: 100%;
        opacity: 1;
      }
    }
  </style>
</head>
<body>

  <!-- Background video -->
  <video autoplay muted loop id="bgVideo">
    <source src="romantic-video.mp4" type="video/mp4" />
    Your browser does not support the video tag.
  </video>

  <div class="overlay"></div>

  <div class="container">
    <h1>I'm Sorry, My Sushiii</h1>
    <p id="introText">You are my everything, Sauranshi. <br />I never meant to hurt you, and I hope you can forgive me.</p>

    <div class="letter">
      <p id="apologyText">
        Dear Sauranshi,<br><br>
        From the bottom of my heart, I want to say I'm truly sorry. I know I’ve hurt you, and that’s the last thing I ever wanted to do. You mean the world to me, and it breaks my heart knowing I caused you pain.<br><br>
        I miss your smile, your voice, and the way you light up my life. Every moment with you is precious, and I can't imagine my life without you in it. I love you deeply, and I will do anything to make things right again.<br><br>
        Please forgive me, my sweet Sushiii. I promise to be better, to love you harder, and to always cherish you like you deserve.<br><br>
        Forever yours,<br>
        Dhruv
      </p>
    </div>
  </div>

  <!-- Music -->
  <audio autoplay loop>
    <source src="romantic-music.mp3" type="audio/mpeg" />
  </audio>

  <script>
    // Floating hearts
    function createHeart() {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = (Math.random() * 5 + 5) + "s";
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 10000);
    }

    setInterval(createHeart, 300);
  </script>
</body>
</html>
