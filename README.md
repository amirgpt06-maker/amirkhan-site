```html
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="Амирхан — веб-разработчик. Создаю современные продающие сайты с помощью чистого кода. Лендинги, корпоративные сайты, интернет-магазины.">
<title>Амирхан — Веб-разработчик · Продающие сайты</title>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/fontsource-inter@5.0.16/index.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/fontsource-jetbrains-mono@5.0.16/index.css">
<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  :root {
    --orange: #ff6b00;
    --orange-light: #ff8c3a;
    --orange-dark: #cc5500;
    --orange-glow: rgba(255, 107, 0, 0.5);
    --black: #0a0a0a;
    --black-2: #121212;
    --black-3: #1a1a1a;
    --black-4: #222;
    --gray: rgba(255,255,255,0.78);
    --gray-2: rgba(255,255,255,0.55);
    --gray-3: rgba(255,255,255,0.12);
    --success: #22c55e;
    --error: #ef4444;
  }

  html {
    scroll-behavior: smooth;
  }

  body {
    font-family: 'Inter', system-ui, -apple-system, sans-serif;
    background: var(--black);
    color: #fff;
    overflow-x: hidden;
    line-height: 1.6;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }

  :focus-visible {
    outline: 2px solid var(--orange);
    outline-offset: 3px;
    border-radius: 4px;
  }

  /* ===== Background ===== */
  .bg-wrapper {
    position: fixed;
    inset: 0;
    z-index: 0;
    pointer-events: none;
    overflow: hidden;
  }

  .blob {
    position: absolute;
    border-radius: 50%;
    filter: blur(120px);
    opacity: 0.35;
    animation: floatBlob 20s ease-in-out infinite;
    will-change: transform;
  }

  .blob-1 {
    width: 500px;
    height: 500px;
    background: var(--orange);
    top: -150px;
    left: -150px;
  }

  .blob-2 {
    width: 400px;
    height: 400px;
    background: #ff3d00;
    bottom: 10%;
    right: -100px;
    animation-delay: -7s;
    opacity: 0.25;
  }

  .blob-3 {
    width: 350px;
    height: 350px;
    background: var(--orange-light);
    top: 40%;
    left: 40%;
    animation-delay: -14s;
    opacity: 0.2;
  }

  @keyframes floatBlob {
    0%, 100% { transform: translate(0, 0) scale(1); }
    33% { transform: translate(60px, -40px) scale(1.1); }
    66% { transform: translate(-40px, 50px) scale(0.95); }
  }

  .bg-grid {
    position: fixed;
    inset: 0;
    background-image: 
      linear-gradient(rgba(255,255,255,0.025) 1px, transparent 1px),
      linear-gradient(90deg, rgba(255,255,255,0.025) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none;
    z-index: 1;
    mask-image: radial-gradient(ellipse at center, black 40%, transparent 80%);
    -webkit-mask-image: radial-gradient(ellipse at center, black 40%, transparent 80%);
  }

  .bg-noise {
    position: fixed;
    inset: 0;
    pointer-events: none;
    z-index: 1;
    opacity: 0.04;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
  }

  /* ===== Navigation ===== */
  .nav {
    position: fixed;
    top: 20px;
    left: 50%;
    transform: translateX(-50%);
    z-index: 100;
    padding: 12px 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 32px;
    backdrop-filter: blur(20px);
    -webkit-backdrop-filter: blur(20px);
    background: rgba(10, 10, 10, 0.6);
    border: 1px solid var(--gray-3);
    border-radius: 100px;
    transition: all 0.3s ease;
    max-width: calc(100% - 40px);
    width: fit-content;
    min-width: 280px;
  }

  .nav.scrolled {
    top: 10px;
    background: rgba(10, 10, 10, 0.85);
    border-color: rgba(255, 107, 0, 0.2);
  }

  .nav-logo {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 15px;
    font-weight: 700;
    letter-spacing: -0.02em;
    text-decoration: none;
    color: #fff;
  }

  .nav-logo-mark {
    width: 28px;
    height: 28px;
    background: linear-gradient(135deg, var(--orange), var(--orange-dark));
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    color: #fff;
    font-weight: 800;
    font-size: 13px;
    box-shadow: 0 4px 12px var(--orange-glow);
    flex-shrink: 0;
  }

  .nav-links {
    display: flex;
    gap: 24px;
    list-style: none;
  }

  .nav-links a {
    color: var(--gray);
    text-decoration: none;
    font-size: 13px;
    font-weight: 500;
    transition: color 0.2s ease;
  }

  .nav-links a:hover,
  .nav-links a:focus {
    color: var(--orange);
  }

  .nav-cta {
    padding: 8px 16px;
    background: var(--orange);
    border: none;
    border-radius: 100px;
    color: #000;
    font-size: 13px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s ease;
    text-decoration: none;
    white-space: nowrap;
  }

  .nav-cta:hover,
  .nav-cta:focus {
    background: var(--orange-light);
    box-shadow: 0 4px 20px var(--orange-glow);
  }

  /* Burger menu */
  .burger {
    display: none;
    width: 40px;
    height: 40px;
    background: transparent;
    border: none;
    cursor: pointer;
    position: relative;
    padding: 0;
    z-index: 101;
    border-radius: 8px;
    transition: background 0.2s;
  }

  .burger:hover {
    background: rgba(255,255,255,0.05);
  }

  .burger-line {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    width: 20px;
    height: 2px;
    background: #fff;
    border-radius: 2px;
    transition: all 0.3s ease;
  }

  .burger-line:nth-child(1) { top: 14px; }
  .burger-line:nth-child(2) { top: 19px; }
  .burger-line:nth-child(3) { top: 24px; }

  .burger.active .burger-line:nth-child(1) {
    top: 19px;
    transform: translateX(-50%) rotate(45deg);
  }
  .burger.active .burger-line:nth-child(2) { opacity: 0; }
  .burger.active .burger-line:nth-child(3) {
    top: 19px;
    transform: translateX(-50%) rotate(-45deg);
  }

  /* Mobile menu */
  .mobile-menu {
    position: fixed;
    inset: 0;
    background: rgba(10, 10, 10, 0.95);
    backdrop-filter: blur(20px);
    -webkit-backdrop-filter: blur(20px);
    z-index: 99;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 24px;
    opacity: 0;
    visibility: hidden;
    transition: opacity 0.3s ease, visibility 0.3s ease;
  }

  .mobile-menu.active {
    opacity: 1;
    visibility: visible;
  }

  .mobile-menu a {
    color: #fff;
    text-decoration: none;
    font-size: 24px;
    font-weight: 700;
    letter-spacing: -0.02em;
    transition: color 0.2s ease;
    opacity: 0;
    transform: translateY(20px);
  }

  .mobile-menu.active a {
    animation: menuFadeIn 0.4s ease forwards;
  }

  .mobile-menu.active a:nth-child(1) { animation-delay: 0.05s; }
  .mobile-menu.active a:nth-child(2) { animation-delay: 0.1s; }
  .mobile-menu.active a:nth-child(3) { animation-delay: 0.15s; }
  .mobile-menu.active a:nth-child(4) { animation-delay: 0.2s; }
  .mobile-menu.active a:nth-child(5) { animation-delay: 0.25s; }
  .mobile-menu.active a:nth-child(6) { animation-delay: 0.3s; }
  .mobile-menu.active a:nth-child(7) { animation-delay: 0.35s; }

  @keyframes menuFadeIn {
    to { opacity: 1; transform: translateY(0); }
  }

  .mobile-menu a:hover { color: var(--orange); }

  .mobile-menu .mobile-cta {
    margin-top: 20px;
    padding: 14px 32px;
    background: var(--orange);
    color: #000;
    border-radius: 100px;
    font-weight: 600;
    font-size: 16px;
  }

  body.menu-open {
    overflow: hidden;
  }

  /* ===== Hero ===== */
  .hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    align-items: center;
    padding: 140px 40px 80px;
    z-index: 2;
  }

  .hero-content {
    position: relative;
    z-index: 2;
    max-width: 1200px;
    margin: 0 auto;
    width: 100%;
  }

  .hero-top {
    display: flex;
    align-items: center;
    gap: 16px;
    margin-bottom: 32px;
    flex-wrap: wrap;
  }

  .hero-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 8px 16px;
    background: rgba(255, 107, 0, 0.1);
    border: 1px solid rgba(255, 107, 0, 0.3);
    border-radius: 100px;
    color: var(--orange-light);
    font-size: 13px;
    font-weight: 500;
  }

  .hero-badge .dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--orange);
    box-shadow: 0 0 10px var(--orange);
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.6; transform: scale(1.3); }
  }

  .hero-location {
    font-size: 13px;
    color: var(--gray-2);
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .hero h1 {
    font-size: clamp(44px, 7.5vw, 104px);
    font-weight: 800;
    line-height: 0.95;
    letter-spacing: -0.04em;
    margin-bottom: 32px;
  }

  .hero h1 .line {
    display: block;
    overflow: hidden;
  }

  .hero h1 .gradient-text {
    background: linear-gradient(135deg, var(--orange) 0%, #ff3d00 100%);
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .hero h1 .outline {
    -webkit-text-stroke: 2px rgba(255,255,255,0.3);
    color: transparent;
  }

  .hero-bottom {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 60px;
    align-items: end;
    margin-top: 40px;
  }

  .hero-desc {
    font-size: 17px;
    color: var(--gray);
    max-width: 460px;
    line-height: 1.6;
  }

  .hero-desc strong {
    color: #fff;
    font-weight: 600;
  }

  .hero-stats {
    display: flex;
    gap: 32px;
    justify-content: flex-end;
    flex-wrap: wrap;
  }

  .stat {
    display: flex;
    flex-direction: column;
    text-align: right;
  }

  .stat-number {
    font-size: 42px;
    font-weight: 800;
    letter-spacing: -0.03em;
    line-height: 1;
    color: var(--orange);
    font-family: 'JetBrains Mono', monospace;
  }

  .stat-label {
    font-size: 12px;
    color: var(--gray-2);
    margin-top: 8px;
    text-transform: uppercase;
    letter-spacing: 0.1em;
  }

  /* Floating code card */
  .floating-code {
    position: absolute;
    right: 40px;
    top: 50%;
    transform: translateY(-50%);
    width: 380px;
    max-width: 40vw;
    background: linear-gradient(145deg, rgba(26,26,26,0.95), rgba(18,18,18,0.95));
    border: 1px solid rgba(255, 107, 0, 0.2);
    border-radius: 16px;
    overflow: hidden;
    backdrop-filter: blur(20px);
    -webkit-backdrop-filter: blur(20px);
    box-shadow: 0 30px 80px -20px rgba(255, 107, 0, 0.25), 0 0 60px -10px rgba(255, 107, 0, 0.15);
    animation: floatCard 6s ease-in-out infinite;
    z-index: 3;
    will-change: transform;
  }

  @keyframes floatCard {
    0%, 100% { transform: translateY(-50%) rotate(-1deg); }
    50% { transform: translateY(-55%) rotate(1deg); }
  }

  .code-header {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 14px 16px;
    border-bottom: 1px solid rgba(255,255,255,0.08);
    background: rgba(0,0,0,0.3);
  }

  .code-dot {
    width: 10px;
    height: 10px;
    border-radius: 50%;
  }

  .code-dot.red { background: #ff5f56; }
  .code-dot.yellow { background: #ffbd2e; }
  .code-dot.green { background: #27c93f; }

  .code-title {
    margin-left: auto;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--gray-2);
  }

  .code-body {
    padding: 20px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    line-height: 1.7;
  }

  .code-line {
    display: flex;
    gap: 12px;
  }

  .code-num {
    color: rgba(255,255,255,0.2);
    user-select: none;
    min-width: 20px;
    text-align: right;
  }

  .code-tag { color: #ff6b9d; }
  .code-attr { color: #c792ea; }
  .code-str { color: var(--orange); }
  .code-var { color: #82aaff; }
  .code-fn { color: #82aaff; }
  .code-comment { color: rgba(255,255,255,0.3); font-style: italic; }

  .code-cursor {
    display: inline-block;
    width: 7px;
    height: 14px;
    background: var(--orange);
    animation: blink 1s infinite;
    vertical-align: middle;
  }

  @keyframes blink {
    0%, 50% { opacity: 1; }
    51%, 100% { opacity: 0; }
  }

  .scroll-indicator {
    position: absolute;
    bottom: 30px;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    color: var(--gray-2);
    font-size: 11px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    z-index: 5;
  }

  .scroll-line {
    width: 1px;
    height: 40px;
    background: linear-gradient(180deg, var(--orange), transparent);
    animation: scrollLine 2s ease-in-out infinite;
  }

  @keyframes scrollLine {
    0% { transform: scaleY(0); transform-origin: top; }
    50% { transform: scaleY(1); transform-origin: top; }
    51% { transform-origin: bottom; }
    100% { transform: scaleY(0); transform-origin: bottom; }
  }

  /* ===== Sections ===== */
  section {
    position: relative;
    z-index: 2;
    padding: 120px 40px;
  }

  .container {
    max-width: 1200px;
    margin: 0 auto;
  }

  .section-header {
    margin-bottom: 60px;
    max-width: 700px;
  }

  .section-label {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    font-weight: 500;
    color: var(--orange);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-bottom: 20px;
  }

  .section-label::before {
    content: '';
    width: 24px;
    height: 1px;
    background: var(--orange);
  }

  .section-title {
    font-size: clamp(32px, 5vw, 56px);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -0.03em;
    margin-bottom: 20px;
  }

  .section-title .highlight {
    color: var(--orange);
  }

  .section-subtitle {
    font-size: 17px;
    color: var(--gray);
    line-height: 1.7;
  }

  /* Marquee */
  .marquee {
    position: relative;
    overflow: hidden;
    padding: 40px 0;
    border-top: 1px solid var(--gray-3);
    border-bottom: 1px solid var(--gray-3);
    background: var(--black-2);
    z-index: 2;
  }

  .marquee-track {
    display: flex;
    gap: 60px;
    animation: marquee 30s linear infinite;
    white-space: nowrap;
    will-change: transform;
  }

  .marquee-item {
    font-size: 48px;
    font-weight: 800;
    letter-spacing: -0.03em;
    color: rgba(255,255,255,0.08);
    display: flex;
    align-items: center;
    gap: 60px;
    flex-shrink: 0;
  }

  .marquee-item .dot {
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background: var(--orange);
    box-shadow: 0 0 20px var(--orange);
  }

  @keyframes marquee {
    from { transform: translateX(0); }
    to { transform: translateX(-50%); }
  }

  /* About */
  .about {
    background: linear-gradient(180deg, transparent 0%, rgba(255, 107, 0, 0.02) 50%, transparent 100%);
  }

  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 60px;
    align-items: center;
  }

  .about-text p {
    font-size: 16px;
    color: var(--gray);
    margin-bottom: 20px;
    line-height: 1.7;
  }

  .about-text p strong {
    color: #fff;
    font-weight: 600;
  }

  .about-visual {
    position: relative;
    aspect-ratio: 1;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .about-visual-circle {
    position: absolute;
    border-radius: 50%;
    border: 1px solid rgba(255, 107, 0, 0.2);
    will-change: transform;
  }

  .about-visual-circle.c1 {
    width: 100%;
    height: 100%;
    animation: rotate 30s linear infinite;
  }

  .about-visual-circle.c2 {
    width: 75%;
    height: 75%;
    animation: rotate 20s linear infinite reverse;
    border-color: rgba(255, 107, 0, 0.3);
  }

  .about-visual-circle.c3 {
    width: 50%;
    height: 50%;
    animation: rotate 15s linear infinite;
    border-color: rgba(255, 107, 0, 0.4);
  }

  @keyframes rotate {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
  }

  .about-visual-circle::before {
    content: '';
    position: absolute;
    top: -5px;
    left: 50%;
    width: 10px;
    height: 10px;
    background: var(--orange);
    border-radius: 50%;
    box-shadow: 0 0 20px var(--orange);
  }

  .about-center {
    position: relative;
    z-index: 2;
    width: 140px;
    height: 140px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--orange), var(--orange-dark));
    display: flex;
    align-items: center;
    justify-content: center;
    box-shadow: 0 0 60px var(--orange-glow);
  }

  .about-center svg {
    width: 60px;
    height: 60px;
    color: #000;
  }

  .features-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 16px;
    margin-top: 60px;
  }

  .feature-card {
    padding: 28px 24px;
    background: linear-gradient(145deg, var(--black-3), var(--black-2));
    border: 1px solid var(--gray-3);
    border-radius: 16px;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
    overflow: hidden;
  }

  .feature-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--orange), transparent);
    transform: translateX(-100%);
    transition: transform 0.6s ease;
  }

  .feature-card:hover {
    border-color: rgba(255, 107, 0, 0.3);
    transform: translateY(-6px);
    box-shadow: 0 20px 40px -10px rgba(255, 107, 0, 0.2);
  }

  .feature-card:hover::before {
    transform: translateX(0);
  }

  .feature-icon {
    width: 44px;
    height: 44px;
    border-radius: 10px;
    background: linear-gradient(135deg, rgba(255, 107, 0, 0.2), rgba(255, 107, 0, 0.05));
    border: 1px solid rgba(255, 107, 0, 0.3);
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 16px;
    color: var(--orange);
  }

  .feature-icon svg {
    width: 22px;
    height: 22px;
  }

  .feature-card h3 {
    font-size: 16px;
    font-weight: 700;
    margin-bottom: 8px;
    letter-spacing: -0.01em;
  }

  .feature-card p {
    font-size: 13px;
    color: var(--gray-2);
    line-height: 1.5;
  }

  /* Services */
  .services {
    background: var(--black-2);
  }

  .services-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
  }

  .service-card {
    padding: 40px;
    background: linear-gradient(145deg, var(--black-3), var(--black));
    border: 1px solid var(--gray-3);
    border-radius: 20px;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
    overflow: hidden;
    min-height: 260px;
    display: flex;
    flex-direction: column;
  }

  .service-card::after {
    content: '';
    position: absolute;
    top: -100px;
    right: -100px;
    width: 250px;
    height: 250px;
    background: radial-gradient(circle, var(--orange-glow), transparent 70%);
    opacity: 0;
    transition: opacity 0.4s ease;
  }

  .service-card:hover {
    border-color: rgba(255, 107, 0, 0.4);
    transform: translateY(-4px);
  }

  .service-card:hover::after {
    opacity: 0.6;
  }

  .service-card > * {
    position: relative;
    z-index: 2;
  }

  .service-icon {
    width: 56px;
    height: 56px;
    border-radius: 14px;
    background: linear-gradient(135deg, var(--orange), var(--orange-dark));
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 24px;
    color: #000;
    box-shadow: 0 10px 30px -10px var(--orange-glow);
  }

  .service-icon svg {
    width: 28px;
    height: 28px;
  }

  .service-card h3 {
    font-size: 24px;
    font-weight: 700;
    margin-bottom: 12px;
    letter-spacing: -0.02em;
  }

  .service-card p {
    font-size: 15px;
    color: var(--gray);
    line-height: 1.6;
    flex: 1;
  }

  .service-arrow {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    margin-top: 20px;
    color: var(--orange);
    font-size: 13px;
    font-weight: 600;
    transition: gap 0.3s ease;
  }

  .service-card:hover .service-arrow {
    gap: 14px;
  }

  /* Selling */
  .selling {
    position: relative;
  }

  .selling-wrapper {
    display: grid;
    grid-template-columns: 1.2fr 1fr;
    gap: 80px;
    align-items: center;
  }

  .selling-visual {
    position: relative;
    aspect-ratio: 1;
    background: linear-gradient(145deg, var(--black-3), var(--black-2));
    border: 1px solid var(--gray-3);
    border-radius: 24px;
    overflow: hidden;
    padding: 40px;
  }

  .selling-visual::before {
    content: '';
    position: absolute;
    inset: 0;
    background: 
      radial-gradient(circle at 30% 30%, rgba(255, 107, 0, 0.15) 0%, transparent 50%),
      radial-gradient(circle at 70% 70%, rgba(255, 61, 0, 0.1) 0%, transparent 50%);
  }

  .selling-visual-grid {
    position: relative;
    z-index: 2;
    height: 100%;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(3, 1fr);
    gap: 12px;
  }

  .selling-tile {
    background: rgba(255, 107, 0, 0.08);
    border: 1px solid rgba(255, 107, 0, 0.2);
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--orange);
    transition: all 0.4s ease;
    animation: pulseTile 3s ease-in-out infinite;
  }

  .selling-tile:nth-child(2) { animation-delay: 0.5s; }
  .selling-tile:nth-child(3) { animation-delay: 1s; }
  .selling-tile:nth-child(4) { animation-delay: 1.5s; }
  .selling-tile:nth-child(5) { animation-delay: 2s; }
  .selling-tile:nth-child(6) { animation-delay: 2.5s; }

  @keyframes pulseTile {
    0%, 100% { transform: scale(1); opacity: 0.8; }
    50% { transform: scale(1.02); opacity: 1; border-color: var(--orange); background: rgba(255, 107, 0, 0.15); }
  }

  .selling-tile svg {
    width: 28px;
    height: 28px;
  }

  .selling-tile.big {
    grid-column: span 2;
  }

  .selling-tile.tall {
    grid-row: span 2;
  }

  .selling-points {
    margin-top: 32px;
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  .selling-point {
    display: flex;
    align-items: flex-start;
    gap: 16px;
    padding: 18px 20px;
    background: var(--black-3);
    border: 1px solid var(--gray-3);
    border-radius: 12px;
    transition: all 0.3s ease;
  }

  .selling-point:hover {
    border-color: rgba(255, 107, 0, 0.3);
    transform: translateX(6px);
  }

  .selling-point-num {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    color: var(--orange);
    font-weight: 600;
    flex-shrink: 0;
    margin-top: 2px;
  }

  .selling-point span {
    font-size: 15px;
    color: #fff;
    line-height: 1.5;
  }

  /* Niches */
  .niches {
    background: var(--black-2);
  }

  .niches-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
  }

  .niche-card {
    padding: 32px 24px;
    background: linear-gradient(145deg, var(--black-3), var(--black));
    border: 1px solid var(--gray-3);
    border-radius: 16px;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
    overflow: hidden;
  }

  .niche-card:hover {
    border-color: rgba(255, 107, 0, 0.4);
    transform: translateY(-4px);
    box-shadow: 0 20px 40px -10px rgba(255, 107, 0, 0.15);
  }

  .niche-card::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(circle at 50% 0%, rgba(255, 107, 0, 0.1), transparent 70%);
    opacity: 0;
    transition: opacity 0.4s ease;
  }

  .niche-card:hover::before {
    opacity: 1;
  }

  .niche-card > * {
    position: relative;
    z-index: 2;
  }

  .niche-icon {
    width: 48px;
    height: 48px;
    border-radius: 12px;
    background: linear-gradient(135deg, rgba(255, 107, 0, 0.15), rgba(255, 107, 0, 0.05));
    border: 1px solid rgba(255, 107, 0, 0.2);
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--orange);
    margin-bottom: 20px;
  }

  .niche-icon svg {
    width: 24px;
    height: 24px;
  }

  .niche-card h3 {
    font-size: 18px;
    font-weight: 700;
    margin-bottom: 8px;
    letter-spacing: -0.01em;
  }

  .niche-card p {
    font-size: 13px;
    color: var(--gray-2);
    line-height: 1.5;
  }

  /* Pricing */
  .pricing {
    position: relative;
  }

  .pricing-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
  }

  .price-card {
    padding: 40px 32px;
    background: linear-gradient(145deg, var(--black-3), var(--black-2));
    border: 1px solid var(--gray-3);
    border-radius: 20px;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
    overflow: hidden;
    display: flex;
    flex-direction: column;
  }

  .price-card:hover {
    border-color: rgba(255, 107, 0, 0.4);
    transform: translateY(-6px);
    box-shadow: 0 30px 60px -15px rgba(255, 107, 0, 0.2);
  }

  .price-card.featured {
    border-color: rgba(255, 107, 0, 0.5);
    background: linear-gradient(145deg, rgba(255, 107, 0, 0.08), var(--black-2));
  }

  .price-card.featured::before {
    content: 'Популярный';
    position: absolute;
    top: 20px;
    right: 20px;
    padding: 4px 10px;
    background: var(--orange);
    color: #000;
    font-size: 11px;
    font-weight: 700;
    border-radius: 100px;
    letter-spacing: 0.05em;
    text-transform: uppercase;
  }

  .price-card-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--orange);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-bottom: 12px;
  }

  .price-card h3 {
    font-size: 26px;
    font-weight: 800;
    margin-bottom: 12px;
    letter-spacing: -0.02em;
  }

  .price-card-desc {
    font-size: 14px;
    color: var(--gray);
    margin-bottom: 24px;
    line-height: 1.6;
    min-height: 64px;
  }

  .price-amount {
    display: flex;
    align-items: baseline;
    gap: 6px;
    margin-bottom: 8px;
  }

  .price-from {
    font-size: 14px;
    color: var(--gray-2);
  }

  .price-value {
    font-size: 44px;
    font-weight: 800;
    color: var(--orange);
    letter-spacing: -0.03em;
    font-family: 'JetBrains Mono', monospace;
    line-height: 1;
  }

  .price-currency {
    font-size: 18px;
    color: var(--gray-2);
    font-weight: 600;
  }

  .price-note {
    font-size: 12px;
    color: var(--gray-2);
    margin-bottom: 28px;
  }

  .price-divider {
    height: 1px;
    background: var(--gray-3);
    margin: 4px 0 24px;
  }

  .price-features {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 12px;
    margin-bottom: 32px;
    flex: 1;
  }

  .price-features li {
    display: flex;
    align-items: flex-start;
    gap: 10px;
    font-size: 14px;
    color: var(--gray);
    line-height: 1.4;
  }

  .price-features .check {
    width: 18px;
    height: 18px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--orange), var(--orange-dark));
    display: flex;
    align-items: center;
    justify-content: center;
    color: #000;
    font-size: 11px;
    font-weight: 800;
    flex-shrink: 0;
    margin-top: 2px;
  }

  .price-btn {
    padding: 14px 24px;
    background: transparent;
    border: 1px solid var(--gray-3);
    border-radius: 12px;
    color: #fff;
    font-size: 14px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s ease;
    text-align: center;
    text-decoration: none;
    display: inline-block;
  }

  .price-btn:hover,
  .price-btn:focus {
    border-color: var(--orange);
    color: var(--orange);
  }

  .price-card.featured .price-btn {
    background: var(--orange);
    border-color: var(--orange);
    color: #000;
  }

  .price-card.featured .price-btn:hover,
  .price-card.featured .price-btn:focus {
    background: var(--orange-light);
    border-color: var(--orange-light);
    color: #000;
    box-shadow: 0 10px 30px -10px var(--orange-glow);
  }

  /* Tech */
  .tech-stack {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    margin-bottom: 40px;
  }

  .tech-tag {
    padding: 14px 22px;
    background: var(--black-3);
    border: 1px solid var(--gray-3);
    border-radius: 100px;
    color: #fff;
    font-size: 14px;
    font-weight: 500;
    font-family: 'JetBrains Mono', monospace;
    transition: all 0.3s ease;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .tech-tag .tag-dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--orange);
  }

  .tech-tag:hover {
    border-color: var(--orange);
    color: var(--orange);
    transform: translateY(-2px);
  }

  .tech-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 16px;
  }

  .tech-card {
    padding: 32px;
    background: linear-gradient(145deg, var(--black-3), var(--black-2));
    border: 1px solid var(--gray-3);
    border-radius: 16px;
    display: flex;
    gap: 20px;
    align-items: flex-start;
    transition: all 0.4s ease;
  }

  .tech-card:hover {
    border-color: rgba(255, 107, 0, 0.3);
    transform: translateY(-4px);
  }

  .tech-card-icon {
    width: 44px;
    height: 44px;
    border-radius: 10px;
    background: linear-gradient(135deg, var(--orange), var(--orange-dark));
    display: flex;
    align-items: center;
    justify-content: center;
    color: #000;
    flex-shrink: 0;
  }

  .tech-card-icon svg {
    width: 22px;
    height: 22px;
  }

  .tech-card h3 {
    font-size: 17px;
    font-weight: 700;
    margin-bottom: 6px;
    letter-spacing: -0.01em;
  }

  .tech-card p {
    font-size: 14px;
    color: var(--gray);
    line-height: 1.6;
  }

  /* Process */
  .process {
    background: var(--black-2);
  }

  .process-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
    position: relative;
  }

  .process-grid::before {
    content: '';
    position: absolute;
    top: 30px;
    left: 10%;
    right: 10%;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--orange), transparent);
    opacity: 0.3;
    z-index: 0;
  }

  .process-card {
    padding: 32px 24px;
    background: linear-gradient(145deg, var(--black-3), var(--black));
    border: 1px solid var(--gray-3);
    border-radius: 20px;
    position: relative;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    z-index: 1;
  }

  .process-card:hover {
    border-color: rgba(255, 107, 0, 0.4);
    transform: translateY(-6px);
  }

  .process-number {
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px;
    color: var(--orange);
    font-weight: 600;
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .process-number::after {
    content: '';
    flex: 1;
    height: 1px;
    background: rgba(255, 107, 0, 0.3);
  }

  .process-card h3 {
    font-size: 19px;
    font-weight: 700;
    margin-bottom: 12px;
    letter-spacing: -0.01em;
  }

  .process-card p {
    font-size: 14px;
    color: var(--gray);
    line-height: 1.6;
  }

  /* Advantages */
  .advantages-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
  }

  .advantage-card {
    padding: 36px 28px;
    background: linear-gradient(145deg, var(--black-3), var(--black-2));
    border: 1px solid var(--gray-3);
    border-radius: 20px;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
    overflow: hidden;
  }

  .advantage-card::before {
    content: '';
    position: absolute;
    bottom: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: radial-gradient(circle, rgba(255, 107, 0, 0.15), transparent 40%);
    opacity: 0;
    transition: opacity 0.5s ease;
    pointer-events: none;
  }

  .advantage-card:hover {
    border-color: rgba(255, 107, 0, 0.3);
    transform: translateY(-6px);
  }

  .advantage-card:hover::before {
    opacity: 1;
  }

  .advantage-card > * {
    position: relative;
    z-index: 2;
  }

  .advantage-icon {
    width: 56px;
    height: 56px;
    border-radius: 14px;
    background: linear-gradient(135deg, rgba(255, 107, 0, 0.2), rgba(255, 107, 0, 0.05));
    border: 1px solid rgba(255, 107, 0, 0.3);
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--orange);
    margin-bottom: 20px;
  }

  .advantage-icon svg {
    width: 28px;
    height: 28px;
  }

  .advantage-card h3 {
    font-size: 19px;
    font-weight: 700;
    margin-bottom: 10px;
    letter-spacing: -0.01em;
  }

  .advantage-card p {
    font-size: 14px;
    color: var(--gray);
    line-height: 1.6;
  }

  /* FAQ */
  .faq {
    background: var(--black-2);
  }

  .faq-list {
    display: flex;
    flex-direction: column;
    gap: 12px;
    max-width: 900px;
    margin: 0 auto;
  }

  .faq-item {
    background: linear-gradient(145deg, var(--black-3), var(--black));
    border: 1px solid var(--gray-3);
    border-radius: 16px;
    overflow: hidden;
    transition: all 0.3s ease;
  }

  .faq-item:hover {
    border-color: rgba(255, 107, 0, 0.2);
  }

  .faq-item.active {
    border-color: rgba(255, 107, 0, 0.4);
  }

  .faq-question {
    padding: 24px 28px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 20px;
    cursor: pointer;
    width: 100%;
    background: transparent;
    border: none;
    color: #fff;
    font-size: 17px;
    font-weight: 600;
    text-align: left;
    font-family: inherit;
    letter-spacing: -0.01em;
  }

  .faq-question:focus {
    outline: none;
  }

  .faq-icon {
    width: 32px;
    height: 32px;
    border-radius: 8px;
    background: rgba(255, 107, 0, 0.1);
    border: 1px solid rgba(255, 107, 0, 0.2);
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
    transition: all 0.3s ease;
    color: var(--orange);
  }

  .faq-item.active .faq-icon {
    background: var(--orange);
    color: #000;
    transform: rotate(45deg);
  }

  .faq-icon svg {
    width: 14px;
    height: 14px;
  }

  .faq-answer {
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  }

  .faq-answer-inner {
    padding: 0 28px 24px;
    font-size: 15px;
    color: var(--gray);
    line-height: 1.7;
  }

  /* Contact form */
  .contact {
    position: relative;
    padding: 120px 40px;
    overflow: hidden;
  }

  .contact::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse at center, rgba(255, 107, 0, 0.15), transparent 60%);
    z-index: 0;
  }

  .contact-wrapper {
    position: relative;
    z-index: 2;
    max-width: 900px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 1.2fr;
    gap: 60px;
    align-items: start;
  }

  .contact-info h2 {
    font-size: clamp(32px, 4.5vw, 48px);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -0.03em;
    margin-bottom: 20px;
  }

  .contact-info h2 .highlight {
    color: var(--orange);
  }

  .contact-info p {
    font-size: 16px;
    color: var(--gray);
    line-height: 1.7;
    margin-bottom: 32px;
  }

  .contact-features {
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  .contact-feature {
    display: flex;
    align-items: center;
    gap: 14px;
    font-size: 14px;
    color: var(--gray);
  }

  .contact-feature-icon {
    width: 36px;
    height: 36px;
    border-radius: 10px;
    background: linear-gradient(135deg, rgba(255, 107, 0, 0.2), rgba(255, 107, 0, 0.05));
    border: 1px solid rgba(255, 107, 0, 0.3);
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--orange);
    flex-shrink: 0;
  }

  .contact-feature-icon svg {
    width: 18px;
    height: 18px;
  }

  .contact-form {
    background: linear-gradient(145deg, var(--black-3), var(--black-2));
    border: 1px solid var(--gray-3);
    border-radius: 24px;
    padding: 40px;
    position: relative;
  }

  .form-group {
    margin-bottom: 20px;
  }

  .form-label {
    display: block;
    font-size: 13px;
    color: var(--gray);
    margin-bottom: 8px;
    font-weight: 500;
  }

  .form-label .required {
    color: var(--orange);
  }

  .form-input,
  .form-textarea,
  .form-select {
    width: 100%;
    padding: 14px 16px;
    background: var(--black);
    border: 1px solid var(--gray-3);
    border-radius: 12px;
    color: #fff;
    font-size: 14px;
    font-family: inherit;
    transition: all 0.2s ease;
  }

  .form-input:focus,
  .form-textarea:focus,
  .form-select:focus {
    outline: none;
    border-color: var(--orange);
    box-shadow: 0 0 0 3px rgba(255, 107, 0, 0.15);
  }

  .form-input::placeholder,
  .form-textarea::placeholder {
    color: var(--gray-2);
  }

  .form-textarea {
    resize: vertical;
    min-height: 100px;
    font-family: inherit;
  }

  .form-select {
    appearance: none;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 24 24' fill='none' stroke='%23ff6b00' stroke-width='2'%3E%3Cpolyline points='6 9 12 15 18 9'%3E%3C/polyline%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-position: right 16px center;
    padding-right: 40px;
    cursor: pointer;
  }

  .form-select option {
    background: var(--black-2);
    color: #fff;
  }

  .form-submit {
    width: 100%;
    padding: 16px;
    background: linear-gradient(135deg, var(--orange), var(--orange-dark));
    border: none;
    border-radius: 12px;
    color: #000;
    font-size: 15px;
    font-weight: 700;
    cursor: pointer;
    transition: all 0.3s ease;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    margin-top: 8px;
  }

  .form-submit:hover:not(:disabled) {
    background: linear-gradient(135deg, var(--orange-light), var(--orange));
    transform: translateY(-2px);
    box-shadow: 0 15px 40px -10px var(--orange-glow);
  }

  .form-submit:disabled {
    opacity: 0.7;
    cursor: wait;
  }

  .form-submit .spinner {
    width: 16px;
    height: 16px;
    border: 2px solid rgba(0,0,0,0.2);
    border-top-color: #000;
    border-radius: 50%;
    animation: spin 0.8s linear infinite;
    display: none;
  }

  .form-submit.loading .spinner {
    display: block;
  }

  .form-submit.loading .btn-text {
    display: none;
  }

  @keyframes spin {
    to { transform: rotate(360deg); }
  }

  .form-status {
    margin-top: 16px;
    padding: 12px 16px;
    border-radius: 10px;
    font-size: 14px;
    display: none;
    align-items: flex-start;
    gap: 10px;
  }

  .form-status.show {
    display: flex;
  }

  .form-status.success {
    background: rgba(34, 197, 94, 0.1);
    border: 1px solid rgba(34, 197, 94, 0.3);
    color: var(--success);
  }

  .form-status.error {
    background: rgba(239, 68, 68, 0.1);
    border: 1px solid rgba(239, 68, 68, 0.3);
    color: var(--error);
  }

  .form-status-icon {
    width: 20px;
    height: 20px;
    flex-shrink: 0;
  }

  .form-note {
    margin-top: 16px;
    font-size: 12px;
    color: var(--gray-2);
    text-align: center;
    line-height: 1.5;
  }

  /* Footer */
  footer {
    position: relative;
    z-index: 2;
    padding: 40px;
    text-align: center;
    border-top: 1px solid var(--gray-3);
    background: var(--black-2);
  }

  footer p {
    font-size: 14px;
    color: var(--gray-2);
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    flex-wrap: wrap;
  }

  footer .name {
    color: var(--orange);
    font-weight: 600;
  }

  footer .heart {
    color: var(--orange);
    animation: heartBeat 1.5s ease-in-out infinite;
    display: inline-block;
  }

  @keyframes heartBeat {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.15); }
  }

  /* ===== Animations ===== */
  .fade-in,
  .fade-in-left,
  .fade-in-right,
  .scale-in {
    transition: opacity 0.8s cubic-bezier(0.4, 0, 0.2, 1), transform 0.8s cubic-bezier(0.4, 0, 0.2, 1);
  }

  .fade-in {
    opacity: 0;
    transform: translateY(40px);
  }

  .fade-in-left {
    opacity: 0;
    transform: translateX(-40px);
  }

  .fade-in-right {
    opacity: 0;
    transform: translateX(40px);
  }

  .scale-in {
    opacity: 0;
    transform: scale(0.9);
  }

  .fade-in.visible,
  .fade-in-left.visible,
  .fade-in-right.visible,
  .scale-in.visible {
    opacity: 1;
    transform: translate(0, 0) scale(1);
  }

  .stagger > * {
    transition-delay: calc(var(--i, 0) * 0.08s);
  }

  /* Reduced motion */
  @media (prefers-reduced-motion: reduce) {
    *, *::before, *::after {
      animation-duration: 0.01ms !important;
      animation-iteration-count: 1 !important;
      transition-duration: 0.01ms !important;
      scroll-behavior: auto !important;
    }
    .fade-in, .fade-in-left, .fade-in-right, .scale-in {
      opacity: 1;
      transform: none;
    }
  }

  /* ===== Responsive ===== */
  @media (max-width: 1100px) {
    .floating-code {
      display: none;
    }

    .hero-bottom {
      grid-template-columns: 1fr;
      gap: 32px;
    }

    .hero-stats {
      justify-content: flex-start;
    }

    .about-grid,
    .selling-wrapper,
    .contact-wrapper {
      grid-template-columns: 1fr;
      gap: 40px;
    }

    .process-grid {
      grid-template-columns: repeat(2, 1fr);
    }

    .process-grid::before {
      display: none;
    }

    .features-grid {
      grid-template-columns: repeat(2, 1fr);
    }

    .pricing-grid {
      grid-template-columns: repeat(2, 1fr);
    }

    .pricing-grid .price-card:nth-child(3) {
      grid-column: span 2;
    }
  }

  @media (max-width: 860px) {
    .nav {
      padding: 10px 14px 10px 16px;
      gap: 12px;
    }

    .nav-links,
    .nav-cta {
      display: none;
    }

    .burger {
      display: block;
    }

    .hero {
      padding: 110px 20px 60px;
    }

    section {
      padding: 80px 20px;
    }

    .contact {
      padding: 80px 20px;
    }

    .services-grid,
    .tech-grid,
    .niches-grid,
    .advantages-grid,
    .features-grid,
    .process-grid,
    .pricing-grid {
      grid-template-columns: 1fr;
    }

    .pricing-grid .price-card:nth-child(3) {
      grid-column: span 1;
    }

    .marquee-item {
      font-size: 32px;
    }

    .hero h1 {
      font-size: 44px;
    }

    .stat-number {
      font-size: 32px;
    }

    .hero-stats {
      gap: 20px;
    }

    .contact-form {
      padding: 28px 24px;
    }

    .service-card,
    .advantage-card,
    .process-card {
      padding: 28px 24px;
    }

    .selling-visual {
      padding: 24px;
    }

    .about-visual {
      max-width: 320px;
      margin: 0 auto;
    }
  }

  @media (max-width: 480px) {
    .hero h1 {
      font-size: 36px;
    }

    .stat-number {
      font-size: 28px;
    }

    .section-title {
      font-size: 28px;
    }

    .hero-stats {
      flex-direction: column;
      gap: 16px;
      align-items: flex-start;
    }

    .stat {
      text-align: left;
    }

    .faq-question {
      padding: 20px;
      font-size: 15px;
    }

    .faq-answer-inner {
      padding: 0 20px 20px;
    }
  }
</style>
</head>
<body>
  <div class="bg-wrapper" aria-hidden="true">
    <div class="blob blob-1"></div>
    <div class="blob blob-2"></div>
    <div class="blob blob-3"></div>
  </div>
  <div class="bg-grid" aria-hidden="true"></div>
  <div class="bg-noise" aria-hidden="true"></div>

  <!-- Navigation -->
  <nav class="nav" id="nav" aria-label="Главная навигация">
    <a href="#" class="nav-logo" aria-label="Амирхан — на главную">
      <div class="nav-logo-mark" aria-hidden="true">A</div>
      <span>Амирхан</span>
    </a>
    <ul class="nav-links">
      <li><a href="#about">Обо мне</a></li>
      <li><a href="#services">Услуги</a></li>
      <li><a href="#pricing">Цены</a></li>
      <li><a href="#niches">Ниши</a></li>
      <li><a href="#process">Процесс</a></li>
      <li><a href="#faq">FAQ</a></li>
    </ul>
    <a href="#contact" class="nav-cta">Обсудить проект</a>
    <button class="burger" id="burger" aria-label="Открыть меню" aria-expanded="false" aria-controls="mobileMenu">
      <span class="burger-line"></span>
      <span class="burger-line"></span>
      <span class="burger-line"></span>
    </button>
  </nav>

  <!-- Mobile menu -->
  <div class="mobile-menu" id="mobileMenu" aria-hidden="true">
    <a href="#about">Обо мне</a>
    <a href="#services">Услуги</a>
    <a href="#pricing">Цены</a>
    <a href="#niches">Ниши</a>
    <a href="#process">Процесс</a>
    <a href="#faq">FAQ</a>
    <a href="#contact" class="mobile-cta">Обсудить проект</a>
  </div>

  <!-- Hero -->
  <section class="hero" id="top">
    <div class="hero-content">
      <div class="hero-top fade-in">
        <div class="hero-badge">
          <span class="dot" aria-hidden="true"></span>
          <span>Открыт для новых проектов</span>
        </div>
        <div class="hero-location">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path><circle cx="12" cy="10" r="3"></circle></svg>
          <span>Веб-разработчик</span>
        </div>
      </div>
      <h1>
        <span class="line fade-in"><span class="gradient-text">Современные</span></span>
        <span class="line fade-in">сайты, которые</span>
        <span class="line fade-in"><span class="outline">продают</span> за вас</span>
      </h1>
      <div class="hero-bottom">
        <p class="hero-desc fade-in">
          Привет, меня зовут <strong>Амирхан</strong>. Создаю продающие сайты с помощью чистого веб-кода — без конструкторов и шаблонов. Каждый проект уникален, адаптивен и заточен под результат вашего бизнеса.
        </p>
        <div class="hero-stats fade-in">
          <div class="stat">
            <span class="stat-number" data-count="100">0</span><span class="stat-number">%</span>
            <span class="stat-label">Код с нуля</span>
          </div>
          <div class="stat">
            <span class="stat-number">24/7</span>
            <span class="stat-label">Работа сайта</span>
          </div>
          <div class="stat">
            <span class="stat-number">∞</span>
            <span class="stat-label">Ниш</span>
          </div>
        </div>
      </div>
    </div>

    <!-- Floating code card -->
    <div class="floating-code" aria-hidden="true">
      <div class="code-header">
        <span class="code-dot red"></span>
        <span class="code-dot yellow"></span>
        <span class="code-dot green"></span>
        <span class="code-title">amirkhan.dev</span>
      </div>
      <div class="code-body">
        <div class="code-line"><span class="code-num">1</span><span><span class="code-comment">// Ваш продающий сайт</span></span></div>
        <div class="code-line"><span class="code-num">2</span><span><span class="code-tag">const</span> <span class="code-var">project</span> = {</span></div>
        <div class="code-line"><span class="code-num">3</span><span>&nbsp;&nbsp;design: <span class="code-str">"современный"</span>,</span></div>
        <div class="code-line"><span class="code-num">4</span><span>&nbsp;&nbsp;speed: <span class="code-str">"молниеносная"</span>,</span></div>
        <div class="code-line"><span class="code-num">5</span><span>&nbsp;&nbsp;conversion: <span class="code-str">"максимум"</span>,</span></div>
        <div class="code-line"><span class="code-num">6</span><span>&nbsp;&nbsp;mobile: <span class="code-tag">true</span>,</span></div>
        <div class="code-line"><span class="code-num">7</span><span>&nbsp;&nbsp;seo: <span class="code-tag">true</span></span></div>
        <div class="code-line"><span class="code-num">8</span><span>};</span></div>
        <div class="code-line"><span class="code-num">9</span><span><span class="code-fn">launch</span>(project);<span class="code-cursor"></span></span></div>
      </div>
    </div>

    <div class="scroll-indicator" aria-hidden="true">
      <span>Scroll</span>
      <div class="scroll-line"></div>
    </div>
  </section>

  <!-- Marquee -->
  <div class="marquee" aria-hidden="true">
    <div class="marquee-track">
      <div class="marquee-item">ЛЕНДИНГИ <span class="dot"></span></div>
      <div class="marquee-item">МАГАЗИНЫ <span class="dot"></span></div>
      <div class="marquee-item">ПОРТФОЛИО <span class="dot"></span></div>
      <div class="marquee-item">КОРПОРАТИВНЫЕ <span class="dot"></span></div>
      <div class="marquee-item">ЛЕНДИНГИ <span class="dot"></span></div>
      <div class="marquee-item">МАГАЗИНЫ <span class="dot"></span></div>
      <div class="marquee-item">ПОРТФОЛИО <span class="dot"></span></div>
      <div class="marquee-item">КОРПОРАТИВНЫЕ <span class="dot"></span></div>
    </div>
  </div>

  <!-- About -->
  <section class="about" id="about">
    <div class="container">
      <div class="about-grid">
        <div class="about-text fade-in-left">
          <div class="section-label">Обо мне</div>
          <h2 class="section-title">Веб-разработка — это моё <span class="highlight">призвание</span></h2>
          <p>
            Меня зовут <strong>Амирхан</strong>, мне 20 лет. Я специализируюсь на создании <strong>продающих сайтов</strong>, которые не просто красиво выглядят, но и помогают бизнесу привлекать клиентов.
          </p>
          <p>
            Работаю только с чистым кодом — без конструкторов и шаблонов. Это значит, что ваш сайт будет <strong>быстрым, гибким и полностью уникальным</strong>.
          </p>
          <p>
            Беру проекты из самых разных ниш: от салонов красоты и ресторанов до IT-стартапов и интернет-магазинов. Для каждого бизнеса создаю индивидуальный дизайн и структуру.
          </p>
        </div>
        <div class="about-visual fade-in-right" aria-hidden="true">
          <div class="about-visual-circle c1"></div>
          <div class="about-visual-circle c2"></div>
          <div class="about-visual-circle c3"></div>
          <div class="about-center">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="16 18 22 12 16 6"></polyline><polyline points="8 6 2 12 8 18"></polyline></svg>
          </div>
        </div>
      </div>

      <div class="features-grid stagger">
        <div class="feature-card fade-in" style="--i:0">
          <div class="feature-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 19l7-7 3 3-7 7-3-3z"></path><path d="M18 13l-1.5-7.5L2 2l3.5 14.5L13 18l5-5z"></path><path d="M2 2l7.586 7.586"></path><circle cx="11" cy="11" r="2"></circle></svg>
          </div>
          <h3>Уникальный дизайн</h3>
          <p>Каждый сайт создаётся под ваш бренд с нуля</p>
        </div>
        <div class="feature-card fade-in" style="--i:1">
          <div class="feature-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"></polygon></svg>
          </div>
          <h3>Быстрая загрузка</h3>
          <p>Оптимизированный код для максимальной скорости</p>
        </div>
        <div class="feature-card fade-in" style="--i:2">
          <div class="feature-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="5" y="2" width="14" height="20" rx="2" ry="2"></rect><line x1="12" y1="18" x2="12.01" y2="18"></line></svg>
          </div>
          <h3>Адаптивность</h3>
          <p>Идеально выглядит на всех устройствах и экранах</p>
        </div>
        <div class="feature-card fade-in" style="--i:3">
          <div class="feature-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="12" y1="1" x2="12" y2="23"></line><path d="M17 5H9.5a3.5 3.5 0 0 0 0 7h5a3.5 3.5 0 0 1 0 7H6"></path></svg>
          </div>
          <h3>Продающая структура</h3>
          <p>Сайт, который конвертирует посетителей в клиентов</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Services -->
  <section class="services" id="services">
    <div class="container">
      <div class="section-header">
        <div class="section-label fade-in">Что я создаю</div>
        <h2 class="section-title fade-in">Типы сайтов, которые <span class="highlight">я разрабатываю</span></h2>
        <p class="section-subtitle fade-in">От простых лендингов до сложных корпоративных решений — работаю с проектами любой сложности</p>
      </div>
      <div class="services-grid stagger">
        <div class="service-card fade-in" style="--i:0">
          <div class="service-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle><circle cx="12" cy="12" r="6"></circle><circle cx="12" cy="12" r="2"></circle></svg>
          </div>
          <h3>Продающие лендинги</h3>
          <p>Одностраничные сайты с чёткой структурой, убедительными призывами и высокой конверсией. Созданы специально для превращения посетителей в клиентов.</p>
          <div class="service-arrow">Подробнее →</div>
        </div>
        <div class="service-card fade-in" style="--i:1">
          <div class="service-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 21h18"></path><path d="M5 21V7l8-4v18"></path><path d="M19 21V11l-6-4"></path><path d="M9 9v.01"></path><path d="M9 12v.01"></path><path d="M9 15v.01"></path><path d="M9 18v.01"></path></svg>
          </div>
          <h3>Корпоративные сайты</h3>
          <p>Многостраничные сайты для бизнеса любого масштаба. Полное представительство вашей компании в интернете со всеми услугами и преимуществами.</p>
          <div class="service-arrow">Подробнее →</div>
        </div>
        <div class="service-card fade-in" style="--i:2">
          <div class="service-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="9" cy="21" r="1"></circle><circle cx="20" cy="21" r="1"></circle><path d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h9.72a2 2 0 0 0 2-1.61L23 6H6"></path></svg>
          </div>
          <h3>Интернет-магазины</h3>
          <p>Каталоги товаров с удобным интерфейсом, фильтрацией и корзиной. Создаю магазины, в которых покупателям приятно совершать покупки.</p>
          <div class="service-arrow">Подробнее →</div>
        </div>
        <div class="service-card fade-in" style="--i:3">
          <div class="service-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"></polygon></svg>
          </div>
          <h3>Сайты-визитки и портфолио</h3>
          <p>Стильные презентации для специалистов и творческих людей. Минималистичный дизайн, который подчёркивает ваш профессионализм и экспертизу.</p>
          <div class="service-arrow">Подробнее →</div>
        </div>
      </div>
    </div>
  </section>

  <!-- Selling -->
  <section class="selling" id="selling">
    <div class="container">
      <div class="selling-wrapper">
        <div class="selling-visual fade-in-left" aria-hidden="true">
          <div class="selling-visual-grid">
            <div class="selling-tile big">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"></path></svg>
            </div>
            <div class="selling-tile">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="23 6 13.5 15.5 8.5 10.5 1 18"></polyline><polyline points="17 6 23 6 23 12"></polyline></svg>
            </div>
            <div class="selling-tile tall">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 8h1a4 4 0 0 1 0 8h-1"></path><path d="M2 8h16v9a4 4 0 0 1-4 4H6a4 4 0 0 1-4-4V8z"></path><line x1="6" y1="1" x2="6" y2="4"></line><line x1="10" y1="1" x2="10" y2="4"></line><line x1="14" y1="1" x2="14" y2="4"></line></svg>
            </div>
            <div class="selling-tile">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"></path></svg>
            </div>
            <div class="selling-tile">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle><polyline points="12 6 12 12 16 14"></polyline></svg>
            </div>
          </div>
        </div>
        <div class="fade-in-right">
          <div class="section-label">Продающие сайты</div>
          <h2 class="section-title">Сайт, который <span class="highlight">работает</span> на ваш бизнес</h2>
          <p class="section-subtitle">Продающий сайт — это не просто красивая картинка. Это инструмент, который привлекает клиентов и побуждает к действию.</p>
          <div class="selling-points">
            <div class="selling-point">
              <span class="selling-point-num">01</span>
              <span>Привлекательный первый экран, захватывающий внимание за 3 секунды</span>
            </div>
            <div class="selling-point">
              <span class="selling-point-num">02</span>
              <span>Чёткое описание преимуществ и выгод для клиента</span>
            </div>
            <div class="selling-point">
              <span class="selling-point-num">03</span>
              <span>Социальные доказательства и результаты</span>
            </div>
            <div class="selling-point">
              <span class="selling-point-num">04</span>
              <span>Убедительные призывы к действию на каждом экране</span>
            </div>
            <div class="selling-point">
              <span class="selling-point-num">05</span>
              <span>Адаптивный дизайн для всех устройств</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Pricing -->
  <section class="pricing" id="pricing">
    <div class="container">
      <div class="section-header">
        <div class="section-label fade-in">Стоимость</div>
        <h2 class="section-title fade-in">Прозрачные <span class="highlight">цены</span> без скрытых платежей</h2>
        <p class="section-subtitle fade-in">Диапазон от 15 000 до 60 000 ₽. Точная стоимость зависит от сложности, количества страниц и дополнительных функций</p>
      </div>
      <div class="pricing-grid stagger">
        <div class="price-card fade-in" style="--i:0">
          <div class="price-card-label">Базовый</div>
          <h3>Лендинг</h3>
          <p class="price-card-desc">Одностраничный сайт для презентации продукта, услуги или акции</p>
          <div class="price-amount">
            <span class="price-from">от</span>
            <span class="price-value">15</span>
            <span class="price-currency">000 ₽</span>
          </div>
          <div class="price-note">Срок: 3–7 дней</div>
          <div class="price-divider"></div>
          <ul class="price-features">
            <li><span class="check" aria-hidden="true">✓</span> Индивидуальный дизайн</li>
            <li><span class="check" aria-hidden="true">✓</span> Адаптив под все устройства</li>
            <li><span class="check" aria-hidden="true">✓</span> Анимации и интерактив</li>
            <li><span class="check" aria-hidden="true">✓</span> Базовая SEO-оптимизация</li>
            <li><span class="check" aria-hidden="true">✓</span> Форма заявки</li>
          </ul>
          <a href="#contact" class="price-btn" data-project="Лендинг">Заказать лендинг</a>
        </div>
        <div class="price-card featured fade-in" style="--i:1">
          <div class="price-card-label">Оптимальный</div>
          <h3>Многостраничный</h3>
          <p class="price-card-desc">Корпоративный сайт или сайт-визитка с несколькими разделами</p>
          <div class="price-amount">
            <span class="price-from">от</span>
            <span class="price-value">30</span>
            <span class="price-currency">000 ₽</span>
          </div>
          <div class="price-note">Срок: 7–14 дней</div>
          <div class="price-divider"></div>
          <ul class="price-features">
            <li><span class="check" aria-hidden="true">✓</span> До 7 уникальных страниц</li>
            <li><span class="check" aria-hidden="true">✓</span> Премиальный дизайн</li>
            <li><span class="check" aria-hidden="true">✓</span> Сложные анимации</li>
            <li><span class="check" aria-hidden="true">✓</span> Расширенная SEO</li>
            <li><span class="check" aria-hidden="true">✓</span> Интеграции с сервисами</li>
            <li><span class="check" aria-hidden="true">✓</span> Поддержка 30 дней</li>
          </ul>
          <a href="#contact" class="price-btn" data-project="Многостраничный сайт">Заказать сайт</a>
        </div>
        <div class="price-card fade-in" style="--i:2">
          <div class="price-card-label">Продвинутый</div>
          <h3>Интернет-магазин</h3>
          <p class="price-card-desc">Полноценный магазин с каталогом, фильтрами и корзиной</p>
          <div class="price-amount">
            <span class="price-from">от</span>
            <span class="price-value">45</span>
            <span class="price-currency">000 ₽</span>
          </div>
          <div class="price-note">Срок: 14–21 день</div>
          <div class="price-divider"></div>
          <ul class="price-features">
            <li><span class="check" aria-hidden="true">✓</span> Каталог товаров</li>
            <li><span class="check" aria-hidden="true">✓</span> Фильтры и поиск</li>
            <li><span class="check" aria-hidden="true">✓</span> Корзина и оформление</li>
            <li><span class="check" aria-hidden="true">✓</span> Панель управления</li>
            <li><span class="check" aria-hidden="true">✓</span> Интеграция оплаты</li>
            <li><span class="check" aria-hidden="true">✓</span> Поддержка 60 дней</li>
          </ul>
          <a href="#contact" class="price-btn" data-project="Интернет-магазин">Заказать магазин</a>
        </div>
      </div>
    </div>
  </section>

  <!-- Niches -->
  <section class="niches" id="niches">
    <div class="container">
      <div class="section-header">
        <div class="section-label fade-in">Разнообразие ниш</div>
        <h2 class="section-title fade-in">Работаю с <span class="highlight">любыми сферами</span> бизнеса</h2>
        <p class="section-subtitle fade-in">Не важно, чем вы занимаетесь — я создам сайт, идеально подходящий именно для вашей ниши</p>
      </div>
      <div class="niches-grid stagger">
        <div class="niche-card fade-in" style="--i:0">
          <div class="niche-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 8h1a4 4 0 0 1 0 8h-1"></path><path d="M2 8h16v9a4 4 0 0 1-4 4H6a4 4 0 0 1-4-4V8z"></path></svg>
          </div>
          <h3>Рестораны и кафе</h3>
          <p>Меню, бронирование столиков, атмосфера заведения</p>
        </div>
        <div class="niche-card fade-in" style="--i:1">
          <div class="niche-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"></path></svg>
          </div>
          <h3>Салоны красоты</h3>
          <p>Услуги, мастера, онлайн-запись, портфолио работ</p>
        </div>
        <div class="niche-card fade-in" style="--i:2">
          <div class="niche-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="16 18 22 12 16 6"></polyline><polyline points="8 6 2 12 8 18"></polyline></svg>
          </div>
          <h3>IT и технологии</h3>
          <p>Стартапы, SaaS, технологические решения</p>
        </div>
        <div class="niche-card fade-in" style="--i:3">
          <div class="niche-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"></path><polyline points="14 2 14 8 20 8"></polyline><line x1="16" y1="13" x2="8" y2="13"></line><line x1="16" y1="17" x2="8" y2="17"></line></svg>
          </div>
          <h3>Мода и стиль</h3>
          <p>Бренды одежды, аксессуары, лукбуки</p>
        </div>
        <div class="niche-card fade-in" style="--i:4">
          <div class="niche-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 12h-4l-3 9L9 3l-3 9H2"></path></svg>
          </div>
          <h3>Фитнес и спорт</h3>
          <p>Тренажёрные залы, тренеры, расписание занятий</p>
        </div>
        <div class="niche-card fade-in" style="--i:5">
          <div class="niche-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"></path><polyline points="9 22 9 12 15 12 15 22"></polyline></svg>
          </div>
          <h3>Недвижимость</h3>
          <p>Агентства, застройщики, каталоги объектов</p>
        </div>
        <div class="niche-card fade-in" style="--i:6">
          <div class="niche-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M2 3h6a4 4 0 0 1 4 4v14a3 3 0 0 0-3-3H2z"></path><path d="M22 3h-6a4 4 0 0 0-4 4v14a3 3 0 0 1 3-3h7z"></path></svg>
          </div>
          <h3>Образование</h3>
          <p>Курсы, школы, онлайн-обучение, платформы</p>
        </div>
        <div class="niche-card fade-in" style="--i:7">
          <div class="niche-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle><path d="M12 8v8"></path><path d="M8 12h8"></path></svg>
          </div>
          <h3>Медицина</h3>
          <p>Клиники, врачи, запись на приём, услуги</p>
        </div>
        <div class="niche-card fade-in" style="--i:8">
          <div class="niche-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="7" width="20" height="14" rx="2" ry="2"></rect><path d="M16 21V5a2 2 0 0 0-2-2h-4a2 2 0 0 0-2 2v16"></path></svg>
          </div>
          <h3>Бизнес-услуги</h3>
          <p>Консалтинг, юридические фирмы, агентства</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Tech -->
  <section class="tech" id="tech">
    <div class="container">
      <div class="section-header">
        <div class="section-label fade-in">Технологии</div>
        <h2 class="section-title fade-in">Современный <span class="highlight">стек</span> технологий</h2>
        <p class="section-subtitle fade-in">Использую только проверенные и актуальные инструменты для создания надёжных и быстрых сайтов</p>
      </div>
      <div class="tech-stack fade-in">
        <span class="tech-tag"><span class="tag-dot" aria-hidden="true"></span>HTML5</span>
        <span class="tech-tag"><span class="tag-dot" aria-hidden="true"></span>CSS3</span>
        <span class="tech-tag"><span class="tag-dot" aria-hidden="true"></span>JavaScript</span>
        <span class="tech-tag"><span class="tag-dot" aria-hidden="true"></span>GSAP анимации</span>
        <span class="tech-tag"><span class="tag-dot" aria-hidden="true"></span>Адаптивная вёрстка</span>
        <span class="tech-tag"><span class="tag-dot" aria-hidden="true"></span>SEO-оптимизация</span>
        <span class="tech-tag"><span class="tag-dot" aria-hidden="true"></span>Кроссбраузерность</span>
        <span class="tech-tag"><span class="tag-dot" aria-hidden="true"></span>WebP оптимизация</span>
      </div>
      <div class="tech-grid stagger">
        <div class="tech-card fade-in" style="--i:0">
          <div class="tech-card-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="16 18 22 12 16 6"></polyline><polyline points="8 6 2 12 8 18"></polyline></svg>
          </div>
          <div>
            <h3>Чистый и валидный код</h3>
            <p>Семантическая вёрстка по стандартам W3C для максимальной надёжности</p>
          </div>
        </div>
        <div class="tech-card fade-in" style="--i:1">
          <div class="tech-card-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"></path></svg>
          </div>
          <div>
            <h3>Плавные анимации</h3>
            <p>CSS и JavaScript анимации для улучшения пользовательского опыта</p>
          </div>
        </div>
        <div class="tech-card fade-in" style="--i:2">
          <div class="tech-card-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="5" y="2" width="14" height="20" rx="2" ry="2"></rect><line x1="12" y1="18" x2="12.01" y2="18"></line></svg>
          </div>
          <div>
            <h3>Мобильная адаптация</h3>
            <p>Идеальное отображение на всех устройствах: от смартфонов до десктопов</p>
          </div>
        </div>
        <div class="tech-card fade-in" style="--i:3">
          <div class="tech-card-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"></polygon></svg>
          </div>
          <div>
            <h3>Быстрая загрузка</h3>
            <p>Оптимизация изображений и кода для максимальной скорости работы</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Process -->
  <section class="process" id="process">
    <div class="container">
      <div class="section-header">
        <div class="section-label fade-in">Как я работаю</div>
        <h2 class="section-title fade-in">Процесс <span class="highlight">создания</span> сайта</h2>
        <p class="section-subtitle fade-in">Прозрачный и понятный процесс от идеи до готового результата</p>
      </div>
      <div class="process-grid stagger">
        <div class="process-card fade-in" style="--i:0">
          <div class="process-number">01</div>
          <h3>Обсуждение</h3>
          <p>Узнаю о вашем бизнесе, целях и пожеланиях. Обсуждаем структуру, стиль и функционал будущего сайта.</p>
        </div>
        <div class="process-card fade-in" style="--i:1">
          <div class="process-number">02</div>
          <h3>Дизайн</h3>
          <p>Создаю макет сайта с учётом ваших предпочтений и современных трендов веб-дизайна.</p>
        </div>
        <div class="process-card fade-in" style="--i:2">
          <div class="process-number">03</div>
          <h3>Разработка</h3>
          <p>Верстаю сайт с нуля, добавляю анимации, адаптирую под мобильные устройства и тестирую.</p>
        </div>
        <div class="process-card fade-in" style="--i:3">
          <div class="process-number">04</div>
          <h3>Запуск</h3>
          <p>Провожу финальные тесты, вношу правки и передаю вам готовый продукт с инструкциями.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Advantages -->
  <section class="advantages">
    <div class="container">
      <div class="section-header">
        <div class="section-label fade-in">Почему я</div>
        <h2 class="section-title fade-in">Преимущества <span class="highlight">работы</span> со мной</h2>
        <p class="section-subtitle fade-in">Что вы получаете, выбирая меня в качестве разработчика</p>
      </div>
      <div class="advantages-grid stagger">
        <div class="advantage-card fade-in" style="--i:0">
          <div class="advantage-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle><circle cx="12" cy="12" r="6"></circle><circle cx="12" cy="12" r="2"></circle></svg>
          </div>
          <h3>Индивидуальный подход</h3>
          <p>Каждый проект уникален. Не использую шаблоны — создаю сайт специально под ваш бизнес.</p>
        </div>
        <div class="advantage-card fade-in" style="--i:1">
          <div class="advantage-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="12" y1="1" x2="12" y2="23"></line><path d="M17 5H9.5a3.5 3.5 0 0 0 0 7h5a3.5 3.5 0 0 1 0 7H6"></path></svg>
          </div>
          <h3>Доступные цены</h3>
          <p>Качественная веб-разработка по разумным ценам. Профессиональный сайт без переплат.</p>
        </div>
        <div class="advantage-card fade-in" style="--i:2">
          <div class="advantage-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"></polygon></svg>
          </div>
          <h3>Быстрые сроки</h3>
          <p>Разработаю ваш сайт в кратчайшие сроки без потери качества. Ценю ваше время.</p>
        </div>
        <div class="advantage-card fade-in" style="--i:3">
          <div class="advantage-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"></path></svg>
          </div>
          <h3>Постоянная связь</h3>
          <p>На связи на всех этапах работы. Показываю промежуточные результаты, учитываю правки.</p>
        </div>
        <div class="advantage-card fade-in" style="--i:4">
          <div class="advantage-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="5" y="2" width="14" height="20" rx="2" ry="2"></rect><line x1="12" y1="18" x2="12.01" y2="18"></line></svg>
          </div>
          <h3>Адаптивность</h3>
          <p>Ваш сайт будет идеально выглядеть на компьютерах, планшетах и смартфонах.</p>
        </div>
        <div class="advantage-card fade-in" style="--i:5">
          <div class="advantage-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"></path></svg>
          </div>
          <h3>Гарантия качества</h3>
          <p>Бесплатно исправляю любые недочёты в течение 30 дней после запуска проекта.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- FAQ -->
  <section class="faq" id="faq">
    <div class="container">
      <div class="section-header" style="margin: 0 auto 60px; text-align: center;">
        <div class="section-label fade-in" style="justify-content: center;">Вопросы и ответы</div>
        <h2 class="section-title fade-in" style="text-align: center;">Частые <span class="highlight">вопросы</span></h2>
        <p class="section-subtitle fade-in" style="margin-left: auto; margin-right: auto;">Собрал самые популярные вопросы и дал на них честные ответы</p>
      </div>
      <div class="faq-list">
        <div class="faq-item fade-in">
          <button class="faq-question" aria-expanded="false">
            <span>Сколько времени занимает создание сайта?</span>
            <span class="faq-icon" aria-hidden="true">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round"><line x1="12" y1="5" x2="12" y2="19"></line><line x1="5" y1="12" x2="19" y2="12"></line></svg>
            </span>
          </button>
          <div class="faq-answer">
            <div class="faq-answer-inner">
              Простой лендинг — 3–7 дней. Многостраничный сайт — 7–14 дней. Интернет-магазин — 14–21 день. Точные сроки зависят от сложности, количества страниц и того, насколько быстро вы будете предоставлять контент и обратную связь.
            </div>
          </div>
        </div>
        <div class="faq-item fade-in">
          <button class="faq-question" aria-expanded="false">
            <span>Что входит в стоимость сайта?</span>
            <span class="faq-icon" aria-hidden="true">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round"><line x1="12" y1="5" x2="12" y2="19"></line><line x1="5" y1="12" x2="19" y2="12"></line></svg>
            </span>
          </button>
          <div class="faq-answer">
            <div class="faq-answer-inner">
              В стоимость входит: обсуждение проекта, дизайн, вёрстка, анимации, адаптация под все устройства, базовая SEO-оптимизация, тестирование и запуск. Хостинг и домен оплачиваются отдельно (обычно это небольшие суммы).
            </div>
          </div>
        </div>
        <div class="faq-item fade-in">
          <button class="faq-question" aria-expanded="false">
            <span>Нужно ли предоставлять контент (тексты, фото)?</span>
            <span class="faq-icon" aria-hidden="true">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round"><line x1="12" y1="5" x2="12" y2="19"></line><line x1="5" y1="12" x2="19" y2="12"></line></svg>
            </span>
          </button>
          <div class="faq-answer">
            <div class="faq-answer-inner">
              Желательно. Тексты и фото от вас делают сайт максимально релевантным для вашего бизнеса. Если у вас нет готовых материалов — подскажу, где взять качественные изображения и как правильно написать тексты. Также могу помочь с копирайтингом за дополнительную плату.
            </div>
          </div>
        </div>
        <div class="faq-item fade-in">
          <button class="faq-question" aria-expanded="false">
            <span>Можно ли вносить правки во время работы?</span>
            <span class="faq-icon" aria-hidden="true">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round"><line x1="12" y1="5" x2="12" y2="19"></line><line x1="5" y1="12" x2="19" y2="12"></line></svg>
            </span>
          </button>
          <div class="faq-answer">
            <div class="faq-answer-inner">
              Конечно. Я показываю промежуточные результаты на каждом этапе и учитываю ваши замечания. 2–3 раунда правок входят в стоимость. Глобальные изменения концепции обсуждаются отдельно.
            </div>
          </div>
        </div>
        <div class="faq-item fade-in">
          <button class="faq-question" aria-expanded="false">
            <span>Что если мне не понравится результат?</span>
            <span class="faq-icon" aria-hidden="true">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round"><line x1="12" y1="5" x2="12" y2="19"></line><line x1="5" y1="12" x2="19" y2="12"></line></svg>
            </span>
          </button>
          <div class="faq-answer">
            <div class="faq-answer-inner">
              Чтобы этого не случилось, мы детально обсуждаем задачу на старте и я показываю работу по этапам. Вы видите, куда движется проект, и можете вносить корректировки. После запуска в течение 30 дней бесплатно исправляю любые недочёты.
            </div>
          </div>
        </div>
        <div class="faq-item fade-in">
          <button class="faq-question" aria-expanded="false">
            <span>Как происходит оплата?</span>
            <span class="faq-icon" aria-hidden="true">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round"><line x1="12" y1="5" x2="12" y2="19"></line><line x1="5" y1="12" x2="19" y2="12"></line></svg>
            </span>
          </button>
          <div class="faq-answer">
            <div class="faq-answer-inner">
              Обычно работаем по схеме: 50% предоплата перед стартом, 50% после завершения и приёмки работы. Для крупных проектов возможна разбивка на 3 платежа по этапам. Все детали фиксируем в переписке.
            </div>
          </div>
        </div>
        <div class="faq-item fade-in">
          <button class="faq-question" aria-expanded="false">
            <span>Будет ли поддержка после запуска сайта?</span>
            <span class="faq-icon" aria-hidden="true">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round"><line x1="12" y1="5" x2="12" y2="19"></line><line x1="5" y1="12" x2="19" y2="12"></line></svg>
            </span>
          </button>
          <div class="faq-answer">
            <div class="faq-answer-inner">
              Да. После сдачи проекта даю гарантию: 30 дней для лендингов и визиток, 60 дней для магазинов. В этот период бесплатно исправляю любые технические недочёты. Дальнейшие доработки и развитие — по договорённости.
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Contact -->
  <section class="contact" id="contact">
    <div class="contact-wrapper">
      <div class="contact-info fade-in-left">
        <div class="section-label">Заявка</div>
        <h2>Обсудим ваш <span class="highlight">проект</span></h2>
        <p>Заполните форму, и я свяжусь с вами, чтобы обсудить детали. Обычно отвечаю в течение часа.</p>
        <div class="contact-features">
          <div class="contact-feature">
            <div class="contact-feature-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"></polygon></svg>
            </div>
            <span>Быстрый ответ в течение часа</span>
          </div>
          <div class="contact-feature">
            <div class="contact-feature-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"></path></svg>
            </div>
            <span>Конфиденциальность ваших данных</span>
          </div>
          <div class="contact-feature">
            <div class="contact-feature-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"></path></svg>
            </div>
            <span>Бесплатная консультация</span>
          </div>
        </div>
      </div>

      <form class="contact-form fade-in-right" id="contactForm" novalidate>
        <div class="form-group">
          <label class="form-label" for="name">Ваше имя <span class="required">*</span></label>
          <input type="text" id="name" name="name" class="form-input" placeholder="Как к вам обращаться?" required maxlength="60">
        </div>
        <div class="form-group">
          <label class="form-label" for="contact">Телефон или Telegram <span class="required">*</span></label>
          <input type="text" id="contact" name="contact" class="form-input" placeholder="+7 999 123-45-67 или @username" required maxlength="60">
        </div>
        <div class="form-group">
          <label class="form-label" for="projectType">Тип проекта</label>
          <select id="projectType" name="projectType" class="form-select">
            <option value="">Выберите тип сайта</option>
            <option value="Лендинг">Лендинг (15 000–25 000 ₽)</option>
            <option value="Многостраничный сайт">Многостраничный сайт (30 000–45 000 ₽)</option>
            <option value="Интернет-магазин">Интернет-магазин (45 000–60 000 ₽)</option>
            <option value="Сайт-визитка">Сайт-визитка / Портфолио</option>
            <option value="Другое">Другое / не определился</option>
          </select>
        </div>
        <div class="form-group">
          <label class="form-label" for="budget">Примерный бюджет</label>
          <select id="budget" name="budget" class="form-select">
            <option value="">Выберите бюджет</option>
            <option value="15-25к">15 000 – 25 000 ₽</option>
            <option value="25-40к">25 000 – 40 000 ₽</option>
            <option value="40-60к">40 000 – 60 000 ₽</option>
            <option value="60к+">60 000 ₽ и больше</option>
          </select>
        </div>
        <div class="form-group">
          <label class="form-label" for="message">О проекте</label>
          <textarea id="message" name="message" class="form-textarea" placeholder="Опишите кратко, что за бизнес, какие задачи должен решить сайт" maxlength="1000"></textarea>
        </div>
        <button type="submit" class="form-submit" id="submitBtn">
          <span class="btn-text">Отправить заявку</span>
          <span class="spinner" aria-hidden="true"></span>
        </button>
        <div class="form-status" id="formStatus" role="alert"></div>
        <p class="form-note">Нажимая «Отправить», вы соглашаетесь на обработку данных</p>
      </form>
    </div>
  </section>

  <!-- Footer -->
  <footer>
    <p>
      Создано с <span class="heart" aria-label="любовью">♥</span> <span class="name">Амирханом</span> · Веб-разработчик
    </p>
  </footer>

<script>
  // ===== Navigation scroll =====
  const nav = document.getElementById('nav');
  let lastScroll = 0;
  window.addEventListener('scroll', () => {
    if (window.scrollY > 50) {
      nav.classList.add('scrolled');
    } else {
      nav.classList.remove('scrolled');
    }
  }, { passive: true });

  // ===== Burger menu =====
  const burger = document.getElementById('burger');
  const mobileMenu = document.getElementById('mobileMenu');
  const mobileLinks = mobileMenu.querySelectorAll('a');

  burger.addEventListener('click', () => {
    const isOpen = burger.classList.toggle('active');
    mobileMenu.classList.toggle('active');
    document.body.classList.toggle('menu-open');
    burger.setAttribute('aria-expanded', String(isOpen));
    mobileMenu.setAttribute('aria-hidden', String(!isOpen));
  });

  mobileLinks.forEach(link => {
    link.addEventListener('click', () => {
      burger.classList.remove('active');
      mobileMenu.classList.remove('active');
      document.body.classList.remove('menu-open');
      burger.setAttribute('aria-expanded', 'false');
      mobileMenu.setAttribute('aria-hidden', 'true');
    });
  });

  // Close menu on Escape
  document.addEventListener('keydown', (e) => {
    if (e.key === 'Escape' && mobileMenu.classList.contains('active')) {
      burger.click();
    }
  });

  // ===== Scroll animations =====
  const animateElements = document.querySelectorAll('.fade-in, .fade-in-left, .fade-in-right, .scale-in');
  
  const observerOptions = {
    threshold: 0.12,
    rootMargin: '0px 0px -50px 0px'
  };

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
      } else {
        entry.target.classList.remove('visible');
      }
    });
  }, observerOptions);

  animateElements.forEach(el => observer.observe(el));

  // ===== Counter animation =====
  const statEl = document.querySelector('[data-count]');
  let counterStarted = false;

  function startCounter() {
    if (counterStarted || !statEl) return;
    counterStarted = true;
    const target = parseInt(statEl.getAttribute('data-count'));
    let current = 0;
    const duration = 1500;
    const steps = 60;
    const increment = target / steps;
    const interval = duration / steps;
    
    const counter = setInterval(() => {
      current += increment;
      if (current >= target) {
        current = target;
        clearInterval(counter);
      }
      statEl.textContent = Math.floor(current);
    }, interval);
  }

  // Start counter when stat is visible
  if (statEl) {
    const counterObserver = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          startCounter();
        }
      });
    }, { threshold: 0.5 });
    counterObserver.observe(statEl);
  }

  // ===== Smooth scroll =====
  document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function (e) {
      const href = this.getAttribute('href');
      if (href === '#' || href.length < 2) return;
      const target = document.querySelector(href);
      if (target) {
        e.preventDefault();
        target.scrollIntoView({
          behavior: 'smooth',
          block: 'start'
        });
      }
    });
  });

  // ===== FAQ accordion =====
  document.querySelectorAll('.faq-question').forEach(btn => {
    btn.addEventListener('click', () => {
      const item = btn.parentElement;
      const answer = item.querySelector('.faq-answer');
      const isActive = item.classList.contains('active');

      // Close others
      document.querySelectorAll('.faq-item.active').forEach(other => {
        if (other !== item) {
          other.classList.remove('active');
          other.querySelector('.faq-answer').style.maxHeight = '';
          other.querySelector('.faq-question').setAttribute('aria-expanded', 'false');
        }
      });

      if (isActive) {
        item.classList.remove('active');
        answer.style.maxHeight = '';
        btn.setAttribute('aria-expanded', 'false');
      } else {
        item.classList.add('active');
        answer.style.maxHeight = answer.scrollHeight + 'px';
        btn.setAttribute('aria-expanded', 'true');
      }
    });
  });

  // ===== Price button prefill =====
  document.querySelectorAll('.price-btn[data-project]').forEach(btn => {
    btn.addEventListener('click', (e) => {
      const projectType = btn.getAttribute('data-project');
      setTimeout(() => {
        const select = document.getElementById('projectType');
        if (select) {
          for (const opt of select.options) {
            if (opt.value === projectType) {
              select.value = opt.value;
              break;
            }
          }
        }
      }, 600);
    });
  });

  // ===== Telegram Form Submission =====
  const BOT_TOKEN = '8912221706:AAFrL7xQhjAhArvW5M0-shtJMO4OVPFjyYQ';
  const form = document.getElementById('contactForm');
  const submitBtn = document.getElementById('submitBtn');
  const formStatus = document.getElementById('formStatus');
  
  // Cached chat_id (received from bot owner's /start message)
  let ownerChatId = localStorage.getItem('tg_owner_chat_id') || null;

  async function getOwnerChatId() {
    if (ownerChatId) return ownerChatId;
    try {
      const res = await fetch(`https://api.telegram.org/bot${BOT_TOKEN}/getUpdates?limit=10`);
      const data = await res.json();
      if (data.ok && data.result && data.result.length > 0) {
        // Find the most recent message
        const lastUpdate = data.result[data.result.length - 1];
        const msg = lastUpdate.message || lastUpdate.edited_message || lastUpdate.callback_query?.message;
        if (msg && msg.chat && msg.chat.id) {
          ownerChatId = msg.chat.id;
          localStorage.setItem('tg_owner_chat_id', String(ownerChatId));
          return ownerChatId;
        }
      }
      return null;
    } catch (e) {
      return null;
    }
  }

  async function sendToTelegram(text) {
    const chatId = await getOwnerChatId();
    if (!chatId) {
      throw new Error('Бот не настроен. Напишите боту /start в Telegram.');
    }
    const res = await fetch(`https://api.telegram.org/bot${BOT_TOKEN}/sendMessage`, {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({
        chat_id: chatId,
        text: text,
        parse_mode: 'HTML'
      })
    });
    const data = await res.json();
    if (!data.ok) {
      throw new Error(data.description || 'Ошибка отправки');
    }
    return data;
  }

  function showStatus(type, message) {
    formStatus.className = `form-status show ${type}`;
    const icon = type === 'success'
      ? '<svg class="form-status-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>'
      : '<svg class="form-status-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle><line x1="12" y1="8" x2="12" y2="12"></line><line x1="12" y1="16" x2="12.01" y2="16"></line></svg>';
    formStatus.innerHTML = `${icon}<span>${message}</span>`;
  }

  function hideStatus() {
    formStatus.className = 'form-status';
    formStatus.innerHTML = '';
  }

  form.addEventListener('submit', async (e) => {
    e.preventDefault();
    hideStatus();

    const name = document.getElementById('name').value.trim();
    const contact = document.getElementById('contact').value.trim();
    const projectType = document.getElementById('projectType').value;
    const budget = document.getElementById('budget').value;
    const message = document.getElementById('message').value.trim();

    if (!name) {
      showStatus('error', 'Пожалуйста, укажите ваше имя');
      document.getElementById('name').focus();
      return;
    }
    if (!contact) {
      showStatus('error', 'Укажите телефон или Telegram для связи');
      document.getElementById('contact').focus();
      return;
    }

    submitBtn.classList.add('loading');
    submitBtn.disabled = true;

    const text = `🔥 <b>НОВАЯ ЗАЯВКА С САЙТА</b>\n\n` +
      `👤 <b>Имя:</b> ${escapeHtml(name)}\n` +
      `📞 <b>Контакт:</b> ${escapeHtml(contact)}\n` +
      `${projectType ? `🎯 <b>Тип проекта:</b> ${escapeHtml(projectType)}\n` : ''}` +
      `${budget ? `💰 <b>Бюджет:</b> ${escapeHtml(budget)}\n` : ''}` +
      `${message ? `📝 <b>О проекте:</b>\n${escapeHtml(message)}\n` : ''}` +
      `\n🕐 <i>${new Date().toLocaleString('ru-RU')}</i>`;

    try {
      await sendToTelegram(text);
      showStatus('success', 'Заявка отправлена! Я свяжусь с вами в ближайшее время.');
      form.reset();
    } catch (err) {
      showStatus('error', `Не удалось отправить: ${err.message}. Свяжитесь со мной напрямую через Авито.`);
    } finally {
      submitBtn.classList.remove('loading');
      submitBtn.disabled = false;
    }
  });

  function escapeHtml(str) {
    return String(str)
      .replace(/&/g, '&amp;')
      .replace(/</g, '&lt;')
      .replace(/>/g, '&gt;')
      .replace(/"/g, '&quot;')
      .replace(/'/g, '&#39;');
  }
</script>
</body>
</html>
```
