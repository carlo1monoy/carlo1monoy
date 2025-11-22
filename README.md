
> Paste that `README.md` into the repository named exactly `carlo1monoy` and commit.  
> Next, host the `index.html` below and link it from the README.

---

# 2) Full **Interactive Cyberpunk Mini-Portfolio** — single-file `index.html`

Save the code below as `index.html` in a repo (e.g., `carlo1monoy`), then enable **GitHub Pages** (or deploy to Vercel) and the interactive site will be live.

It contains:
- neon cyberpunk UI + matrix rain background
- dark/light toggle
- project cards with expand animation
- an interactive **Chat** UI (client-side) — placeholder handler included and instructions to connect an API (OpenAI / Gemini) via a server or Vercel environment variables for safety (do not put API keys into client JS)

---

### `index.html` (single-file template — copy & paste)

```html
<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Carlo Charles Monoy — Neon Portfolio</title>
<style>
  /* --- Basic reset & font --- */
  @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&family=Inter:wght@300;400;600&display=swap');
  :root{
    --bg:#05030a;
    --panel:#0f0c14;
    --neon1:#ff00ff;
    --neon2:#00d4ff;
    --glass: rgba(255,255,255,0.03);
    --accent: var(--neon2);
    color-scheme: dark;
  }
  *{box-sizing:border-box}
  html,body{height:100%;margin:0;background:var(--bg);font-family:Inter,system-ui,Arial;color:#e6e6f0}
  .wrap{min-height:100vh;display:flex;flex-direction:column;align-items:center;padding:32px}
  header{width:100%;max-width:1100px;display:flex;align-items:center;justify-content:space-between;margin-bottom:18px}
  .brand{display:flex;gap:16px;align-items:center}
  .logo{
    width:64px;height:64px;border-radius:10px;display:grid;place-items:center;
    background:linear-gradient(135deg,var(--neon1),var(--neon2));box-shadow:0 6px 30px rgba(0,0,0,0.6);
    font-family:Orbitron,monospace;font-weight:700;color:#061017;font-size:20px;
    border:2px solid rgba(255,255,255,0.04);
  }
  h1{margin:0;font-family:Orbitron,monospace;font-size:22px;letter-spacing:0.6px}
  .sub{color:#bdb8d6;font-size:13px;margin-top:4px}
  .controls{display:flex;gap:10px;align-items:center}
  .btn{padding:10px 14px;border-radius:10px;background:linear-gradient(90deg, rgba(255,255,255,0.02), rgba(255,255,255,0.00));border:1px solid rgba(255,255,255,0.04);cursor:pointer;color:var(--neon1)}
  .btn.secondary{color:var(--neon2)}
  main{width:100%;max-width:1100px;display:grid;grid-template-columns:2fr 1fr;gap:20px}
  /* left panel */
  .panel{background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));padding:18px;border-radius:12px;border:1px solid rgba(255,255,255,0.03)}
  .hero{display:flex;flex-direction:column;gap:12px}
  .hero .tag{display:inline-block;padding:6px 10px;border-radius:8px;background:linear-gradient(90deg,var(--glass),transparent);color:var(--neon1);font-weight:600}
  .cards{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-top:12px}
  .card{padding:12px;border-radius:10px;background:rgba(255,255,255,0.02);border:1px solid rgba(255,255,255,0.03);cursor:pointer;transition:all .25s}
  .card:hover{transform:translateY(-6px);box-shadow:0 12px 40px rgba(0,0,0,0.6)}
  .card h3{margin:0;font-size:14px;color:var(--neon2)}
  .card p{font-size:13px;color:#bdb8d6;margin-top:8px}
  /* right column - chat */
  .chat-window{display:flex;flex-direction:column;height:520px}
  .messages{flex:1;overflow:auto;padding:12px;border-radius:10px;background:linear-gradient(180deg, rgba(0,0,0,0.12), rgba(255,255,255,0.01));border:1px solid rgba(255,255,255,0.02)}
  .msg{margin:8px 0;display:flex;gap:8px;align-items:flex-end}
  .msg.user{justify-content:flex-end}
  .bubble{max-width:75%;padding:10px 12px;border-radius:10px;background:linear-gradient(90deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border:1px solid rgba(255,255,255,0.03);font-size:13px}
  .bubble.user{background:linear-gradient(90deg, rgba(0,0,0,0.16), rgba(0,0,0,0.06));color:#dbeafe}
  .controls-row{display:flex;gap:8px;margin-top:8px}
  .input{flex:1;padding:10px;border-radius:10px;border:1px solid rgba(255,255,255,0.06);background:transparent;color:inherit}
  /* neon footer */
  footer{width:100%;max-width:1100px;margin-top:20px;color:#9c98b5;font-size:13px;text-align:center}
  /* matrix canvas */
  canvas#matrix{position:fixed;left:0;top:0;pointer-events:none;filter:contrast(140%) blur(0.6px);mix-blend-mode:screen;z-index:-1}
  /* responsive */
  @media(max-width:900px){
    main{grid-template-columns:1fr; }
    .cards{grid-template-columns:1fr}
  }
</style>
</head>
<body>
<canvas id="matrix"></canvas>
<div class="wrap">
  <header>
    <div class="brand">
      <div class="logo">CCM</div>
      <div>
        <h1>Carlo Charles Monoy</h1>
        <div class="sub">Mobile Dev • Machine Learning • Neon Aesthetics</div>
      </div>
    </div>
    <div class="controls">
      <button class="btn" onclick="toggleTheme()">Toggle Theme</button>
      <a class="btn secondary" href="https://github.com/carlo1monoy/Monoy_InstantCoffee_Classification_FinalProject" target="_blank">Featured Project</a>
      <a class="btn" href="mailto:your.email@example.com">Contact</a>
    </div>
  </header>

  <main>
    <section class="panel hero">
      <div>
        <span class="tag">Cyberpunk • Neon • Flutter • Python</span>
        <h2 style="margin-top:10px">Hello — I build mobile experiences and ML explorations with a neon aesthetic.</h2>
        <p style="color:#cfcbe8">Click a project to expand. Use the chat panel on the right to try a demo assistant (local simulation). To enable a real AI assistant, follow the integration notes below.</p>
      </div>

      <div class="cards" id="projectGrid">
        <div class="card" onclick="openProject('Monoy_InstantCoffee_Classification_FinalProject')">
          <h3>Monoy_InstantCoffee_Classification_FinalProject</h3>
          <p>ML pipeline: preprocess → features → train → evaluate. Notebook experiments and TFLite export ideas.</p>
        </div>
        <div class="card" onclick="openProject('Flutter_Widget_UIComponents')">
          <h3>Flutter_Widget_UIComponents</h3>
          <p>Reusable Flutter widgets for rapid prototyping and consistent UI.</p>
        </div>
        <div class="card" onclick="openProject('IT120-Activity1')">
          <h3>IT120-Activity1</h3>
          <p>Coursework & algorithmic exercises demonstrating fundamentals.</p>
        </div>
        <div class="card" onclick="openProject('Anthoy-Charles-Monoy')">
          <h3>Anthoy-Charles-Monoy</h3>
          <p>Personal experiments, small utilities, notes, and demos.</p>
        </div>
      </div>
    </section>

    <aside class="panel chat-window">
      <h3 style="margin:0;color:var(--neon1)">AI Assistant (demo)</h3>
      <div class="messages" id="messages"></div>

      <div class="controls-row">
        <input id="userInput" class="input" placeholder="Ask me about the project, ML pipeline, or Flutter tips..." />
        <button class="btn" onclick="sendMsg()">Send</button>
      </div>
      <div style="font-size:12px;color:#9b98b3;margin-top:8px">Local demo assistant — to enable a real assistant, see the integration notes below.</div>
    </aside>
  </main>

  <footer>
    © <strong>Carlo Charles Monoy</strong> • GitHub: <a href="https://github.com/carlo1monoy" style="color:var(--neon2)">github.com/carlo1monoy</a> • Portfolio (coming soon)
  </footer>
</div>

<script>
  // Matrix rain background
  const canvas = document.getElementById('matrix');
  const ctx = canvas.getContext('2d');
  let w = canvas.width = innerWidth;
  let h = canvas.height = innerHeight;
  window.addEventListener('resize',()=>{ w=canvas.width=innerWidth; h=canvas.height=innerHeight; initCols(); })
  let cols = [];
  function initCols(){
    let fontSize = 16;
    let colsCount = Math.floor(w / fontSize);
    cols = new Array(colsCount).fill(1);
    ctx.font = fontSize + 'px monospace';
  }
  initCols();
  const letters = 'アカサタナハマヤラワ0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ';
  function draw(){
    ctx.fillStyle = 'rgba(5,3,10,0.12)';
    ctx.fillRect(0,0,w,h);
    ctx.fillStyle = 'rgba(0,212,255,0.6)';
    for(let i=0;i<cols.length;i++){
      let x = i*16;
      let text = letters.charAt(Math.floor(Math.random()*letters.length));
      ctx.fillText(text,x,cols[i]*16);
      if(cols[i]*16 > h && Math.random()>0.975) cols[i]=0;
      cols[i]++;
    }
  }
  setInterval(draw,45);

  // Theme toggle
  function toggleTheme(){
    const root = document.documentElement;
    if(root.style.getPropertyValue('--bg') === '#05030a' || !root.style.getPropertyValue('--bg')){
      root.style.setProperty('--bg','#f2f6ff');
      root.style.setProperty('--panel','#ffffff');
      root.style.setProperty('--neon1','#ff0077');
      root.style.setProperty('--neon2','#0066ff');
      document.body.style.color = '#061017';
    } else {
      root.style.setProperty('--bg','#05030a');
      root.style.setProperty('--panel','#0f0c14');
      root.style.setProperty('--neon1','#ff00ff');
      root.style.setProperty('--neon2','#00d4ff');
      document.body.style.color = '#e6e6f0';
    }
  }

  // Project open (simple modal simulation)
  function openProject(name){
    alert('Open project: ' + name + '\\n\\nVisit the repo at https://github.com/carlo1monoy/' + name);
  }

  // Chat demo (local simulated assistant)
  const messagesEl = document.getElementById('messages');
  function append(msg, who='bot'){
    const el = document.createElement('div');
    el.className = 'msg ' + (who === 'user' ? 'user' : 'bot');
    const b = document.createElement('div');
    b.className = 'bubble ' + (who === 'user'? 'user':'' );
    b.innerText = msg;
    el.appendChild(b);
    messagesEl.appendChild(el);
    messagesEl.scrollTop = messagesEl.scrollHeight;
  }
  function sendMsg(){
    const input = document.getElementById('userInput');
    const text = input.value.trim();
    if(!text) return;
    append(text,'user');
    input.value='';
    // Simulated local response (replace with API call)
    setTimeout(()=> {
      const reply = localAssistantReply(text);
      append(reply,'bot');
    }, 650);
  }
  function localAssistantReply(q){
    const qL = q.toLowerCase();
    if(qL.includes('coffee') || qL.includes('classif')) return 'This project uses classic supervised classification flow: clean data → features → train models → evaluate with confusion matrix. Try checking the dataset notebook for feature extraction steps.';
    if(qL.includes('flutter')) return 'Use Stateful widgets for local state and Provider/Bloc for app-wide state. Make sure to optimize build() calls and use const where possible.';
    if(qL.includes('deploy')) return 'For hosting the portfolio, GitHub Pages works great; for a real chatbot you need serverless functions on Vercel or Firebase functions to safely store API keys.';
    return 'Nice question! I can provide tips on model training, Flutter optimization, or deploying to GitHub Pages. Ask me specifically about any of those.';
  }

  // quick welcome
  append('Welcome — ask me about the Monoy Instant Coffee classifier or Flutter tips!');
</script>

<!-- Integration Notes:
  To enable a real AI assistant:
  - Do NOT put API keys in client-side JS.
  - Create a small serverless endpoint (Vercel Serverless Functions / Netlify Functions / Firebase Functions)
    that proxies requests to your AI provider (OpenAI/Gemini). Store API keys in environment variables.
  - Update `sendMsg()` to POST to your serverless endpoint and append the response.
  Example (pseudo):
    fetch('/api/chat', { method:'POST', body: JSON.stringify({message: text})})
      -> respond with assistant text
-->
</body>
</html>
