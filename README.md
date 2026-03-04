<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<meta name="description" content="SAVIA – Ecosistema de Analítica e Inteligencia Artificial de Ecopetrol"/>
<title>SAVIA · Ecosistema Ecopetrol</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Space+Grotesk:wght@500;600;700&display=swap" rel="stylesheet"/>
<style>
/* ═══════════════════════════════════════
   VARIABLES Y RESET GLOBAL
═══════════════════════════════════════ */
:root {
  --green: #14DC80;
  --purple: #3B2677;
  --green-dark: #0fbb6e;
  --green-light: #7fffc4;
  --purple-light: #6d4ec4;
  --purple-dark: #1e1040;
  --bg: #06050f;
  --bg2: #0c0a1f;
  --text: #e8f5ee;
  --text-muted: rgba(232,245,238,0.55);
  --card-bg: rgba(20,15,45,0.85);
  --card-border: rgba(20,220,128,0.18);
  --font-main: 'Inter', sans-serif;
  --font-display: 'Space Grotesk', sans-serif;
  --transition: all 0.35s cubic-bezier(0.4,0,0.2,1);
  --glow-green: 0 0 24px rgba(20,220,128,0.45), 0 0 48px rgba(20,220,128,0.2);
  --glow-purple: 0 0 24px rgba(59,38,119,0.7), 0 0 48px rgba(59,38,119,0.35);
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth;font-size:16px}
body{
  font-family:var(--font-main);
  background:var(--bg);
  color:var(--text);
  overflow:hidden;
  height:100vh;
  width:100vw;
  position:relative;
}
button{cursor:pointer;border:none;background:none;font-family:inherit;color:inherit}
ul{list-style:none}
/* ═══════════════════════════════════════
   PANTALLAS
═══════════════════════════════════════ */
.screen{
  position:fixed;
  inset:0;
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  opacity:0;
  pointer-events:none;
  transition:opacity 0.6s ease, transform 0.6s ease;
  transform:translateY(20px);
  z-index:10;
  overflow:hidden;
}
.screen.active{
  opacity:1;
  pointer-events:all;
  transform:translateY(0);
  z-index:20;
}
/* ═══════════════════════════════════════
   FONDO ANIMADO
═══════════════════════════════════════ */
#bg-canvas{
  position:fixed;
  inset:0;
  z-index:1;
  pointer-events:none;
}
.bg-lines{
  position:fixed;
  inset:0;
  z-index:2;
  pointer-events:none;
  background-image:
    repeating-linear-gradient(90deg,
      rgba(20,220,128,0.03) 0px,
      rgba(20,220,128,0.03) 1px,
      transparent 1px,
      transparent 80px
    );
}
/* ═══════════════════════════════════════
   PANTALLA INTRO
═══════════════════════════════════════ */
#screen-intro{
  z-index:10;
  background:radial-gradient(ellipse at 50% 60%, rgba(59,38,119,0.35) 0%, rgba(6,5,15,0) 70%);
}
.intro-inner{
  position:relative;
  z-index:5;
  display:flex;
  flex-direction:column;
  align-items:center;
  gap:1.6rem;
  padding:2rem;
  text-align:center;
}
.ecopetrol-badge{
  display:inline-flex;
  align-items:center;
  gap:0.5rem;
  background:rgba(59,38,119,0.35);
  border:1px solid rgba(20,220,128,0.25);
  border-radius:100px;
  padding:0.4rem 1.1rem;
  font-size:0.72rem;
  font-weight:600;
  letter-spacing:0.12em;
  text-transform:uppercase;
  color:var(--green);
}
.badge-pulse{
  width:7px;height:7px;
  border-radius:50%;
  background:var(--green);
  animation:pulse-dot 2s ease infinite;
}
@keyframes pulse-dot{
  0%,100%{opacity:1;transform:scale(1)}
  50%{opacity:0.5;transform:scale(1.4)}
}
/* Logo SAVIA */
.savia-logo{
  position:relative;
  display:flex;
  flex-direction:column;
  align-items:center;
}
.savia-word{
  font-family:var(--font-display);
  font-size:clamp(5rem,12vw,9rem);
  font-weight:700;
  letter-spacing:0.15em;
  background:linear-gradient(135deg, var(--green) 0%, #7fffc4 40%, var(--purple-light) 70%, var(--green) 100%);
  background-size:300% 300%;
  -webkit-background-clip:text;
  -webkit-text-fill-color:transparent;
  background-clip:text;
  animation:grad-shift 5s ease infinite;
  filter:drop-shadow(0 0 30px rgba(20,220,128,0.4));
}
@keyframes grad-shift{
  0%,100%{background-position:0% 50%}
  50%{background-position:100% 50%}
}
.savia-tagline-under{
  font-size:0.75rem;
  letter-spacing:0.25em;
  text-transform:uppercase;
  color:var(--text-muted);
  margin-top:-0.5rem;
}
/* SVG Árbol intro */
.intro-tree-wrap{
  position:relative;
  width:min(320px, 60vw);
  height:min(380px, 55vw);
  filter:drop-shadow(0 0 40px rgba(20,220,128,0.3));
  animation:float-tree 6s ease-in-out infinite;
}
@keyframes float-tree{
  0%,100%{transform:translateY(0)}
  50%{transform:translateY(-12px)}
}
.intro-tagline{
  font-size:clamp(0.9rem,2.2vw,1.1rem);
  color:var(--text-muted);
  max-width:460px;
  line-height:1.7;
}
.intro-tagline em{
  color:var(--green);
  font-style:normal;
  font-weight:600;
}
.btn-explore{
  position:relative;
  padding:0.95rem 2.8rem;
  border-radius:100px;
  background:linear-gradient(135deg, var(--green) 0%, #0fbb6e 100%);
  color:#051a0d;
  font-family:var(--font-display);
  font-size:1rem;
  font-weight:700;
  letter-spacing:0.06em;
  text-transform:uppercase;
  transition:var(--transition);
  overflow:hidden;
  box-shadow:0 4px 30px rgba(20,220,128,0.4);
}
.btn-explore::before{
  content:'';
  position:absolute;
  inset:0;
  background:linear-gradient(135deg, var(--purple-light), var(--purple));
  opacity:0;
  transition:opacity 0.4s;
}
.btn-explore:hover{
  transform:translateY(-3px) scale(1.03);
  box-shadow:var(--glow-green);
  color:white;
}
.btn-explore:hover::before{opacity:1}
.btn-explore span{position:relative;z-index:1}
.messages-scroll{
  display:flex;
  gap:2rem;
  overflow:hidden;
  width:100%;
  mask-image:linear-gradient(90deg, transparent, black 15%, black 85%, transparent);
}
.msg-item{
  white-space:nowrap;
  font-size:0.78rem;
  color:var(--text-muted);
  letter-spacing:0.08em;
  padding:0.35rem 1rem;
  border:1px solid rgba(20,220,128,0.12);
  border-radius:100px;
  animation:scroll-msgs 18s linear infinite;
}
@keyframes scroll-msgs{
  0%{transform:translateX(0)}
  100%{transform:translateX(-50%)}
}
/* ═══════════════════════════════════════
   PANTALLA EXPLORACIÓN
═══════════════════════════════════════ */
#screen-explore{
  flex-direction:column;
  padding:0;
}
.explore-header{
  width:100%;
  display:flex;
  align-items:center;
  justify-content:space-between;
  padding:0.85rem 1.5rem;
  background:rgba(6,5,15,0.9);
  border-bottom:1px solid var(--card-border);
  backdrop-filter:blur(20px);
  z-index:100;
  flex-shrink:0;
}
.btn-back{
  display:flex;
  align-items:center;
  gap:0.5rem;
  font-family:var(--font-display);
  font-weight:700;
  font-size:1rem;
  color:var(--green);
  transition:var(--transition);
  letter-spacing:0.08em;
}
.btn-back:hover{transform:translateX(-3px);color:var(--green-light)}
.header-center{
  display:flex;
  flex-direction:column;
  align-items:center;
}
.header-title{
  font-family:var(--font-display);
  font-weight:700;
  font-size:0.95rem;
  color:var(--text);
  letter-spacing:0.08em;
}
.header-sub{
  font-size:0.68rem;
  color:var(--text-muted);
  letter-spacing:0.06em;
}
.header-actions{
  display:flex;
  gap:0.7rem;
  align-items:center;
}
.btn-flow{
  padding:0.5rem 1.1rem;
  border-radius:100px;
  border:1px solid var(--card-border);
  background:rgba(59,38,119,0.25);
  color:var(--green);
  font-size:0.75rem;
  font-weight:600;
  letter-spacing:0.06em;
  transition:var(--transition);
}
.btn-flow:hover{
  background:rgba(59,38,119,0.55);
  border-color:var(--green);
  box-shadow:var(--glow-green);
}
.btn-flow.active{
  background:linear-gradient(135deg, var(--purple), var(--purple-light));
  border-color:var(--purple-light);
  color:white;
}
.btn-fs{
  width:36px;height:36px;
  border-radius:8px;
  border:1px solid var(--card-border);
  background:rgba(59,38,119,0.2);
  color:var(--text-muted);
  display:flex;align-items:center;justify-content:center;
  transition:var(--transition);
  font-size:0.9rem;
}
.btn-fs:hover{color:var(--green);border-color:var(--green)}
/* Layout exploración */
.explore-body{
  display:flex;
  flex:1;
  overflow:hidden;
  height:calc(100vh - 57px);
}
/* Sidebar */
.sidebar{
  width:220px;
  flex-shrink:0;
  background:rgba(6,5,15,0.8);
  border-right:1px solid var(--card-border);
  overflow-y:auto;
  padding:1rem 0.75rem;
  display:flex;
  flex-direction:column;
  gap:0.75rem;
  backdrop-filter:blur(20px);
}
.sidebar::-webkit-scrollbar{width:3px}
.sidebar::-webkit-scrollbar-thumb{background:var(--card-border);border-radius:3px}
.sidebar-section-title{
  font-size:0.6rem;
  font-weight:700;
  letter-spacing:0.15em;
  text-transform:uppercase;
  color:var(--text-muted);
  padding:0 0.5rem;
}
.part-btn{
  display:flex;
  align-items:center;
  gap:0.65rem;
  width:100%;
  padding:0.65rem 0.75rem;
  border-radius:10px;
  border:1px solid transparent;
  background:rgba(255,255,255,0.03);
  text-align:left;
  transition:var(--transition);
  cursor:pointer;
}
.part-btn:hover{
  background:rgba(20,220,128,0.08);
  border-color:rgba(20,220,128,0.2);
}
.part-btn.active{
  background:rgba(20,220,128,0.12);
  border-color:rgba(20,220,128,0.35);
}
.part-btn.explored{
  border-color:rgba(20,220,128,0.15);
}
.part-btn.explored .part-name{color:var(--green)}
.part-icon-badge{
  width:32px;height:32px;
  border-radius:8px;
  display:flex;align-items:center;justify-content:center;
  font-size:1rem;
  flex-shrink:0;
  background:rgba(59,38,119,0.3);
  border:1px solid rgba(59,38,119,0.4);
}
.part-btn.active .part-icon-badge{
  background:rgba(20,220,128,0.15);
  border-color:rgba(20,220,128,0.4);
}
.part-info{flex:1;min-width:0}
.part-name{
  display:block;
  font-size:0.78rem;
  font-weight:600;
  color:var(--text);
  white-space:nowrap;
  overflow:hidden;
  text-overflow:ellipsis;
}
.part-sub{
  display:block;
  font-size:0.63rem;
  color:var(--text-muted);
  margin-top:0.1rem;
}
.part-check{
  width:16px;height:16px;
  border-radius:50%;
  border:1px solid rgba(20,220,128,0.2);
  flex-shrink:0;
  transition:var(--transition);
  display:flex;align-items:center;justify-content:center;
  font-size:0.55rem;
}
.part-btn.explored .part-check{
  background:var(--green);
  border-color:var(--green);
  color:#051a0d;
}
/* Progress */
.progress-card{
  margin-top:auto;
  padding:0.85rem;
  border-radius:12px;
  background:rgba(59,38,119,0.2);
  border:1px solid rgba(59,38,119,0.3);
}
.progress-label{
  display:flex;
  justify-content:space-between;
  font-size:0.65rem;
  color:var(--text-muted);
  margin-bottom:0.5rem;
  font-weight:600;
  letter-spacing:0.05em;
}
.progress-track{
  height:4px;
  border-radius:100px;
  background:rgba(255,255,255,0.06);
  overflow:hidden;
}
.progress-fill{
  height:100%;
  border-radius:100px;
  background:linear-gradient(90deg, var(--purple), var(--green));
  width:0%;
  transition:width 0.6s cubic-bezier(0.4,0,0.2,1);
}
.btn-challenge{
  margin-top:0.75rem;
  width:100%;
  padding:0.6rem;
  border-radius:8px;
  background:linear-gradient(135deg, var(--green), var(--green-dark));
  color:#051a0d;
  font-size:0.72rem;
  font-weight:700;
  letter-spacing:0.06em;
  text-transform:uppercase;
  transition:var(--transition);
  opacity:0.35;
  pointer-events:none;
}
.btn-challenge.ready{
  opacity:1;
  pointer-events:all;
}
.btn-challenge.ready:hover{
  transform:translateY(-2px);
  box-shadow:var(--glow-green);
}
/* ═══ ÁRBOL CENTRAL ═══ */
.tree-stage{
  flex:1;
  display:flex;
  align-items:center;
  justify-content:center;
  position:relative;
  overflow:hidden;
}
.tree-stage-bg{
  position:absolute;
  inset:0;
  background:radial-gradient(ellipse at 50% 60%, rgba(59,38,119,0.2) 0%, transparent 65%);
  pointer-events:none;
}
.tree-wrap{
  position:relative;
  width:min(480px, 55vw);
  height:min(580px, 75vh);
  cursor:default;
}
#main-tree{
  width:100%;
  height:100%;
}
/* Hotspots sobre árbol */
.hotspot{
  position:absolute;
  border-radius:50%;
  cursor:pointer;
  z-index:50;
  transition:var(--transition);
}
.hotspot::before{
  content:'';
  position:absolute;
  inset:-4px;
  border-radius:50%;
  border:2px solid rgba(20,220,128,0);
  transition:var(--transition);
}
.hotspot::after{
  content:attr(data-label);
  position:absolute;
  left:50%;
  transform:translateX(-50%);
  bottom:calc(100% + 8px);
  background:rgba(6,5,15,0.95);
  border:1px solid var(--card-border);
  border-radius:8px;
  padding:0.3rem 0.65rem;
  font-size:0.65rem;
  font-weight:600;
  white-space:nowrap;
  color:var(--green);
  letter-spacing:0.05em;
  opacity:0;
  pointer-events:none;
  transition:opacity 0.2s;
  backdrop-filter:blur(10px);
}
.hotspot:hover::after{opacity:1}
.hotspot:hover::before{
  border-color:rgba(20,220,128,0.7);
  inset:-8px;
}
.hotspot-inner{
  width:100%;
  height:100%;
  border-radius:50%;
  background:radial-gradient(circle, rgba(20,220,128,0.35) 0%, rgba(20,220,128,0) 70%);
  animation:hotspot-pulse 2.5s ease infinite;
}
.hotspot.purple .hotspot-inner{
  background:radial-gradient(circle, rgba(109,78,196,0.4) 0%, rgba(59,38,119,0) 70%);
}
@keyframes hotspot-pulse{
  0%,100%{opacity:0.6;transform:scale(0.9)}
  50%{opacity:1;transform:scale(1.1)}
}
.hotspot.active .hotspot-inner{
  animation:none;
  background:radial-gradient(circle, rgba(20,220,128,0.6) 0%, rgba(20,220,128,0.1) 70%);
}
/* ═══ PANEL INFO DERECHO ═══ */
.info-panel{
  width:300px;
  flex-shrink:0;
  background:rgba(6,5,15,0.85);
  border-left:1px solid var(--card-border);
  overflow-y:auto;
  padding:1.25rem;
  backdrop-filter:blur(20px);
  display:flex;
  flex-direction:column;
  gap:1rem;
  transition:var(--transition);
}
.info-panel::-webkit-scrollbar{width:3px}
.info-panel::-webkit-scrollbar-thumb{background:var(--card-border)}
.panel-empty{
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  flex:1;
  text-align:center;
  gap:1rem;
  opacity:0.5;
}
.panel-empty-icon{
  font-size:2.5rem;
  animation:float-tree 4s ease infinite;
}
.panel-empty p{
  font-size:0.78rem;
  color:var(--text-muted);
  line-height:1.6;
}
.panel-content{display:none;flex-direction:column;gap:1rem}
.panel-content.visible{display:flex}
.panel-badge{
  display:inline-flex;
  align-items:center;
  gap:0.4rem;
  background:rgba(59,38,119,0.35);
  border:1px solid rgba(59,38,119,0.5);
  border-radius:100px;
  padding:0.3rem 0.8rem;
  font-size:0.6rem;
  font-weight:700;
  letter-spacing:0.12em;
  text-transform:uppercase;
  color:var(--purple-light);
  width:fit-content;
}
.panel-title{
  font-family:var(--font-display);
  font-size:1.3rem;
  font-weight:700;
  color:var(--text);
  line-height:1.2;
}
.panel-title em{
  color:var(--green);
  font-style:normal;
}
.panel-desc{
  font-size:0.82rem;
  color:var(--text-muted);
  line-height:1.75;
}
.panel-connections{
  border-top:1px solid var(--card-border);
  padding-top:0.85rem;
}
.panel-connections-title{
  font-size:0.6rem;
  font-weight:700;
  letter-spacing:0.12em;
  text-transform:uppercase;
  color:var(--text-muted);
  margin-bottom:0.6rem;
}
.connection-tags{
  display:flex;
  flex-wrap:wrap;
  gap:0.4rem;
}
.conn-tag{
  padding:0.25rem 0.6rem;
  border-radius:100px;
  border:1px solid rgba(20,220,128,0.2);
  font-size:0.62rem;
  color:var(--green);
  font-weight:500;
  background:rgba(20,220,128,0.06);
  transition:var(--transition);
}
.conn-tag:hover{
  background:rgba(20,220,128,0.15);
  border-color:rgba(20,220,128,0.5);
}
.panel-flow-mini{
  padding:0.85rem;
  border-radius:12px;
  background:rgba(59,38,119,0.15);
  border:1px solid rgba(59,38,119,0.25);
}
.flow-mini-title{
  font-size:0.6rem;
  font-weight:700;
  letter-spacing:0.1em;
  text-transform:uppercase;
  color:var(--purple-light);
  margin-bottom:0.65rem;
}
.flow-mini-steps{
  display:flex;
  flex-direction:column;
  gap:0.4rem;
}
.flow-step-mini{
  display:flex;
  align-items:center;
  gap:0.5rem;
  font-size:0.7rem;
  color:var(--text-muted);
  opacity:0.5;
  transition:var(--transition);
}
.flow-step-mini.current{
  color:var(--green);
  opacity:1;
}
.flow-step-mini.current .fsd{
  background:var(--green);
  color:#051a0d;
}
.fsd{
  width:20px;height:20px;
  border-radius:50%;
  background:rgba(59,38,119,0.4);
  border:1px solid rgba(59,38,119,0.5);
  display:flex;align-items:center;justify-content:center;
  font-size:0.55rem;
  font-weight:700;
  flex-shrink:0;
}
.btn-minigame{
  width:100%;
  padding:0.8rem;
  border-radius:10px;
  background:linear-gradient(135deg, var(--green), var(--green-dark));
  color:#051a0d;
  font-family:var(--font-display);
  font-size:0.82rem;
  font-weight:700;
  letter-spacing:0.04em;
  transition:var(--transition);
  text-align:center;
  border:none;
}
.btn-minigame:hover{
  transform:translateY(-2px);
  box-shadow:var(--glow-green);
}
/* Savia flow overlay */
.savia-overlay{
  position:absolute;
  inset:0;
  pointer-events:none;
  z-index:40;
}
/* ═══════════════════════════════════════
   PANTALLA MINIJUEGO
═══════════════════════════════════════ */
#screen-minigame{
  background:rgba(6,5,15,0.98);
  z-index:30;
  padding:0;
}
.mg-header{
  width:100%;
  display:flex;
  align-items:center;
  justify-content:space-between;
  padding:0.85rem 1.5rem;
  background:rgba(12,10,31,0.95);
  border-bottom:1px solid var(--card-border);
  flex-shrink:0;
}
.mg-title-wrap{display:flex;flex-direction:column}
.mg-eyebrow{
  font-size:0.58rem;
  font-weight:700;
  letter-spacing:0.15em;
  text-transform:uppercase;
  color:var(--green);
}
.mg-title{
  font-family:var(--font-display);
  font-size:1rem;
  font-weight:700;
  color:var(--text);
}
.btn-mg-back{
  padding:0.5rem 1rem;
  border-radius:8px;
  border:1px solid var(--card-border);
  background:transparent;
  color:var(--text-muted);
  font-size:0.75rem;
  transition:var(--transition);
}
.btn-mg-back:hover{color:var(--green);border-color:var(--green)}
.mg-body{
  flex:1;
  overflow:auto;
  display:flex;
  align-items:center;
  justify-content:center;
  padding:1.
