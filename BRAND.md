# BRAND.md — MAXTAX360°
## Sistema de Identidad Visual · Versión 2.0
*Archivo de referencia para Claude Design y Claude Code*
*Mayo 2026*

---

## 01 · ESENCIA DE MARCA

### Quiénes somos
MaxTax360° es el equipo de Tax & Business Services que el emprendedor latino en EE.UU. siempre mereció tener. No somos una firma fría y distante. No somos un notario sin credenciales. Somos profesionales registrados ante el IRS que hablan tu idioma — literal y figurativamente.

### El cliente real
Emprendedor latino de 30-55 años. Puede ser dueño de negocio de construcción, limpieza, restaurante, servicios. Puede tener SSN, ITIN, o estar en proceso. Trabaja duro, no tiene tiempo, desconfía de quien no lo entiende. Quiere sentirse tratado con respeto y confianza — no como un número más.

### Lo que el cliente siente cuando llega
- "¿Me van a pedir papeles que no tengo?"
- "¿Me van a cobrar más de lo que vale?"
- "¿Son reales o son como los notarios que no saben nada?"
- "¿Puedo confiar en alguien que no conozco?"

### Lo que debe sentir al salir
**"Estas personas saben lo que hacen y me pueden ayudar."**

---

## 02 · SISTEMA DE COLOR

### Decisión estratégica
El negro como color dominante transmite tecnología y exclusividad — no confianza profesional financiera. El cliente latino que busca ayuda con sus taxes necesita sentir **claridad, calidez y orden**. Por eso cambiamos la jerarquía.

### Paleta oficial

| Nombre | Hex | Rol | % |
|---|---|---|---|
| **Soft Cream** | `#FAF6ED` | Dominante · Fondos principales | 65% |
| **Onyx Black** | `#0A0A0A` | Secciones de impacto · Hero · Footer | 20% |
| **Signal Gold** | `#F5C518` | Acentos · CTAs · Precios · Énfasis | 12% |
| **Deep Gold** | `#B8860B` | Hover states · Variante oscura del gold | 3% |

### Variables CSS
```css
:root {
  --cream:      #FAF6ED;
  --black:      #0A0A0A;
  --gold:       #F5C518;
  --gold-deep:  #B8860B;
  --grey-soft:  #8a8278;
  --line-cream: #e8e0d0;
  --line-dark:  rgba(245,197,24,0.15);
  --white:      #ffffff;
}
```

### Sistema de secciones — alternancia estratégica
```
NAV         → Cream bg al inicio · Negro bg al scroll (glassmorphism)
HERO        → Negro · máximo impacto · única sección completamente oscura
CONFIANZA   → Cream · calidez · primera impresión post-hero
CATEGORÍAS  → Cream · accesible · no intimidante
PROCESO     → Negro · peso · autoridad · contraste
BOOKKEEPING → Cream · invitador · accesible
FAQ         → Cream · limpio · sin fricciones
CONTACTO    → Negro · CTA final · urgencia elegante
FOOTER      → Negro · cierre profesional
```

**Regla de oro:** El negro aparece con propósito — no como fondo de todo. Cuando aparece, impacta. Cuando el cream domina, genera confianza.

### Colores sobre cream
- Texto principal: `#0A0A0A`
- Texto secundario: `#8a8278`
- Acentos: `#F5C518` o `#B8860B`
- Bordes: `#e8e0d0`
- Cards: `#ffffff` con sombra muy sutil

### Colores sobre negro
- Texto principal: `#FAF6ED`
- Texto secundario: `rgba(250,246,237,0.65)`
- Acentos: `#F5C518`
- Bordes sutiles: `rgba(245,197,24,0.15)`

---

## 03 · TIPOGRAFÍA

### Stack oficial
| Fuente | Rol | Uso | Google Fonts |
|---|---|---|---|
| **Bebas Neue** | Display / Headlines | Titulares grandes, números, CTAs principales | ✅ |
| **DM Serif Display** | Serif editorial | Frases de impacto, énfasis emocional en headlines | ✅ |
| **Manrope** | Body / UI | Todo el texto de párrafo, labels, botones | ✅ |
| **JetBrains Mono** | Técnica / Datos | Precios, etiquetas de categoría, metadata | ✅ |

### Jerarquía tipográfica
```
H1 Hero:      Bebas Neue · clamp(3.5rem, 8vw, 6.5rem) · uppercase · leading 0.95
              Mix: parte en negro/cream + parte key en DM Serif italic gold

H2 Sección:   Bebas Neue · clamp(2rem, 4vw, 3.5rem) · uppercase
              Mix: primera palabra negro + segunda DM Serif italic gold

H3 Sub:       DM Serif Display italic · clamp(1.1rem, 2vw, 1.5rem)

Body:         Manrope 300-400 · 0.95rem · leading 1.7

Labels:       JetBrains Mono 500 · 0.6rem · tracking 0.25em · uppercase

Precios:      Bebas Neue large · gold · "$" en Manrope pequeño

CTAs:         Manrope 700 · 0.85rem · tracking 0.06em · uppercase
```

