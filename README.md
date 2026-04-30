<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ms Kath De Leon</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

<div class="container">
  <div class="glass-card">
    <!-- Top Bar -->
    <div class="editor-bar">
      <div class="dots">
        <span class="red"></span>
        <span class="yellow"></span>
        <span class="green"></span>
      </div>
      <div class="filename">style.css</div>
    </div>

    <!-- Custom Message -->
    <pre class="code">
<span class="comment">/* Hello babyyy jk */</span>

i hope u appreciate this hehe
    </pre>

    <!-- Button -->
    <button onclick="flipCard()">Open</button>
  </div>
</div>

<!-- Flip Card Popup -->
<div class="popup-card" id="popupCard">
  <div class="flip-card-inner">
    <div class="flip-card-front">
      <div class="ribbon">💝</div>
      <h2>Surprise!</h2>
    </div>
    <div class="flip-card-back">
      <p id="message1">
        I just want you to feel comfortable and peaceful.<br>
        No pressure to reply, I just hope you rest well.<br>
        Take care of yourself, okay?<br>
        When u need me andito lang ako boii 💖
      </p>

      <p id="message2" class="hidden">
        I miss u and please kapag dumating yung point<br>
        na hindi na tayo nag uusap sana wag HAHAA<br>
        nag ooverthink lang ako 💕
      </p>

      <!-- Next button -->
      <button id="nextBtn" onclick="showNext()">Next ➜</button>
    </div>
  </div>
</div>

<!-- Hearts explosion container -->
<div class="heart-explosion" id="heartExplosion"></div>

<script>
  function flipCard() {
    const popup = document.getElementById("popupCard");
    popup.classList.toggle("show");

    if (popup.classList.contains("show")) {
      explodeHearts();
      // reset to first message
      document.getElementById("message1").style.display = "block";
      document.getElementById("message2").classList.add("hidden");
      document.getElementById("nextBtn").style.display = "inline-block";
    }
  }

  function showNext() {
    document.getElementById("message1").style.display = "none";
    const msg2 = document.getElementById("message2");
    msg2.classList.remove("hidden");
    msg2.classList.add("fadeInScale"); // trigger animation
    document.getElementById("nextBtn").style.display = "none";
  }

  function explodeHearts() {
    const explosion = document.getElementById("heartExplosion");
    explosion.innerHTML = "";
    for (let i = 0; i < 50; i++) {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.top = Math.random() * 100 + "vh";
      heart.style.background = ["#ffb6c1","#ff69b4","#ffc1cc"][Math.floor(Math.random()*3)];
      heart.style.width = heart.style.height = (10 + Math.random()*20) + "px";
      heart.style.animationDelay = (Math.random() * 2) + "s";
      explosion.appendChild(heart);
    }
  }
</script>

</body>
</html>
