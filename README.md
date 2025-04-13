<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Happy New Year 2082</title>
  <style>
    @import url('https://fonts.googleapis.com/css?family=Montserrat:700|Pacifico');

    *, *:after, *:before {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      -webkit-transition: all 100ms ease-in;
      transition: all 100ms ease-in;
    }

    html, body {
      background: linear-gradient(135deg, #222048 0%, #1a1838 50%, #0e0c24 100%);
      height: 100%;
      overflow: hidden;
    }

    /* New Background Elements */
    .stars {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
    }

    .star {
      position: absolute;
      background-color: #fff;
      border-radius: 50%;
      animation: twinkle var(--duration) infinite ease-in-out;
    }

    @keyframes twinkle {
      0%, 100% { opacity: 0.2; }
      50% { opacity: 1; }
    }

    .confetti {
      position: absolute;
      width: 10px;
      height: 10px;
      background-color: #f48fb1;
      opacity: 0;
      animation: confetti-fall 5s linear infinite;
    }

    @keyframes confetti-fall {
      0% {
        transform: translateY(-100px) rotate(0deg);
        opacity: 1;
      }
      100% {
        transform: translateY(100vh) rotate(360deg);
        opacity: 0;
      }
    }

    .glow-effect {
      position: absolute;
      width: 200vw;
      height: 200vh;
      background: radial-gradient(circle at center, rgba(122, 143, 232, 0.1) 0%, transparent 70%);
      top: -50vh;
      left: -50vw;
      z-index: -1;
      animation: pulse 8s infinite alternate;
    }

    @keyframes pulse {
      0% { transform: scale(0.8); opacity: 0.5; }
      100% { transform: scale(1.2); opacity: 0.8; }
    }

    /* Existing styles with responsive adjustments */
    .feliz {
      width: 100%;
      font-family: 'Pacifico', cursive;
      font-size: clamp(40px, 10vw, 100px);
      font-weight: 700;
      color: #f48fb1;
      text-align: center;
      position: absolute;
      top: 50%;
      opacity: 0;
      animation: vem_feliz 2s ease-in-out 7s forwards;
      text-shadow: 0 0 10px rgba(244, 143, 177, 0.7);
      z-index: 10;
    }

    .ano_novo {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;
      overflow: hidden;
      padding: 200px 100px 0px 0px;
    }

    .ano_novo > span {
      font-family: 'Montserrat', sans-serif;
      font-size: clamp(60px, 15vw, 175px);
      font-weight: 700;
      color: #7a8fe8;
      text-shadow: 0 0 15px rgba(122, 143, 232, 0.5);
    }

    span.seis {
      position: absolute;
      top: 50%;
      right: 50%;
      margin-right: -210px;
      animation: vai_2016 5s ease-in-out 5s forwards;
    }

    span.sete {
      position: absolute;
      right: 0%;
      margin-right: -237px;
      animation: vem_2017 6s ease-in-out forwards;
    }

    span.sete:before {
      content: '';
      width: 0px;
      height: 6px;
      display: block;
      border-radius: 3px;
      background: #7a8fe8;
      transform: rotate(0deg);
      transform-origin: left top;
      position: absolute;
      top: 55px;
      left: 10px;
      z-index: -1;
      animation: entrega_balao 1s ease-in-out 4s;
    }

    .balao {
      width: clamp(60px, 10vw, 100px);
      height: clamp(60px, 10vw, 100px);
      display: block;
      background: #e8d57a;
      border-radius: 50%;
      position: absolute;
      top: 50%;
      margin-top: -165px;
      right: 0%;
      margin-right: -200px;
      animation: vem_e_vai_balao 10s ease-in-out forwards;
      box-shadow: 0 0 20px rgba(232, 213, 122, 0.6);
    }

    .balao:before {
      content: '';
      width: 0;
      height: 0;
      border-style: solid;
      border-width: 0 10px 20px 10px;
      border-color: transparent transparent #b19b32 transparent;
      position: absolute;
      left: 50%;
      margin-left: -10px;
      bottom: -10px;
      z-index: -1;
    }

    .balao:after {
      content: '';
      width: 4px;
      height: 100px;
      display: block;
      background: #fff;
      border-radius: 0px 0px 3px 3px;
      position: absolute;
      left: 50%;
      margin-left: -2px;
      bottom: -110px;
    }

    .fogos {
      width: 100%;
      height: 100%;
      display: block;
      position: absolute;
      top: 0;
      left: 0;
      overflow: hidden;
    }

    .fogos > div {
      border: 2px solid #fff;
      position: absolute;
      opacity: 0;
      animation: solta_fogos 1.5s ease-in-out 8s forwards;
    }

    .fogos > div.f1 {
      left: 20%;
      top: 40%;
    }

    .fogos > div.f2 {
      left: 15%;
      top: 70%;
    }

    .fogos > div.f3 {
      right: 20%;
      top: 40%;
    }

    .fogos > div.f4 {
      right: 15%;
      top: 70%;
    }

    .fogos > div span {
      width: 6px;
      height: 6px;
      display: block;
      position: absolute;
      top: 0;
      left: 0;
      opacity: 0;
      animation: estoura_fogos 0.5s ease-in-out 9s forwards;
    }

    .fogos > div span:nth-child(1) {
      transform: rotate(0deg);
    }

    .fogos > div span:nth-child(2) {
      transform: rotate(120deg);
    }

    .fogos > div span:nth-child(3) {
      transform: rotate(240deg);
    }

    .fogos > div span:before {
      content: '';
      width: 2px;
      height: 50px;
      display: block;
      background: #f5cc06;
      position: absolute;
      top: -60px;
      left: 2px;
    }

    .fogos > div span:after {
      content: '';
      width: 2px;
      height: 50px;
      display: block;
      background: #f5cc06;
      position: absolute;
      bottom: -60px;
      left: 2px;
    }

    .fogos > div span i:before {
      content: '';
      width: 3px;
      height: 3px;
      display: block;
      border-radius: 50%;
      background: #fff;
      position: absolute;
      top: -15px;
      left: 10px;
    }

    .fogos > div span i:after {
      content: '';
      width: 3px;
      height: 3px;
      display: block;
      border-radius: 50%;
      background: #fff;
      position: absolute;
      top: -15px;
      right: 10px;
    }

    /* New floating elements */
    .floating-element {
      position: absolute;
      opacity: 0.6;
      animation: float 15s infinite linear;
    }

    @keyframes float {
      0% { transform: translateY(0) rotate(0deg); }
      50% { transform: translateY(-50px) rotate(180deg); }
      100% { transform: translateY(0) rotate(360deg); }
    }

    /* Responsive adjustments */
    @media (max-width: 768px) {
      .ano_novo {
        padding: 150px 50px 0px 0px;
      }
      
      span.seis {
        margin-right: -150px;
      }
      
      span.sete {
        margin-right: -170px;
      }
      
      .balao {
        margin-right: -150px;
      }
    }

    @keyframes vem_2017 {
      0% { right: 0%; }
      66.6666% { right: 50%; margin-right: -300px; }
      90% { right: 50%; margin-right: -300px; }
      100% { right: 50%; }
    }

    @keyframes vem_e_vai_balao {
      0% { right: 0%; }
      40% { right: 50%; margin-right: -300px; }
      50% { right: 50%; margin-right: -200px; top: 50%; }
      100% { top: -100%; right: 50%; }
    }

    @keyframes entrega_balao {
      0% { transform: rotate(-30deg); width: 40px; }
      100% { transform: rotate(-150deg); width: 70px; }
    }

    @keyframes vai_2016 {
      0% { top: 50%; }
      100% { top: -100%; }
    }

    @keyframes vem_feliz {
      0% { margin-top: 0px; opacity: 0; }
      100% { margin-top: -200px; opacity: 1; }
    }

    @keyframes solta_fogos {
      0% {
        margin-top: 100%;
        opacity: 0;
        width: 2px;
        height: 30px;
        display: block;
        border-radius: 50%;
      }
      75% {
        margin-top: 0%;
        opacity: 1;
        width: 2px;
        height: 30px;
        display: block;
        border-radius: 50%;
      }
      80% {
        margin-top: 0px;
        margin-left: 0px;
        opacity: 1;
        width: 10px;
        height: 10px;
        display: block;
        border-radius: 50%;
        transform: scale(0.2);
      }
      100% {
        opacity: 1;
        width: 10px;
        height: 10px;
        display: block;
        border-radius: 50%;
        transform: scale(1);
      }
    }

    @keyframes estoura_fogos {
      0% { opacity: 0; }
      100% { opacity: 1; }
    }
  </style>
</head>
<body>
  <!-- New background elements -->
  <div class="stars" id="stars"></div>
  <div class="glow-effect"></div>
  
  <!-- Existing content -->
  <div class="feliz">Happy new year Babina</div>
  <div class="ano_novo">
    <span>208</span>
    <span class="seis">1</span>
    <span class="sete">2</span>
    <div class="balao"></div>
  </div>
  <div class="fogos">
    <div class="f1"><span><i></i></span><span><i></i></span><span><i></i></span></div>
    <div class="f2"><span><i></i></span><span><i></i></span><span><i></i></span></div>
    <div class="f3"><span><i></i></span><span><i></i></span><span><i></i></span></div>
    <div class="f4"><span><i></i></span><span><i></i></span><span><i></i></span></div>
  </div>
  
  <!-- New floating elements -->
  <div class="floating-element" style="top:20%; left:10%; width:30px; height:30px; background:rgba(244, 143, 177, 0.4); border-radius:50%; animation-delay:0s;"></div>
  <div class="floating-element" style="top:30%; right:15%; width:40px; height:40px; background:rgba(122, 143, 232, 0.4); border-radius:50%; animation-delay:2s;"></div>
  <div class="floating-element" style="top:70%; left:20%; width:25px; height:25px; background:rgba(232, 213, 122, 0.4); border-radius:50%; animation-delay:4s;"></div>
  
  <script>
    // Create stars
    const starsContainer = document.getElementById('stars');
    for (let i = 0; i < 100; i++) {
      const star = document.createElement('div');
      star.className = 'star';
      star.style.width = `${Math.random() * 3 + 1}px`;
      star.style.height = star.style.width;
      star.style.left = `${Math.random() * 100}%`;
      star.style.top = `${Math.random() * 100}%`;
      star.style.setProperty('--duration', `${Math.random() * 3 + 2}s`);
      starsContainer.appendChild(star);
    }
    
    // Create confetti
    for (let i = 0; i < 50; i++) {
      const confetti = document.createElement('div');
      confetti.className = 'confetti';
      confetti.style.left = `${Math.random() * 100}%`;
      confetti.style.animationDelay = `${Math.random() * 5}s`;
      confetti.style.backgroundColor = `hsl(${Math.random() * 360}, 100%, 70%)`;
      confetti.style.width = `${Math.random() * 8 + 5}px`;
      confetti.style.height = `${Math.random() * 8 + 5}px`;
      document.body.appendChild(confetti);
    }
  </script>
</body>
</html>
