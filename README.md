<!--
  Datei: index.html
  Zweck: Startseite für https://Chaosnico9000.github.io
  Anleitung (weil Menschen gerne Dinge kompliziert machen):
  - Repo: Chaosnico9000/Chaosnico9000.github.io
  - Diese Datei als "index.html" ins Repo-Root pushen
  - GitHub Pages aktivieren: Settings -> Pages -> Deploy from branch -> main / root
-->
<!doctype html>
<html lang="de">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <meta name="description" content="Chaosnico9000 – Projekte, Tools, Experimente. Ein gepflegtes Maß an Chaos." />
  <meta name="theme-color" content="#0b1020" />
  <title>Chaosnico9000 | GitHub Pages</title>

  <style>
    :root{
      --bg: #070a12;
      --panel: rgba(255,255,255,.06);
      --panel2: rgba(255,255,255,.09);
      --text: rgba(255,255,255,.88);
      --muted: rgba(255,255,255,.62);
      --line: rgba(255,255,255,.12);
      --glow: rgba(120, 130, 255, .24);
      --accent: #7c5cff;
      --accent2: #23c4f8;
      --ok: #33d6a6;
      --warn: #ffcf5c;
      --danger: #ff5c7a;
      --radius: 18px;
      --shadow: 0 20px 60px rgba(0,0,0,.55);
      --mono: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
      --sans: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji","Segoe UI Emoji";
    }

    *{ box-sizing:border-box; }
    html,body{ height:100%; }
    body{
      margin:0;
      font-family:var(--sans);
      color:var(--text);
      background:
        radial-gradient(1200px 800px at 10% 0%, rgba(124,92,255,.22), transparent 65%),
        radial-gradient(900px 700px at 90% 10%, rgba(35,196,248,.18), transparent 60%),
        radial-gradient(700px 600px at 60% 100%, rgba(51,214,166,.10), transparent 55%),
        linear-gradient(180deg, #060812 0%, #070a12 100%);
      overflow-x:hidden;
    }

    a{ color:inherit; text-decoration:none; }
    a:hover{ text-decoration:underline; text-underline-offset:3px; }

    .wrap{
      width:min(1100px, calc(100% - 44px));
      margin:0 auto;
      padding:28px 0 60px;
    }

    /* Topbar */
    .topbar{
      position:sticky;
      top:0;
      z-index:50;
      backdrop-filter: blur(10px);
      background: linear-gradient(180deg, rgba(7,10,18,.72), rgba(7,10,18,.22));
      border-bottom:1px solid var(--line);
    }
    .topbar .inner{
      width:min(1100px, calc(100% - 44px));
      margin:0 auto;
      display:flex;
      align-items:center;
      justify-content:space-between;
      padding:14px 0;
    }
    .brand{
      display:flex;
      align-items:center;
      gap:12px;
      letter-spacing:.2px;
    }
    .logo{
      width:36px;
      height:36px;
      border-radius:12px;
      background:
        radial-gradient(10px 10px at 30% 30%, rgba(255,255,255,.9), transparent 50%),
        linear-gradient(135deg, rgba(124,92,255,1), rgba(35,196,248,1));
      box-shadow: 0 0 0 1px rgba(255,255,255,.12), 0 10px 30px rgba(124,92,255,.25);
    }
    .brand strong{ font-weight:750; }
    .brand span{
      color:var(--muted);
      font-family:var(--mono);
      font-size:12px;
    }

    nav{
      display:flex;
      gap:10px;
      align-items:center;
      flex-wrap:wrap;
      justify-content:flex-end;
    }
    .chip{
      padding:9px 12px;
      border-radius:999px;
      background:rgba(255,255,255,.05);
      border:1px solid rgba(255,255,255,.10);
      transition: transform .12s ease, background .12s ease, border-color .12s ease;
      font-size:13px;
      color:var(--muted);
      user-select:none;
    }
    .chip:hover{
      transform: translateY(-1px);
      background:rgba(255,255,255,.08);
      border-color: rgba(255,255,255,.18);
      text-decoration:none;
    }
    .chip.primary{
      color:rgba(255,255,255,.88);
      background: linear-gradient(135deg, rgba(124,92,255,.22), rgba(35,196,248,.12));
      border-color: rgba(124,92,255,.32);
    }

    /* Hero */
    .hero{
      display:grid;
      grid-template-columns: 1.25fr .75fr;
      gap:18px;
      padding:34px 0 10px;
      align-items:stretch;
    }
    @media (max-width: 880px){
      .hero{ grid-template-columns: 1fr; }
    }

    .card{
      background: linear-gradient(180deg, rgba(255,255,255,.07), rgba(255,255,255,.04));
      border:1px solid rgba(255,255,255,.12);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      position:relative;
      overflow:hidden;
    }
    .card::before{
      content:"";
      position:absolute; inset:-120px -120px auto auto;
      width:260px; height:260px;
      background: radial-gradient(circle at 30% 30%, rgba(124,92,255,.35), transparent 60%);
      filter: blur(6px);
      pointer-events:none;
    }
    .card .pad{ padding:22px; }

    h1{
      margin:0 0 10px;
      font-size: clamp(28px, 4vw, 44px);
      line-height:1.05;
      letter-spacing:-.6px;
    }
    .subtitle{
      margin:0;
      color:var(--muted);
      font-size:15px;
      line-height:1.5;
    }
    .ctaRow{
      display:flex;
      gap:10px;
      flex-wrap:wrap;
      margin-top:16px;
    }
    .btn{
      padding:10px 13px;
      border-radius:14px;
      border:1px solid rgba(255,255,255,.14);
      background: rgba(255,255,255,.06);
      color:rgba(255,255,255,.86);
      display:inline-flex;
      gap:10px;
      align-items:center;
      text-decoration:none;
      transition: transform .12s ease, background .12s ease, border-color .12s ease;
      font-size:13px;
    }
    .btn:hover{
      transform: translateY(-1px);
      background: rgba(255,255,255,.09);
      border-color: rgba(255,255,255,.22);
      text-decoration:none;
    }
    .btn.accent{
      border-color: rgba(124,92,255,.40);
      background: linear-gradient(135deg, rgba(124,92,255,.28), rgba(35,196,248,.12));
    }
    .kbd{
      font-family:var(--mono);
      font-size:12px;
      padding:2px 7px;
      border-radius:8px;
      border:1px solid rgba(255,255,255,.14);
      background: rgba(0,0,0,.25);
      color: rgba(255,255,255,.72);
    }

    /* Side stats */
    .stats{
      display:grid;
      grid-template-columns: 1fr;
      gap:12px;
    }
    .stat{
      padding:16px 16px 14px;
      border-radius: var(--radius);
      background: linear-gradient(180deg, rgba(255,255,255,.06), rgba(255,255,255,.03));
      border:1px solid rgba(255,255,255,.12);
      position:relative;
      overflow:hidden;
    }
    .stat small{
      display:block;
      color:var(--muted);
      font-size:12px;
      font-family:var(--mono);
      letter-spacing:.4px;
      text-transform:uppercase;
      margin-bottom:6px;
    }
    .stat strong{
      font-size:18px;
      letter-spacing:-.2px;
    }
    .stat .pill{
      display:inline-flex;
      margin-top:10px;
      gap:8px;
      flex-wrap:wrap;
    }
    .tag{
      border:1px solid rgba(255,255,255,.14);
      background: rgba(255,255,255,.05);
      padding:6px 10px;
      border-radius:999px;
      font-size:12px;
      color:var(--muted);
      font-family:var(--mono);
    }

    /* Sections */
    .grid{
      display:grid;
      grid-template-columns: repeat(12, 1fr);
      gap:14px;
      margin-top:16px;
    }
    .col-7{ grid-column: span 7; }
    .col-5{ grid-column: span 5; }
    .col-6{ grid-column: span 6; }
    .col-12{ grid-column: span 12; }
    @media (max-width: 900px){
      .col-7,.col-5,.col-6{ grid-column: span 12; }
    }

    h2{
      margin:0 0 10px;
      font-size:18px;
      letter-spacing:-.2px;
    }
    .muted{ color:var(--muted); }
    .list{
      display:flex;
      flex-direction:column;
      gap:10px;
      margin-top:10px;
    }
    .item{
      padding:14px;
      border-radius:16px;
      border:1px solid rgba(255,255,255,.12);
      background: rgba(255,255,255,.05);
      transition: transform .12s ease, background .12s ease, border-color .12s ease;
    }
    .item:hover{
      transform: translateY(-1px);
      background: rgba(255,255,255,.07);
      border-color: rgba(255,255,255,.20);
    }
    .item .top{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:10px;
    }
    .item strong{
      font-size:14px;
      letter-spacing:-.1px;
    }
    .item p{
      margin:8px 0 0;
      color:var(--muted);
      font-size:13px;
      line-height:1.5;
    }
    .badge{
      font-family:var(--mono);
      font-size:11px;
      padding:5px 9px;
      border-radius:999px;
      border:1px solid rgba(255,255,255,.14);
      background: rgba(0,0,0,.22);
      color: rgba(255,255,255,.70);
      white-space:nowrap;
    }
    .badge.ok{ border-color: rgba(51,214,166,.35); background: rgba(51,214,166,.10); }
    .badge.warn{ border-color: rgba(255,207,92,.35); background: rgba(255,207,92,.10); }
    .badge.danger{ border-color: rgba(255,92,122,.35); background: rgba(255,92,122,.10); }

    /* Terminal */
    .terminal{
      font-family:var(--mono);
      font-size:13px;
      line-height:1.55;
      background: rgba(0,0,0,.35);
      border:1px solid rgba(255,255,255,.12);
      border-radius:16px;
      padding:14px;
      overflow:auto;
    }
    .terminal .prompt{ color: rgba(35,196,248,.82); }
    .terminal .path{ color: rgba(124,92,255,.86); }
    .terminal .out{ color: rgba(255,255,255,.72); }

    footer{
      margin-top:18px;
      padding:16px 0 0;
      border-top:1px solid var(--line);
      color:var(--muted);
      font-size:13px;
      display:flex;
      justify-content:space-between;
      flex-wrap:wrap;
      gap:10px;
    }

    /* subtle floating dots */
    .dots{
      position:fixed;
      inset:0;
      pointer-events:none;
      opacity:.28;
      background-image: radial-gradient(rgba(255,255,255,.10) 1px, transparent 1px);
      background-size: 22px 22px;
      mask-image: radial-gradient(700px 400px at 50% 0%, black, transparent 75%);
    }
  </style>
</head>

<body>
  <div class="dots" aria-hidden="true"></div>

  <header class="topbar">
    <div class="inner">
      <div class="brand" title="Chaos, aber organisiert. Meistens.">
        <div class="logo" aria-hidden="true"></div>
        <div>
          <strong>Chaosnico9000</strong><br />
          <span>github.io // home base</span>
        </div>
      </div>

      <nav aria-label="Navigation">
        <a class="chip" href="#projekte">Projekte</a>
        <a class="chip" href="#stack">Stack</a>
        <a class="chip" href="#kontakt">Kontakt</a>
        <a class="chip primary" href="https://github.com/Chaosnico9000" rel="me">GitHub ↗</a>
      </nav>
    </div>
  </header>

  <main class="wrap">
    <section class="hero">
      <article class="card">
        <div class="pad">
          <h1>Ein gepflegtes Maß an Chaos.<br><span style="color:rgba(255,255,255,.75)">Und ein paar Projekte.</span></h1>
          <p class="subtitle">
            Willkommen auf <span class="kbd">Chaosnico9000.github.io</span>.
            Hier landen Tools, Experimente und Dinge, die ich angefangen habe, weil ich dachte,
            “das dauert nur kurz”. Spoiler: tat es nicht.
          </p>

          <div class="ctaRow">
            <a class="btn accent" href="#projekte">Zu den Projekten</a>
            <a class="btn" href="https://github.com/Chaosnico9000?tab=repositories">Repos ansehen ↗</a>
            <a class="btn" href="#kontakt">Kontakt</a>
            <span class="btn" style="cursor:default" title="Für die Menschen, die gern Shortcuts drücken">
              <span class="kbd">/</span> Suche <span class="muted">(kommt irgendwann…)</span>
            </span>
          </div>

          <div style="margin-top:16px" class="terminal" aria-label="Terminal Demo">
            <div><span class="prompt">nico@dev</span>:<span class="path">~/chaosnico9000</span>$ <span class="out">dotnet --info</span></div>
            <div class="out">.NET: modern enough. Motivation: intermittierend. ☑</div>
            <div style="margin-top:6px"><span class="prompt">nico@dev</span>:<span class="path">~/chaosnico9000</span>$ <span class="out">git status</span></div>
            <div class="out">On branch main<br/>nothing to commit, working tree clean<br/><span class="muted">Seltenes Ereignis.</span></div>
          </div>
        </div>
      </article>

      <aside class="stats">
        <div class="stat">
          <small>Schwerpunkt</small>
          <strong>Dev • Tools • UI • Automatisierung</strong>
          <div class="pill">
            <span class="tag">.NET</span>
            <span class="tag">WPF/Blazor</span>
            <span class="tag">SQL Server</span>
            <span class="tag">CI/CD</span>
          </div>
        </div>
        <div class="stat">
          <small>Status</small>
          <strong>“Gerade in Arbeit”</strong>
          <div class="pill">
            <span class="tag">Refactor</span>
            <span class="tag">Docs</span>
            <span class="tag">Performance</span>
          </div>
        </div>
        <div class="stat">
          <small>Seite</small>
          <strong>Minimal. Schnell. Hübsch genug.</strong>
          <div class="pill">
            <span class="tag">Single-File</span>
            <span class="tag">No Build-Step</span>
            <span class="tag">GitHub Pages</span>
          </div>
        </div>
      </aside>
    </section>

    <section id="projekte" class="grid" aria-label="Projekte">
      <article class="card col-7">
        <div class="pad">
          <h2>Projekte</h2>
          <p class="muted" style="margin:0 0 10px">
            Platzhalter, bis du echte Projekte einträgst. Ich weiß, du machst das “später”.
          </p>

          <div class="list">
            <a class="item" href="https://github.com/Chaosnico9000" target="_blank" rel="noreferrer">
              <div class="top">
                <strong>BizMMonitoring</strong>
                <span class="badge ok">Blazor • Monitoring</span>
              </div>
              <p>Monitoring-Tooling, Services, Dashboards. Dinge, die piepen, wenn Server Unsinn machen.</p>
            </a>

            <a class="item" href="https://github.com/Chaosnico9000" target="_blank" rel="noreferrer">
              <div class="top">
                <strong>AZUBITOOLS</strong>
                <span class="badge warn">PDF • Reporting</span>
              </div>
              <p>PDF-Berichtshefte verwalten, sortieren, strukturieren. Bürokratie, aber wenigstens automatisiert.</p>
            </a>

            <a class="item" href="https://github.com/Chaosnico9000" target="_blank" rel="noreferrer">
              <div class="top">
                <strong>PluginTester</strong>
                <span class="badge danger">CLI • Hot Reload</span>
              </div>
              <p>Plugins scannen, bauen, ausführen, wieder beenden. Wie ein Zirkus, nur mit weniger Elefanten.</p>
            </a>
          </div>
        </div>
      </article>

      <article class="card col-5">
        <div class="pad">
          <h2>Was hier passieren soll</h2>
          <div class="list">
            <div class="item" style="cursor:default">
              <div class="top">
                <strong>Portfolio</strong>
                <span class="badge">Roadmap</span>
              </div>
              <p>Kurze, ehrliche Projektseiten mit Screenshots, Features, Tech-Stack und Links.</p>
            </div>

            <div class="item" style="cursor:default">
              <div class="top">
                <strong>Downloads</strong>
                <span class="badge">Artifacts</span>
              </div>
              <p>Releases, Demos, vielleicht mal ein Installer. Falls du dich traust.</p>
            </div>

            <div class="item" style="cursor:default">
              <div class="top">
                <strong>Changelog</strong>
                <span class="badge">git-cliff</span>
              </div>
              <p>Damit “was hab ich da eigentlich gemacht?” nicht jedes Mal ein Mystery-Game ist.</p>
            </div>
          </div>
        </div>
      </article>
    </section>

    <section id="stack" class="grid" aria-label="Stack">
      <article class="card col-6">
        <div class="pad">
          <h2>Stack</h2>
          <div class="list">
            <div class="item" style="cursor:default">
              <div class="top">
                <strong>.NET</strong>
                <span class="badge ok">Backend & Apps</span>
              </div>
              <p>Services, APIs, Tools. Stabil, performant, und du kannst damit sehr viel Unfug treiben.</p>
            </div>
            <div class="item" style="cursor:default">
              <div class="top">
                <strong>UI</strong>
                <span class="badge warn">WPF / Blazor</span>
              </div>
              <p>WPF wenn’s Desktop sein muss, Blazor wenn’s elegant im Browser sein soll.</p>
            </div>
            <div class="item" style="cursor:default">
              <div class="top">
                <strong>DevOps</strong>
                <span class="badge">CI/CD</span>
              </div>
              <p>Build, Test, Release. Maschinen machen Maschinen-Dinge, damit Menschen nicht weinen.</p>
            </div>
          </div>
        </div>
      </article>

      <article class="card col-6">
        <div class="pad">
          <h2>Mini-FAQ</h2>
          <div class="list">
            <div class="item" style="cursor:default">
              <div class="top">
                <strong>Ist das ein Template?</strong>
                <span class="badge">Ja.</span>
              </div>
              <p>Du ersetzt die Links und Texte durch echte Inhalte. Verrückt, ich weiß.</p>
            </div>
            <div class="item" style="cursor:default">
              <div class="top">
                <strong>Warum Single-File?</strong>
                <span class="badge ok">Schnell</span>
              </div>
              <p>Weil GitHub Pages dann einfach funktioniert und du keinen Build-Kram pflegen musst.</p>
            </div>
            <div class="item" style="cursor:default">
              <div class="top">
                <strong>Kann ich mehr Seiten machen?</strong>
                <span class="badge warn">Klar</span>
              </div>
              <p>Leg Ordner an (z.B. <span class="kbd">/projekte/</span>) und pack dort eigene <span class="kbd">index.html</span> rein.</p>
            </div>
          </div>
        </div>
      </article>
    </section>

    <section id="kontakt" class="grid" aria-label="Kontakt">
      <article class="card col-12">
        <div class="pad">
          <h2>Kontakt</h2>
          <p class="muted" style="margin:0 0 12px">
            Du kannst hier echte Links eintragen, oder du lässt es und wunderst dich später, warum dich niemand findet.
          </p>

          <div class="list" style="display:grid; grid-template-columns: repeat(12, 1fr); gap:12px; margin:0;">
            <a class="item" style="grid-column: span 6" href="https://github.com/Chaosnico9000" rel="me">
              <div class="top">
                <strong>GitHub</strong>
                <span class="badge">/Chaosnico9000</span>
              </div>
              <p>Repos, Issues, Releases. Der ganze Spaß.</p>
            </a>

            <a class="item" style="grid-column: span 6" href="#" onclick="copyEmail(event)">
              <div class="top">
                <strong>E-Mail</strong>
                <span class="badge warn">klicken zum kopieren</span>
              </div>
              <p><span id="emailText" class="kbd">dein.name@example.com</span> <span class="muted">(ersetzen)</span></p>
            </a>
          </div>

          <footer>
            <div>© <span id="year"></span> Chaosnico9000. Keine Garantien, nur gute Absichten.</div>
            <div class="muted">Built with HTML + CSS + menschlicher Sturheit.</div>
          </footer>
        </div>
      </article>
    </section>
  </main>

  <script>
    // Ja, JS. Keine Panik. Es kopiert nur eine Mail-Adresse und setzt das Jahr.
    document.getElementById("year").textContent = new Date().getFullYear();

    function copyEmail(ev){
      ev.preventDefault();
      const el = document.getElementById("emailText");
      const text = el.textContent.trim();
      navigator.clipboard?.writeText(text).then(() => {
        toast("E-Mail kopiert. Jetzt musst du nur noch… naja… schreiben.");
      }).catch(() => {
        toast("Clipboard ging nicht. Willkommen in der Realität. Markier es halt manuell.");
      });
    }

    function toast(msg){
      const t = document.createElement("div");
      t.textContent = msg;
      t.style.position = "fixed";
      t.style.left = "50%";
      t.style.bottom = "22px";
      t.style.transform = "translateX(-50%)";
      t.style.padding = "10px 14px";
      t.style.borderRadius = "14px";
      t.style.border = "1px solid rgba(255,255,255,.14)";
      t.style.background = "rgba(0,0,0,.55)";
      t.style.backdropFilter = "blur(10px)";
      t.style.color = "rgba(255,255,255,.85)";
      t.style.fontFamily = "ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, 'Liberation Mono', 'Courier New', monospace";
      t.style.fontSize = "12px";
      t.style.boxShadow = "0 18px 50px rgba(0,0,0,.55)";
      t.style.zIndex = "9999";
      document.body.appendChild(t);
      setTimeout(() => t.remove(), 2400);
    }
  </script>
</body>
</html>
