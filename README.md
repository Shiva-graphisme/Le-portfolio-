# Le-portfolio-<!DOCTYPE html>
<!DOCTYPE html>

<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Shiva — Portfolio Créatif</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --gold: #c9a84c;
      --gold-light: #e8c97a;
      --gold-dim: rgba(201,168,76,0.18);
      --bg: #0b0b0b;
      --bg2: #111111;
      --card: #161616;
      --border: rgba(201,168,76,0.2);
      --text: #f0ede8;
      --muted: #7a7670;
      --white: #fff;
    }
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }
    body { font-family: 'DM Sans', sans-serif; background: var(--bg); color: var(--text); overflow-x: hidden; }
    @media (pointer: fine) { body { cursor: none; } }

```
.cursor { position: fixed; top: 0; left: 0; z-index: 9999; width: 12px; height: 12px; background: var(--gold); border-radius: 50%; pointer-events: none; transform: translate(-50%,-50%); mix-blend-mode: difference; display:none; }
.cursor-ring { position: fixed; top: 0; left: 0; z-index: 9998; width: 40px; height: 40px; border: 1px solid var(--gold); border-radius: 50%; pointer-events: none; transform: translate(-50%,-50%); opacity: 0.5; transition: left 0.18s ease, top 0.18s ease; display:none; }
@media (pointer: fine) { .cursor { display:block; } .cursor-ring { display:block; } }

body::before { content: ''; position: fixed; inset: 0; z-index: 9000; background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E"); pointer-events: none; opacity: 0.35; }

nav { position: fixed; top: 0; inset-x: 0; z-index: 500; display: flex; align-items: center; justify-content: space-between; padding: 1.4rem 3rem; background: rgba(11,11,11,0.85); backdrop-filter: blur(20px); border-bottom: 1px solid var(--border); }
.nav-logo { font-family: 'Playfair Display', serif; font-size: 1.5rem; font-weight: 900; letter-spacing: 0.08em; color: var(--gold); text-decoration: none; }
.nav-links { display: flex; gap: 2.5rem; list-style: none; }
.nav-links a { font-size: 0.82rem; letter-spacing: 0.15em; text-transform: uppercase; color: var(--muted); text-decoration: none; transition: color 0.25s; position: relative; }
.nav-links a::after { content: ''; position: absolute; bottom: -4px; left: 0; width: 0; height: 1px; background: var(--gold); transition: width 0.3s; }
.nav-links a:hover { color: var(--gold); }
.nav-links a:hover::after { width: 100%; }
.nav-admin-btn { font-size: 0.75rem; letter-spacing: 0.12em; text-transform: uppercase; border: 1px solid var(--border); color: var(--muted); background: transparent; padding: 0.5rem 1.2rem; border-radius: 4px; cursor: pointer; transition: all 0.25s; }
.nav-admin-btn:hover { border-color: var(--gold); color: var(--gold); }
.mobile-toggle { display: none; background: none; border: none; color: var(--gold); cursor: pointer; }

.hero { min-height: 100vh; display: flex; flex-direction: column; align-items: center; justify-content: center; text-align: center; padding: 8rem 2rem 4rem; position: relative; overflow: hidden; }
.hero-bg { position: absolute; inset: 0; z-index: 0; background: radial-gradient(ellipse 80% 60% at 50% 60%, rgba(201,168,76,0.07) 0%, transparent 70%); }
.hero-line { position: absolute; top: 0; left: 50%; transform: translateX(-50%); width: 1px; height: 120px; background: linear-gradient(to bottom, transparent, var(--gold)); animation: lineDown 1.2s ease forwards; }
@keyframes lineDown { from { height: 0; opacity: 0; } to { height: 120px; opacity: 1; } }
.hero-eyebrow { font-size: 0.72rem; letter-spacing: 0.35em; text-transform: uppercase; color: var(--gold); margin-bottom: 1.5rem; opacity: 0; animation: fadeUp 0.8s 0.4s ease forwards; }
.hero-title { font-family: 'Playfair Display', serif; font-size: clamp(4rem, 10vw, 9rem); font-weight: 900; line-height: 0.92; letter-spacing: -0.02em; color: var(--text); opacity: 0; animation: fadeUp 0.9s 0.6s ease forwards; }
.hero-title em { font-style: italic; color: var(--gold); }
.hero-sub { max-width: 480px; margin: 2rem auto 0; font-size: 1rem; line-height: 1.7; color: var(--muted); opacity: 0; animation: fadeUp 0.9s 0.85s ease forwards; }
.hero-cta { margin-top: 3rem; opacity: 0; animation: fadeUp 0.9s 1.05s ease forwards; }
.btn-gold { display: inline-flex; align-items: center; gap: 0.6rem; background: var(--gold); color: #0b0b0b; font-size: 0.82rem; letter-spacing: 0.15em; text-transform: uppercase; font-weight: 600; padding: 1rem 2.4rem; border-radius: 2px; text-decoration: none; transition: background 0.25s, transform 0.2s; cursor: pointer; }
.btn-gold:hover { background: var(--gold-light); transform: translateY(-2px); }
.hero-scroll { position: absolute; bottom: 2.5rem; left: 50%; transform: translateX(-50%); display: flex; flex-direction: column; align-items: center; gap: 0.5rem; font-size: 0.68rem; letter-spacing: 0.3em; text-transform: uppercase; color: var(--muted); opacity: 0; animation: fadeUp 1s 1.4s ease forwards; }
.hero-scroll-arrow { width: 1px; height: 50px; background: linear-gradient(to bottom, var(--gold), transparent); animation: scrollPulse 2s ease-in-out infinite; }
@keyframes scrollPulse { 0%,100% { opacity: 1; } 50% { opacity: 0.3; } }
@keyframes fadeUp { from { opacity: 0; transform: translateY(30px); } to { opacity: 1; transform: translateY(0); } }

.section-portfolio { padding: 8rem 3rem 6rem; max-width: 1400px; margin: 0 auto; }
.section-header { display: flex; align-items: flex-end; justify-content: space-between; margin-bottom: 5rem; border-bottom: 1px solid var(--border); padding-bottom: 2rem; }
.section-num { font-size: 0.7rem; letter-spacing: 0.3em; text-transform: uppercase; color: var(--gold); margin-bottom: 0.5rem; }
.section-title { font-family: 'Playfair Display', serif; font-size: clamp(2.5rem, 5vw, 4.5rem); font-weight: 700; line-height: 1; color: var(--text); }
.section-count { font-family: 'Playfair Display', serif; font-size: 5rem; font-weight: 900; color: var(--gold-dim); line-height: 1; opacity: 0.6; }

.portfolio-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(340px, 1fr)); gap: 2px; }
.portfolio-card { position: relative; overflow: hidden; background: var(--card); aspect-ratio: 3/4; cursor: none; }
.portfolio-card img { width: 100%; height: 100%; object-fit: cover; transition: transform 0.8s cubic-bezier(0.25,0.46,0.45,0.94), filter 0.5s; filter: brightness(0.85) saturate(0.9); }
.portfolio-card:hover img { transform: scale(1.08); filter: brightness(0.6) saturate(1.1); }
.portfolio-card-overlay { position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: flex-end; padding: 2rem; background: linear-gradient(to top, rgba(0,0,0,0.85) 0%, transparent 60%); transform: translateY(30px); opacity: 0; transition: transform 0.45s ease, opacity 0.45s ease; }
.portfolio-card:hover .portfolio-card-overlay { transform: translateY(0); opacity: 1; }
.card-meta { display: flex; justify-content: space-between; align-items: center; margin-bottom: 0.5rem; }
.card-cat { font-size: 0.7rem; letter-spacing: 0.2em; text-transform: uppercase; color: var(--gold); }
.card-year { font-size: 0.75rem; color: var(--muted); }
.card-title { font-family: 'Playfair Display', serif; font-size: 1.6rem; font-weight: 700; line-height: 1.15; color: var(--white); margin-bottom: 0.5rem; }
.card-desc { font-size: 0.85rem; color: rgba(240,237,232,0.7); line-height: 1.6; }
.card-delete-btn { margin-top: 1rem; background: none; border: 1px solid rgba(239,68,68,0.5); color: #f87171; font-size: 0.75rem; letter-spacing: 0.1em; padding: 0.4rem 1rem; border-radius: 2px; cursor: none; transition: all 0.2s; display: none; align-items: center; gap: 0.4rem; }
.card-delete-btn:hover { background: rgba(239,68,68,0.15); }
body.admin-active .card-delete-btn { display: flex; }
.card-corner { position: absolute; top: 1.2rem; left: 1.2rem; font-size: 0.65rem; letter-spacing: 0.2em; text-transform: uppercase; background: rgba(11,11,11,0.8); color: var(--gold); padding: 0.3rem 0.7rem; border-radius: 2px; backdrop-filter: blur(8px); }

.section-about { padding: 8rem 3rem; max-width: 1400px; margin: 0 auto; display: grid; grid-template-columns: 1fr 1fr; gap: 6rem; align-items: center; }
.about-rect { width: 100%; aspect-ratio: 4/5; background: var(--card); border: 1px solid var(--border); display: flex; align-items: center; justify-content: center; position: relative; overflow: hidden; }
.about-rect::before { content: ''; position: absolute; inset: 0; background: radial-gradient(ellipse at 30% 40%, rgba(201,168,76,0.12) 0%, transparent 60%); }
.about-monogram { font-family: 'Playfair Display', serif; font-size: 12rem; font-weight: 900; font-style: italic; color: rgba(201,168,76,0.08); user-select: none; line-height: 1; }
.about-tag { position: absolute; bottom: 2rem; right: -1.5rem; background: var(--gold); color: #0b0b0b; font-size: 0.7rem; letter-spacing: 0.2em; text-transform: uppercase; font-weight: 600; padding: 0.8rem 1.6rem; writing-mode: vertical-rl; }
.about-text { font-size: 1rem; line-height: 1.9; color: var(--muted); margin-bottom: 2rem; }
.about-stats { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-top: 3rem; }
.stat { border-top: 1px solid var(--border); padding-top: 1.2rem; }
.stat-num { font-family: 'Playfair Display', serif; font-size: 2.8rem; font-weight: 700; color: var(--gold); line-height: 1; }
.stat-label { font-size: 0.75rem; letter-spacing: 0.15em; text-transform: uppercase; color: var(--muted); margin-top: 0.3rem; }

.section-contact { padding: 8rem 3rem; background: var(--bg2); border-top: 1px solid var(--border); }
.contact-inner { max-width: 700px; margin: 0 auto; text-align: center; }
.contact-tagline { font-size: 1.1rem; color: var(--muted); line-height: 1.8; margin-bottom: 3rem; }
.contact-email { display: inline-block; font-family: 'Playfair Display', serif; font-size: clamp(1.2rem, 3vw, 1.8rem); font-style: italic; color: var(--gold); text-decoration: none; border-bottom: 1px solid var(--border); padding-bottom: 0.3rem; transition: border-color 0.3s, color 0.3s; }
.contact-email:hover { color: var(--gold-light); border-color: var(--gold); }

.admin-panel { display: none; margin: 4rem 0 0; padding: 2.5rem; background: var(--card); border: 1px solid var(--border); }
body.admin-active .admin-panel { display: block; }
.admin-panel h3 { font-family: 'Playfair Display', serif; font-size: 1.8rem; color: var(--gold); margin-bottom: 2rem; display: flex; align-items: center; gap: 0.7rem; }
.admin-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
.admin-grid input, .admin-grid textarea { background: var(--bg2); border: 1px solid var(--border); color: var(--text); font-family: 'DM Sans', sans-serif; font-size: 0.9rem; padding: 0.9rem 1.2rem; border-radius: 2px; outline: none; transition: border-color 0.2s; cursor: text; }
.admin-grid input:focus, .admin-grid textarea:focus { border-color: var(--gold); }
.admin-grid textarea { grid-column: 1/-1; min-height: 100px; resize: vertical; }
.admin-save-btn { margin-top: 1.5rem; background: var(--gold); color: #0b0b0b; font-size: 0.82rem; letter-spacing: 0.15em; text-transform: uppercase; font-weight: 600; padding: 1rem 2.5rem; border: none; border-radius: 2px; cursor: pointer; transition: background 0.25s, transform 0.2s; display: inline-flex; align-items: center; gap: 0.6rem; }
.admin-save-btn:hover { background: var(--gold-light); transform: translateY(-2px); }

.modal-overlay { display: none; position: fixed; inset: 0; z-index: 800; background: rgba(0,0,0,0.85); backdrop-filter: blur(10px); align-items: center; justify-content: center; }
.modal-overlay.open { display: flex; }
.modal-box { background: var(--card); border: 1px solid var(--border); padding: 3rem; width: 90%; max-width: 420px; }
.modal-title { font-family: 'Playfair Display', serif; font-size: 2rem; font-weight: 700; color: var(--text); margin-bottom: 0.5rem; }
.modal-subtitle { font-size: 0.85rem; color: var(--muted); margin-bottom: 2rem; }
.modal-input { width: 100%; background: var(--bg2); border: 1px solid var(--border); color: var(--text); font-family: 'DM Sans', sans-serif; font-size: 1rem; padding: 1rem 1.2rem; border-radius: 2px; outline: none; margin-bottom: 1.5rem; transition: border-color 0.2s; cursor: text; }
.modal-input:focus { border-color: var(--gold); }
.modal-btns { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
.modal-btn-primary { background: var(--gold); color: #0b0b0b; font-size: 0.82rem; letter-spacing: 0.12em; text-transform: uppercase; font-weight: 600; padding: 1rem; border: none; border-radius: 2px; cursor: pointer; transition: background 0.25s; }
.modal-btn-primary:hover { background: var(--gold-light); }
.modal-btn-secondary { background: transparent; border: 1px solid var(--border); color: var(--muted); font-size: 0.82rem; padding: 1rem; border-radius: 2px; cursor: pointer; transition: border-color 0.25s, color 0.25s; }
.modal-btn-secondary:hover { border-color: var(--gold); color: var(--gold); }

footer { border-top: 1px solid var(--border); padding: 2rem 3rem; display: flex; align-items: center; justify-content: space-between; font-size: 0.78rem; color: var(--muted); letter-spacing: 0.08em; }
footer a { color: var(--gold); text-decoration: none; }

.mobile-nav { display: none; position: fixed; inset: 0; z-index: 490; background: var(--bg); flex-direction: column; align-items: center; justify-content: center; gap: 2.5rem; }
.mobile-nav.open { display: flex; }
.mobile-nav a { font-family: 'Playfair Display', serif; font-size: 3rem; font-weight: 700; font-style: italic; color: var(--text); text-decoration: none; transition: color 0.25s; }
.mobile-nav a:hover { color: var(--gold); }

.reveal { opacity: 1; transform: none; }
.reveal.visible { opacity: 1; transform: none; }
.reveal-delay-1 { }
.reveal-delay-2 { }
.reveal-delay-3 { }

@media (max-width: 900px) {
  nav { padding: 1.2rem 1.5rem; }
  .nav-links { display: none; }
  .nav-admin-btn { display: none; }
  .mobile-toggle { display: block; }
  .hero-title { font-size: clamp(3rem, 14vw, 6rem); }
  .section-portfolio { padding: 6rem 1.5rem; }
  .portfolio-grid { grid-template-columns: 1fr 1fr; gap: 2px; }
  .section-about { grid-template-columns: 1fr; gap: 3rem; padding: 5rem 1.5rem; }
  .about-tag { display: none; }
  .section-contact { padding: 6rem 1.5rem; }
  .admin-grid { grid-template-columns: 1fr; }
  footer { flex-direction: column; gap: 1rem; text-align: center; }
}
@media (max-width: 520px) {
  .portfolio-grid { grid-template-columns: 1fr; }
}
```

  </style>
