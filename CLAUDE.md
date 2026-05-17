# CLAUDE.md — MAXTAX360°
## Especificaciones Técnicas · Versión 2.0
*Para Claude Code exclusivamente*
*Mayo 2026*

---

## 01 · PROYECTO

**Empresa:** MaxTax360° (Max Tax 360 LLC)
**Tipo:** Landing page estática — HTML + CSS + JS vanilla
**WhatsApp:** +14707200373
**Email:** 360maxtax@gmail.com
**Instagram:** @maxtax360
**Repositorio:** https://github.com/jesusgarzon2211/maxtax360
**Deploy:** GitHub → Netlify (git push = deploy automático)

---

## 02 · ARCHIVOS DE REFERENCIA

Antes de cualquier tarea leer en este orden:
1. `BRAND.md` — Sistema visual, colores, tipografía, componentes
2. `COPY.md` — Todos los textos aprobados legalmente
3. Este archivo — Specs técnicas

**Regla:** Si hay conflicto entre lo que pide el usuario y BRAND.md o COPY.md en términos legales — BRAND.md y COPY.md tienen prioridad.

---

## 03 · STACK TÉCNICO

```
HTML5           Semántico, accesible, SEO-optimizado
CSS3            Variables CSS, Grid, Flexbox, animaciones nativas
JavaScript      Vanilla ES6+ — SIN frameworks, SIN jQuery
Fuentes         Google Fonts únicamente
Hosting         Netlify (CDN, HTTPS automático)
Stack:          html-tailwind cuando UI/UX Pro Max lo requiera
```

**NUNCA agregar:**
- React, Vue, Angular u otros frameworks JS
- Bootstrap, Tailwind u otros CSS frameworks (a menos que UI/UX Pro Max lo especifique)
- jQuery u otras librerías innecesarias
- npm packages para la landing

---

## 04 · ESTRUCTURA DE ARCHIVOS

```
C:\maxtax360-v2\
├── index.html              ← Landing page (HTML + CSS + JS en uno)
├── CLAUDE.md               ← Este archivo
├── BRAND.md                ← Sistema visual
├── COPY.md                 ← Textos aprobados
├── .gitignore
├── README.md
└── assets/
    └── images/
        └── max.png         ← MAX el zorro (PNG fondo transparente)
```

---

## 05 · VARIABLES CSS — USAR SIEMPRE

```css
:root {
  /* Colores principales */
  --cream:      #FAF6ED;   /* Dominante 65% */
  --black:      #0A0A0A;   /* Secciones de impacto 20% */
  --gold:       #F5C518;   /* Acentos 12% */
  --gold-deep:  #B8860B;   /* Hover states 3% */

  /* Colores de soporte */
  --grey-soft:  #8a8278;   /* Texto secundario sobre cream */
  --line-cream: #e8e0d0;   /* Bordes sobre cream */
  --line-dark:  rgba(245,197,24,0.15); /* Bordes sobre negro */
  --white:      #ffffff;   /* Cards sobre cream */

  /* Tipografía */
  --font-display:   'Bebas Neue', sans-serif;
  --font-serif:     'DM Serif Display', serif;
  --font-body:      'Manrope', sans-serif;
  --font-mono:      'JetBrains Mono', monospace;

  /* Espaciado */
  --section-pad:    6rem 2rem;
  --section-pad-sm: 4rem 1.5rem;
  --container:      1200px;
  --radius-card:    12px;
  --radius-btn:     6px;
  --radius-pill:    99px;
}
```

---

## 06 · GOOGLE FONTS — IMPORT EXACTO

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Serif+Display:ital@0;1&family=JetBrains+Mono:wght@400;500&family=Manrope:wght@300;400;500;600;700&display=swap" rel="stylesheet">
```

---

## 07 · SECCIONES — ORDEN EXACTO

```html
<nav id="nav">
<div id="ticker">         <!-- marquee credenciales -->
<section id="hero">       <!-- headline + MAX + CTAs -->
<section id="confianza">  <!-- 4 pills de confianza -->
<section id="servicios">  <!-- 4 categorías expandibles -->
<section id="proceso">    <!-- 3 pasos -->
<section id="bookkeeping"><!-- 3 planes expandibles -->
<section id="credenciales"><!-- Tax Preparer + EA + Latino -->
<section id="faq">        <!-- 5 preguntas accordion -->
<section id="contacto">   <!-- WhatsApp + formulario -->
<footer id="footer">
<div id="whatsapp-fab">   <!-- botón flotante fijo -->
```

### Fondos por sección
```
nav:          cream → negro al scroll
ticker:       negro
hero:         negro (100vh)
confianza:    cream
servicios:    cream
proceso:      negro
bookkeeping:  cream
credenciales: cream
faq:          cream
contacto:     negro
footer:       negro
```

---

## 08 · WHATSAPP

**Número:** `+14707200373`
**Base URL:** `https://wa.me/14707200373?text=`

