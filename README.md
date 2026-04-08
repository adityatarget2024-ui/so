# so
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>For Tashuuu ❤️</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body {
      min-height: 100vh;
      font-family: Georgia, 'Times New Roman', serif;
      background: linear-gradient(160deg, #fff0f5 0%, #ffe4ef 40%, #fff5f8 100%);
      color: #5a2030;
      overflow-x: hidden;
    }
    /* Floating hearts */
    .floating-heart {
      position: fixed;
      bottom: -2rem;
      pointer-events: none;
      z-index: 0;
      animation: float-up linear infinite;
      user-select: none;
    }
    @keyframes float-up {
      0%   { transform: translateY(0) rotate(0deg) scale(1); opacity: 1; }
      100% { transform: translateY(-110vh) rotate(20deg) scale(0.4); opacity: 0; }
    }
    @keyframes heartbeat {
      0%, 100% { transform: scale(1); }
      14%       { transform: scale(1.3); }
      28%       { transform: scale(1); }
      42%       { transform: scale(1.3); }
      70%       { transform: scale(1); }
    }
    @keyframes shimmer {
      0%, 100% { opacity: 0.7; }
      50%       { opacity: 1; }
    }
    @keyframes wiggle {
      0%, 100% { transform: rotate(-3deg); }
      50%       { transform: rotate(3deg); }
    }
    @keyframes sparkle {
      0%, 100% { transform: scale(0) rotate(0deg); opacity: 0; }
      50%       { transform: scale(1) rotate(180deg); opacity: 1; }
    }
    @keyframes fade-in-up {
      from { opacity: 0; transform: translateY(30px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    /* Layout */
    .wrapper {
      position: relative;
      z-index: 10;
      max-width: 680px;
      margin: 0 auto;
      padding: 4rem 1.5rem 3rem;
    }
    /* Header */
    .header {
      text-align: center;
      margin-bottom: 3rem;
      animation: fade-in-up 0.8s ease-out both;
    }
    .big-heart {
      font-size: 4rem;
      display: inline-block;
      animation: heartbeat 1.5s ease-in-out infinite;
    }
    .title {
      font-size: 2.4rem;
      font-weight: bold;
      color: #c0395a;
      letter-spacing: 0.03em;
      margin-top: 0.4rem;
    }
    .subtitle {
      font-size: 1.1rem;
      color: #d4607a;
      font-style: italic;
      margin-top: 0.3rem;
      animation: shimmer 2s ease-in-out infinite;
    }
    .emoji-row {
      margin-top: 0.8rem;
      font-size: 1.6rem;
      display: flex;
      justify-content: center;
      gap: 0.5rem;
    }
    .wiggle { display: inline-block; animation: wiggle 2s ease-in-out infinite; }
    .wiggle.d1 { animation-delay: 0.3s; }
    .wiggle.d2 { animation-delay: 0.6s; }
    /* Card */
    .card {
      background: rgba(255,255,255,0.85);
      backdrop-filter: blur(10px);
      border-radius: 1.5rem;
      padding: 2.5rem 2.5rem;
      box-shadow: 0 8px 40px rgba(192,57,90,0.12);
      border: 1.5px solid rgba(220,90,120,0.15);
      position: relative;
      overflow: hidden;
    }
    .card-deco-tr {
      position: absolute; top: 1rem; right: 1.2rem;
      font-size: 2rem; opacity: 0.18;
      animation: wiggle 2s ease-in-out infinite;
    }
    .card-deco-bl {
      position: absolute; bottom: 1rem; left: 1.2rem;
      font-size: 2rem; opacity: 0.18;
      animation: wiggle 2.2s ease-in-out infinite 0.4s;
    }
    .para {
      line-height: 1.9;
      font-size: 1.07rem;
      color: #5a2030;
      transition: opacity 0.7s ease, transform 0.7s ease;
      opacity: 0;
      transform: translateY(22px);
    }
    .para + .para { margin-top: 1.4rem; }
    .para.visible {
      opacity: 1;
      transform: translateY(0);
    }
    /* Button section */
    .question {
      text-align: center;
      margin-top: 3rem;
      animation: fade-in-up 0.8s ease-out both;
    }
    .question p {
      font-size: 1.05rem;
      color: #c0395a;
      font-style: italic;
      margin-bottom: 1.2rem;
    }
    .forgive-btn {
      padding: 0.9rem 2.5rem;
      border-radius: 999px;
      border: none;
      background: linear-gradient(135deg, #e8527a, #c0395a);
      color: #fff;
      font-size: 1.1rem;
      font-family: Georgia, serif;
      font-weight: 600;
      cursor: pointer;
      box-shadow: 0 4px 20px rgba(192,57,90,0.35);
      transition: transform 0.2s ease, box-shadow 0.2s ease;
    }
    .forgive-btn:hover  { transform: scale(1.07); box-shadow: 0 6px 28px rgba(192,57,90,0.45); }
    .forgive-btn:active { transform: scale(0.95); }
    /* Forgiven card */
    .forgiven-card {
      display: none;
      margin-top: 3rem;
      text-align: center;
      background: linear-gradient(135deg, #fff0f5, #ffe4ef);
      border: 1.5px solid rgba(220,90,120,0.25);
      border-radius: 1.5rem;
      padding: 2rem 2rem;
      box-shadow: 0 6px 30px rgba(192,57,90,0.12);
      animation: fade-in-up 0.7s ease-out both;
    }
    .forgiven-card.show { display: block; }
    .forgiven-card .big-heart-2 {
      font-size: 3.2rem;
      display: inline-block;
      animation: heartbeat 1.5s ease-in-out infinite;
    }
    .forgiven-card h2 {
      font-size: 1.6rem;
      font-weight: bold;
      color: #c0395a;
      margin: 0.5rem 0 0.4rem;
    }
    .forgiven-card p {
      font-size: 1.02rem;
      line-height: 1.8;
      color: #7a3045;
      font-style: italic;
    }
    .forgiven-emojis {
      margin-top: 0.8rem;
      font-size: 1.8rem;
      display: flex;
      justify-content: center;
      gap: 0.5rem;
    }
    /* Footer */
    .footer {
      text-align: center;
      margin-top: 3rem;
      font-size: 0.9rem;
      color: #c0859a;
      font-style: italic;
    }
    /* Sparkle stars */
    .sparkle {
      position: fixed;
      pointer-events: none;
      color: #f4a8c0;
      animation: sparkle 2s ease-in-out infinite;
      z-index: 0;
    }
  </style>
</head>
<body>
<!-- Sparkle stars -->
<span class="sparkle" style="top:8%;left:5%;font-size:0.9rem;animation-delay:0s">✦</span>
<span class="sparkle" style="top:12%;right:8%;font-size:0.7rem;animation-delay:0.3s">✦</span>
<span class="sparkle" style="top:30%;left:2%;font-size:0.8rem;animation-delay:0.6s">✦</span>
<span class="sparkle" style="top:50%;right:3%;font-size:0.6rem;animation-delay:0.9s">✦</span>
<span class="sparkle" style="top:70%;left:4%;font-size:0.9rem;animation-delay:1.2s">✦</span>
<span class="sparkle" style="top:85%;right:6%;font-size:0.7rem;animation-delay:1.5s">✦</span>
<div class="wrapper">
  <!-- Header -->
  <div class="header">
    <div class="big-heart">❤️</div>
    <h1 class="title">Tashuuuu ❤️</h1>
    <p class="subtitle">My sweet rasmalai, this is for you.</p>
    <div class="emoji-row">
      <span class="wiggle">🌸</span>
      <span class="wiggle d1">💕</span>
      <span class="wiggle d2">🌸</span>
    </div>
  </div>
  <!-- Message card -->
  <div class="card">
    <span class="card-deco-tr">🌷</span>
    <span class="card-deco-bl">🌷</span>
    <p class="para" id="p0">
      I've been thinking about what happened and I really want to say this properly. I am truly sorry for the word I used. I know it hurt you and that honestly makes me feel really bad. You are someone very special to me, my sweet rasmalai 🍮, and the last person in the world I would ever want to disrespect or make feel bad.
    </p>
    <p class="para" id="p1">
      The truth is that when that guruveer name came up, I reacted suddenly because you know how much I dislike that person. In that moment I didn't think before speaking and the word came out in the wrong way. It was never meant for you, but for the guruverr. But I understand that even if it was a mistake, hearing that word from me must have hurt you, and for that I am really sorry.
    </p>
    <p class="para" id="p2">
      You mean a lot to me, and I respect you more than you think. I hate that my careless reaction made you feel upset or disrespected. If I could take that moment back, I absolutely would. I promise you that I will be more careful with my words because you deserve kindness, respect, and love from me, not hurt.
    </p>
    <p class="para" id="p3">
      Please don't think that I see you in any negative way. In my eyes you are someone very sweet, important, and close to my heart. Hurting you was never my intention.
    </p>
    <p class="para" id="p4">
      I hope you can forgive me. I really am sorry, Tashuu. ❤️🥺
    </p>
  </div>
  <!-- Forgiveness button -->
  <div class="question" id="questionSection" style="display:none;">
    <p>Will you forgive me, Tashuu? 🥺</p>
    <button class="forgive-btn" onclick="onForgive()">Yes, I forgive you ❤️</button>
  </div>
  <!-- Forgiven message -->
  <div class="forgiven-card" id="forgivenCard">
    <div class="big-heart-2">🥰</div>
    <h2>Thank you, Tashuu ❤️</h2>
    <p>
      You are the sweetest, most special person to me. I promise to always be more careful with my words.
      You deserve all the love and kindness in the world. 🌸✨
    </p>
    <div class="forgiven-emojis">
      <span class="wiggle">💕</span>
      <span class="wiggle d1">🍮</span>
      <span class="wiggle d2">💕</span>
    </div>
  </div>
  <div class="footer">Made with all my heart, just for you. 💖</div>
</div>
<script>
  // Floating hearts
  const emojis = ["❤️","🌸","💕","🍮","💝","✨","🌷"];
  for (let i = 0; i < 18; i++) {
    const el = document.createElement("span");
    el.className = "floating-heart";
    el.textContent = emojis[Math.floor(Math.random() * emojis.length)];
    el.style.left = Math.random() * 100 + "%";
    el.style.fontSize = (Math.random() * 1.4 + 0.8) + "rem";
    el.style.animationDuration = (Math.random() * 8 + 8) + "s";
    el.style.animationDelay = (Math.random() * 5) + "s";
    document.body.appendChild(el);
  }
  // Scroll-reveal paragraphs
  const paras = document.querySelectorAll(".para");
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add("visible");
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.15 });
  paras.forEach(p => observer.observe(p));
  // Show button after 4 seconds
  setTimeout(() => {
    document.getElementById("questionSection").style.display = "block";
  }, 4000);
  // Forgive button
  function onForgive() {
    document.getElementById("questionSection").style.display = "none";
    const card = document.getElementById("forgivenCard");
    card.classList.add("show");
    card.scrollIntoView({ behavior: "smooth", block: "center" });
  }
</script>
</body>
</html>