</head>
<body>

  <div class="cursor" id="cursor"></div>
  <div class="cursor-ring" id="cursorRing"></div>

  <div class="mobile-nav" id="mobileNav">
    <a href="#portfolio" onclick="closeMobile()">Portfolio</a>
    <a href="#about" onclick="closeMobile()">A propos</a>
    <a href="#contact" onclick="closeMobile()">Contact</a>
  </div>

  <nav>
    <a href="#" class="nav-logo">SHIVA</a>
    <ul class="nav-links">
      <li><a href="#portfolio">Portfolio</a></li>
      <li><a href="#about">A propos</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
    <div style="display:flex;align-items:center;gap:1rem;">
      <button class="nav-admin-btn" id="adminBtn" onclick="openLogin()">Admin</button>
      <button class="mobile-toggle" onclick="toggleMobile()" aria-label="Menu">
        <svg id="menuIcon" width="22" height="22" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><line x1="3" y1="6" x2="21" y2="6"/><line x1="3" y1="12" x2="21" y2="12"/><line x1="3" y1="18" x2="21" y2="18"/></svg>
        <svg id="closeIcon" width="22" height="22" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24" style="display:none"><line x1="18" y1="6" x2="6" y2="18"/><line x1="6" y1="6" x2="18" y2="18"/></svg>
      </button>
    </div>
  </nav>

  <section class="hero" id="home">
    <div class="hero-bg"></div>
    <div class="hero-line"></div>
    <p class="hero-eyebrow" style="position:relative;z-index:1;">Direction Artistique &amp; Design Graphique</p>
    <h1 class="hero-title" style="position:relative;z-index:1;">Creer,<br><em>Inspirer,</em><br>Marquer.</h1>
    <p class="hero-sub" style="position:relative;z-index:1;">Portfolio de creation visuelle — affiches, identite de marque, photographie &amp; branding premium.</p>
    <div class="hero-cta" style="position:relative;z-index:1;">
      <a href="#portfolio" class="btn-gold">Voir les projets <svg width="16" height="16" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg></a>
    </div>
    <div class="hero-scroll">Scroll<div class="hero-scroll-arrow"></div></div>
  </section>

  <section class="section-portfolio" id="portfolio">
    <div class="section-header reveal">
      <div>
        <div class="section-num">01 — Selection</div>
        <h2 class="section-title">Galerie de<br>Projets</h2>
      </div>
      <div class="section-count" id="projectCount">02</div>
    </div>
    <div class="portfolio-grid" id="portfolioGrid"></div>
    <div class="admin-panel">
      <h3>Ajouter un projet</h3>
      <div class="admin-grid">
        <input type="text" id="newTitle" placeholder="Titre *"/>
        <input type="text" id="newImage" placeholder="URL de l'image *"/>
        <input type="text" id="newCategory" placeholder="Categorie"/>
        <input type="text" id="newYear" placeholder="Annee"/>
        <textarea id="newDesc" placeholder="Description"></textarea>
      </div>
      <button class="admin-save-btn" onclick="addProject()">Enregistrer</button>
    </div>
  </section>

  <section class="section-about" id="about">
    <div class="reveal">
      <div class="about-rect">
        <div class="about-monogram">S</div>
        <div class="about-tag">Creatif depuis 2020</div>
      </div>
    </div>
    <div>
      <div class="section-num reveal">02 — Profil</div>
      <h2 class="section-title reveal reveal-delay-1">Direction<br>Artistique</h2>
      <p class="about-text reveal reveal-delay-2">Passionne par l'image et la narration visuelle, je cree des identites graphiques qui marquent les esprits. De l'affiche au branding complet, chaque projet est une opportunite de tisser une histoire unique entre une marque et son audience.</p>
      <p class="about-text reveal reveal-delay-2">Mon approche mele esthetique cinematique, typographie expressive et direction photographique pour des resultats toujours authentiques et impactants.</p>
      <div class="about-stats reveal reveal-delay-3">
        <div class="stat"><div class="stat-num" id="statProjects">2+</div><div class="stat-label">Projets realises</div></div>
        <div class="stat"><div class="stat-num">4+</div><div class="stat-label">Annees d'experience</div></div>
        <div class="stat"><div class="stat-num">100%</div><div class="stat-label">Projets sur mesure</div></div>
        <div class="stat"><div class="stat-num">inf</div><div class="stat-label">Passion creative</div></div>
      </div>
    </div>
  </section>

  <section class="section-contact" id="contact">
    <div class="contact-inner">
      <div class="section-num reveal">03 — Contact</div>
      <h2 class="section-title reveal">Travaillons<br><em style="font-family:'Playfair Display',serif;font-style:italic;">Ensemble</em></h2>
      <p class="contact-tagline reveal">Un projet en tete ? Une collaboration a imaginer ?<br>Je suis disponible pour donner vie a vos idees.</p>
      <a href="/cdn-cgi/l/email-protection#2b4142584042454c474e5843425d4a6b4c464a424705484446" class="contact-email reveal"><span class="__cf_email__" data-cfemail="c7adaeb4acaea9a0aba2b4afaeb1a687a0aaa6aeabe9a4a8aa">[email&#160;protected]</span></a>
      <div style="margin-top:1.5rem;" class="reveal">
        <a href="https://wa.me/237658874939" target="_blank" class="contact-email" style="font-size:1.3rem;display:inline-flex;align-items:center;gap:0.7rem;border-bottom:none;">
          <svg width="22" height="22" fill="#c9a84c" viewBox="0 0 24 24"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
          +237 658 874 939
        </a>
      </div>
      <div style="margin-top:2rem;" class="reveal">
        <a href="/cdn-cgi/l/email-protection#452f2c362e2c2b222920362d2c3324052228242c296b262a28" class="btn-gold">Prendre contact</a>
      </div>
    </div>
  </section>

  <footer>
    <span>2024 <a href="#">Shiva</a> — Direction Artistique</span>
    <span style="letter-spacing:0.2em;">PORTFOLIO</span>
    <span style="cursor:pointer;color:var(--muted);padding:1rem;font-size:1rem;" onclick="openLogin()">Admin</span>
  </footer>

  <div class="modal-overlay" id="loginModal">
    <div class="modal-box">
      <h2 class="modal-title">Acces Admin</h2>
      <p class="modal-subtitle">Entrez le mot de passe pour gerer le portfolio.</p>
      <input type="password" class="modal-input" id="passInput" placeholder="Mot de passe secret"/>
      <div class="modal-btns">
        <button class="modal-btn-primary" onclick="handleLogin()">Connexion</button>
        <button class="modal-btn-secondary" onclick="closeLogin()">Annuler</button>
      </div>
    </div>
  </div>

  <script data-cfasync="false" src="/cdn-cgi/scripts/5c5dd728/cloudflare-static/email-decode.min.js"></script><script>

```
var DEFAULT_ITEMS = [
  { id: '1', title: 'Campus Bar', category: 'Restaurant Poster', description: 'Affiche promotionnelle avec mise en scene appetissante des plats, typographie bold et ambiance chaleureuse', imageUrl: 'https://i.ibb.co/rK1JBVVZ/IMG-7176.jpg', year: '2024' },
  { id: '2', title: 'Alexandre Shooting', category: 'Photography Services', description: 'Branding services photo avec esthetique cinematique', imageUrl: 'https://d2xsxph8kpxj0f.cloudfront.net/310519663356405594/SYWtHwBsBKdNV2fuuUx2B7/20240804_181245_11_-Ue3Kd5xvvYqL8W8zNLqGR.png', year: '2024' },
  { id: '3', title: 'One Day', category: 'Music Cover', description: 'Pochette single pour El Fredo x Ice Kwaro, direction artistique cinematique en rouge et blanc', imageUrl: 'https://i.ibb.co/Ps0STZjc/20240711-190144.png', year: '2024' },
  { id: '4', title: 'La Nuit des Artistes Tchadiens', category: 'Event Poster', description: 'Affiche evenementielle pour une nuit culturelle tchadienne a Douala, ambiance sombre et vibrante', imageUrl: 'https://i.ibb.co/Mx7Yr36p/IMG-9387.png', year: '2025' },
  { id: '5', title: 'Showcase Succy B', category: 'Event Poster', description: 'Affiche showcase pour Succy B le Lion, design dynamique avec typographie impactante et ambiance artistique', imageUrl: 'https://i.ibb.co/WpnK918V/IMG-6809.jpg', year: '2024' }
];

var items;
try { var s = localStorage.getItem('portfolioItems'); items = s ? JSON.parse(s) : DEFAULT_ITEMS; } catch(e) { items = DEFAULT_ITEMS; }

var isAdmin;
try { isAdmin = localStorage.getItem('adminAccess') === 'true'; } catch(e) { isAdmin = false; }

function saveItems() { try { localStorage.setItem('portfolioItems', JSON.stringify(items)); } catch(e) {} }

function renderGrid() {
  var grid = document.getElementById('portfolioGrid');
  var count = document.getElementById('projectCount');
  var stat = document.getElementById('statProjects');
  if (count) count.textContent = String(items.length).padStart(2, '0');
  if (stat) stat.textContent = items.length + '+';
  if (!grid) return;
  var html = '';
  for (var i = 0; i < items.length; i++) {
    var item = items[i];
    var delBtn = isAdmin ? '<button class="card-delete-btn" onclick="deleteProject(\'' + item.id + '\')"><svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><polyline points="3 6 5 6 21 6"/><path d="M19 6l-1 14H6L5 6"/><path d="M10 11v6"/><path d="M14 11v6"/><path d="M9 6V4h6v2"/></svg> Supprimer</button>' : '';
    html += '<div class="portfolio-card"><div class="card-corner">' + item.category + '</div><img src="' + item.imageUrl + '" alt="' + item.title + '" loading="lazy"/><div class="portfolio-card-overlay"><div class="card-meta"><span class="card-cat">' + item.category + '</span><span class="card-year">' + item.year + '</span></div><h3 class="card-title">' + item.title + '</h3><p class="card-desc">' + item.description + '</p>' + delBtn + '</div></div>';
  }
  grid.innerHTML = html;
}

function openLogin() { document.getElementById('loginModal').classList.add('open'); }
function closeLogin() { document.getElementById('loginModal').classList.remove('open'); document.getElementById('passInput').value = ''; }

function handleLogin() {
  var pass = document.getElementById('passInput').value;
  if (pass === 'Orijeanori235') {
    isAdmin = true;
    try { localStorage.setItem('adminAccess', 'true'); } catch(e) {}
    document.body.classList.add('admin-active');
    closeLogin();
    var btn = document.getElementById('adminBtn');
    if (btn) btn.textContent = 'Admin';
    renderGrid();
  } else {
    var inp = document.getElementById('passInput');
    inp.style.borderColor = '#f87171';
    setTimeout(function() { inp.style.borderColor = ''; }, 1200);
  }
}

function addProject() {
  var title = document.getElementById('newTitle').value.trim();
  var imageUrl = document.getElementById('newImage').value.trim();
  if (!title || !imageUrl) { alert('Titre et image obligatoires'); return; }
  items.push({ id: Date.now().toString(), title: title, category: document.getElementById('newCategory').value.trim() || 'Projet', description: document.getElementById('newDesc').value.trim(), imageUrl: imageUrl, year: document.getElementById('newYear').value.trim() || new Date().getFullYear().toString() });
  saveItems(); renderGrid();
  ['newTitle','newImage','newCategory','newYear','newDesc'].forEach(function(id) { document.getElementById(id).value = ''; });
}

function deleteProject(id) {
  if (!confirm('Supprimer ce projet ?')) return;
  items = items.filter(function(i) { return i.id !== id; });
  saveItems(); renderGrid();
}

var mobileOpen = false;
function toggleMobile() {
  mobileOpen = !mobileOpen;
  document.getElementById('mobileNav').classList.toggle('open', mobileOpen);
  document.getElementById('menuIcon').style.display = mobileOpen ? 'none' : 'block';
  document.getElementById('closeIcon').style.display = mobileOpen ? 'block' : 'none';
}
function closeMobile() {
  mobileOpen = false;
  document.getElementById('mobileNav').classList.remove('open');
  document.getElementById('menuIcon').style.display = 'block';
  document.getElementById('closeIcon').style.display = 'none';
}

var cursor = document.getElementById('cursor');
var ring = document.getElementById('cursorRing');
var mx = 0, my = 0;
document.addEventListener('mousemove', function(e) {
  mx = e.clientX; my = e.clientY;
  if (cursor) { cursor.style.left = mx + 'px'; cursor.style.top = my + 'px'; }
  if (ring) { ring.style.left = mx + 'px'; ring.style.top = my + 'px'; }
});

var obs = new IntersectionObserver(function(entries) {
  entries.forEach(function(e) { if (e.isIntersecting) { e.target.classList.add('visible'); obs.unobserve(e.target); } });
}, { threshold: 0.12 });
document.querySelectorAll('.reveal').forEach(function(el) { obs.observe(el); });

renderGrid();
if (isAdmin) { document.body.classList.add('admin-active'); }

setTimeout(function() {
  document.querySelectorAll('.portfolio-card').forEach(function(el, i) {
    el.style.opacity = '0'; el.style.transform = 'translateY(30px)';
    el.style.transition = 'opacity 0.7s ' + (i * 0.1) + 's ease, transform 0.7s ' + (i * 0.1) + 's ease';
    var cardObs = new IntersectionObserver(function(entries) {
      entries.forEach(function(e) { if (e.isIntersecting) { e.target.style.opacity = '1'; e.target.style.
```