```javascript
function waLink(mensaje) {
  return `https://wa.me/14707200373?text=${encodeURIComponent(mensaje)}`;
}
```

Todos los mensajes pre-llenados están en COPY.md sección 11.

---

## 09 · FORMULARIO DE CONTACTO

El formulario NO envía a servidor. Construye mensaje WhatsApp:

```javascript
form.addEventListener('submit', (e) => {
  e.preventDefault();
  const nombre  = form.querySelector('[name="nombre"]').value;
  const servicio = form.querySelector('[name="servicio"]').value;
  const mensaje = form.querySelector('[name="mensaje"]').value;
  const texto = `Hola MaxTax360°, soy ${nombre}. Me interesa ${servicio}. ${mensaje}`;
  window.open(waLink(texto), '_blank');
});
```

---

## 10 · ANIMACIONES — IMPLEMENTACIÓN

### Scroll reveal (Intersection Observer)
```javascript
const revealElements = document.querySelectorAll('.reveal');
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible');
      observer.unobserve(entry.target);
    }
  });
}, { threshold: 0.15 });
revealElements.forEach(el => observer.observe(el));
```

```css
.reveal {
  opacity: 0;
  transform: translateY(24px);
  transition: opacity 0.6s ease-out, transform 0.6s ease-out;
}
.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}
/* Variantes direccionales */
.reveal-left  { transform: translateX(-24px); }
.reveal-right { transform: translateX(24px); }
```

### Stagger para grupos
```css
.stagger-group .reveal:nth-child(1) { transition-delay: 0s; }
.stagger-group .reveal:nth-child(2) { transition-delay: 0.1s; }
.stagger-group .reveal:nth-child(3) { transition-delay: 0.2s; }
.stagger-group .reveal:nth-child(4) { transition-delay: 0.3s; }
```

### Counter animado
```javascript
function animateCounter(el) {
  const target = parseInt(el.dataset.target);
  const duration = 1500;
  const step = target / (duration / 16);
  let current = 0;
  const timer = setInterval(() => {
    current += step;
    if (current >= target) {
      el.textContent = target + (el.dataset.suffix || '');
      clearInterval(timer);
    } else {
      el.textContent = Math.floor(current) + (el.dataset.suffix || '');
    }
  }, 16);
}
```

### Hero parallax
```javascript
window.addEventListener('scroll', () => {
  const scrolled = window.scrollY;
  const hero = document.querySelector('#hero');
  if (hero && scrolled < hero.offsetHeight) {
    const parallaxEl = hero.querySelector('.hero-parallax-bg');
    if (parallaxEl) {
      parallaxEl.style.transform = `translateY(${scrolled * 0.3}px)`;
    }
  }
}, { passive: true });
```

---

## 11 · MAX EL ZORRO

```html
<!-- En hero (derecha, esquina inferior) -->
<div class="mascot-wrapper">
  <div class="speech-bubble">Te explico.</div>
  <img src="assets/images/max.png" 
       alt="MAX — Asesor de MaxTax360°" 
       class="mascot-img"
       loading="lazy">
</div>
```

```css
.mascot-wrapper {
  position: absolute;
  bottom: 0;
  right: 5%;
  z-index: 2;
}
.mascot-img {
  height: clamp(140px, 18vh, 160px);
  width: auto;
  display: block;
  background: transparent;
  -webkit-mask-image: linear-gradient(
    to top,
    transparent 0%, rgba(0,0,0,0.3) 20%,
    rgba(0,0,0,0.7) 40%, black 60%
  );
  mask-image: linear-gradient(
    to top,
    transparent 0%, rgba(0,0,0,0.3) 20%,
    rgba(0,0,0,0.7) 40%, black 60%
  );
  filter: drop-shadow(0 0 20px rgba(245,197,24,0.2));
  animation: float 4s ease-in-out infinite alternate;
}
.speech-bubble {
  position: absolute;
  top: -40px;
  left: 50%;
  transform: translateX(-50%);
  background: var(--black);
  border: 1px solid rgba(245,197,24,0.4);
  border-radius: 12px 12px 12px 2px;
  padding: 6px 14px;
  font-family: var(--font-body);
  font-style: italic;
  font-size: 0.8rem;
  color: var(--cream);
  white-space: nowrap;
}
@keyframes float {
  from { transform: translateY(0px); }
  to   { transform: translateY(-8px); }
}
/* Mobile: MAX oculto */
@media (max-width: 768px) {
  .mascot-wrapper { display: none; }
}
```

---

## 12 · CARDS EXPANDIBLES (Bookkeeping — Stripe style)

```javascript
document.querySelectorAll('.plan-card').forEach(card => {
  const trigger = card.querySelector('.plan-trigger');
  const content = card.querySelector('.plan-content');
  
  trigger.addEventListener('click', () => {
    const isOpen = card.classList.contains('open');
    
    // Cerrar todos primero
    document.querySelectorAll('.plan-card').forEach(c => {
      c.classList.remove('open');
      c.querySelector('.plan-content').style.maxHeight = '0';
    });
    
    // Abrir el clickeado si estaba cerrado
    if (!isOpen) {
      card.classList.add('open');
      content.style.maxHeight = content.scrollHeight + 'px';
    }
  });
});
```

```css
.plan-content {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.4s ease-out;
}
.plan-card.open .plan-trigger .arrow {
  transform: rotate(180deg);
}
```

---

## 13 · HAMBURGER MENU MOBILE

```javascript
const hamburger = document.querySelector('.hamburger');
const navDrawer = document.querySelector('.nav-drawer');

