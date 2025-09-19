# Sorry-ayuu
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Sorry Ayuu ❤️</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background: #ffe6eb;
      color: #333;
      overflow: hidden;
    }
    section {
      width: 100%;
      height: 100vh;
      display: none;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      text-align: center;
      padding: 20px;
    }
    section.active {
      display: flex;
      animation: fadeIn 1s ease-in-out;
    }
    h1 {
      font-size: 2.5em;
      margin-bottom: 20px;
    }
    p {
      font-size: 1.2em;
      line-height: 1.6em;
      max-width: 800px;
    }
    button {
      margin-top: 25px;
      padding: 12px 24px;
      background: #ff4e50;
      color: white;
      border: none;
      border-radius: 10px;
      font-size: 1em;
      cursor: pointer;
      transition: 0.3s;
    }
    button:hover {
      background: #ff758c;
    }
    .hearts {
      position: absolute;
      width: 100%;
      height: 100%;
      top: 0; left: 0;
      overflow: hidden;
      z-index: -1;
    }
    .heart {
      position: absolute;
      bottom: -50px;
      width: 20px; height: 20px;
      background: rgba(255, 0, 100, 0.6);
      transform: rotate(45deg);
      animation: float 8s linear infinite;
    }
    .heart:before, .heart:after {
      content: "";
      position: absolute;
      width: 20px; height: 20px;
      background: inherit;
      border-radius: 50%;
    }
    .heart:before { top: -10px; left: 0; }
    .heart:after { left: -10px; top: 0; }
    @keyframes float {
      0% { transform: translateY(0) rotate(45deg); opacity: 1; }
      100% { transform: translateY(-800px) rotate(45deg); opacity: 0; }
    }
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(40px); }
      to { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body>
  <div class="hearts"></div>

  <!-- Page 1 -->
  <section class="active" id="page1">
    <h1>(A SORRY GIFT FROM ME)</h1>
    <p>HELLO AYUU ❤️ HOW WAS YOUR DAY TODAY?</p>
    <button onclick="nextPage(2)">GOOD 😊</button>
    <button onclick="badDay()">BAD 😢</button>
    <p id="badMessage" style="display:none; font-size:1.3em; margin-top:20px; color:#ff3366;">
      LET ME MAKE YOUR DAY GOOD ❤️<br>💖💖💖
      <br><button onclick="nextPage(2)">OK</button>
    </p>
  </section>

  <!-- Page 2 -->
  <section id="page2" style="background:linear-gradient(135deg,#a1c4fd,#c2e9fb); color:white;">
    <h1>MY APOLOGY 💌</h1>
    <p style="background:white; color:#333; padding:20px; border-radius:15px;">
      I KNOW YESTERDAY WAS A VERY BAD DAY FOR YOU BECAUSE OF ME 💔<br><br>
      IT WAS MY STUPIDITY THAT I OVERREACTED ABOUT MANY THINGS AND ALSO I SHOWED YOU SO MUCH ANGER AND MADE YOU FEEL SAD 😢.<br><br>
      I CANNOT MAKE YESTERDAY BETTER BUT I WILL MAKE YOUR TODAY BETTER AND I AM SORRY FOR EVERYTHING I HAVE DONE IN THE PAST DAYS ❤️‍🩹.<br><br>
      I PROMISE I WILL BEHAVE WELL, AND LOVE YOU AS MUCH AS I CAN BECAUSE I REALLY DO 💖.
    </p>
    <button onclick="nextPage(3)">OK</button>
    <audio autoplay loop>
      <source src="https://www2.cs.uic.edu/~i101/SoundFiles/StarWars60.wav" type="audio/mpeg">
    </audio>
  </section>

  <!-- Page 3 -->
  <section id="page3" style="background:#f7e6ff;">
    <h1>I HOPE YOU FORGIVE ME 🥺🙏 😭</h1>
    <div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(120px,1fr));gap:15px;margin-top:20px;">
      <div style="background:white;padding:15px;border-radius:10px;">🤗 HUG</div>
      <div style="background:white;padding:15px;border-radius:10px;">❤️ SORRY</div>
      <div style="background:white;padding:15px;border-radius:10px;">💝 CUTE HUG</div>
      <div style="background:white;padding:15px;border-radius:10px;">🍫 CHOCOLATE</div>
      <div style="background:white;padding:15px;border-radius:10px;">💖 LOVE</div>
      <div style="background:white;padding:15px;border-radius:10px;">🌹 ROSE</div>
    </div>
    <button onclick="nextPage(4)">OK</button>
  </section>

  <!-- Page 4 -->
  <section id="page4" style="background:#ffd6e7;">
    <h1>MY PROMISE TO YOU 💍</h1>
    <p style="background:white;color:#333;padding:20px;border-radius:15px;margin-bottom:15px;">
      MEIN YE PROMISE NHI KAR SAKTA KI MEIN GUSSA NHI KRUNGA...<br>
      BUT I CAN PROMISE I WILL BE A GOOD LISTENER TO YOU ❤️<br>
      I WILL UNDERSTAND YOU, AND LOVE YOU MORE EACH DAY 💕.
    </p>
    <p style="background:white;color:#333;padding:20px;border-radius:15px;">
      YOU ARE THE MOST PRECIOUS PERSON IN MY LIFE 🌎.<br>
      YOUR SMILE IS MY HAPPINESS 😊💖.<br>
      I LOVE YOU VERY VERY MUCH, FOREVER INFINITY ♾️❤️.
    </p>
    <h2>💖💖💖</h2>
  </section>

  <script>
    let currentPage = 1;
    function nextPage(n) {
      document.getElementById("page" + currentPage).classList.remove("active");
      document.getElementById("page" + n).classList.add("active");
      currentPage = n;
    }
    function badDay() {
      document.getElementById("badMessage").style.display = "block";
    }
    // Hearts floating animation
    const heartsContainer = document.querySelector('.hearts');
    function createHeart() {
      const heart = document.createElement('div');
      heart.classList.add('heart');
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = (5 + Math.random() * 5) + "s";
      heartsContainer.appendChild(heart);
      setTimeout(() => heart.remove(), 10000);
    }
    setInterval(createHeart, 400);
  </script>
</body>
</html>
