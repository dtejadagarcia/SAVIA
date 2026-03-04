<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="description" content="SAVIA – Ecosistema de Analítica e Inteligencia Artificial de Ecopetrol. Explora cómo la inteligencia fluye y genera valor." />
  <meta name="theme-color" content="#0d0d1a" />
  <title>SAVIA · Ecosistema Ecopetrol</title>

  <!-- Preconnect fuentes -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Space+Grotesk:wght@400;500;600;700&display=swap" rel="stylesheet" />

  <!-- GSAP CDN -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js" defer></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/ScrollTrigger.min.js" defer></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/MotionPathPlugin.min.js" defer></script>

  <link rel="stylesheet" href="styles/main.css" />
  <link rel="stylesheet" href="styles/animations.css" />
  <link rel="stylesheet" href="styles/responsive.css" />
</head>
<body>

  <!-- ═══════════════════════════════════════════
       PANTALLA 1: INTRO / SPLASH
  ═══════════════════════════════════════════ -->
  <section id="screen-intro" class="screen screen-active" role="main" aria-label="Pantalla de bienvenida SAVIA">

    <!-- Fondo con líneas verticales sutiles -->
    <div class="bg-grid" aria-hidden="true"></div>

    <!-- Partículas flotantes -->
    <canvas id="particles-canvas" aria-hidden="true"></canvas>

    <!-- Contenido central -->
    <div class="intro-content">

      <!-- Badge corporativo -->
      <div class="badge-ecopetrol" aria-label="Ecopetrol">
        <span class="badge-dot"></span>
        <span>Ecopetrol · VTI</span>
      </div>

      <!-- Logo SAVIA con efecto luminoso -->
      <div class="savia-logo-wrapper" aria-label="SAVIA">
        <div class="savia-glow-ring" aria-hidden="true"></div>
        <h1 class="savia-title">
          <span class="savia-letter" style="--i:0">S</span><span
            class="savia-letter" style="--i:1">A</span><span
            class="savia-letter" style="--i:2">V</span><span
            class="savia-letter" style="--i:3">I</span><span
            class="savia-letter" style="--i:4">A</span>
        </h1>
        <div class="savia-underline" aria-hidden="true"></div>
      </div>

      <!-- Tagline -->
      <p class="intro-tagline">
        Sembramos decisiones con <em>Analítica</em> e <em>Inteligencia Artificial</em>
      </p>

      <!-- Árbol preview animado en intro -->
      <div class="intro-tree-container" aria-hidden="true">
        <div class="tree-preview-wrapper">
          <!-- SVG del árbol SAVIA oficial representado como SVG inline -->
          <svg id="intro-tree-svg" viewBox="0 0 400 520" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Árbol SAVIA Ecopetrol">
            <!-- RAÍCES -->
            <g id="svg-roots" class="tree-part">
              <ellipse cx="200" cy="490" rx="130" ry="22" fill="none" stroke="#3B2677" stroke-width="1.5" opacity="0.3"/>
              <line x1="200" y1="470" x2="120" y2="495" stroke="#3B2677" stroke-width="3" stroke-linecap="round"/>
              <line x1="200" y1="470" x2="160" y2="498" stroke="#3B2677" stroke-width="2.5" stroke-linecap="round"/>
              <line x1="200" y1="470" x2="200" y2="500" stroke="#3B2677" stroke-width="4" stroke-linecap="round"/>
              <line x1="200" y1="470" x2="240" y2="498" stroke="#3B2677" stroke-width="2.5" stroke-linecap="round"/>
              <line x1="200" y1="470" x2="280" y2="495" stroke="#3B2677" stroke-width="3" stroke-linecap="round"/>
              <line x1="120" y1="495" x2="90" y2="510" stroke="#3B2677" stroke-width="1.5" stroke-linecap="round"/>
              <line x1="120" y1="495" x2="110" y2="512" stroke="#3B2677" stroke-width="1.5" stroke-linecap="round"/>
              <line x1="280" y1="495" x2="300" y2="510" stroke="#3B2677" stroke-width="1.5" stroke-linecap="round"/>
              <line x1="280" y1="495" x2="290" y2="512" stroke="#3B2677" stroke-width="1.5" stroke-linecap="round"/>
              <!-- Label raíces -->
              <text x="200" y="518" text-anchor="middle" fill="#3B2677" font-size="9" font-family="Inter" font-weight="600" opacity="0.7">GOBIERNO · RAÍCES</text>
            </g>

            <!-- TRONCO -->
            <g id="svg-trunk" class="tree-part">
              <rect x="176" y="290" width="48" height="185" rx="10" fill="url(#trunkGrad)" opacity="0.95"/>
              <!-- Líneas internas del tronco (áreas VTI) -->
              <line x1="188" y1="300" x2="188" y2="465" stroke="#14DC80" stroke-width="0.8" opacity="0.4"/>
              <line x1="200" y1="295" x2="200" y2="468" stroke="#14DC80" stroke-width="1.2" opacity="0.6"/>
              <line x1="212" y1="300" x2="212" y2="465" stroke="#14DC80" stroke-width="0.8" opacity="0.4"/>
              <!-- Label tronco -->
              <text x="200" y="385" text-anchor="middle" fill="white" font-size="7" font-family="Inter" font-weight="700" transform="rotate(-90 200 385)">TRONCO · VTI</text>
            </g>

            <!-- COPA / FOLLAJE -->
            <g id="svg-canopy" class="tree-part">
              <!-- Capa inferior copa -->
              <ellipse cx="200" cy="235" rx="115" ry="70" fill="url(#canopyGrad1)" opacity="0.9"/>
              <!-- Capa media copa -->
              <ellipse cx="200" cy="190" rx="95" ry="65" fill="url(#canopyGrad2)" opacity="0.9"/>
              <!-- Capa superior copa -->
              <ellipse cx="200" cy="148" rx="72" ry="55" fill="url(#canopyGrad3)" opacity="0.95"/>
              <!-- Cima -->
              <ellipse cx="200" cy="108" rx="45" ry="38" fill="url(#canopyGrad4)" opacity="1"/>
            </g>

            <!-- RAMAS (Hubs y áreas) -->
            <g id="svg-branches" class="tree-part">
              <!-- Rama izquierda principal -->
              <path d="M 185 290 Q 140 270 100 240" stroke="#2a5c3a" stroke-width="8" fill="none" stroke-linecap="round"/>
              <path d="M 100 240 Q 70 215 55 185" stroke="#2a5c3a" stroke-width="5" fill="none" stroke-linecap="round"/>
              <!-- Rama derecha principal -->
              <path d="M 215 290 Q 260 270 300 240" stroke="#2a5c3a" stroke-width="8" fill="none" stroke-linecap="round"/>
              <path d="M 300 240 Q 330 215 345 185" stroke="#2a5c3a" stroke-width="5" fill="none" stroke-linecap="round"/>
              <!-- Sub-ramas izquierda -->
              <path d="M 130 258 Q 105 235 85 210" stroke="#2a5c3a" stroke-width="4" fill="none" stroke-linecap="round"/>
              <!-- Sub-ramas derecha -->
              <path d="M 270 258 Q 295 235 315 210" stroke="#2a5c3a" stroke-width="4" fill="none" stroke-linecap="round"/>
            </g>

            <!-- HOJAS (Datos) -->
            <g id="svg-leaves" class="tree-part">
              <ellipse cx="58" cy="178" rx="18" ry="12" fill="#14DC80" opacity="0.85" transform="rotate(-20 58 178)"/>
              <ellipse cx="42" cy="165" rx="14" ry="9" fill="#0fbb6e" opacity="0.75" transform="rotate(15 42 165)"/>
              <ellipse cx="72" cy="162" rx="15" ry="10" fill="#14DC80" opacity="0.8" transform="rotate(-35 72 162)"/>
              <ellipse cx="345" cy="178" rx="18" ry="12" fill="#14DC80" opacity="0.85" transform="rotate(20 345 178)"/>
              <ellipse cx="360" cy="163" rx="14" ry="9" fill="#0fbb6e" opacity="0.75" transform="rotate(-15 360 163)"/>
              <ellipse cx="331" cy="162" rx="15" ry="10" fill="#14DC80" opacity="0.8" transform="rotate(35 331 162)"/>
              <!-- Hojas copa -->
              <ellipse cx="155" cy="240" rx="16" ry="10" fill="#14DC80" opacity="0.7" transform="rotate(-25 155 240)"/>
              <ellipse cx="245" cy="240" rx="16" ry="10" fill="#14DC80" opacity="0.7" transform="rotate(25 245 240)"/>
              <ellipse cx="135" cy="200" rx="14" ry="9" fill="#0fbb6e" opacity="0.75" transform="rotate(-40 135 200)"/>
              <ellipse cx="265" cy="200" rx="14" ry="9" fill="#0fbb6e" opacity="0.75" transform="rotate(40 265 200)"/>
              <!-- Hojas cima -->
              <ellipse cx="165" cy="105" rx="15" ry="9" fill="#14DC80" opacity="0.8" transform="rotate(-30 165 105)"/>
              <ellipse cx="235" cy="105" rx="15" ry="9" fill="#14DC80" opacity="0.8" transform="rotate(30 235 105)"/>
              <ellipse cx="200" cy="78" rx="13" ry="8" fill="#14DC80" opacity="0.9" transform="rotate(5 200 78)"/>
            </g>

            <!-- FLORES (Soluciones digitales) -->
            <g id="svg-flowers" class="tree-part">
              <!-- Flor 1 -->
              <g transform="translate(88, 205)">
                <circle cx="0" cy="0" r="6" fill="#c084fc" opacity="0.9"/>
                <circle cx="0" cy="-9" r="3.5" fill="#a855f7" opacity="0.8"/>
                <circle cx="8" cy="-5" r="3.5" fill="#a855f7" opacity="0.8"/>
                <circle cx="8" cy="5" r="3.5" fill="#a855f7" opacity="0.8"/>
                <circle cx="0" cy="9" r="3.5" fill="#a855f7" opacity="0.8"/>
                <circle cx="-8" cy="5" r="3.5" fill="#a855f7" opacity="0.8"/>
                <circle cx="-8" cy="-5" r="3.5" fill="#a855f7" opacity="0.8"/>
                <circle cx="0" cy="0" r="3" fill="white" opacity="0.9"/>
              </g>
              <!-- Flor 2 -->
              <g transform="translate(312, 205)">
                <circle cx="0" cy="0" r="6" fill="#c084fc" opacity="0.9"/>
                <circle cx="0" cy="-9" r="3.5" fill="#a855f7" opacity="0.8"/>
                <circle cx="8" cy="-5" r="3.5" fill="#a855f7" opacity="0.8"/>
                <circle cx="8" cy="5" r="3.5" fill="#a855f7" opacity="0.8"/>
                <circle cx="0" cy="9" r="3.5" fill="#a855f7" opacity="0.8"/>
                <circle cx="-8" cy="5" r="3.5" fill="#a855f7" opacity="0.8"/>
                <circle cx="-8" cy="-5" r="3.5" fill="#a855f7" opacity="0.8"/>
                <circle cx="0" cy="0" r="3" fill="white" opacity="0.9"/>
              </g>
              <!-- Flor 3 (superior) -->
              <g transform="translate(200, 75)">
                <circle cx="0" cy="0" r="5" fill="#c084fc" opacity="0.9"/>
                <circle cx="0" cy="-8" r="3" fill="#a855f7" opacity="0.8"/>
                <circle cx="7" cy="-4" r="3" fill="#a855f7" opacity="0.8"/>
                <circle cx="7" cy="4" r="3" fill="#a855f7" opacity="0.8"/>
                <circle cx="0" cy="8" r="3" fill="#a855f7" opacity="0.8"/>
                <circle cx="-7" cy="4" r="3" fill="#a855f7" opacity="0.8"/>
                <circle cx="-7" cy="-4" r="3" fill="#a855f7" opacity="0.8"/>
                <circle cx="0" cy="0" r="2.5" fill="white" opacity="0.9"/>
              </g>
            </g>

            <!-- FRUTOS (Decisiones) -->
            <g id="svg-fruits" class="tree-part">
              <ellipse cx="155" cy="170" rx="10" ry="13" fill="#f59e0b" opacity="0.9"/>
              <ellipse cx="245" cy="170" rx="10" ry="13" fill="#f59e0b" opacity="0.9"/>
              <ellipse cx="200" cy="140" rx="9" ry="12" fill="#f59e0b" opacity="0.95"/>
              <ellipse cx="175" cy="215" rx="8" ry="11" fill="#fb923c" opacity="0.85"/>
              <ellipse cx="225" cy="215" rx="8" ry="11" fill="#fb923c" opacity="0.85"/>
              <!-- Brillo frutos -->
              <ellipse cx="152" cy="165" rx="3" ry="4" fill="white" opacity="0.4"/>
              <ellipse cx="242" cy="165" rx="3" ry="4" fill="white" opacity="0.4"/>
              <ellipse cx="197" cy="136" rx="2.5" ry="3.5" fill="white" opacity="0.4"/>
            </g>

            <!-- FLUJO SAVIA animado (paths) -->
            <g id="svg-savia-flow" aria-hidden="true">
              <path id="savia-path-1" d="M 200 490 L 200 470 L 200 350 L 200 295 Q 200 275 185 260 Q 160 240 130 220 Q 100 200 85 185" 
                stroke="url(#saviaGrad)" stroke-width="2" fill="none" stroke-dasharray="8 6" opacity="0"/>
              <path id="savia-path-2" d="M 200 490 L 200 295 Q 215 275 240 255 Q 270 235 300 218 Q 325 205 340 190"
                stroke="url(#saviaGrad)" stroke-width="2" fill="none" stroke-dasharray="8 6" opacity="0"/>
              <path id="savia-path-3" d="M 200 295 L 200 220 L 200 148 L 200 108 L 200 78"
                stroke="url(#saviaGrad)" stroke-width="2.5" fill="none" stroke-dasharray="10 5" opacity="0"/>
            </g>

            <!-- DEFINICIONES SVG (Gradientes) -->
            <defs>
              <linearGradient id="trunkGrad" x1="0" y1="0" x2="1" y2="0">
                <stop offset="0%" stop-color="#1a4a2a"/>
                <stop offset="40%" stop-color="#2d7a4a"/>
                <stop offset="60%" stop-color="#3B2677"/>
                <stop offset="100%" stop-color="#2a1a5e"/>
              </linearGradient>
              <linearGradient id="canopyGrad1" x1="0" y1="0" x2="0" y2="1">
                <stop offset="0%" stop-color="#166534"/>
                <stop offset="100%" stop-color="#14532d"/>
              </linearGradient>
              <linearGradient id="canopyGrad2" x1="0" y1="0" x2="0" y2="1">
                <stop offset="0%" stop-color="#15803d"/>
                <stop offset="100%" stop-color="#166534"/>
              </linearGradient>
              <linearGradient id="canopyGrad3" x1="0" y1="0" x2="0" y2="1">
                <stop offset="0%" stop-color="#16a34a"/>
                <stop offset="100%" stop-color="#15803d"/>
              </linearGradient>
              <linearGradient id="canopyGrad4" x1="0" y1="0" x2="0" y2="1">
                <stop offset="0%" stop-color="#22c55e"/>
                <stop offset="100%" stop-color="#16a34a"/>
              </linearGradient>
              <linearGradient id="saviaGrad" x1="0%" y1="100%" x2="0%" y2="0%">
                <stop offset="0%" stop-color="#3B2677"/>
                <stop offset="50%" stop-color="#14DC80"/>
                <stop offset="100%" stop-color="#3B2677"/>
              </linearGradient>
              <filter id="glow-filter">
                <feGaussianBlur stdDeviation="3" result="coloredBlur"/>
                <feMerge>
                  <feMergeNode in="coloredBlur"/>
                  <feMergeNode in="SourceGraphic"/>
                </feMerge>
              </filter>
            </defs>
          </svg>

          <!-- Partículas de savia en intro -->
          <div class="savia-particles-intro" aria-hidden="true">
            <span class="sp sp-1"></span>
            <span class="sp sp-2"></span>
            <span class="sp sp-3"></span>
            <span class="sp sp-4"></span>
            <span class="sp sp-5"></span>
          </div>
        </div>
      </div>

      <!-- Mensaje inspirador -->
      <p class="intro-message" aria-live="polite">
        La inteligencia que fluye contigo.
      </p>

      <!-- CTA principal -->
      <button id="btn-explore" class="btn-primary" aria-label="Explorar el ecosistema SAVIA">
        <span class="btn-text">Explorar el Ecosistema</span>
        <span class="btn-arrow" aria-hidden="true">→</span>
        <div class="btn-glow" aria-hidden="true"></div>
      </button>

      <!-- Indicadores scroll subtle -->
      <div class="scroll-hint" aria-hidden="true">
        <div class="scroll-dot"></div>
        <div class="scroll-dot"></div>
        <div class="scroll-dot"></div>
      </div>

    </div>
  </section>

  <!-- ═══════════════════════════════════════════
       PANTALLA 2: EXPLORACIÓN INTERACTIVA
  ═══════════════════════════════════════════ -->
  <section id="screen-explore" class="screen" role="main" aria-label="Exploración interactiva del árbol SAVIA">

    <div class="bg-grid" aria-hidden="true"></div>

    <!-- Header de exploración -->
    <header class="explore-header" role="banner">
      <button id="btn-back" class="btn-back" aria-label="Volver al inicio">
        <span aria-hidden="true">←</span> SAVIA
      </button>
      <div class="header-center">
        <span class="header-title">Ecosistema Interactivo</span>
        <span class="header-subtitle">Haz clic en cada parte del árbol</span>
      </div>
      <div class="header-actions">
        <button id="btn-flow-mode" class="btn-secondary" aria-label="Activar modo flujo de savia">
          <span class="btn-icon" aria-hidden="true">⟳</span>
          Descubre el flujo
        </button>
        <button id="btn-fullscreen" class="btn-icon-only" aria-label="Pantalla completa" title="Pantalla completa">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" aria-hidden="true">
            <path d="M8 3H5a2 2 0 0 0-2 2v3m18 0V5a2 2 0 0 0-2-2h-3m0 18h3a2 2 0 0 0 2-2v-3M3 16v3a2 2 0 0 0 2 2h3"/>
          </svg>
        </button>
      </div>
    </header>

    <!-- Layout principal de exploración -->
    <div class="explore-layout">

      <!-- Panel izquierdo: info del árbol -->
      <aside class="sidebar-left" role="complementary" aria-label="Guía de exploración">
        <div class="sidebar-card">
          <h3 class="sidebar-title">Partes del Ecosistema</h3>
          <ul class="parts-list" role="list">
            <li class="part-item" data-part="roots" role="button" tabindex="0" aria-label="Explorar Raíces - Gobierno">
              <span class="part-icon" aria-hidden="true">🌱</span>
              <div>
                <strong>Raíces</strong>
                <small>Gobierno</small>
              </div>
              <span class="part-arrow" aria-hidden="true">›</span>
            </li>
            <li class="part-item" data-part="trunk" role="button" tabindex="0" aria-label="Explorar Tronco - Herramientas y Áreas VTI">
              <span class="part-icon" aria-hidden="true">🪵</span>
              <div>
                <strong>Tronco</strong>
                <small>Herramientas + Áreas VTI</small>
              </div>
              <span class="part-arrow" aria-hidden="true">›</span>
            </li>
            <li class="part-item" data-part="branches" role="button" tabindex="0" aria-label="Explorar Ramas - Hubs y áreas de negocio">
              <span class="part-icon" aria-hidden="true">🌿</span>
              <div>
                <strong>Ramas</strong>
                <small>Hubs y áreas de negocio</small>
              </div>
              <span class="part-arrow" aria-hidden="true">›</span>
            </li>
            <li class="part-item" data-part="leaves" role="button" tabindex="0" aria-label="Explorar Hojas - Datos">
              <span class="part-icon" aria-hidden="true">🍃</span>
              <div>
                <strong>Hojas</strong>
                <small>Datos</small>
              </div>
              <span class="part-arrow" aria-hidden="true">›</span>
            </li>
            <li class="part-item" data-part="flowers" role="button" tabindex="0" aria-label="Explorar Flores - Soluciones digitales">
              <span class="part-icon" aria-hidden="true">🌸</span>
              <div>
                <strong>Flores</strong>
                <small>Soluciones digitales</small>
              </div>
              <span class="part-arrow" aria-hidden="true">›</span>
            </li>
            <li class="part-item" data-part="fruits" role="button" tabindex="0" aria-label="Explorar Frutos - Decisiones basadas en datos">
              <span class="part-icon" aria-hidden="true">🍊</span>
              <div>
                <strong>Frutos</strong>
                <small>Decisiones basadas en datos</small>
              </div>
              <span class="part-arrow" aria-hidden="true">›</span>
            </li>
            <li class="part-item part-savia" data-part="savia" role="button" tabindex="0" aria-label="Explorar la Savia - Analítica e IA">
              <span class="part-icon" aria-hidden="true">✨</span>
              <div>
                <strong>Savia</strong>
                <small>Analítica · IA</small>
              </div>
              <span class="part-arrow" aria-hidden="true">›</span>
            </li>
          </ul>
        </div>

        <!-- Progreso de exploración -->
        <div class="progress-card" aria-label="Progreso de exploración">
          <div class="progress-header">
            <span>Explorado</span>
            <span id="progress-count" aria-live="polite">0 / 7</span>
          </div>
          <div class="progress-bar-container" role="progressbar" aria-valuenow="0" aria-valuemin="0" aria-valuemax="7" aria-label="Progreso de exploración">
            <div id="progress-bar" class="progress-bar-fill"></div>
          </div>
          <p class="progress-hint">Descubre cada parte para desbloquear el reto final</p>
        </div>
      </aside>

      <!-- Centro: Árbol interactivo -->
      <main class="tree-stage" role="main" aria-label="Árbol interactivo SAVIA">

        <!-- Contenedor del árbol con overlay SVG -->
        <div class="tree-container" id="tree-container">

          <!-- ===================================
               ÁRBOL PRINCIPAL SAVIA
               (SVG inline completo - representación
               fiel del árbol oficial del documento)
          =================================== -->
          <svg id="main-tree-svg" viewBox="0 0 500 650" xmlns="http://www.w3.org/2000/svg"
               role="img" aria-label="Árbol oficial del Ecosistema SAVIA de Ecopetrol"
               class="main-tree">

            <defs>
              <!-- Gradientes árbol principal -->
              <linearGradient id="main-trunkGrad" x1="0" y1="0" x2="1" y2="0">
                <stop offset="0%" stop-color="#14532d"/>
                <stop offset="35%" stop-color="#166534"/>
                <stop offset="55%" stop-color="#3B2677"/>
                <stop offset="100%" stop-color="#2a1a5e"/>
              </linearGradient>
              <linearGradient id="main-canopy1" x1="0" y1="0" x2="0" y2="1">
                <stop offset="0%" stop-color="#1a6b3c"/>
                <stop
