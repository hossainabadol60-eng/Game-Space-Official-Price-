# Game-Space-Official-Price-/* ---------------------------------------
   BASE STYLES + THEME VARIABLES
--------------------------------------- */

* { margin:0; padding:0; box-sizing:border-box; }
body {
  font-family: Poppins, sans-serif;
  min-height:100vh;
  overflow-x:hidden;
  transition:0.5s ease;
}

/* Themes */
.theme-dark {
  --bg1:#04070e;
  --bg2:#0a1022;
  --text:#e8f8ff;
  --muted:#94a3b8;
  --accent:#19e3ff;
  --accent2:#ff008c;
  --card:rgba(255,255,255,0.05);
}

.theme-neon {
  --bg1:#12001e;
  --bg2:#23003c;
  --text:#ffffff;
  --muted:#d1b3ff;
  --accent:#ff00ff;
  --accent2:#00eaff;
  --card:rgba(255,255,255,0.08);
}

.theme-light {
  --bg1:#e9f0ff;
  --bg2:#d2dfff;
  --text:#0a0a0a;
  --muted:#4b4b4b;
  --accent:#006eff;
  --accent2:#00b3ff;
  --card:#ffffff;
}

/* Background gradient */
body {
  background: linear-gradient(150deg, var(--bg1), var(--bg2));
  color:var(--text);
}

/* ---------------------------------------
   CYBER MOVING GRID BACKGROUND
--------------------------------------- */
.cyber-grid {
  position:fixed;
  inset:0;
  background:
    repeating-linear-gradient(0deg, rgba(255,255,255,0.03) 0px, transparent 2px, transparent 80px),
    repeating-linear-gradient(90deg, rgba(255,255,255,0.03) 0px, transparent 2px, transparent 80px);
  animation: gridMove 14s linear infinite;
  pointer-events:none;
  z-index:-1;
}
@keyframes gridMove {
  0% { transform: translateY(0); }
  100% { transform: translateY(100px); }
}

/* ---------------------------------------
   THEME SWITCHER BUTTONS
--------------------------------------- */
.theme-toggle {
  position:fixed;
  top:15px;
  right:15px;
  z-index:999;
  display:flex;
  gap:8px;
}
.theme-toggle button {
  padding:7px 14px;
  background:var(--card);
  border:1px solid var(--accent);
  color:var(--text);
  border-radius:6px;
  cursor:pointer;
  font-size:0.85rem;
  transition:0.25s;
}
.theme-toggle button:hover {
  background:var(--accent);
  color:#000;
}

/* ---------------------------------------
   HEADER
--------------------------------------- */
.fade-in {
  opacity:0;
  animation: fadeIn 1s forwards;
}
@keyframes fadeIn {
  to { opacity:1; }
}

.site-header {
  max-width:1100px;
  margin:45px auto 20px;
  padding:20px;
  display:flex;
  justify-content:space-between;
  align-items:center;
}

h1 {
  font-size:2rem;
  font-weight:700;
  background:linear-gradient(90deg, var(--accent), var(--accent2));
  -webkit-background-clip:text;
  color:transparent;
}

.tagline { color:var(--muted); margin-top:4px; }

.contact { text-align:right; }
.contact-item a {
  color:var(--accent);
  text-decoration:none;
  font-weight:600;
}

/* ---------------------------------------
   NOTE BOX
--------------------------------------- */
.glow-box {
  padding:15px;
  background:var(--card);
  border-radius:10px;
  box-shadow:0 0 15px rgba(0,255,255,0.2);
  border:1px solid rgba(255,255,255,0.06);
}

/* ---------------------------------------
   PRICE CARDS
--------------------------------------- */
.container {
  max-width:1100px;
  margin:auto;
  padding:20px;
}

.slide-up {
  opacity:0;
  animation: slideUp 0.9s forwards;
}
@keyframes slideUp {
  0% { transform:translateY(40px); opacity:0; }
  100% { transform:translateY(0); opacity:1; }
}

.price-grid {
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:22px;
  margin-top:25px;
}

.price-card {
  padding:20px;
  background:var(--card);
  border-radius:12px;
  border:1px solid rgba(255,255,255,0.1);
  backdrop-filter:blur(6px);
  position:relative;
  overflow:hidden;
  transition:0.4s;
}

/* Shine animation */
.price-card::before {
  content:"";
  position:absolute;
  top:0;
  left:-120%;
  width:120%;
  height:100%;
  background:linear-gradient(100deg, transparent, rgba(255,255,255,0.2), transparent);
  transition:0.7s;
}
.price-card:hover::before {
  left:120%;
}

.price-card:hover {
  transform:scale(1.03);
  box-shadow:0 0 25px rgba(0,255,255,0.25);
}

.price-card h2 {
  display:flex;
  justify-content:space-between;
  font-size:1.25rem;
}

.sub {
  font-size:0.9rem;
  color:var(--muted);
}

/* Price list */
.prices {
  list-style:none;
  margin-top:12px;
  display:flex;
  flex-direction:column;
  gap:12px;
}
.prices li {
  background:rgba(255,255,255,0.05);
  padding:12px;
  border-radius:10px;
  display:flex;
  justify-content:space-between;
  border:1px solid rgba(255,255,255,0.08);
  transition:0.25s;
}
.prices li:hover {
  background:rgba(0,255,255,0.15);
  transform:scale(1.03);
}

.price {
  font-weight:700;
  color:var(--accent);
}

/* ---------------------------------------
   FOOTER
--------------------------------------- */
.site-footer {
  text-align:center;
  padding:25px;
  color:var(--muted);
  font-size:0.85rem;
  margin-top:20px;
}

/* ---------------------------------------
   RESPONSIVE
--------------------------------------- */
@media (max-width:850px) {
  .price-grid { grid-template-columns:1fr; }
  .site-header {
    flex-direction:column;
    text-align:center;
  }
  .contact { text-align:center; }
}
