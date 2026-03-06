<!DOCTYPE html>

<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Shiva Graphisme — Portfolio</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --gold: #c9a84c;
      --gold-light: #e8c97a;
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

```
/* NAV */
nav { position: fixed; top: 0; inset-x: 0; z-index: 500; display: flex; align-items: center; justify-content: space-between; padding: 1.2rem 2rem; background: rgba(11,11,11,0.92); backdrop-filter: blur(20px); border-bottom: 1px solid var(--border); }
.nav-logo { font-family: 'Playfair Display', serif; font-size: 1.4rem; font-weight: 900; letter-spacing: 0.08em; color: var(--gold); text-decoration: none; }
.nav-links { display: flex; gap: 2rem; list-style: none; }
.nav-links a { font-size: 0.82rem; letter-spacing: 0.15em; text-transform: uppercase; color: var(--muted); text-decoration: none; transition: color 0.25s; }
.nav-links a:hover { color: var(--gold); }
.nav-admin-btn { font-size: 0.75rem; letter-spacing: 0.12em; text-transform: uppercase; border: 1px solid var(--border); color: var(--muted); background: transparent; padding: 0.5rem 1.2rem; border-radius: 4px; cursor: pointer; transition: all 0.25s; }
.nav-admin-btn:hover { border-color: var(--gold); color: var(--gold); }
.mobile-toggle { display: none; background: none; border: none; color: var(--gold); cursor: pointer; font-size: 1.5rem; }
.mobile-nav { display: none; position: fixed; inset: 0; z-index: 490; background: var(--bg); flex-direction: column; align-items: center; justify-content: center; gap: 2.5rem; }
.mobile-nav.open { display: flex; }
.mobile-nav a { font-family: 'Playfair Display', serif; font-size: 2.5rem; font-weight: 700; font-style: italic; color: var(--text); text-decoration: none; }
.mobile-nav a:hover { color: var(--gold); }

/* HERO */
.hero { min-height: 100vh; display: flex; flex-direction: column; align-items: center; justify-content: center; text-align: center; padding: 8rem 2rem 4rem; background: radial-gradient(ellipse 80% 60% at 50% 60%, rgba(201,168,76,0.07) 0%, transparent 70%); }
.hero-eyebrow { font-size: 0.72rem; letter-spacing: 0.35em; text-transform: uppercase; color: var(--gold); margin-bottom: 1.5rem; }
.hero-title { font-family: 'Playfair Display', serif; font-size: clamp(3.5rem, 10vw, 9rem); font-weight: 900; line-height: 0.95; color: var(--text); }
.hero-title em { font-style: italic; color: var(--gold); }
.hero-sub { max-width: 480px; margin: 2rem auto 0; font-size: 1rem; line-height: 1.7; color: var(--muted); }
.hero-cta { margin-top: 3rem; }
.btn-gold { display: inline-flex; align-items: center; gap: 0.6rem; background: var(--gold); color: #0b0b0b; font-size: 0.82rem; letter-spacing: 0.15em; text-transform: uppercase; font-weight: 600; padding: 1rem 2.4rem; border-radius: 2px; text-decoration: none; transition: background 0.25s; cursor: pointer; }
.btn-gold:hover { background: var(--gold-light); }

/* PORTFOLIO */
.section-portfolio { padding: 6rem 2rem; max-width: 1400px; margin: 0 auto; }
.section-header { margin-bottom: 4rem; border-bottom: 1px solid var(--border); padding-bottom: 2rem; display: flex; align-items: flex-end; justify-content: space-between; }
.section-num { font-size: 0.7rem; letter-spacing: 0.3em; text-transform: uppercase; color: var(--gold); margin-bottom: 0.5rem; }
.section-title { font-family: 'Playfair Display', serif; font-size: clamp(2rem, 5vw, 4rem); font-weight: 700; line-height: 1; color: var(--text); }
.section-count { font-family: 'Playfair Display', serif; font-size: 4rem; font-weight: 900; color: rgba(201,168,76,0.15); line-height: 1; }
.portfolio-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; }

.portfolio-card { position: relative; overflow: hidden; background: var(--card); border-radius: 4px; }
.portfolio-card img { width: 100%; aspect-ratio: 3/4; object-fit: cover; display: block; transition: transform 0.6s ease; }
.portfolio-card:hover img { transform: scale(1.05); }
.card-info { padding: 1.2rem; }
.card-cat { font-size: 0.68rem; letter-spacing: 0.2em; text-transform: uppercase; color: var(--gold); }
.card-title { font-family: 'Playfair Display', serif; font-size: 1.2rem; font-weight: 700; color: var(--text); margin: 0.3rem 0; }
.card-desc { font-size: 0.8rem; color: var(--muted); line-height: 1.5; }
.card-year { font-size: 0.75rem; color: var(--muted); margin-top: 0.3rem; }
.card-delete-btn { display: none; margin-top: 0.8rem; background: none; border: 1px solid rgba(239,68,68,0.5); color: #f87171; font-size: 0.75rem; padding: 0.4rem 1rem; border-radius: 2px; cursor: pointer; }
body.admin-active .card-delete-btn { display: block; }

/* ABOUT */
.section-about { padding: 6rem 2rem; max-width: 1400px; margin: 0 auto; display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: center; }
.about-rect { width: 100%; aspect-ratio: 4/5; background: var(--card); border: 1px solid var(--border); display: flex; align-items: center; justify-content: center; }
.about-monogram { font-family: 'Playfair Display', serif; font-size: 10rem; font-weight: 900; font-style: italic; color: rgba(201,168,76,0.08); }
.about-text { font-size: 1rem; line-height: 1.9; color: var(--muted); margin-bottom: 1.5rem; }
.about-stats { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-top: 2.5rem; }
.stat { border-top: 1px solid var(--border); padding-top: 1rem; }
.stat-num { font-family: 'Playfair Display', serif; font-size: 2.5rem; font-weight: 700; color: var(--gold); }
.stat-label { font-size: 0.72rem; letter-spacing: 0.15em; text-transform: uppercase; color: var(--muted); }

/* CONTACT */
.section-contact { padding: 6rem 2rem; background: var(--bg2); border-top: 1px solid var(--border); text-align: center; }
.contact-inner { max-width: 600px; margin: 0 auto; }
.contact-tagline { font-size: 1rem; color: var(--muted); line-height: 1.8; margin-bottom: 2.5rem; }
.contact-email { display: inline-block; font-family: 'Playfair Display', serif; font-size: clamp(1.1rem, 3vw, 1.7rem); font-style: italic; color: var(--gold); text-decoration: none; border-bottom: 1px solid var(--border); padding-bottom: 0.3rem; }
.contact-whatsapp { display: inline-flex; align-items: center; gap: 0.6rem; font-family: 'Playfair Display', serif; font-size: 1.3rem; font-style: italic; color: var(--gold); text-decoration: none; margin-top: 1rem; }

/* ADMIN */
.admin-panel { display: none; margin: 3rem 0 0; padding: 2rem; background: var(--card); border: 1px solid var(--border); }
body.admin-active .admin-panel { display: block; }
.admin-panel h3 { font-family: 'Playfair Display', serif; font-size: 1.5rem; color: var(--gold); margin-bottom: 1.5rem; }
.admin-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
.admin-grid input, .admin-grid textarea { background: var(--bg2); border: 1px solid var(--border); color: var(--text); font-family: 'DM Sans', sans-serif; font-size: 0.9rem; padding: 0.8rem 1rem; border-radius: 2px; outline: none; }
.admin-grid input:focus, .admin-grid textarea:focus { border-color: var(--gold); }
.admin-grid textarea { grid-column: 1/-1; min-height: 80px; }
.admin-save-btn { margin-top: 1rem; background: var(--gold); color: #0b0b0b; font-size: 0.82rem; letter-spacing: 0.1em; text-transform: uppercase; font-weight: 600; padding: 0.9rem 2rem; border: none; border-radius: 2px; cursor: pointer; }

/* MODAL */
.modal-overlay { display: none; position: fixed; inset: 0; z-index: 800; background: rgba(0,0,0,0.88); align-items: center; justify-content: center; }
.modal-overlay.open { display: flex; }
.modal-box { background: var(--card); border: 1px solid var(--border); padding: 2.5rem; width: 90%; max-width: 400px; border-radius: 4px; }
.modal-title { font-family: 'Playfair Display', serif; font-size: 1.8rem; color: var(--text); margin-bottom: 0.4rem; }
.modal-subtitle { font-size: 0.85rem; color: var(--muted); margin-bottom: 1.8rem; }
.modal-input { width: 100%; background: var(--bg2); border: 1px solid var(--border); color: var(--text); font-size: 1rem; padding: 0.9rem 1rem; border-radius: 2px; outline: none; margin-bottom: 1.2rem; }
.modal-input:focus { border-color: var(--gold); }
.modal-btns { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
.modal-btn-primary { background: var(--gold); color: #0b0b0b; font-size: 0.82rem; font-weight: 600; padding: 0.9rem; border: none; border-radius: 2px; cursor: pointer; }
.modal-btn-secondary { background: transparent; border: 1px solid var(--border); color: var(--muted); font-size: 0.82rem; padding: 0.9rem; border-radius: 2px; cursor: pointer; }

/* FOOTER */
footer { border-top: 1px solid var(--border); padding: 1.5rem 2rem; display: flex; align-items: center; justify-content: space-between; font-size: 0.78rem; color: var(--muted); }
footer a { color: var(--gold); text-decoration: none; }
.footer-admin { cursor: pointer; color: var(--muted); padding: 0.5rem; }

/* RESPONSIVE */
@media (max-width: 900px) {
  .nav-links { display: none; }
  .nav-admin-btn { display: none; }
  .mobile-toggle { display: block; }
  .portfolio-grid { grid-template-columns: 1fr 1fr; }
  .section-about { grid-template-columns: 1fr; gap: 2.5rem; }
}
@media (max-width: 520px) {
  .portfolio-grid { grid-template-columns: 1fr; }
  .admin-grid { grid-template-columns: 1fr; }
}
```

  </style>
