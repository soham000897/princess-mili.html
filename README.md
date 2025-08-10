# princess-mili.html
I love you Mili 💌
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>For Princess Mili — King Soham</title>

<!-- Fonts (system fallback included) -->
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&family=Dancing+Script:wght@400;700&display=swap" rel="stylesheet">

<style>
  :root{
    --accent:#ff6fb5;
    --accent-2:#ff7fc9;
    --glass: rgba(255,255,255,0.08);
    --white:#fff;
    --soft:#ffeef8;
    --text-deep:#9b2168;
    --bg1:#6a00f4;
    --bg2:#4f97ff;
    --bg3:#b88cff;
  }
  *{box-sizing:border-box}
  html,body{height:100%; margin:0; -webkit-font-smoothing:antialiased; -moz-osx-font-smoothing:grayscale;}
  body{
    font-family: 'Poppins', system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
    background: radial-gradient(1200px 600px at 10% 10%, rgba(255,255,255,0.06), transparent 8%),
                linear-gradient(135deg, var(--bg1) 0%, var(--bg2) 50%, var(--bg3) 100%);
    color: var(--white);
    min-height:100vh;
    display:flex;
    align-items:center;
    justify-content:center;
    overflow:hidden;
  }

  /* container */
  .wrap{
    width:100%;
    max-width:760px;
    height:92vh;
    margin:auto;
    padding:28px;
    display:flex;
    flex-direction:column;
    align-items:center;
    justify-content:center;
    gap:20px;
    border-radius:20px;
    position:relative;
    backdrop-filter: blur(6px) saturate(1.05);
    box-shadow: 0 10px 40px rgba(10,10,30,0.35);
  }

  /* page card */
  .card{
    width:100%;
    max-width:680px;
    padding:26px;
    border-radius:18px;
    background: linear-gradient(180deg, rgba(255,255,255,0.06), rgba(255,255,255,0.03));
    box-shadow: 0 6px 20px rgba(0,0,0,0.28);
    display:flex;
    flex-direction:column;
    align-items:center;
    gap:18px;
    transform-origin:center;
  }

  h1{
    margin:0;
    font-family: 'Dancing Script', 'Poppins', cursive;
    font-size:clamp(20px,4.4vw,36px);
    color:var(--white);
    text-shadow: 0 8px 30px rgba(0,0,0,0.35);
    letter-spacing:0.6px;
  }
  p.lead{
    margin:0;
    font-size:14px;
    color:rgba(255,255,255,0.9);
  }

  /* pages (flow) */
  .page{ display:none; width:100%; align-items:center; justify-content:center; flex-direction:column; gap:16px; padding:6px; }
  .page.active{ display:flex; animation:fadeIn .45s ease both; }

  @keyframes fadeIn { from {opacity:0; transform:translateY(8px);} to {opacity:1; transform:translateY(0);} }

  .row{ display:flex; gap:12px; flex-wrap:wrap; justify-content:center; margin-top:6px; }

  /* Buttons */
  .btn{
    --btn-bg: linear-gradient(180deg, rgba(255,255,255,0.98), rgba(255,255,255,0.92));
    background: var(--btn-bg);
    color:#9b2168;
    border:0;
    padding:12px 22px;
    border-radius:14px;
    font-size:16px;
    box-shadow: 0 12px 30px rgba(0,0,0,0.28), 0 2px 0 rgba(255,255,255,0.04) inset;
    cursor:pointer;
    min-width:140px;
    transition: transform .18s cubic-bezier(.2,.9,.3,1), box-shadow .18s, filter .18s;
    font-weight:700;
  }
  .btn:hover{ transform:translateY(-4px) scale(1.01); box-shadow: 0 18px 38px rgba(0,0,0,0.36); filter:brightness(1.03); }
  .btn.ghost{
    background: transparent;
    border: 1px solid rgba(255,255,255,0.12);
    color:var(--white);
    box-shadow:none;
    min-width:120px;
  }

  /* glowing accent button (primary) */
  .btn.primary{
    background: linear-gradient(90deg, var(--accent) 0%, var(--accent-2) 100%);
    color: white;
    min-width:150px;
    box-shadow: 0 12px 30px rgba(167,45,131,0.28), 0 0 30px rgba(255,127,185,0.12);
    border: none;
    text-shadow: 0 2px 6px rgba(0,0,0,0.25);
  }
  .btn.primary:after{
    content:'';
    position:absolute;
    pointer-events:none;
  }

  /* message modal */
  .msg{
    position:fixed;
    left:50%;
    top:12%;
    transform:translateX(-50%);
    background:linear-gradient(180deg, rgba(255,255,255,0.98), rgba(255,255,255,0.95));
    color:var(--text-deep);
    padding:14px 18px;
    border-radius:12px;
    box-shadow:0 12px 40px rgba(0,0,0,0.35);
    font-weight:700;
    display:none;
    z-index:60;
    max-width:92%;
    text-align:center;
    font-size:15px;
  }

  /* envelope */
  .final-area{ width:100%; display:flex; gap:20px; align-items:center; justify-content:center; flex-direction:column; padding:6px;}
  .envelope-wrap{ width:190px; height:140px; perspective:900px; }
  .envelope{ width:100%; height:100%; position:relative; transform-style:preserve-3d; transition:transform .85s cubic-bezier(.2,.9,.3,1); cursor:pointer; }
  .flap{ position:absolute; left:0; right:0; top:0; height:56%; background:linear-gradient(180deg,#ffd0e8,#ff7fc9); border-radius:10px; transform-origin: top center; backface-visibility:hidden; box-shadow: 0 8px 26px rgba(0,0,0,0.28); }
  .body{ position:absolute; left:6px; right:6px; bottom:6px; top:40%; background:linear-gradient(180deg,#fff2fb,#ffe8f8); border-radius:10px; box-shadow: inset 0 1px 0 rgba(255,255,255,0.8); display:flex; align-items:center; justify-content:center; }
  .paper{ width:84%; height:74%; background:linear-gradient(180deg,#fff,#fffefc); border-radius:8px; transform:translateY(22%) scale(.96); box-shadow:0 10px 18px rgba(0,0,0,0.12); opacity:0; transition: all .9s ease; display:flex; align-items:center; justify-content:center; padding:10px; font-weight:800; color:var(--text-deep); font-size:15px; text-align:center; }
  .envelope.open .flap{ transform:rotateX(-180deg) translateY(-6px); }
  .envelope.open .paper{ transform:translateY(0) scale(1); opacity:1; }

  /* heartbeat text */
  .heartbeat{
    display:inline-block;
    animation: heartbeat 1.1s infinite;
    transform-origin:center;
  }
  @keyframes heartbeat{
    0%{ transform:scale(1); }
    25%{ transform:scale(1.06); }
    40%{ transform:scale(0.98); }
    60%{ transform:scale(1.04); }
    100%{ transform:scale(1); }
  }

  /* corner name (glowing) */
  .corner-text{
    position:fixed;
    right:18px;
    bottom:14px;
    font-size:13px;
    color: #ffdff4;
    letter-spacing:0.6px;
    font-weight:700;
    padding:8px 12px;
    border-radius:10px;
    background: linear-gradient(90deg, rgba(255,255,255,0.03), rgba(255,255,255,0.02));
    box-shadow: 0 6px 30px rgba(167,45,131,0.14), 0 0 28px rgba(255,127,185,0.06);
    text-shadow: 0 6px 26px rgba(167,45,131,0.18);
  }
  .corner-text .glow{ color:#fff; text-shadow: 0 0 12px rgba(255,215,245,0.9); }

  /* small helpers */
  .small { font-size:13px; color:rgba(255,255,255,0.92); }
  .muted { color: rgba(255,255,255,0.7); font-size:13px; }

  /* confetti canvas */
  canvas#confettiCanvas{ position:fixed; inset:0; width:100%; height:100%; pointer-events:none; z-index:55; }

  /* responsive */
  @media (max-width:480px){
    .wrap{ padding:16px; height:100vh; border-radius:0; }
    .envelope-wrap{ width:150px; height:110px; }
    .btn{ min-width:120px; padding:10px 14px; font-size:15px; }
    h1{ font-size:20px; }
  }
</style>
</head>
<body>

  <!-- confetti canvas -->
  <canvas id="confettiCanvas"></canvas>

  <div class="wrap card" role="main" aria-live="polite">

    <!-- PAGE 1 -->
    <section id="p1" class="page active" aria-labelledby="q1">
      <h1 id="q1">Do you want to continue? 😇👉👈</h1>
      <p class="lead">A little surprise for Princess Mili ✨</p>
      <div class="row">
        <button class="btn primary" id="p1yes" aria-label="Yes continue">Yes 💖</button>
      </div>
    </section>

    <!-- PAGE 2 -->
    <section id="p2" class="page" aria-labelledby="q2">
      <h1 id="q2">What's your bestu's favorite? 🤔</h1>
      <p class="muted">Choose the right one to continue...</p>
      <div class="row" role="list">
        <button class="btn ghost" id="opt-choc" role="listitem">Chocolate 🍫</button>
        <button class="btn" id="opt-you" role="listitem">You 🥰</button>
        <button class="btn ghost" id="opt-other" role="listitem">Other 🤨</button>
      </div>
    </section>

    <!-- PAGE 3 -->
    <section id="p3" class="page" aria-labelledby="q3">
      <h1 id="q3">Who is cute in the world?</h1>
      <p class="muted">Pick carefully 😉</p>
      <div class="row">
        <button class="btn primary" id="opt-you2">You 💖</button>
        <button class="btn ghost" id="opt-other2">Other 🙈</button>
      </div>
    </section>

    <!-- PAGE 4 (FINAL) -->
    <section id="p4" class="page" aria-labelledby="q4">
      <div class="final-area">
        <h1 class="heartbeat">I love you princess Mili 👑</h1>
        <p class="small">Tap the envelope to open your special note 💌</p>

        <div class="envelope-wrap" aria-hidden="true">
          <div id="envelope" class="envelope" tabindex="0" role="button" aria-label="Open envelope">
            <div class="flap"></div>
            <div class="body">
              <div id="paper" class="paper">I love you princess Mili 👑</div>
            </div>
          </div>
        </div>

        <p class="muted">Send this to Princess Mili and make her smile 😊</p>
      </div>
    </section>

  </div>

  <!-- small floating corner name -->
  <div class="corner-text" aria-hidden="true"><span class="glow">King Soham</span> × Princess Mili</div>

  <!-- in-page message -->
  <div id="msg" class="msg" role="status" aria-live="polite"></div>

  <!-- sounds (CDN) -->
  <audio id="bg" src="https://cdn.pixabay.com/download/audio/2021/09/28/audio_9b5d4b3d4e.mp3?filename=happy-music.mp3" preload="auto"></audio>
  <audio id="love" src="https://cdn.pixabay.com/download/audio/2021/09/01/audio_c7f2b02c4d.mp3?filename=romantic.mp3" preload="auto"></audio>
  <audio id="pop" src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_2f54f05a8a.mp3?filename=pop.mp3" preload="auto"></audio>

  <!-- confetti library -->
  <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>

<script>
/* ---------- helpers ---------- */
const showMsg = (text, ms=1200) => {
  const m = document.getElementById('msg');
  m.textContent = text;
  m.style.display = 'block';
  clearTimeout(m._t);
  m._t = setTimeout(()=>{ m.style.display='none'; }, ms);
};

/* confetti util */
const confettiCanvas = document.getElementById('confettiCanvas');
const confettiOpts = (count=40) => ({
  particleCount: count,
  spread: 70,
  ticks: 160,
  origin: { y: 0.6 }
});
function popConfetti(bursts=1){
  for(let i=0;i<bursts;i++){
    confetti(confettiOpts(30));
  }
}

/* sounds safe play */
const S_bg = document.getElementById('bg');
const S_love = document.getElementById('love');
const S_pop = document.getElementById('pop');
function safePlay(el){
  try{ el.currentTime = 0; el.play().catch(()=>{}); }catch(e){}
}

/* page flow */
const showPage = (id) => {
  document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));
  const el = document.getElementById(id);
  if(el) el.classList.add('active');
  window.scrollTo({top:0,behavior:'smooth'});
};

/* prevent selection on mobile */
document.addEventListener('touchstart', ()=>{}, {passive:true});

/* ---------- interactions ---------- */
/* PAGE 1 */
document.getElementById('p1yes').addEventListener('click', ()=>{
  popConfetti(2);
  safePlay(S_pop);
  safePlay(S_bg);
  setTimeout(()=> showPage('p2'), 700);
});

/* PAGE 2 */
document.getElementById('opt-choc').addEventListener('click', ()=> showMsg('Try again 😜', 1100));
document.getElementById('opt-other').addEventListener('click', ()=> showMsg('Try again 😜', 1100));

document.getElementById('opt-you').addEventListener('click', ()=>{
  popConfetti(1);
  safePlay(S_pop);
  setTimeout(()=>{
    showMsg('Sweet choice! 💖', 1200);
    popConfetti(1);
    setTimeout(()=> showPage('p3'), 1100);
  }, 700);
});

/* PAGE 3 */
document.getElementById('opt-other2').addEventListener('click', ()=> showMsg('Try again 🙈', 1200));
document.getElementById('opt-you2').addEventListener('click', ()=>{
  popConfetti(2);
  safePlay(S_pop);
  setTimeout(()=>{
    showMsg('You picked the best! 💖', 1200);
    safePlay(S_love);
    popConfetti(2);
    setTimeout(()=> showPage('p4'), 1100);
  }, 800);
});

/* FINAL: envelope open/close */
const envelope = document.getElementById('envelope');
const paper = document.getElementById('paper');
function openEnvelope(){
  envelope.classList.add('open');
  popConfetti(3);
  safePlay(S_pop);
}
function closeEnvelope(){
  envelope.classList.remove('open');
}
envelope.addEventListener('click', ()=>{
  if(envelope.classList.contains('open')) closeEnvelope();
  else openEnvelope();
});
envelope.addEventListener('keydown', (e)=>{ if(e.key === 'Enter' || e.key === ' ') { e.preventDefault(); envelope.click(); } });

/* auto-open on arriving final page */
const observer = new MutationObserver((entries)=>{
  entries.forEach(e=>{
    if(e.target.classList && e.target.classList.contains('page') && e.target.classList.contains('active')){
      if(e.target.id === 'p4'){
        setTimeout(()=> openEnvelope(), 700);
      }
    }
  });
});
document.querySelectorAll('.page').forEach(p=> observer.observe(p, {attributes:true}));

/* friendly autoplay fallback */
let interacted = false;
const firstTouch = ()=>{ interacted = true; try{ S_bg.volume = 0.9; }catch(e){}; window.removeEventListener('touchstart', firstTouch); };
window.addEventListener('touchstart', firstTouch, {passive:true});

</script>
</body>
</html>
