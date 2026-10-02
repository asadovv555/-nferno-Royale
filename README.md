# Inferno-Royale
{
  "template": "nextjs-shadcn"
}
components/ui/*
hooks/use-toast.ts
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer base {
  :root {
    --background: 0 0% 4%;
    --foreground: 30 10% 95%;
    --card: 0 0% 7%;
    --card-foreground: 30 10% 95%;
    --popover: 0 0% 7%;
    --popover-foreground: 30 10% 95%;
    --primary: 18 100% 56%;
    --primary-foreground: 0 0% 100%;
    --secondary: 0 0% 12%;
    --secondary-foreground: 30 10% 90%;
    --muted: 0 0% 12%;
    --muted-foreground: 0 0% 55%;
    --accent: 42 100% 48%;
    --accent-foreground: 0 0% 5%;
    --destructive: 0 72% 51%;
    --destructive-foreground: 0 0% 98%;
    --border: 0 0% 15%;
    --input: 0 0% 15%;
    --ring: 18 100% 56%;
    --radius: 0.625rem;
  }
}

@layer base {
  * {
    border-color: hsl(var(--border));
  }
  body {
    background-color: #0B0B10;
    color: hsl(var(--foreground));
    font-feature-settings: "rlig" 1, "calt" 1;
  }
}

/* === SCROLLBAR === */
::-webkit-scrollbar { width: 8px; height: 8px; }
::-webkit-scrollbar-track { background: #0B0B10; }
::-webkit-scrollbar-thumb { background: #2a2a35; border-radius: 4px; }
::-webkit-scrollbar-thumb:hover { background: #FF5A1F; }

/* === UTILITY === */
.text-glow-orange { text-shadow: 0 0 20px rgba(255, 90, 31, 0.6); }
.text-glow-gold { text-shadow: 0 0 20px rgba(245, 184, 0, 0.6); }
.text-glow-blue { text-shadow: 0 0 20px rgba(47, 128, 237, 0.6); }
.box-glow-orange { box-shadow: 0 0 30px rgba(255, 90, 31, 0.3), 0 0 60px rgba(255, 90, 31, 0.1); }
.box-glow-gold { box-shadow: 0 0 30px rgba(245, 184, 0, 0.3), 0 0 60px rgba(245, 184, 0, 0.1); }
.box-glow-blue { box-shadow: 0 0 30px rgba(47, 128, 237, 0.3), 0 0 60px rgba(47, 128, 237, 0.1); }

.heading-condensed {
  font-weight: 800;
  letter-spacing: -0.02em;
  line-height: 1.1;
}

/* === EMBER PARTICLE BACKGROUND === */
.ember-particles {
  position: absolute;
  inset: 0;
  overflow: hidden;
  pointer-events: none;
}
.ember-particle {
  position: absolute;
  bottom: -10px;
  width: 3px;
  height: 3px;
  border-radius: 50%;
  background: #FF5A1F;
  opacity: 0;
  animation: emberRise linear infinite;
}
@keyframes emberRise {
  0% { opacity: 0; transform: translateY(0) translateX(0); }
  10% { opacity: 0.8; }
  50% { opacity: 0.6; }
  90% { opacity: 0.3; }
  100% { opacity: 0; transform: translateY(-100vh) translateX(var(--drift, 30px)); }
}

/* === AVATAR FRAMES === */
.frame-rainbow {
  border-radius: 50%;
  padding: 4px;
  background: conic-gradient(from 0deg, #ff0000, #ff8800, #ffee00, #00ff44, #00aaff, #aa00ff, #ff0088, #ff0000);
  animation: rainbowSpin 3s linear infinite;
}
@keyframes rainbowSpin {
  to { transform: rotate(360deg); }
}
.frame-rainbow-inner {
  border-radius: 50%;
  background: #0B0B10;
  padding: 3px;
}
.frame-rainbow-glow {
  box-shadow: 0 0 15px 3px rgba(255, 0, 200, 0.4), 0 0 30px 6px rgba(0, 200, 255, 0.3);
  animation: rainbowGlowPulse 2s ease-in-out infinite alternate;
}
@keyframes rainbowGlowPulse {
  0% { box-shadow: 0 0 15px 3px rgba(255, 0, 100, 0.4), 0 0 30px 6px rgba(0, 100, 255, 0.3); }
  100% { box-shadow: 0 0 20px 5px rgba(0, 255, 100, 0.5), 0 0 40px 8px rgba(255, 200, 0, 0.4); }
}

.frame-fire {
  border-radius: 50%;
  padding: 4px;
  background: linear-gradient(0deg, #ff5a1f, #ff8800, #ffcc00, #ff5a1f);
  background-size: 100% 200%;
  animation: fireFlow 2s ease-in-out infinite alternate;
  box-shadow: 0 0 20px 4px rgba(255, 90, 31, 0.5);
}
@keyframes fireFlow {
  0% { background-position: 0% 0%; box-shadow: 0 0 15px 3px rgba(255, 90, 31, 0.4); }
  100% { background-position: 0% 100%; box-shadow: 0 0 25px 6px rgba(255, 136, 0, 0.6); }
}
.frame-fire-inner {
  border-radius: 50%;
  background: #0B0B10;
  padding: 3px;
}

.frame-electric {
  border-radius: 50%;
  padding: 4px;
  background: #1a1a2e;
  box-shadow: 0 0 10px 2px rgba(47, 128, 237, 0.6), inset 0 0 8px 2px rgba(47, 128, 237, 0.3);
  animation: electricPulse 1.5s ease-in-out infinite;
}
@keyframes electricPulse {
  0%, 100% { box-shadow: 0 0 10px 2px rgba(47, 128, 237, 0.5), inset 0 0 8px 2px rgba(47, 128, 237, 0.3); }
  50% { box-shadow: 0 0 20px 5px rgba(47, 128, 237, 0.8), inset 0 0 12px 3px rgba(47, 128, 237, 0.5); }
}
.frame-electric::before {
  content: '';
  position: absolute;
  inset: 0;
  border-radius: 50%;
  border: 2px solid transparent;
  border-top-color: #2F80ED;
  border-right-color: #2F80ED;
  animation: electricSpin 1s linear infinite;
}
@keyframes electricSpin {
  to { transform: rotate(360deg); }
}
.frame-electric-inner {
  border-radius: 50%;
  background: #0B0B10;
  padding: 3px;
}

.frame-golden {
  border-radius: 50%;
  padding: 4px;
  background: linear-gradient(135deg, #F5B800, #ffd700, #F5B800, #b8860b);
  background-size: 200% 200%;
  animation: goldShimmer 3s ease-in-out infinite;
  box-shadow: 0 0 18px 4px rgba(245, 184, 0, 0.5);
}
@keyframes goldShimmer {
  0%, 100% { background-position: 0% 0%; box-shadow: 0 0 15px 3px rgba(245, 184, 0, 0.4); }
  50% { background-position: 100% 100%; box-shadow: 0 0 25px 6px rgba(255, 215, 0, 0.6); }
}
.frame-golden-inner {
  border-radius: 50%;
  background: #0B0B10;
  padding: 3px;
}

.frame-none {
  border-radius: 50%;
  padding: 4px;
  background: #1a1a25;
}
.frame-none-inner {
  border-radius: 50%;
  background: #0B0B10;
  padding: 3px;
}

/* === PROFILE BACKGROUNDS === */
.bg-animated-gradient {
  background: linear-gradient(-45deg, #1a0a05, #2a1100, #1a0510, #051015);
  background-size: 400% 400%;
  animation: gradientShift 8s ease infinite;
}
@keyframes gradientShift {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}

.bg-particles {
  background: #0d0d15;
  position: relative;
  overflow: hidden;
}
.bg-particles::before {
  content: '';
  position: absolute;
  inset: 0;
  background-image: 
    radial-gradient(2px 2px at 20% 30%, rgba(255, 90, 31, 0.4), transparent),
    radial-gradient(2px 2px at 60% 70%, rgba(245, 184, 0, 0.3), transparent),
    radial-gradient(1px 1px at 50% 50%, rgba(47, 128, 237, 0.3), transparent),
    radial-gradient(2px 2px at 80% 10%, rgba(255, 90, 31, 0.3), transparent),
    radial-gradient(1px 1px at 90% 60%, rgba(245, 184, 0, 0.3), transparent),
    radial-gradient(2px 2px at 33% 80%, rgba(47, 128, 237, 0.2), transparent),
    radial-gradient(1px 1px at 15% 90%, rgba(255, 90, 31, 0.3), transparent);
  background-size: 200% 200%;
  animation: particleDrift 20s linear infinite;
}
@keyframes particleDrift {
  0% { background-position: 0% 0%; }
  100% { background-position: 100% 100%; }
}

.bg-flowing-fire {
  background: linear-gradient(0deg, #1a0500, #2a0a00, #1a0500);
  position: relative;
  overflow: hidden;
}
.bg-flowing-fire::before {
  content: '';
  position: absolute;
  inset: 0;
  background: 
    radial-gradient(ellipse at 20% 100%, rgba(255, 90, 31, 0.25), transparent 50%),
    radial-gradient(ellipse at 50% 100%, rgba(255, 136, 0, 0.2), transparent 60%),
    radial-gradient(ellipse at 80% 100%, rgba(245, 184, 0, 0.15), transparent 50%);
  animation: fireFlicker 3s ease-in-out infinite alternate;
}
@keyframes fireFlicker {
  0% { opacity: 0.7; transform: scaleY(1); }
  100% { opacity: 1; transform: scaleY(1.05); }
}
.bg-flowing-fire::after {
  content: '';
  position: absolute;
  inset: 0;
  background-image: 
    radial-gradient(2px 3px at 25% 90%, rgba(255, 90, 31, 0.6), transparent),
    radial-gradient(1px 2px at 55% 95%, rgba(255, 136, 0, 0.5), transparent),
    radial-gradient(2px 3px at 75% 85%, rgba(255, 90, 31, 0.4), transparent),
    radial-gradient(1px 2px at 40% 100%, rgba(245, 184, 0, 0.5), transparent);
  background-size: 100% 100%;
  animation: fireEmbers 4s linear infinite;
}
@keyframes fireEmbers {
  0% { transform: translateY(0); opacity: 0.8; }
  100% { transform: translateY(-100px); opacity: 0; }
}

.bg-none {
  background: linear-gradient(135deg, #0B0B10, #131320);
}

/* === RARITY GLOWS === */
.rarity-common { border-color: #555555; }
.rarity-rare { border-color: #2F80ED; box-shadow: 0 0 12px rgba(47, 128, 237, 0.25); }
.rarity-epic { border-color: #a855f7; box-shadow: 0 0 12px rgba(168, 85, 247, 0.3); }
.rarity-legendary { border-color: #F5B800; box-shadow: 0 0 16px rgba(245, 184, 0, 0.35); }
.rarity-mythic {
  border-color: transparent;
  background: linear-gradient(45deg, #ff0080, #ff8800, #ffee00, #00ff88, #00aaff, #aa00ff, #ff0080);
  background-size: 300% 300%;
  animation: mythicGlow 4s linear infinite;
}
@keyframes mythicGlow {
  0% { background-position: 0% 50%; box-shadow: 0 0 20px rgba(255, 0, 128, 0.4); }
  33% { background-position: 33% 50%; box-shadow: 0 0 20px rgba(255, 136, 0, 0.4); }
  66% { background-position: 66% 50%; box-shadow: 0 0 20px rgba(0, 170, 255, 0.4); }
  100% { background-position: 100% 50%; box-shadow: 0 0 20px rgba(170, 0, 255, 0.4); }
}

/* === FADE IN ANIMATION === */
.fade-in-up {
  animation: fadeInUp 0.6s ease-out forwards;
}
@keyframes fadeInUp {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}

.fade-in {
  animation: fadeIn 0.4s ease-out forwards;
}
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

/* === CARD HOVER === */
.card-hover {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}
.card-hover:hover {
  transform: translateY(-4px);
}

/* === REDUCED MOTION === */
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