### Combinaciones de headline aprobadas
- `"SERVICIOS"` Bebas Negro + `"Puntuales"` DM Serif italic gold
- `"TUS TAXES Y TU NEGOCIO,"` Bebas cream + `"en las mejores manos."` DM Serif italic gold
- `"CREDENCIALES"` Bebas cream + `"Reales."` DM Serif italic gold

---

## 04 · IDENTIDAD GRÁFICA

### Logo
- **Nombre:** MaxTax360° (símbolo de grado siempre presente)
- **Razón social:** Max Tax 360 LLC
- **Tagline:** Tax & Business Services
- **Estructura:** "Max" negro/cream · "Tax" gold · "360°" negro/cream · "°" gold

**Nota:** Logo definitivo pendiente de crear en Claude Design.
Por ahora usar tipografía Bebas Neue con la combinación de colores.

### Iconografía
- Íconos SVG lineales — stroke 1.5px monocromo
- Color: gold sobre negro · negro/deep-gold sobre cream
- Sin emojis del sistema operativo como íconos de sección
- Sin ilustraciones complejas
- Sin stock icons genéricos
- Preferir numeración tipográfica cuando sea posible

---

## 05 · MAX EL ZORRO

### Uso estratégico — Secundario, no protagonista
MAX es un diferenciador de marca único en el nicho. Nadie más en tax services latinos tiene mascota. Pero MAX apoya — no lidera.

**MAX aparece:**
- Hero: esquina inferior derecha · máximo 160px · CSS mask que lo disuelve en el fondo · speech bubble "Te explico."
- FAQ: al lado del título · máximo 100px · speech bubble "Vamos por partes."
- Contacto: señalando el formulario · máximo 100px · speech bubble "Escríbenos hoy."

**MAX NO aparece:**
- Sección de categorías/servicios
- Sección de bookkeeping
- Proceso
- Credenciales

### Implementación CSS para MAX en hero
```css
.mascot-img {
  height: clamp(140px, 18vh, 160px);
  width: auto;
  position: absolute;
  bottom: 0;
  right: 5%;
  background: transparent;
  -webkit-mask-image: linear-gradient(
    to top,
    transparent 0%,
    rgba(0,0,0,0.3) 20%,
    rgba(0,0,0,0.7) 40%,
    black 60%
  );
  mask-image: linear-gradient(
    to top,
    transparent 0%,
    rgba(0,0,0,0.3) 20%,
    rgba(0,0,0,0.7) 40%,
    black 60%
  );
  filter: drop-shadow(0 0 20px rgba(245,197,24,0.2));
  animation: float 4s ease-in-out infinite alternate;
}

@keyframes float {
  from { transform: translateY(0px); }
  to { transform: translateY(-8px); }
}
```

### Speech bubbles de MAX
```css
.speech-bubble {
  background: #0A0A0A;
  border: 1px solid rgba(245,197,24,0.4);
  border-radius: 12px 12px 12px 2px;
  padding: 6px 12px;
  font-family: 'Manrope', sans-serif;
  font-style: italic;
  font-size: 0.8rem;
  color: #FAF6ED;
  white-space: nowrap;
  position: absolute;
  top: -35px;
  left: 50%;
  transform: translateX(-50%);
}
```

---

## 06 · COMPONENTES VISUALES

### Cards de categoría (cream section)
```
Fondo:        #ffffff con sombra muy sutil
Borde:        1px solid #e8e0d0 · hover: 1.5px solid #F5C518
Radius:       12px (bordes redondeados — estilo Uber)
Padding:      2rem
Header:       Número JetBrains Mono gold + ícono SVG + nombre categoría
Precio:       "Desde $X" Bebas Neue gold grande / "Consulta personalizada" italic
CTA:          Botón gold · texto negro bold · border-radius 6px
Hover:        Lift sutil (translateY -3px) + sombra gold 15% opacidad
```

### Cards de bookkeeping expandibles (Stripe-style)
```
Estado cerrado:
  Fondo: #ffffff · borde cream · 12px radius
  Visible: Nombre plan · Precio /mes · "Ver todo lo que incluye ↓"
  
Estado abierto (click):
  Altura: auto (transición smooth max-height)
  Aparece: Lista de beneficios con checkmarks gold
  Aparece: CTA "Empezar ahora" gold button
  
Plan destacado (Business):
  Borde: 2px solid #F5C518
  Badge: "MÁS POPULAR" JetBrains Mono · bg gold · texto negro
```

### Sección de proceso (negro)
```
3 pasos en línea horizontal
Conector: línea gold (1px) entre círculos numerados
Círculo: 48px · borde gold · número Bebas Neue gold
Título: Manrope 600 cream
Descripción: Manrope 300 cream 70% opacidad
```