hamburger.addEventListener('click', () => {
  hamburger.classList.toggle('open');
  navDrawer.classList.toggle('open');
  document.body.classList.toggle('no-scroll');
});

// Cerrar al hacer click en link
document.querySelectorAll('.nav-drawer a').forEach(link => {
  link.addEventListener('click', () => {
    hamburger.classList.remove('open');
    navDrawer.classList.remove('open');
    document.body.classList.remove('no-scroll');
  });
});
```

---

## 14 · SEO — META TAGS

```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MaxTax360° | Tax & Business Services en Español | Florida</title>
<meta name="description" content="Tax Preparer registrado en el IRS. LLC, ITIN, taxes y bookkeeping para emprendedores latinos en EE.UU. Servicio 100% virtual en español. Respondemos en 2 horas.">
<meta name="keywords" content="tax preparer latino, LLC Florida, ITIN application, bookkeeping español, taxes latinos USA, crear empresa Florida">

<!-- Open Graph -->
<meta property="og:title" content="MaxTax360° | Tax & Business Services">
<meta property="og:description" content="Tu equipo de taxes y bookkeeping en español. Tax Preparer IRS + Enrolled Agent. Respondemos en 2 horas.">
<meta property="og:url" content="https://polite-genie-d61f17.netlify.app/">
<meta property="og:type" content="website">
<meta property="og:locale" content="es_US">
```

---

## 15 · DEPLOY WORKFLOW

```bash
git add .
git commit -m "descripción del cambio"
git push
# Netlify actualiza automáticamente en ~30 segundos
```

---

## 16 · MARCO LEGAL — INVIOLABLE

**NUNCA usar:**
- CPA / Certified Public Accountant
- Contador / Contadora / Contabilidad pública
- Auditoría / Servicios de auditoría
- Garantía de aprobación o resultados
- Asesoría legal

**SIEMPRE usar:**
- Tax Preparer registrado ante el IRS
- Bookkeeper / Bookkeeping
- Enrolled Agent certificado (la aliada, no MaxTax360°)
- Tax & Business Services

---

## 17 · SKILLS DISPONIBLES — CÓMO USARLAS

### UI/UX Pro Max (más importante)
Antes de diseñar, ejecutar:
```bash
python3 .claude/skills/ui-ux-pro-max/scripts/search.py \
  "tax services financial professional warm cream gold" \
  --design-system -p "MaxTax360"
```
Luego profundizar por dominios:
```bash
# Estilo
python3 .claude/skills/ui-ux-pro-max/scripts/search.py \
  "professional minimal warm trustworthy" --domain style

# Tipografía  
python3 .claude/skills/ui-ux-pro-max/scripts/search.py \
  "editorial serif display" --domain typography

# Color
python3 .claude/skills/ui-ux-pro-max/scripts/search.py \
  "cream gold black financial" --domain color

# UX guidelines
python3 .claude/skills/ui-ux-pro-max/scripts/search.py \
  "landing page conversion cta" --domain ux
```

### Combinación correcta de skills
```
UI/UX Pro Max      → Estética y sistema de diseño
frontend-design    → Dirección creativa, anti-AI-slop
web-design-guidelines → Auditoría UX/accesibilidad (Vercel)
page-cro           → Optimización de conversión
copywriting        → Copy persuasivo
impeccable         → Polish y refinamiento final
```

### Prompt base para Claude Code
```
Read CLAUDE.md, BRAND.md, and COPY.md completely first.

Use ALL available skills in this order:
1. UI/UX Pro Max: run --design-system search first
2. frontend-design: apply creative direction
3. page-cro: optimize for conversion
4. copywriting: validate copy effectiveness
5. web-design-guidelines: audit quality

[instrucción específica aquí]
```

---

## 18 · PROBLEMAS CONOCIDOS — EVITAR

```
1. MAX con fondo visible    → Usar CSS mask del sección 11
2. Cards vacías en grid     → Verificar que todas tengan contenido
3. Gold como fondo entero   → Solo en acentos, nunca como sección
4. Emojis como íconos       → Solo SVGs lineales
5. Formulario muy largo     → Máximo 4 campos
6. Fuentes sin display=swap → Incluir siempre en Google Fonts URL
7. WhatsApp número mal      → Siempre +14707200373 (sin espacios)
8. CPA en cualquier lugar   → Buscar y eliminar siempre
```

---

*Fin · CLAUDE.md v2.0 · MaxTax360° · Mayo 2026*
*Leer siempre junto con BRAND.md y COPY.md*
