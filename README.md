# Training-.1
<!-- Aoi — Anime Health Companion -->
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Aoi — your health guardian</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Mochiy+Pop+One&family=M+PLUS+Rounded+1c:wght@400;500;700;800&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#FDF6FB;
    --ink:#2A2150;
    --ink-soft:#6B6391;
    --pink:#FF6FA5;
    --pink-deep:#E8488A;
    --blue:#4DA8FF;
    --mint:#3FD9B6;
    --sun:#FFD166;
    --card:#FFFFFF;
    --line:#F0E2EE;
    --shadow:0 18px 40px -22px rgba(90,40,90,.45);
    --glow:0 0 0 6px rgba(255,111,165,.12);
  }
  *{box-sizing:border-box}
  html{scroll-behavior:smooth}
  body{
    margin:0;background:
      radial-gradient(1200px 600px at 80% -10%, rgba(77,168,255,.10), transparent 60%),
      radial-gradient(900px 500px at 0% 10%, rgba(255,111,165,.12), transparent 55%),
      var(--bg);
    color:var(--ink);font-family:"M PLUS Rounded 1c",system-ui,sans-serif;
    line-height:1.55;overflow-x:hidden;
  }
  a{color:inherit}
  .wrap{max-width:1080px;margin:0 auto;padding:0 22px}
  .display{font-family:"Mochiy Pop One",sans-serif;font-weight:400}

  /* sparkle field */
  .sparkles{position:fixed;inset:0;pointer-events:none;z-index:0}
  .sparkles i{position:absolute;width:8px;height:8px;background:var(--sun);
    border-radius:50%;opacity:.0;animation:twinkle 5s ease-in-out infinite}
  @keyframes twinkle{0%,100%{opacity:0;transform:scale(.4)}50%{opacity:.8;transform:scale(1)}}

  /* nav */
  header{position:sticky;top:0;z-index:30;backdrop-filter:blur(10px);
    background:rgba(253,246,251,.78);border-bottom:1px solid var(--line)}
  nav{display:flex;align-items:center;justify-content:space-between;height:66px}
  .brand{display:flex;align-items:center;gap:10px;font-weight:800;font-size:20px}
  .brand .badge{width:34px;height:34px;border-radius:12px;
    background:linear-gradient(135deg,var(--pink),var(--blue));
    display:grid;place-items:center;color:#fff;font-family:"Mochiy Pop One";font-size:16px;
    box-shadow:var(--shadow)}
  .navlinks{display:flex;gap:26px;font-weight:500;font-size:15px}
  .navlinks a{text-decoration:none;color:var(--ink-soft);transition:color .2s}
  .navlinks a:hover{color:var(--pink-deep)}
  .pill{background:var(--ink);color:#fff;padding:9px 18px;border-radius:999px;
    font-weight:700;font-size:14px;text-decoration:none;transition:transform .15s,box-shadow .2s}
  .pill:hover{transform:translateY(-2px);box-shadow:var(--shadow)}
  @media(max-width:760px){.navlinks{display:none}}

  /* hero */
  .hero{position:relative;z-index:1;padding:54px 0 30px;
    display:grid;grid-template-columns:1.05fr .95fr;gap:30px;align-items:center}
  .eyebrow{display:inline-flex;align-items:center;gap:8px;font-weight:700;font-size:13px;
    letter-spacing:.04em;color:var(--pink-deep);background:#fff;border:1px solid var(--line);
    padding:6px 14px;border-radius:999px;box-shadow:var(--shadow)}
  .eyebrow b{color:var(--blue)}
  h1{font-family:"Mochiy Pop One";font-size:clamp(34px,5.4vw,58px);line-height:1.06;
    margin:18px 0 14px;letter-spacing:-.5px}
  h1 .grad{background:linear-gradient(120deg,var(--pink),var(--blue));
    -webkit-background-clip:text;background-clip:text;color:transparent}
  .lede{font-size:17px;color:var(--ink-soft);max-width:38ch;margin:0 0 24px}
  .cta-row{display:flex;gap:12px;flex-wrap:wrap}
  .btn{border:none;cursor:pointer;font-family:inherit;font-weight:700;font-size:15px;
    padding:13px 22px;border-radius:14px;text-decoration:none;transition:transform .15s,box-shadow .2s}
  .btn-primary{background:linear-gradient(135deg,var(--pink),var(--pink-deep));color:#fff;
    box-shadow:0 14px 26px -12px var(--pink-deep)}
  .btn-primary:hover{transform:translateY(-2px)}
  .btn-ghost{background:#fff;color:var(--ink);border:1px solid var(--line)}
  .btn-ghost:hover{transform:translateY(-2px);box-shadow:var(--shadow)}

  /* mascot stage */
  .stage{position:relative;display:grid;place-items:center;min-height:380px}
  .blob{position:absolute;width:330px;height:330px;border-radius:46% 54% 60% 40%/52% 44% 56% 48%;
    background:radial-gradient(circle at 35% 30%,#fff,rgba(255,209,102,.35) 70%,transparent);
    filter:blur(2px);animation:morph 9s ease-in-out infinite}
  @keyframes morph{0%,100%{border-radius:46% 54% 60% 40%/52% 44% 56% 48%}
    50%{border-radius:60% 40% 44% 56%/40% 60% 40% 60%}}
  .mascot{position:relative;width:300px;animation:float 4.5s ease-in-out infinite}
  @keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-14px)}}
  .blink{animation:blink 4.2s infinite}
  @keyframes blink{0%,7%,100%{transform:scaleY(1)}3.5%{transform:scaleY(.1)}}
  .speech{position:absolute;top:6px;right:-8px;background:#fff;border:2px solid var(--ink);
    border-radius:16px;padding:8px 14px;font-weight:700;font-size:13px;box-shadow:var(--shadow);
    max-width:160px;transition:opacity .3s}
  .speech:after{content:"";position:absolute;left:-9px;bottom:14px;width:14px;height:14px;
    background:#fff;border-left:2px solid var(--ink);border-bottom:2px solid var(--ink);
    transform:rotate(45deg)}

  /* sections */
  section{position:relative;z-index:1;padding:46px 0}
  .sec-head{display:flex;align-items:baseline;gap:14px;margin-bottom:22px}
  .sec-kanji{font-family:"Mochiy Pop One";font-size:30px;color:var(--pink);opacity:.85}
  .sec-head h2{font-family:"Mochiy Pop One";font-size:clamp(22px,3vw,30px);margin:0}
  .sec-head p{margin:0;color:var(--ink-soft);font-size:15px}

  /* vitals dashboard */
  .vitals{display:grid;grid-template-columns:repeat(4,1fr);gap:16px}
  .vcard{background:var(--card);border:1px solid var(--line);border-radius:20px;padding:18px;
    box-shadow:var(--shadow);position:relative;overflow:hidden}
  .vcard .ico{width:42px;height:42px;border-radius:13px;display:grid;place-items:center;
    font-size:22px;margin-bottom:10px}
  .vcard h3{margin:0;font-size:13px;color:var(--ink-soft);font-weight:700;letter-spacing:.02em}
  .vcard .num{font-family:"Mochiy Pop One";font-size:30px;margin:2px 0 0}
  .vcard .unit{font-size:13px;color:var(--ink-soft)}
  .vcard .spark{position:absolute;right:-6px;bottom:-6px;opacity:.18;font-size:64px}
  .vcard.heart .ico{background:rgba(255,111,165,.15);color:var(--pink-deep)}
  .vcard.steps .ico{background:rgba(77,168,255,.15);color:var(--blue)}
  .vcard.sleep .ico{background:rgba(120,90,255,.15);color:#7a5aff}
  .vcard.water .ico{background:rgba(63,217,182,.18);color:var(--mint)}
  @media(max-width:760px){.vitals{grid-template-columns:1fr 1fr}}

  /* ECG line */
  .ecg{margin-top:22px;background:var(--ink);border-radius:20px;padding:18px 20px;
    color:#fff;display:flex;align-items:center;gap:18px;box-shadow:var(--shadow)}
  .ecg svg{flex:1;height:60px}
  .ecg .label{font-weight:700;font-size:14px}
  .ecg .bpm{font-family:"Mochiy Pop One";font-size:26px;color:var(--pink)}
  .ecg path{stroke:var(--mint);stroke-width:3;fill:none;
    stroke-dasharray:600;stroke-dashoffset:600;animation:draw 2.4s linear infinite}
  @keyframes draw{to{stroke-dashoffset:-600}}

  /* check-in */
  .checkin{background:linear-gradient(135deg,#fff,#FFF4F9);border:1px solid var(--line);
    border-radius:24px;padding:28px;box-shadow:var(--shadow);display:grid;
    grid-template-columns:auto 1fr;gap:26px;align-items:center}
  .moods{display:flex;gap:12px;flex-wrap:wrap;margin-top:6px}
  .mood{cursor:pointer;border:2px solid var(--line);background:#fff;border-radius:16px;
    padding:12px 16px;font-size:30px;transition:transform .15s,border-color .2s,box-shadow .2s}
  .mood:hover{transform:translateY(-4px) scale(1.05)}
  .mood.active{border-color:var(--pink);box-shadow:var(--glow)}
  .reply{margin-top:16px;font-weight:700;color:var(--pink-deep);min-height:24px}
  .mini{width:120px}
  @media(max-width:620px){.checkin{grid-template-columns:1fr;text-align:center}.mini{margin:0 auto}}

  /* quests */
  .quests{display:grid;grid-template-columns:repeat(3,1fr);gap:16px}
  .quest{background:var(--card);border:1px solid var(--line);border-radius:20px;padding:20px;
    box-shadow:var(--shadow);transition:transform .2s}
  .quest:hover{transform:translateY(-5px)}
  .quest .tag{display:inline-block;font-size:11px;font-weight:700;padding:4px 10px;border-radius:999px;
    background:rgba(77,168,255,.15);color:var(--blue);margin-bottom:10px}
  .quest h3{margin:0 0 6px;font-size:17px}
  .quest p{margin:0;color:var(--ink-soft);font-size:14px}
  .quest .bar{height:8px;border-radius:999px;background:var(--line);margin-top:14px;overflow:hidden}
  .quest .bar i{display:block;height:100%;border-radius:999px;
    background:linear-gradient(90deg,var(--pink),var(--blue))}
  @media(max-width:760px){.quests{grid-template-columns:1fr}}

  /* footer */
  footer{position:relative;z-index:1;border-top:1px solid var(--line);margin-top:30px;
    padding:30px 0;color:var(--ink-soft);font-size:14px;text-align:center}
  footer b{color:var(--ink)}

  @media (prefers-reduced-motion: reduce){
    *{animation:none!important}
  }
</style>

<div class="sparkles" id="sparkles"></div>

<header>
  <nav class="wrap">
    <div class="brand"><span class="badge">葵</span> Aoi</div>
    <div class="navlinks">
      <a href="#vitals">Vitals</a>
      <a href="#checkin">Check-in</a>
      <a href="#quests">Quests</a>
      <a href="#footer">About</a>
    </div>
    <a class="pill" href="#checkin">Open app</a>
  </nav>
</header>

<main class="wrap">
  <section class="hero">
    <div>
      <span class="eyebrow">健康 · health, but make it <b>kawaii</b></span>
      <h1>Your health has a <span class="grad">guardian</span>.</h1>
      <p class="lede">Aoi watches your vitals, cheers your daily check-ins, and turns healthy habits into quests you actually want to finish.</p>
      <div class="cta-row">
        <a class="btn btn-primary" href="#checkin">Start today's check-in</a>
        <a class="btn btn-ghost" href="#vitals">See the dashboard</a>
      </div>
    </div>

    <div class="stage">
      <div class="blob"></div>
      <!-- SVG chibi mascot: Aoi -->
      <svg class="mascot" viewBox="0 0 300 320" xmlns="http://www.w3.org/2000/svg" aria-label="Aoi, the health guardian mascot">
        <!-- body -->
        <ellipse cx="150" cy="232" rx="86" ry="78" fill="#4DA8FF"/>
        <ellipse cx="150" cy="232" rx="86" ry="78" fill="url(#g1)"/>
        <!-- belly heart screen -->
        <rect x="108" y="200" width="84" height="66" rx="18" fill="#fff"/>
        <path id="hb" d="M150 224 c-9-14-30-6-30 9 c0 13 18 22 30 31 c12-9 30-18 30-31 c0-15-21-23-30-9z" fill="#FF6FA5">
          <animateTransform attributeName="transform" type="scale" additive="sum"
            values="1;1.12;1;1.12;1" dur="1.4s" repeatCount="indefinite"
            keyTimes="0;.12;.24;.36;1" transform-origin="150 240"/>
        </path>
        <!-- head -->
        <circle cx="150" cy="118" r="84" fill="#EAF4FF"/>
        <circle cx="150" cy="118" r="84" fill="url(#g2)"/>
        <!-- hair tuft -->
        <path d="M150 36 q-20 -6 -28 14 q22 -8 28 2 q6 -10 28 -2 q-8 -20 -28 -14z" fill="#5fb0ff"/>
        <!-- cheeks -->
        <circle cx="104" cy="138" r="13" fill="#FFB3CF" opacity=".8"/>
        <circle cx="196" cy="138" r="13" fill="#FFB3CF" opacity=".8"/>
        <!-- eyes -->
        <g class="blink" transform-origin="150 116">
          <ellipse cx="118" cy="116" rx="13" ry="17" fill="#2A2150"/>
          <ellipse cx="182" cy="116" rx="13" ry="17" fill="#2A2150"/>
          <circle cx="123" cy="109" r="5" fill="#fff"/>
          <circle cx="187" cy="109" r="5" fill="#fff"/>
        </g>
        <!-- smile -->
        <path d="M138 146 q12 12 24 0" stroke="#2A2150" stroke-width="4" fill="none" stroke-linecap="round"/>
        <!-- little antenna with plus (medical) -->
        <line x1="150" y1="36" x2="150" y2="14" stroke="#FF6FA5" stroke-width="5" stroke-linecap="round"/>
        <g transform="translate(150 8)">
          <circle r="11" fill="#FF6FA5"/>
          <path d="M-5 0H5 M0 -5V5" stroke="#fff" stroke-width="3" stroke-linecap="round"/>
        </g>
        <!-- arms -->
        <path d="M70 220 q-22 6 -24 -18" stroke="#4DA8FF" stroke-width="16" stroke-linecap="round" fill="none"/>
        <path d="M230 220 q22 6 24 -18" stroke="#4DA8FF" stroke-width="16" stroke-linecap="round" fill="none"/>
        <defs>
          <linearGradient id="g1" x1="0" y1="0" x2="0" y2="1">
            <stop offset="0" stop-color="#7cc0ff"/><stop offset="1" stop-color="#3b8ee6"/>
          </linearGradient>
          <linearGradient id="g2" x1="0" y1="0" x2="0" y2="1">
            <stop offset="0" stop-color="#ffffff"/><stop offset="1" stop-color="#dcecff"/>
          </linearGradient>
        </defs>
      </svg>
      <div class="speech" id="speech">Hi! Let's check in 🌸</div>
    </div>
  </section>

  <section id="vitals">
    <div class="sec-head">
      <span class="sec-kanji">脈</span>
      <div><h2>Today's vitals</h2><p>Synced from your wearable, read at a glance.</p></div>
    </div>
    <div class="vitals">
      <div class="vcard heart"><div class="ico">💗</div><h3>HEART RATE</h3>
        <div class="num">72<span class="unit"> bpm</span></div><span class="spark">💗</span></div>
      <div class="vcard steps"><div class="ico">👟</div><h3>STEPS</h3>
        <div class="num">8,240</div><span class="unit">82% of goal</span><span class="spark">👟</span></div>
      <div class="vcard sleep"><div class="ico">🌙</div><h3>SLEEP</h3>
        <div class="num">7.4<span class="unit"> hrs</span></div><span class="spark">🌙</span></div>
      <div class="vcard water"><div class="ico">💧</div><h3>HYDRATION</h3>
        <div class="num">1.6<span class="unit"> L</span></div><span class="unit">2 cups to go</span><span class="spark">💧</span></div>
    </div>

    <div class="ecg">
      <div><div class="label">Live rhythm</div><div class="bpm">72 bpm · steady</div></div>
      <svg viewBox="0 0 600 60" preserveAspectRatio="none">
        <path d="M0 30 H120 l10 0 l8 -22 l10 44 l8 -22 H300 l10 0 l8 -22 l10 44 l8 -22 H600"/>
      </svg>
    </div>
  </section>

  <section id="checkin">
    <div class="sec-head">
      <span class="sec-kanji">気</span>
      <div><h2>Daily check-in</h2><p>Tap how you feel. Aoi listens.</p></div>
    </div>
    <div class="checkin">
      <svg class="mini" viewBox="0 0 120 130" aria-hidden="true">
        <ellipse cx="60" cy="95" rx="40" ry="35" fill="#4DA8FF"/>
        <circle cx="60" cy="50" r="38" fill="#EAF4FF"/>
        <circle cx="44" cy="50" r="6" fill="#2A2150" id="me1"/>
        <circle cx="76" cy="50" r="6" fill="#2A2150" id="me2"/>
        <path d="M50 64 q10 9 20 0" stroke="#2A2150" stroke-width="3" fill="none" stroke-linecap="round" id="mmouth"/>
        <circle cx="40" cy="60" r="6" fill="#FFB3CF" opacity=".8"/>
        <circle cx="80" cy="60" r="6" fill="#FFB3CF" opacity=".8"/>
      </svg>
      <div>
        <strong>How are you feeling right now?</strong>
        <div class="moods" id="moods">
          <button class="mood" data-msg="Yatta! Let's ride that energy — go crush a quest! ⚡">😄</button>
          <button class="mood" data-msg="Steady and calm is a great place to be. I'm proud of you. 🍵">🙂</button>
          <button class="mood" data-msg="Some days are just... meh. Let's keep it gentle today. 🌿">😐</button>
          <button class="mood" data-msg="I hear you. Drink some water, breathe slow with me — in 4, out 6. 💙">😞</button>
          <button class="mood" data-msg="That's tough. You logged it, and that's brave. Rest is allowed. 🌙">😣</button>
        </div>
        <div class="reply" id="reply">Pick the one that fits.</div>
      </div>
    </div>
  </section>

  <section id="quests">
    <div class="sec-head">
      <span class="sec-kanji">挑</span>
      <div><h2>Health quests</h2><p>Habits, but with XP and a cheerleader.</p></div>
    </div>
    <div class="quests">
      <div class="quest">
        <span class="tag">MOVE</span>
        <h3>Walk the cherry path</h3>
        <p>Hit 10,000 steps before sunset.</p>
        <div class="bar"><i style="width:82%"></i></div>
      </div>
      <div class="quest">
        <span class="tag">HYDRATE</span>
        <h3>Fill the water meter</h3>
        <p>8 cups today. Aoi refills with you.</p>
        <div class="bar"><i style="width:64%"></i></div>
      </div>
      <div class="quest">
        <span class="tag">REST</span>
        <h3>Lights-out by 11</h3>
        <p>Wind down with a 5-min breathe routine.</p>
        <div class="bar"><i style="width:40%"></i></div>
      </div>
    </div>
  </section>
</main>

<footer id="footer">
  <p><b>Aoi</b> — a friendly concept for human-centered health tech. 葵 means "hollyhock," a flower that turns toward the sun.</p>
  <p>Demo only · not medical advice · be kind to yourself today.</p>
</footer>

<script>
  // sparkle field
  const sf = document.getElementById('sparkles');
  for(let i=0;i<26;i++){
    const s=document.createElement('i');
    s.style.left=Math.random()*100+'vw';
    s.style.top=Math.random()*100+'vh';
    s.style.animationDelay=(Math.random()*5)+'s';
    s.style.background=['#FFD166','#FF6FA5','#4DA8FF','#3FD9B6'][i%4];
    sf.appendChild(s);
  }

  // mood check-in
  const reply=document.getElementById('reply');
  const speech=document.getElementById('speech');
  const mouth=document.getElementById('mmouth');
  document.getElementById('moods').addEventListener('click',e=>{
    const b=e.target.closest('.mood'); if(!b) return;
    document.querySelectorAll('.mood').forEach(m=>m.classList.remove('active'));
    b.classList.add('active');
    reply.textContent=b.dataset.msg;
    speech.textContent=b.textContent+' got it!';
    // mini mascot reacts: happier choices = bigger smile
    const idx=[...b.parentNode.children].indexOf(b);
    const curves=['q10 14 20 0','q10 9 20 0','q10 2 20 0','q10 -4 20 0','q10 -8 20 0'];
    mouth.setAttribute('d','M50 64 '+curves[idx]);
  });
</script>
