<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Chaosnico9000 | Portfolio</title>

<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet">

<style>
:root{
  --bg:#0f172a;
  --glass:rgba(255,255,255,0.06);
  --border:rgba(255,255,255,0.15);
  --text:#ffffff;
  --muted:#94a3b8;
  --accent:#38bdf8;
}

*{box-sizing:border-box;margin:0;padding:0;}

body{
  font-family:'Inter',sans-serif;
  background: radial-gradient(circle at 20% 30%, #1e3a8a, transparent 40%),
              radial-gradient(circle at 80% 70%, #0ea5e9, transparent 40%),
              var(--bg);
  color:var(--text);
  overflow-x:hidden;
}

/* Animated background glow */
body::before{
  content:"";
  position:fixed;
  width:800px;
  height:800px;
  background:radial-gradient(circle,#38bdf8,transparent 60%);
  filter:blur(120px);
  opacity:.15;
  animation:float 12s infinite alternate ease-in-out;
  z-index:-1;
}

@keyframes float{
  from{transform:translate(-200px,-150px);}
  to{transform:translate(200px,150px);}
}

.container{
  width:min(1200px,calc(100% - 40px));
  margin:auto;
  padding:40px 0;
}

/* Header */
header{
  display:flex;
  justify-content:space-between;
  align-items:center;
  padding:20px 0;
}

.logo{
  font-weight:800;
  font-size:22px;
  letter-spacing:1px;
}

nav a{
  margin-left:25px;
  color:var(--muted);
  text-decoration:none;
  font-size:14px;
}

nav a:hover{
  color:var(--accent);
}

/* Hero */
.hero{
  padding:120px 0 100px;
}

.hero h1{
  font-size:60px;
  font-weight:800;
  line-height:1.1;
  margin-bottom:20px;
}

.hero p{
  max-width:650px;
  color:var(--muted);
  font-size:20px;
}

/* Sections */
.section{
  margin-top:120px;
}

.section h2{
  font-size:28px;
  margin-bottom:40px;
  font-weight:700;
}

/* Glass Cards */
.grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
  gap:30px;
}

.card{
  background:var(--glass);
  backdrop-filter:blur(20px);
  border:1px solid var(--border);
  border-radius:20px;
  padding:30px;
  transition:.3s ease;
  opacity:0;
  transform:translateY(40px);
}

.card.visible{
  opacity:1;
  transform:translateY(0);
}

.card:hover{
  transform:translateY(-8px);
  border-color:var(--accent);
}

.card h3{
  margin-bottom:15px;
  font-size:20px;
}

.card p{
  color:var(--muted);
  font-size:15px;
  margin-bottom:15px;
}

.tech{
  font-size:13px;
  color:var(--accent);
}

/* Skills visual bars */
.skill{
  margin-bottom:25px;
}

.skill-title{
  display:flex;
  justify-content:space-between;
  margin-bottom:6px;
  font-size:14px;
}

.bar{
  height:6px;
  background:rgba(255,255,255,0.1);
  border-radius:4px;
  overflow:hidden;
}

.bar-fill{
  height:100%;
  background:linear-gradient(90deg,#38bdf8,#0ea5e9);
  width:0;
  transition:1.2s ease;
}

/* Footer */
footer{
  margin-top:140px;
  padding:50px 0;
  border-top:1px solid rgba(255,255,255,0.1);
  text-align:center;
  color:var(--muted);
  font-size:14px;
}

/* Responsive */
@media(max-width:800px){
  .hero h1{font-size:40px;}
  .hero p{font-size:18px;}
}
</style>
</head>

<body>

<div class="container">

<header>
  <div class="logo">Chaosnico9000</div>
  <nav>
    <a href="#projects">Projekte</a>
    <a href="#skills">Skills</a>
    <a href="https://github.com/Chaosnico9000" target="_blank">GitHub ↗</a>
  </nav>
</header>

<section class="hero">
  <h1>Software mit Substanz.<br>Design mit Präzision.</h1>
  <p>
    Ich entwickle performante .NET Anwendungen,
    Monitoring-Systeme und moderne Web-Interfaces
    mit klarem Fokus auf Architektur, Wartbarkeit und Automatisierung.
  </p>
</section>

<section class="section" id="projects">
  <h2>Projekte</h2>
  <div class="grid">

    <div class="card">
      <h3>BizMMonitoring</h3>
      <p>Monitoring-Ökosystem für BizTalk mit BackgroundServices und Live-Dashboard.</p>
      <div class="tech">Blazor • .NET • SQL Server</div>
    </div>

    <div class="card">
      <h3>AZUBITOOLS</h3>
      <p>PDF-Berichtsverwaltung mit Versionierung, Strukturierung und API.</p>
      <div class="tech">Blazor Server • EF Core</div>
    </div>

    <div class="card">
      <h3>PluginTester</h3>
      <p>CLI-Tool mit automatischem Build, Live-Reload und Plugin-Management.</p>
      <div class="tech">.NET • Dynamic Loading</div>
    </div>

  </div>
</section>

<section class="section" id="skills">
  <h2>Technologien</h2>

  <div class="skill">
    <div class="skill-title"><span>.NET / C#</span><span>95%</span></div>
    <div class="bar"><div class="bar-fill" data-width="95%"></div></div>
  </div>

  <div class="skill">
    <div class="skill-title"><span>Blazor / UI</span><span>90%</span></div>
    <div class="bar"><div class="bar-fill" data-width="90%"></div></div>
  </div>

  <div class="skill">
    <div class="skill-title"><span>SQL / Architektur</span><span>88%</span></div>
    <div class="bar"><div class="bar-fill" data-width="88%"></div></div>
  </div>

</section>

<footer>
  © <span id="year"></span> Chaosnico9000 • Built with Precision
</footer>

</div>

<script>
document.getElementById("year").textContent = new Date().getFullYear();

/* Scroll Reveal */
const cards = document.querySelectorAll('.card');
const observer = new IntersectionObserver(entries=>{
  entries.forEach(entry=>{
    if(entry.isIntersecting){
      entry.target.classList.add('visible');
    }
  });
},{threshold:0.2});
cards.forEach(card=>observer.observe(card));

/* Animate skill bars */
const bars = document.querySelectorAll('.bar-fill');
setTimeout(()=>{
  bars.forEach(bar=>{
    bar.style.width = bar.dataset.width;
  });
},500);
</script>

</body>
</html>