### Botones
```
Primario:   bg gold · texto negro · Manrope 700 · padding 0.9rem 1.8rem
            border-radius: 6px · hover: bg deep-gold
            
Secundario: borde 1.5px negro (en cream) / cream (en negro)
            texto negro/cream · hover: bg gold · texto negro

WhatsApp:   bg #25D366 · texto blanco · ícono WA SVG
            (solo para CTAs de WhatsApp)
            
Outline:    borde gold · texto gold · hover: bg gold · texto negro
```

### Franja de confianza (cream section)
```
4 pills horizontales con ícono SVG pequeño gold + texto:
✓ Atención en español e inglés
✓ Respuesta rápida por WhatsApp
✓ Sin importar tu situación migratoria
✓ Servicio claro y paso a paso

Pills: borde 1px #e8e0d0 · padding 0.6rem 1.2rem · border-radius 99px
       fondo blanco · texto Manrope 400 negro · ícono gold
```

---

## 07 · ANIMACIONES

### Filosofía
Sutiles, con propósito. Nunca decorativas. Cada animación debe comunicar algo — no solo moverse.

### Animaciones aprobadas
```
Scroll reveal:    opacity 0→1 + translateY 24px→0
                  duration: 0.6s · easing: ease-out
                  Activar: Intersection Observer threshold 0.15

Word stagger:     Palabras del H1 aparecen una por una
                  Delay: 0.08s por palabra

Card hover:       translateY -3px + box-shadow gold 15% opacity
                  duration: 0.2s · ease-out

MAX float:        translateY 0 → -8px · 4s · ease-in-out · infinite alternate

FAQ accordion:    max-height transition · 0.35s ease-in-out

Bookkeeping expand: max-height + opacity · 0.4s ease-out

Nav scroll:       backdrop-filter blur(20px) activa al scroll > 50px

Hero scroll anim: Elementos del hero se revelan con parallax sutil
                  al hacer scroll (speed: 0.3)

Counter:          Números en stats cuentan de 0 → valor final
                  Al entrar viewport · duration: 1.5s
```

### NO hacer
- Animaciones > 0.8s (se sienten lentas)
- Bounce effects (infantilizan)
- Rotaciones sin propósito
- Parpadeos o flashes
- Gradientes animados agresivos
- Parallax que cause mareo

---

## 08 · MERCURY-STYLE HERO ANIMATION

### La animación del scroll (inspiración Mercury.com)
El hero tiene una animación de "product reveal" al hacer scroll. Para MaxTax360° (sin producto digital), usamos un documento oficial animado.

### Implementación sugerida
```
Capa 1 (estática): Headline + CTAs (visible desde el inicio)

Capa 2 (animada con scroll): 
  Un "documento flotante" glassmorphism que emerge al hacer scroll:
  - Aparenta ser un LLC Approval Letter del Estado de Florida
  - Campos que se "completan" con efecto typewriter al entrar
  - Sello/stamp "APPROVED" en gold que aparece con fade + scale
  - Posición: lado derecho del hero, ligeramente inclinado (-3deg)
  - Fondo: rgba(255,255,255,0.08) backdrop-filter blur(10px)
  - Borde: 1px solid rgba(245,197,24,0.3)

Parallax:
  background-attachment: el fondo del hero hace parallax sutil
  Los elementos del hero se mueven a diferentes velocidades al scroll
```

---

## 09 · MOBILE FIRST

### Breakpoints
```
Mobile:   < 768px
Tablet:   768px – 1024px
Desktop:  > 1024px
```

### Comportamiento mobile crítico
```
NAV:          Hamburger (3 líneas → X) · drawer full-width desde arriba
              Links apilados · CTA WhatsApp al final del drawer

HERO:         MAX desaparece completamente en mobile
              Copy apilado full-width · CTAs stack vertical

CONFIANZA:    Pills en 2 columnas en mobile

CATEGORÍAS:   1 card por fila · full-width

PROCESO:      Stack vertical (no horizontal) · línea vertical gold

BOOKKEEPING:  1 card por fila · featured card primero

WhatsApp FAB: 56px mínimo (touch target) · siempre visible
```

---

## 10 · LO QUE NUNCA DEBE APARECER

### Términos prohibidos legalmente
- CPA / Certified Public Accountant
- Contador Público Certificado
- Auditoría / Audit services
- Asesoría legal
- Garantía de resultados
- Representación ilimitada ante el IRS

### Elementos de diseño prohibidos
- Emojis del SO como íconos de sección
- Testimoniales con nombres y fotos inventadas
- Gradientes fuertes o brillos excesivos
- Efectos de confetti, partículas, o glitch
- Texto blanco sobre cream (ilegible)
- Gold como fondo de sección entera (pierde impacto)
- Más de 3 fuentes en una misma sección

### Comportamientos prohibidos
- Precios ocultos (siempre visibles o "Desde $X")
- Formularios con más de 4 campos
- Pop-ups en el primer scroll
- Auto-play de audio o video

---

*Fin · BRAND.md v2.0 · MaxTax360° · Mayo 2026*
*Usar junto con COPY.md y CLAUDE.md*