</head>
<body>

  <!-- Mobile Nav -->

  <div class="mobile-nav" id="mobileNav">
    <a href="#portfolio" onclick="closeMobile()">Portfolio</a>
    <a href="#about" onclick="closeMobile()">A propos</a>
    <a href="#contact" onclick="closeMobile()">Contact</a>
  </div>

  <!-- Nav -->

  <nav>
    <a href="#" class="nav-logo">SHIVA</a>
    <ul class="nav-links">
      <li><a href="#portfolio">Portfolio</a></li>
      <li><a href="#about">A propos</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
    <div style="display:flex;align-items:center;gap:1rem;">
      <button class="nav-admin-btn" id="adminBtn" onclick="openLogin()">Admin</button>
      <button class="mobile-toggle" onclick="toggleMobile()">&#9776;</button>
    </div>
  </nav>

  <!-- Hero -->

  <section class="hero" id="home">
    <p class="hero-eyebrow">Direction Artistique &amp; Design Graphique</p>
    <h1 class="hero-title">Creer,<br><em>Inspirer,</em><br>Marquer.</h1>
    <p class="hero-sub">Portfolio de creation visuelle — affiches, identite de marque, photographie &amp; branding premium.</p>
    <div class="hero-cta">
      <a href="#portfolio" class="btn-gold">Voir les projets &rarr;</a>
    </div>
  </section>

  <!-- Portfolio -->

  <section class="section-portfolio" id="portfolio">
    <div class="section-header">
      <div>
        <div class="section-num">01 — Selection</div>
        <h2 class="section-title">Galerie de<br>Projets</h2>
      </div>
      <div class="section-count">05</div>
    </div>

