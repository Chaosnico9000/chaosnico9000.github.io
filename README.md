<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Chaosnico9000 | Portfolio</title>

<style>
:root{
  --bg:#0e1117;
  --panel:#161b22;
  --border:#262c36;
  --text:#e6edf3;
  --muted:#8b949e;
  --accent:#3b82f6;
  --radius:18px;
}

*{box-sizing:border-box;}
body{
  margin:0;
  font-family:system-ui,-apple-system,Segoe UI,Roboto,sans-serif;
  background:var(--bg);
  color:var(--text);
  line-height:1.6;
}

a{
  color:var(--accent);
  text-decoration:none;
}
a:hover{ text-decoration:underline; }

.container{
  width:min(1100px,calc(100% - 40px));
  margin:auto;
  padding:40px 0;
}

header{
  display:flex;
  justify-content:space-between;
  align-items:center;
  padding:25px 0;
}

.logo{
  font-weight:700;
  font-size:20px;
}

nav a{
  margin-left:20px;
  color:var(--muted);
  font-size:14px;
}

.hero{
  padding:60px 0;
}

.hero h1{
  font-size:48px;
  margin:0 0 15px;
  line-height:1.1;
}

.hero p{
  max-width:600px;
  color:var(--muted);
  font-size:18px;
}

.section{
  margin-top:80px;
}

.section h2{
  font-size:24px;
  margin-bottom:25px;
}

.grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
  gap:20px;
}

.card{
  background:var(--panel);
  border:1px solid var(--border);
  border-radius:var(--radius);
  padding:25px;
  transition:.2s ease;
}

.card:hover{
  transform:translateY(-4px);
  border-color:var(--accent);
}

.card h3{
  margin:0 0 10px;
  font-size:18px;
}

.card p{
  color:var(--muted);
  font-size:14px;
}

.tech{
  margin-top:15px;
  font-size:12px;
  color:var(--muted);
}

.footer{
  margin-top:100px;
  padding:40px 0;
  border-top:1px solid var(--border);
  color:var(--muted);
  font-size:14px;
  display:flex;
  justify-content:space-between;
  flex-wrap:wrap;
}

@media(max-width:700px){
  .hero h1{font-size:34px;}
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
    <a href="#contact">Kontakt</a>
    <a href="https://github.com/Chaosnico9000" target="_blank">GitHub ↗</a>
  </nav>
</header>

<section class="hero">
  <h1>Ich entwickle Software,<br>die funktioniert.</h1>
  <p>
    Anwendungsentwickler mit Fokus auf .NET, moderne UI-Architekturen,
    saubere Code-Strukturen und Automatisierung.
    Ich baue Tools, Monitoring-Systeme und produktionsreife Anwendungen.
  </p>
</section>

<section class="section" id="projects">
  <h2>Ausgewählte Projekte</h2>

  <div class="grid">

    <div class="card">
      <h3>BizMMonitoring</h3>
      <p>Monitoring-System für BizTalk-Umgebungen mit Dashboard, Hintergrundservices und API.</p>
      <div class="tech">Blazor • .NET • SQL Server • Serilog</div>
    </div>

    <div class="card">
      <h3>AZUBITOOLS</h3>
      <p>Webbasierte PDF-Berichtsverwaltung mit Strukturierung nach Jahr, Status und Versionierung.</p>
      <div class="tech">Blazor Server • PDF Processing • EF Core</div>
    </div>

    <div class="card">
      <h3>PluginTester</h3>
      <p>CLI-Tool zum automatischen Kompilieren, Laden und Ausführen von Plugins mit Live-Reload.</p>
      <div class="tech">.NET • Spectre.Console • Dynamic Loading</div>
    </div>

  </div>
</section>

<section class="section" id="skills">
  <h2>Technologien</h2>
  <div class="grid">

    <div class="card">
      <h3>Backend</h3>
      <p>.NET 8/9, C#, Entity Framework Core, REST APIs, Background Services</p>
    </div>

    <div class="card">
      <h3>Frontend</h3>
      <p>Blazor Server, MudBlazor, WPF (Material Design), moderne UI-Konzepte</p>
    </div>

    <div class="card">
      <h3>DevOps</h3>
      <p>GitHub Actions, Windows Services, CI/CD Pipelines, Deployment Automation</p>
    </div>

  </div>
</section>

<section class="section" id="contact">
  <h2>Kontakt</h2>
  <p>
    GitHub: <a href="https://github.com/Chaosnico9000" target="_blank">github.com/Chaosnico9000</a><br>
    E-Mail: deine.email@domain.de
  </p>
</section>

<div class="footer">
  <div>© <span id="year"></span> Chaosnico9000</div>
  <div>Clean Code. Klare Strukturen. Fokus auf Qualität.</div>
</div>

</div>

<script>
document.getElementById("year").textContent = new Date().getFullYear();
</script>

</body>
</html>