```
<div class="portfolio-grid" id="portfolioGrid">
  <div class="portfolio-card">
    <img src="https://i.ibb.co/rK1JBVVZ/IMG-7176.jpg" alt="Campus Bar" loading="lazy"/>
    <div class="card-info">
      <div class="card-cat">Restaurant Poster</div>
      <h3 class="card-title">Campus Bar</h3>
      <p class="card-desc">Affiche promotionnelle avec mise en scene appetissante des plats, typographie bold et ambiance chaleureuse</p>
      <div class="card-year">2024</div>
      <button class="card-delete-btn" onclick="deleteCard(this)">Supprimer</button>
    </div>
  </div>
  <div class="portfolio-card">
    <img src="https://d2xsxph8kpxj0f.cloudfront.net/310519663356405594/SYWtHwBsBKdNV2fuuUx2B7/20240804_181245_11_-Ue3Kd5xvvYqL8W8zNLqGR.png" alt="Alexandre Shooting" loading="lazy"/>
    <div class="card-info">
      <div class="card-cat">Photography Services</div>
      <h3 class="card-title">Alexandre Shooting</h3>
      <p class="card-desc">Branding services photo avec esthetique cinematique</p>
      <div class="card-year">2024</div>
      <button class="card-delete-btn" onclick="deleteCard(this)">Supprimer</button>
    </div>
  </div>
  <div class="portfolio-card">
    <img src="https://i.ibb.co/Ps0STZjc/20240711-190144.png" alt="One Day" loading="lazy"/>
    <div class="card-info">
      <div class="card-cat">Music Cover</div>
      <h3 class="card-title">One Day</h3>
      <p class="card-desc">Pochette single pour El Fredo x Ice Kwaro, direction artistique cinematique en rouge et blanc</p>
      <div class="card-year">2024</div>
      <button class="card-delete-btn" onclick="deleteCard(this)">Supprimer</button>
    </div>
  </div>
  <div class="portfolio-card">
    <img src="https://i.ibb.co/Mx7Yr36p/IMG-9387.png" alt="Nuit des Artistes" loading="lazy"/>
    <div class="card-info">
      <div class="card-cat">Event Poster</div>
      <h3 class="card-title">La Nuit des Artistes Tchadiens</h3>
      <p class="card-desc">Affiche evenementielle pour une nuit culturelle tchadienne a Douala, ambiance sombre et vibrante</p>
      <div class="card-year">2025</div>
      <button class="card-delete-btn" onclick="deleteCard(this)">Supprimer</button>
    </div>
  </div>
  <div class="portfolio-card">
    <img src="https://i.ibb.co/WpnK918V/IMG-6809.jpg" alt="Showcase Succy B" loading="lazy"/>
    <div class="card-info">
      <div class="card-cat">Event Poster</div>
      <h3 class="card-title">Showcase Succy B</h3>
      <p class="card-desc">Affiche showcase pour Succy B le Lion, design dynamique avec typographie impactante et ambiance artistique</p>
      <div class="card-year">2024</div>
      <button class="card-delete-btn" onclick="deleteCard(this)">Supprimer</button>
    </div>
  </div>
</div>

<!-- Admin Add Form -->
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
```

  </section>

  <!-- About -->

  <section class="section-about" id="about">
    <div>
      <div class="about-rect"><div class="about-monogram">S</div></div>
    </div>
    <div>
      <div class="section-num">02 — Profil</div>
      <h2 class="section-title" style="margin-bottom:1.5rem;">Direction<br>Artistique</h2>
      <p class="about-text">Passionne par l'image et la narration visuelle, je cree des identites graphiques qui marquent les esprits. De l'affiche au branding complet, chaque projet est une opportunite de tisser une histoire unique entre une marque et son audience.</p>
      <p class="about-text">Mon approche mele esthetique cinematique, typographie expressive et direction photographique pour des resultats toujours authentiques et impactants.</p>
      <div class="about-stats">
        <div class="stat"><div class="stat-num">5+</div><div class="stat-label">Projets realises</div></div>
        <div class="stat"><div class="stat-num">4+</div><div class="stat-label">Annees d'experience</div></div>
        <div class="stat"><div class="stat-num">100%</div><div class="stat-label">Projets sur mesure</div></div>
        <div class="stat"><div class="stat-num">&#8734;</div><div class="stat-label">Passion creative</div></div>
      </div>
    </div>
  </section>

  <!-- Contact -->

  <section class="section-contact" id="contact">
    <div class="contact-inner">
      <div class="section-num" style="margin-bottom:1rem;">03 — Contact</div>
      <h2 class="section-title" style="margin-bottom:1.5rem;">Travaillons<br><em style="font-family:'Playfair Display',serif;font-style:italic;">Ensemble</em></h2>
      <p class="contact-tagline">Un projet en tete ? Une collaboration a imaginer ?<br>Je suis disponible pour donner vie a vos idees.</p>
      <a href="mailto:jiskingleshiva@gmail.com" class="contact-email">jiskingleshiva@gmail.com</a>
      <br>
      <a href="https://wa.me/237658874939" target="_blank" class="contact-whatsapp">
        <svg width="22" height="22" fill="#c9a84c" viewBox="0 0 24 24"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
        +237 658 874 939
      </a>
      <div style="margin-top:2rem;">
        <a href="mailto:jiskingleshiva@gmail.com" class="btn-gold">Prendre contact</a>
      </div>
    </div>
  </section>

  <!-- Footer -->

  <footer>
    <span>2024 <a href="#">Shiva</a> — Direction Artistique</span>
    <span>PORTFOLIO</span>
    <span class="footer-admin" onclick="openLogin()">Admin</span>
  </footer>

  <!-- Login Modal -->

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

  <script>
    var isAdmin = false;
    try { isAdmin = localStorage.getItem('adminAccess') === 'true'; } catch(e) {}
    if (isAdmin) document.body.classList.add('admin-active');

    function openLogin() { document.getElementById('loginModal').classList.add('open'); }
    function closeLogin() { document.getElementById('loginModal').classList.remove('open'); document.getElementById('passInput').value = ''; }

    function handleLogin() {
      var pass = document.getElementById('passInput').value;
      if (pass === 'Orijeanori235') {
        isAdmin = true;
        try { localStorage.setItem('adminAccess', 'true'); } catch(e) {}
        document.body.classList.add('admin-active');
        closeLogin();
        document.getElementById('adminBtn').textContent = 'Admin OK';
      } else {
        document.getElementById('passInput').style.borderColor = '#f87171';
        setTimeout(function() { document.getElementById('passInput').style.borderColor = ''; }, 1200);
      }
    }

    document.getElementById('passInput').addEventListener('keydown', function(e) {
      if (e.key === 'Enter') handleLogin();
    });

    function addProject() {
      var title = document.getElementById('newTitle').value.trim();
      var imageUrl = document.getElementById('newImage').value.trim();
      if (!title || !imageUrl) { alert('Titre et image obligatoires'); return; }
      var cat = document.getElementById('newCategory').value.trim() || 'Projet';
      var year = document.getElementById('newYear').value.trim() || new Date().getFullYear().toString();
      var desc = document.getElementById('newDesc').value.trim();
      var grid = document.getElementById('portfolioGrid');
      var card = document.createElement('div');
      card.className = 'portfolio-card';
      card.innerHTML = '<img src="' + imageUrl + '" alt="' + title + '" loading="lazy"/><div class="card-info"><div class="card-cat">' + cat + '</div><h3 class="card-title">' + title + '</h3><p class="card-desc">' + desc + '</p><div class="card-year">' + year + '</div><button class="card-delete-btn" onclick="deleteCard(this)">Supprimer</button></div>';
      grid.appendChild(card);
      ['newTitle','newImage','newCategory','newYear','newDesc'].forEach(function(id) { document.getElementById(id).value = ''; });
    }

    function deleteCard(btn) {
      if (confirm('Supprimer ce projet ?')) btn.closest('.portfolio-card').remove();
    }

    var mobileOpen = false;
    function toggleMobile() {
      mobileOpen = !mobileOpen;
      document.getElementById('mobileNav').classList.toggle('open', mobileOpen);
    }
    function closeMobile() {
      mobileOpen = false;
      document.getElementById('mobileNav').classList.remove('open');
    }
  </script>

</body>
</html>
