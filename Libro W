<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
  @import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Cinzel+Decorative:wght@400;700&family=Cinzel:wght@400;600&family=IM+Fell+English:ital@0;1&display=swap');

  :root {
    --sepia: #704214;
    --sepia-light: #a0622a;
    --gold: #c9a84c;
    --gold-light: #e8d5a0;
    --gold-pale: #f5edd8;
    --cream: #f9f3e8;
    --ivory: #fdf8f0;
    --burgundy: #6b1a2a;
    --burgundy-dark: #4a0f1c;
    --ink: #2a1a0e;
    --ink-soft: #3d2b1a;
  }

  * { margin:0; padding:0; box-sizing:border-box; }

  body {
    background: #1a0e07;
    display:flex; flex-direction:column;
    align-items:center; justify-content:center;
    min-height:100vh;
    font-family:'Cormorant Garamond',serif;
    overflow-x:hidden;
  }

  .book-wrapper { position:relative; width:100%; max-width:680px; }

  .page {
    display:none; width:100%; min-height:540px;
    background:var(--ivory); position:relative; overflow:hidden;
    box-shadow:0 20px 80px rgba(0,0,0,0.7), inset 0 0 40px rgba(160,98,42,0.1);
    animation:pageReveal 0.8s ease forwards;
  }
  .page.active { display:block; }

  @keyframes pageReveal {
    from { opacity:0; transform:rotateY(-8deg) scale(0.97); }
    to   { opacity:1; transform:rotateY(0deg) scale(1); }
  }

  .page::before {
    content:''; position:absolute; inset:0;
    background:
      radial-gradient(ellipse at 30% 20%, rgba(160,98,42,0.06) 0%, transparent 60%),
      radial-gradient(ellipse at 70% 80%, rgba(107,26,42,0.05) 0%, transparent 50%);
    pointer-events:none; z-index:1;
  }

  .border-outer { position:absolute; inset:10px; border:2px solid var(--gold); pointer-events:none; z-index:5; }
  .border-inner { position:absolute; inset:16px; border:1px solid var(--gold-light); pointer-events:none; z-index:5; }

  .corner { position:absolute; width:28px; height:28px; z-index:6; pointer-events:none; }
  .corner svg { width:100%; height:100%; }
  .corner.tl { top:6px; left:6px; }
  .corner.tr { top:6px; right:6px; transform:scaleX(-1); }
  .corner.bl { bottom:6px; left:6px; transform:scaleY(-1); }
  .corner.br { bottom:6px; right:6px; transform:scale(-1); }

  .page-content {
    position:relative; z-index:3;
    padding:48px 62px 44px;
    min-height:540px;
    display:flex; flex-direction:column;
    align-items:center; justify-content:center;
  }

  .title-main {
    font-family:'Cinzel Decorative',serif;
    font-size:clamp(15px,3.2vw,24px);
    color:var(--burgundy); text-align:center;
    letter-spacing:0.07em; line-height:1.35;
    text-shadow:1px 1px 3px rgba(107,26,42,0.2);
  }
  .title-sub {
    font-family:'Cinzel',serif;
    font-size:clamp(9px,1.8vw,12px);
    color:var(--sepia); text-align:center;
    letter-spacing:0.28em; text-transform:uppercase; margin-top:8px;
  }
  .title-italic {
    font-family:'IM Fell English',serif; font-style:italic;
    font-size:clamp(12px,2.3vw,16px);
    color:var(--sepia-light); text-align:center; margin-top:6px;
  }
  .body-text {
    font-family:'IM Fell English',serif;
    font-size:clamp(12px,2.1vw,15px);
    color:var(--ink-soft); line-height:1.95;
    text-align:justify; width:100%; max-width:520px;
  }
  .body-text p { margin-bottom:13px; }
  .body-text em { color:var(--burgundy); font-style:italic; }
  .drop-cap::first-letter {
    font-family:'Cinzel Decorative',serif;
    font-size:3.3em; float:left;
    line-height:0.75; margin-right:6px; margin-top:4px;
    color:var(--burgundy);
    text-shadow:2px 2px 4px rgba(107,26,42,0.25);
  }
  .page-number {
    font-family:'Cinzel',serif; font-size:10px;
    color:var(--sepia-light); letter-spacing:0.3em;
    text-align:center; position:absolute;
    bottom:26px; left:50%; transform:translateX(-50%); z-index:6;
  }
  .section-rule {
    width:160px; height:1px;
    background:linear-gradient(90deg,transparent,var(--gold),transparent);
    margin:13px auto;
  }
  .gold-ornament {
    color:var(--gold); font-size:20px;
    text-align:center; letter-spacing:8px;
    margin:6px 0; opacity:0.85;
  }
  .quote-block {
    border-left:2px solid var(--gold);
    padding-left:16px; margin:14px 0;
    font-style:italic; color:var(--burgundy);
  }

  /* PAGE TINTS */
  .page-1  { background:linear-gradient(160deg,#fdf5e6,#f8edd5); }
  .page-2  { background:linear-gradient(145deg,#fdf8f0,#f5ead8); }
  .page-3  { background:linear-gradient(160deg,#fdf6e8,#f6eddb); }
  .page-4  { background:linear-gradient(150deg,#fdf5e5,#f7ecda); }
  .page-5  { background:linear-gradient(155deg,#fdf4e4,#f8ecd8); }
  .page-6  { background:linear-gradient(145deg,#fdf3e5,#f5e8d5); }
  .page-7  { background:linear-gradient(160deg,#fdf2e4,#f5e7d2); }
  .page-8  { background:linear-gradient(140deg,#1e0e16,#2d1020,#1a0c10); }
  .page-8 .body-text  { color:var(--gold-pale); }
  .page-8 .title-main { color:var(--gold); }
  .page-8 .title-sub  { color:var(--gold-light); }
  .page-8 .title-italic { color:var(--gold-light); }
  .page-8 .border-outer { border-color:var(--burgundy); }
  .page-8 .border-inner { border-color:rgba(107,26,42,0.5); }
  .page-8 .page-number { color:var(--gold-light); }
  .page-9  { background:linear-gradient(155deg,#4a0f1c,#6b1a2a,#3d0c16); }
  .page-9 .body-text  { color:var(--gold-pale); }
  .page-9 .title-main { color:var(--gold); }
  .page-9 .title-italic { color:var(--gold-light); }
  .page-9 .page-number { color:rgba(201,168,76,0.6); }
  .page-9 .border-outer { border-color:var(--gold); }
  .page-9 .border-inner { border-color:rgba(201,168,76,0.4); }
  .page-10 { background:linear-gradient(160deg,#fdf8f0,#f5ebd5); }

  /* SVG FLORALS */
  .floral-top    { position:absolute; top:22px;  left:50%; transform:translateX(-50%); z-index:4; }
  .floral-center { margin:12px auto; display:block; }

  /* NAV */
  .nav-bar {
    display:flex; align-items:center; justify-content:space-between;
    width:100%; max-width:680px; padding:14px 10px;
    position:relative; z-index:10;
  }
  .nav-btn {
    font-family:'Cinzel',serif; font-size:11px;
    color:var(--gold-light); background:none;
    border:1px solid rgba(201,168,76,0.4);
    padding:7px 20px; cursor:pointer;
    letter-spacing:0.2em; transition:all 0.3s; text-transform:uppercase;
  }
  .nav-btn:hover { background:rgba(201,168,76,0.15); color:var(--gold); border-color:var(--gold); }
  .nav-btn:disabled { opacity:0.25; cursor:default; }
  .progress-dots { display:flex; gap:7px; }
  .dot {
    width:6px; height:6px; border-radius:50%;
    border:1px solid var(--gold-light); background:transparent; transition:background 0.3s;
  }
  .dot.filled { background:var(--gold); border-color:var(--gold); }

  /* PUZZLE */
  .puzzle-container {
    background:rgba(0,0,0,0.28); border:1px solid rgba(201,168,76,0.4);
    padding:18px 22px; width:100%; max-width:520px; margin:10px 0;
  }
  .puzzle-clues { list-style:none; margin:10px 0; }
  .puzzle-clues li {
    font-family:'IM Fell English',serif; font-style:italic;
    color:var(--gold-pale); font-size:12.5px; line-height:1.85;
    padding-left:16px; position:relative; margin-bottom:4px;
  }
  .puzzle-clues li::before { content:'✦'; position:absolute; left:0; color:var(--gold); font-size:9px; top:4px; }
  .puzzle-input-row { display:flex; gap:10px; margin-top:14px; align-items:center; flex-wrap:wrap; }
  .puzzle-input {
    flex:1; min-width:140px;
    background:rgba(0,0,0,0.3); border:none;
    border-bottom:1px solid var(--gold-light);
    color:var(--gold-pale); font-family:'Cinzel',serif;
    font-size:13px; letter-spacing:0.2em;
    padding:8px 4px; text-transform:uppercase; outline:none; text-align:center;
  }
  .puzzle-input::placeholder { color:rgba(201,168,76,0.4); }
  .puzzle-submit {
    font-family:'Cinzel',serif; font-size:11px;
    color:var(--burgundy-dark); background:var(--gold);
    border:none; padding:8px 18px; cursor:pointer;
    letter-spacing:0.15em; transition:all 0.3s; text-transform:uppercase;
  }
  .puzzle-submit:hover { background:var(--gold-light); }
  .puzzle-feedback {
    font-family:'IM Fell English',serif; font-style:italic;
    font-size:12px; margin-top:10px; text-align:center; min-height:18px;
  }
  .puzzle-feedback.error   { color:#e88; }
  .puzzle-feedback.success { color:var(--gold-light); }

  /* LOCKED */
  .locked-overlay {
    position:absolute; inset:0;
    background:rgba(74,15,28,0.96);
    display:flex; flex-direction:column;
    align-items:center; justify-content:center;
    z-index:20; transition:opacity 0.8s;
  }
  .lock-icon  { font-size:36px; margin-bottom:14px; color:var(--gold); }
  .lock-text  { font-family:'Cinzel',serif; color:var(--gold-light); font-size:12px; letter-spacing:0.25em; text-transform:uppercase; text-align:center; line-height:2; }

  /* RESPONSE */
  .response-area { margin-top:16px; display:flex; gap:16px; justify-content:center; flex-wrap:wrap; }
  .response-btn {
    font-family:'Cinzel',serif; font-size:11px;
    padding:10px 26px; border:1px solid var(--gold);
    color:var(--gold-pale); background:transparent;
    cursor:pointer; letter-spacing:0.18em; transition:all 0.4s; text-transform:uppercase;
  }
  .response-btn:hover { background:rgba(201,168,76,0.2); }
  .response-btn.yes   { background:rgba(201,168,76,0.15); }
  .response-btn.yes:hover { background:rgba(201,168,76,0.35); }
  .response-message {
    font-family:'IM Fell English',serif; font-style:italic;
    color:var(--gold-light); font-size:14px;
    text-align:center; margin-top:14px; min-height:24px; line-height:1.8;
  }

  /* W initial highlight */
  .w-initial {
    font-family:'Cinzel Decorative',serif;
    color:var(--burgundy); font-size:1.15em;
    text-shadow:1px 1px 2px rgba(107,26,42,0.3);
  }
</style>
</head>
<body>

<svg id="corner-svg-def" style="display:none">
  <symbol id="co" viewBox="0 0 28 28">
    <path d="M2,2 Q14,2 26,14" stroke="#c9a84c" stroke-width="1.2" fill="none"/>
    <path d="M2,2 Q2,14 14,26" stroke="#c9a84c" stroke-width="1.2" fill="none"/>
    <circle cx="3" cy="3" r="2" fill="#c9a84c" opacity="0.8"/>
    <circle cx="14" cy="14" r="1.2" fill="#c9a84c" opacity="0.5"/>
  </symbol>
</svg>

<div class="book-wrapper">

<!-- ══════════════════ PÁGINA 1 · PORTADA ══════════════════ -->
<div class="page page-1 active" id="p1">
  <div class="border-outer"></div><div class="border-inner"></div>
  <div class="corner tl"><svg><use href="#co"/></svg></div>
  <div class="corner tr"><svg><use href="#co"/></svg></div>
  <div class="corner bl"><svg><use href="#co"/></svg></div>
  <div class="corner br"><svg><use href="#co"/></svg></div>

  <svg class="floral-top" width="240" height="38" viewBox="0 0 240 38">
    <g opacity="0.5" fill="none" stroke="#c9a84c" stroke-width="0.9">
      <path d="M120,19 Q100,9 80,19 Q100,29 120,19Z" fill="rgba(201,168,76,0.13)"/>
      <path d="M120,19 Q140,9 160,19 Q140,29 120,19Z" fill="rgba(201,168,76,0.13)"/>
      <path d="M80,19 Q60,11 40,19 Q60,27 80,19Z"   fill="rgba(201,168,76,0.08)"/>
      <path d="M160,19 Q180,11 200,19 Q180,27 160,19Z" fill="rgba(201,168,76,0.08)"/>
      <circle cx="120" cy="19" r="3" fill="rgba(107,26,42,0.5)" stroke="none"/>
      <line x1="12" y1="19" x2="38" y2="19" stroke-width="0.6"/>
      <line x1="202" y1="19" x2="228" y2="19" stroke-width="0.6"/>
      <path d="M22,15 Q27,11 32,15 Q27,19 22,15Z" fill="rgba(107,26,42,0.3)" stroke="none"/>
      <path d="M208,15 Q213,11 218,15 Q213,19 208,15Z" fill="rgba(107,26,42,0.3)" stroke="none"/>
    </g>
  </svg>

  <div class="page-content">
    <div class="gold-ornament">✦ ✦ ✦</div>
    <div class="section-rule"></div>
    <div class="title-main">El Jardín<br>de los Días Contados</div>
    <div class="section-rule"></div>
    <div class="title-italic">Una colección de observaciones<br>sobre aquella que hizo del tiempo<br>un lugar más habitable</div>
    <div class="section-rule"></div>
    <div class="gold-ornament" style="font-size:13px; letter-spacing:14px;">— ✾ —</div>

    <!-- Central rose -->
    <svg class="floral-center" width="128" height="128" viewBox="0 0 128 128">
      <g transform="translate(64,64)">
        <g opacity="0.38" fill="none" stroke="#c9a84c" stroke-width="0.8">
          <ellipse rx="30" ry="11" transform="rotate(0)"   fill="rgba(201,168,76,0.12)"/>
          <ellipse rx="30" ry="11" transform="rotate(45)"  fill="rgba(201,168,76,0.12)"/>
          <ellipse rx="30" ry="11" transform="rotate(90)"  fill="rgba(201,168,76,0.12)"/>
          <ellipse rx="30" ry="11" transform="rotate(135)" fill="rgba(201,168,76,0.12)"/>
        </g>
        <g opacity="0.6" fill="none" stroke="#6b1a2a" stroke-width="0.7">
          <ellipse rx="19" ry="7" transform="rotate(22)"  fill="rgba(107,26,42,0.15)"/>
          <ellipse rx="19" ry="7" transform="rotate(67)"  fill="rgba(107,26,42,0.15)"/>
          <ellipse rx="19" ry="7" transform="rotate(112)" fill="rgba(107,26,42,0.15)"/>
          <ellipse rx="19" ry="7" transform="rotate(157)" fill="rgba(107,26,42,0.15)"/>
        </g>
        <circle r="9"  fill="rgba(107,26,42,0.5)" stroke="#c9a84c" stroke-width="1"/>
        <circle r="4"  fill="#c9a84c" opacity="0.7"/>
        <path d="M0,-42 Q9,-34 0,-25 Q-9,-34 0,-42Z" fill="rgba(80,120,60,0.25)" stroke="rgba(80,120,60,0.4)" stroke-width="0.6"/>
        <path d="M0,42  Q9,34 0,25 Q-9,34 0,42Z"   fill="rgba(80,120,60,0.25)" stroke="rgba(80,120,60,0.4)" stroke-width="0.6"/>
        <path d="M-42,0 Q-34,-9 -25,0 Q-34,9 -42,0Z" fill="rgba(80,120,60,0.25)" stroke="rgba(80,120,60,0.4)" stroke-width="0.6"/>
        <path d="M42,0  Q34,-9 25,0 Q34,9 42,0Z"   fill="rgba(80,120,60,0.25)" stroke="rgba(80,120,60,0.4)" stroke-width="0.6"/>
      </g>
    </svg>

    <div class="section-rule"></div>
    <div class="title-sub" style="font-size:9px;">Anno Domini · MDCCCLXXXVII</div>
  </div>
  <div class="page-number">— I —</div>
</div>

<!-- ══════════════════ PÁGINA 2 · INTRODUCCIÓN ══════════════════ -->
<div class="page page-2" id="p2">
  <div class="border-outer"></div><div class="border-inner"></div>
  <div class="corner tl"><svg><use href="#co"/></svg></div><div class="corner tr"><svg><use href="#co"/></svg></div>
  <div class="corner bl"><svg><use href="#co"/></svg></div><div class="corner br"><svg><use href="#co"/></svg></div>
  <div class="page-content" style="padding-top:44px;">
    <div class="title-main" style="font-size:17px;">Sobre Aquellas<br>que Cambian el Aire</div>
    <div class="section-rule"></div>
    <div class="gold-ornament" style="font-size:13px;">❧</div>
    <div class="section-rule"></div>
    <div class="body-text drop-cap">
      <p>Hay personas que entran a un lugar y no lo alteran: se acomodan en él como el agua en un vaso, adoptando la forma que se les ofrece. Y luego está ella. Ella que no adopta la forma del espacio, sino que el espacio parece reacomodarse alrededor de su presencia, como si el aire mismo recordara la cortesía de cederle paso.</p>
      <p>Comencé a escribir estas páginas sin saber muy bien cómo empezar, porque ella es de esas personas que merecen una primera frase que esté a la altura, y ninguna primera frase lo ha estado. Así que decidí empezar desde la honestidad: este es un libro escrito sobre alguien que hace que escribir bien importe más de lo habitual.</p>
      <p>No sé si estas palabras llegarán en el orden correcto. Lo que sí sé es que cada una de ellas fue elegida porque ella se merece palabras elegidas. No palabras dichas de prisa, no frases tomadas prestadas de otros: palabras propias, con el peso y la textura de lo que es verdadero.</p>
      <div class="quote-block">
        <em>"Existen personas que no se describen: se experimentan. Este libro es el intento —imperfecto, humilde— de documentar esa experiencia."</em>
      </div>
    </div>
  </div>
  <div class="page-number">— II —</div>
</div>

<!-- ══════════════════ PÁGINA 3 · INTELIGENCIA ══════════════════ -->
<div class="page page-3" id="p3">
  <div class="border-outer"></div><div class="border-inner"></div>
  <div class="corner tl"><svg><use href="#co"/></svg></div><div class="corner tr"><svg><use href="#co"/></svg></div>
  <div class="corner bl"><svg><use href="#co"/></svg></div><div class="corner br"><svg><use href="#co"/></svg></div>
  <div class="page-content" style="padding-top:40px;">
    <div class="title-main" style="font-size:17px;">La Inteligencia<br>que Siente lo que Comprende</div>
    <div class="section-rule"></div>
    <div class="body-text drop-cap">
      <p>Ella piensa antes de hablar. No porque desconfíe de sus palabras, sino porque las respeta demasiado como para desperdiciarlas. Hay una pausa característica en ella —breve, casi imperceptible— en la que el pensamiento busca no la respuesta más rápida, sino la más justa. Esa pausa es, en sí misma, una forma de inteligencia.</p>
      <p>Tiene también la capacidad extraña de ver lo que los demás dan por invisible: el detalle que todos pisaron, la contradicción que nadie quiso nombrar, el hilo suelto en el argumento más prolijo. No lo señala con crueldad; lo señala con la naturalidad de quien simplemente no puede mirar sin ver.</p>
      <p>Y luego está su humor. El humor de las personas verdaderamente inteligentes no necesita de víctimas: se construye sobre las ideas, sobre las palabras, sobre la ironía que habita en las cosas cotidianas. Su humor es de esa especie. <em>Hace pensar al mismo tiempo que hace reír</em>, y esa combinación es más rara de lo que el mundo admite.</p>
      <div class="gold-ornament" style="margin-top:6px; font-size:12px;">— ✦ —</div>
      <p style="text-align:center; font-style:italic; color:var(--burgundy); font-size:13.5px;">En su presencia, hasta el silencio tiene algo que decir.</p>
    </div>
  </div>
  <div class="page-number">— III —</div>
</div>

<!-- ══════════════════ PÁGINA 4 · FORTALEZA ══════════════════ -->
<div class="page page-4" id="p4">
  <div class="border-outer"></div><div class="border-inner"></div>
  <div class="corner tl"><svg><use href="#co"/></svg></div><div class="corner tr"><svg><use href="#co"/></svg></div>
  <div class="corner bl"><svg><use href="#co"/></svg></div><div class="corner br"><svg><use href="#co"/></svg></div>
  <div class="page-content" style="padding-top:40px;">
    <div class="title-main" style="font-size:17px;">La Fortaleza<br>que no Hace Ruido</div>
    <div class="section-rule"></div>
    <div class="body-text drop-cap">
      <p>Ella no necesita que nadie la vea siendo fuerte para serlo. Esa es, quizás, la distinción más importante: la diferencia entre quienes exhiben la fortaleza como un escudo y quienes la habitan como una casa. Ella pertenece a los segundos. Atraviesa lo difícil sin proclamarlo, sin convertir la adversidad en escenario.</p>
      <p>He visto cómo sostiene lo que le pesa. No con la rigidez de quien aprieta los dientes, sino con la elasticidad de quien ha aprendido que doblarse no es lo mismo que quebrarse. Hay en ella una dignidad tranquila frente a las cosas complicadas que me ha enseñado más sobre el carácter que cualquier libro sobre el tema.</p>
      <p>Y sin embargo, también sabe ser vulnerable. Eso es lo que completa el cuadro: no una fortaleza ciega, sino una <em>fortaleza que elige cuándo abrirse</em>. Saber cuándo ser invulnerable y cuándo no serlo es, en mi opinión, la forma más sofisticada de valentía.</p>
      <div class="quote-block">
        <em>"Hay quienes se rompen ante la tormenta. Hay quienes la atraviesan sin dejar de ser quienes son. Ella es de los segundos."</em>
      </div>
    </div>
  </div>
  <div class="page-number">— IV —</div>
</div>

<!-- ══════════════════ PÁGINA 5 · SENSIBILIDAD ══════════════════ -->
<div class="page page-5" id="p5">
  <div class="border-outer"></div><div class="border-inner"></div>
  <div class="corner tl"><svg><use href="#co"/></svg></div><div class="corner tr"><svg><use href="#co"/></svg></div>
  <div class="corner bl"><svg><use href="#co"/></svg></div><div class="corner br"><svg><use href="#co"/></svg></div>
  <div class="page-content" style="padding-top:40px;">
    <div class="title-main" style="font-size:17px;">La Manera en que<br>Ella Mira y Escucha</div>
    <div class="section-rule"></div>
    <div class="body-text drop-cap">
      <p>Ella mira con una atención que a veces incomoda un poco, en el mejor sentido posible: hace sentir que lo que uno dice importa de verdad, que no se está hablando al vacío ni hacia un oído distraído. Hay algo en su manera de escuchar que obliga a uno a ser más honesto de lo que tenía planeado.</p>
      <p>Cambia el tono de voz cuando algo le interesa genuinamente: se vuelve más quieta, más cercana, como si quisiera reducir la distancia entre ella y la idea que está recibiendo. Es un gesto pequeño y completamente involuntario, y precisamente por eso revela tanto.</p>
      <p>Noto también cómo le afectan las cosas que le afectan: no lo oculta por orgullo, pero tampoco lo exhibe por costumbre. Cuando algo la mueve, se nota en los ojos antes que en las palabras. Y cuando algo le parece absurdo o injusto, hay una honestidad en su reacción que resulta, curiosamente, <em>refrescante</em>.</p>
      <div class="gold-ornament" style="margin:8px 0; font-size:12px;">✾ ✾ ✾</div>
      <p style="text-align:center; font-style:italic; color:var(--burgundy); font-size:13.5px;">Ella siente el mundo con una fidelidad poco común.<br>Y eso, sin duda, la hace más real que la mayoría.</p>
    </div>
  </div>
  <div class="page-number">— V —</div>
</div>

<!-- ══════════════════ PÁGINA 6 · INTIMIDAD ══════════════════ -->
<div class="page page-6" id="p6">
  <div class="border-outer"></div><div class="border-inner"></div>
  <div class="corner tl"><svg><use href="#co"/></svg></div><div class="corner tr"><svg><use href="#co"/></svg></div>
  <div class="corner bl"><svg><use href="#co"/></svg></div><div class="corner br"><svg><use href="#co"/></svg></div>
  <div class="page-content" style="padding-top:40px;">
    <div class="title-main" style="font-size:17px;">Lo que Ocurre<br>con su Presencia</div>
    <div class="section-rule"></div>
    <div class="body-text drop-cap">
      <p>Hay algo que sucede cuando ella está cerca que es difícil de articular sin caer en el territorio de lo vago. Intentaré ser preciso: algo en el tiempo cambia. Los minutos junto a ella tienen una densidad distinta, como si contuvieran más de lo que su medida permite. Una conversación de veinte minutos con ella puede dejar más rastro que una tarde entera con cualquier otra persona.</p>
      <p>He notado que pienso diferente después de hablar con ella. No porque me haya corregido ni instruido, sino porque algo en el intercambio activa zonas del pensamiento que de otro modo permanecen en reposo. Hay personas que nos hacen mejores sin proponérselo. Ella es de esas.</p>
      <p>Y está también lo otro, lo que es más difícil de decir: la conciencia física de su presencia. La certeza, cuando ella está en el mismo espacio, de cada centímetro de distancia que nos separa. No es incomodidad; es atención. Es el tipo de atención que el cuerpo presta antes de que la mente haya terminado de formular las preguntas.</p>
      <div class="quote-block">
        <em>"No busco a alguien que llene lo que me falta. Busco a alguien junto a quien lo que ya tengo se vuelva más luminoso."</em>
      </div>
      <p style="text-align:center; font-style:italic; color:var(--burgundy); font-size:13.5px;">Ella es esa persona.</p>
    </div>
  </div>
  <div class="page-number">— VI —</div>
</div>

<!-- ══════════════════ PÁGINA 7 · TRANSICIÓN ══════════════════ -->
<div class="page page-7" id="p7">
  <div class="border-outer"></div><div class="border-inner"></div>
  <div class="corner tl"><svg><use href="#co"/></svg></div><div class="corner tr"><svg><use href="#co"/></svg></div>
  <div class="corner bl"><svg><use href="#co"/></svg></div><div class="corner br"><svg><use href="#co"/></svg></div>
  <div class="page-content" style="padding-top:40px;">
    <div class="title-main" style="font-size:17px;">El Instante<br>en que Todo Fue Claro</div>
    <div class="section-rule"></div>
    <div class="body-text drop-cap">
      <p>Hubo un momento —no podría señalarlo con exactitud, porque las revelaciones importantes rara vez anuncian su llegada— en que todo lo que venía observando sobre ella confluyó en una sola comprensión. No fue dramático. Fue, más bien, como cuando el ojo finalmente enfoca algo que ha estado frente a él todo el tiempo.</p>
      <p>Quiero estar cerca de ella. No de la versión que presenta al mundo —aunque esa ya me parece extraordinaria en sus propios términos— sino de las capas que están debajo: los miedos que no dice en voz alta, los sueños que guarda con más celo que los logros, las contradicciones que la hacen plenamente humana y, por lo tanto, plenamente real.</p>
      <p>Quiero que las conversaciones que tenemos sigan siendo de las que dejan rastro. Quiero seguir notando el gesto con que escucha, el tono que adopta cuando algo genuinamente le interesa, la risa que llega antes de que ella misma lo espere. Quiero que el tiempo junto a ella continúe siendo ese tiempo de densidad distinta.</p>
      <div class="section-rule" style="margin:14px auto;"></div>
      <p style="text-align:center; font-style:italic; color:var(--burgundy); font-size:13.5px; line-height:1.8;">Pero para continuar, hay una puerta.<br>Y tú tienes la llave.<br><em style="font-size:12px;">Está escondida en estas páginas.</em></p>
    </div>
  </div>
  <div class="page-number">— VII —</div>
</div>

<!-- ══════════════════ PÁGINA 8 · ENIGMA ══════════════════ -->
<div class="page page-8" id="p8">
  <div class="border-outer"></div><div class="border-inner"></div>
  <div class="corner tl"><svg style="opacity:0.6"><use href="#co"/></svg></div>
  <div class="corner tr"><svg style="opacity:0.6"><use href="#co"/></svg></div>
  <div class="corner bl"><svg style="opacity:0.6"><use href="#co"/></svg></div>
  <div class="corner br"><svg style="opacity:0.6"><use href="#co"/></svg></div>
  <div class="page-content" style="padding:38px 48px;">
    <div class="title-main" style="font-size:16px;">El Enigma del Jardín</div>
    <div class="title-italic" style="color:rgba(232,213,160,0.75); margin-top:5px; font-size:13px;">Cinco páginas guardan cinco secretos.<br>Únelos y la puerta se abrirá.</div>
    <div class="section-rule" style="background:linear-gradient(90deg,transparent,rgba(201,168,76,0.5),transparent);"></div>

    <div class="puzzle-container">
      <div style="font-family:'IM Fell English',serif; color:var(--gold-pale); font-style:italic; font-size:12.5px; line-height:1.85; margin-bottom:12px;">
        Cada pista es un paso más para descubrir la palabra que este libro lleva escrita desde la primera línea. Descubre las cinco pistas y la palabra se revelará sola, esa sera la respuesta a todo este libro.
      </div>
      <ul class="puzzle-clues">
        <li><span style="color:var(--gold); font-style:normal; font-size:11px; letter-spacing:0.1em;">Pista 1 ·</span> "Soy el único sentimiento capaz de habitar en el palacio más lujoso y en la choza más humilde al mismo tiempo. No me puedes comprar con oro, pero valgo más que todo el tesoro del mundo."</li>
        <li><span style="color:var(--gold); font-style:normal; font-size:11px; letter-spacing:0.1em;">Pista 2 ·</span> "Dicen que soy ciego, pero soy el único que logra ver la belleza donde los demás ven defectos. No tengo pies, pero soy el motor que hace que el mundo siga girando."</li>
        <li><span style="color:var(--gold); font-style:normal; font-size:11px; letter-spacing:0.1em;">Pista 3 ·</span> "Soy aquello que te hace poner la felicidad de otra persona por encima de la tuya propia, sin sentir que estás perdiendo nada, sino ganándolo todo."</li>
        <li><span style="color:var(--gold); font-style:normal; font-size:11px; letter-spacing:0.1em;">Pista 4 ·</span> "Soy la medicina para la soledad y el veneno más dulce cuando me pierdes. Puedo ser un refugio de paz o una guerra de nervios, pero nadie quiere vivir sin haberme conocido."</li>
        <li><span style="color:var(--gold); font-style:normal; font-size:11px; letter-spacing:0.1em;">Pista 5 ·</span> "Tengo cuatro letras: empiezo con la primera del abecedario, guardo un círculo de oro en mi centro y termino con la fuerza de un rayo. Si me lees al revés, verás que soy lo que se siente por la Roma antigua."</li> 
      </ul>
      <div style="font-family:'Cinzel',serif; color:var(--gold); font-size:9.5px; letter-spacing:0.3em; text-align:center; margin-top:14px; text-transform:uppercase;">La palabra oculta</div>
      <div style="font-family:'IM Fell English',serif; color:rgba(201,168,76,0.55); font-size:11px; font-style:italic; text-align:center; margin-bottom:10px;">(es lo que este libro confiesa sin haber usado esa palabra todavía)</div>
      <div class="puzzle-input-row">
        <input class="puzzle-input" id="puzzle-ans" placeholder="Escribe aquí…" maxlength="12">
        <button class="puzzle-submit" onclick="checkPuzzle()">Desbloquear</button>
      </div>
      <div class="puzzle-feedback" id="puzzle-fb"></div>
    </div>
  </div>
  <div class="page-number" style="color:rgba(201,168,76,0.5);">— VIII —</div>
</div>

<!-- ══════════════════ PÁGINA 9 · REVELACIÓN ══════════════════ -->
<div class="page page-9" id="p9">
  <div class="border-outer"></div><div class="border-inner"></div>
  <div class="corner tl"><svg style="opacity:0.7"><use href="#co"/></svg></div>
  <div class="corner tr"><svg style="opacity:0.7"><use href="#co"/></svg></div>
  <div class="corner bl"><svg style="opacity:0.7"><use href="#co"/></svg></div>
  <div class="corner br"><svg style="opacity:0.7"><use href="#co"/></svg></div>

  <div class="locked-overlay" id="lock-overlay">
    <div class="lock-icon">🔒</div>
    <div class="lock-text">Resuelve el enigma<br>para abrir esta página</div>
  </div>

  <div class="page-content" style="padding:40px 54px;">
    <div class="title-main" style="font-size:15px;">Para Ella,<br>que Llegó Hasta Aquí</div>
    <div class="section-rule" style="background:linear-gradient(90deg,transparent,rgba(201,168,76,0.6),transparent);"></div>
    <div class="body-text" style="color:var(--gold-pale);">
      <p style="text-align:center; font-style:italic; font-size:13px; color:rgba(232,213,160,0.75); margin-bottom:16px;">— Con la misma paciencia con que fue escrito —</p>
      <p>Si ella está leyendo esto, fue porque tuvo la curiosidad y la perseverancia que le he visto tener frente a todo aquello que merece atención. Eso me parece, en sí mismo, un buen augurio.</p>
      <p>He escrito ocho páginas intentando decir algo que el lenguaje casi siempre deja a medias. No porque el sentimiento sea impreciso —al contrario, es de una precisión incómoda— sino porque tiene su forma específica, su voz particular, sus gestos inconfundibles. Tiene, en fin, todo lo que la hace ser quien es, Simplemente hermosa.</p>
      <p>Y por eso, después de todo este viaje entre palabras cuidadas y metáforas elegidas, lo que queda es lo más simple: <strong>Quiero seguir eligiéndola</strong>. Quiero que este libro sea el principio de un capítulo que todavía no tiene título, y que escribamos juntos.</p>
      <div class="section-rule" style="margin:14px auto; background:linear-gradient(90deg,transparent,rgba(201,168,76,0.45),transparent);"></div>
      <p style="text-align:center; font-family:'Cinzel Decorative',serif; font-size:clamp(12px,2.3vw,15px); color:var(--gold); line-height:1.85; letter-spacing:0.04em;">¿Querría ella tener un <br>nuevo capítulo en el amor?</p>
      <div class="section-rule" style="margin:14px auto; background:linear-gradient(90deg,transparent,rgba(201,168,76,0.45),transparent);"></div>
    </div>
    <div class="response-area">
      <button class="response-btn yes" onclick="respondYes()">Sí, ella quisiera</button>
      <button class="response-btn" onclick="respondMaybe()">No, ella no esta preparada</button>
    </div>
    <div class="response-message" id="resp-msg"></div>
  </div>
  <div class="page-number" style="color:rgba(201,168,76,0.5);">— IX —</div>
</div>

<!-- ══════════════════ PÁGINA 10 · EPÍLOGO ══════════════════ -->
<div class="page page-10" id="p10">
  <div class="border-outer"></div><div class="border-inner"></div>
  <div class="corner tl"><svg><use href="#co"/></svg></div><div class="corner tr"><svg><use href="#co"/></svg></div>
  <div class="corner bl"><svg><use href="#co"/></svg></div><div class="corner br"><svg><use href="#co"/></svg></div>

  <svg class="floral-top" width="200" height="32" viewBox="0 0 200 32">
    <g opacity="0.45" fill="none" stroke="#c9a84c" stroke-width="0.8">
      <path d="M100,16 Q80,7 60,16 Q80,25 100,16Z" fill="rgba(201,168,76,0.12)"/>
      <path d="M100,16 Q120,7 140,16 Q120,25 100,16Z" fill="rgba(201,168,76,0.12)"/>
      <circle cx="100" cy="16" r="2.5" fill="rgba(107,26,42,0.5)" stroke="none"/>
      <line x1="15" y1="16" x2="45" y2="16" stroke-width="0.5"/>
      <line x1="155" y1="16" x2="185" y2="16" stroke-width="0.5"/>
    </g>
  </svg>

  <div class="page-content">
    <div class="gold-ornament" style="font-size:18px;">❧</div>
    <div class="section-rule"></div>
    <div class="title-main" style="font-size:15px;">Epílogo</div>
    <div class="section-rule"></div>
    <div class="body-text" style="text-align:center;">
      <p style="font-style:italic; color:var(--burgundy); font-size:14.5px; line-height:2.1;">
        "No la buscaba cuando la encontré.<br>
        Y sin embargo, cuando apareció,<br>
        algo en mí la reconoció<br>
        como se reconoce un idioma<br>
        que uno creía no saber<br>
        y resulta que <em>siempre supo</em>."
      </p>
    </div>
    <div class="section-rule"></div>
    <svg width="86" height="86" viewBox="0 0 86 86" style="margin:10px auto; display:block;">
      <g transform="translate(43,43)" opacity="0.65">
        <path d="M0,-28 C7,-19 19,-9 0,6 C-19,-9 -7,-19 0,-28Z" fill="#6b1a2a" stroke="#c9a84c" stroke-width="0.8"/>
        <path d="M0,6 C9,1 21,9 17,22 C13,30 0,34 0,34 C0,34 -13,30 -17,22 C-21,9 -9,1 0,6Z" fill="#6b1a2a" stroke="#c9a84c" stroke-width="0.8"/>
        <circle cx="0" cy="-8" r="2" fill="#c9a84c" opacity="0.8"/>
      </g>
    </svg>
    <div class="section-rule"></div>
    <div class="title-sub" style="font-size:9px; letter-spacing:0.28em; color:var(--sepia-light); opacity:0.65;">Escrito con cuidado · Guardado con paciencia · Entregado con amor</div>
  </div>
  <div class="page-number">— X —</div>
</div>

</div><!-- /book-wrapper -->

<!-- NAV -->
<div class="nav-bar">
  <button class="nav-btn" id="btn-prev" onclick="changePage(-1)" disabled>◂ Anterior</button>
  <div class="progress-dots" id="dots"></div>
  <button class="nav-btn" id="btn-next" onclick="changePage(1)">Siguiente ▸</button>
</div>

<script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>
<script>
const TOTAL = 10;
let current = 1;
let unlocked = false;

// EmailJS config (reemplaza con tus valores reales)
const EMAILJS_PUBLIC_KEY = 'IiL1hYlVVUWyTBjpP';
const EMAILJS_SERVICE_ID = 'service_hrwsj58';
const EMAILJS_TEMPLATE_ID = 'template_24cunm2';

emailjs.init(EMAILJS_PUBLIC_KEY);

// Dots
const dotsEl = document.getElementById('dots');
for(let i=1;i<=TOTAL;i++){
  const d = document.createElement('div');
  d.className='dot'+(i===1?' filled':'');
  d.id='dot'+i;
  dotsEl.appendChild(d);
}

function showPage(n){
  document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));
  const pg = document.getElementById('p'+n);
  if(pg) pg.classList.add('active');
  document.querySelectorAll('.dot').forEach((d,i)=>d.classList.toggle('filled',i+1<=n));
  document.getElementById('btn-prev').disabled=(n===1);
  document.getElementById('btn-next').disabled=(n===TOTAL);
  current=n;
}

function changePage(dir){
  const next=current+dir;
  if(next===9&&!unlocked){ showPage(8); return; }
  if(next>=1&&next<=TOTAL) showPage(next);
}

// PUZZLE — respuesta: ESFEP → no, let's map properly:
// Pág II: "única" (opuesto a ordinaria, 5 letras) → primera letra U
// Pág III: "silencio" → S
// Pág IV: cita termina en "son" → S  … 
// Simplificado: respuesta = AMOR (la confesión del libro)
// Pistas apuntan metafóricamente a AMOR con la pista final
const VALID = ['amor','AMOR','Amor'];

function checkPuzzle(){
  const val=document.getElementById('puzzle-ans').value.trim();
  const fb=document.getElementById('puzzle-fb');
  if(VALID.includes(val)){
    fb.className='puzzle-feedback success';
    fb.textContent='✦ La puerta se abre… ✦';
    unlocked=true;
    setTimeout(()=>{
      showPage(9);
      const ov=document.getElementById('lock-overlay');
      ov.style.opacity='0';
      setTimeout(()=>ov.style.display='none',800);
    },1300);
  } else {
    fb.className='puzzle-feedback error';
    fb.textContent='La llave no encaja aún. Lee más despacio, recuerda que es el sentimiento mas bonito pero al que le tenemos mas miedo…';
  }
}

document.getElementById('puzzle-ans').addEventListener('keydown',e=>{
  if(e.key==='Enter') checkPuzzle();
});

function respondYes(){
  const m=document.getElementById('resp-msg');
  m.style.color='#e8d5a0';
  m.innerHTML='✦ &nbsp; Esa es la mejor respuesta que pudo haber. &nbsp; ✦<br><em style="font-size:11px;">Ahora cierra el libro y ve a vivirlo.</em>';
  sendResponseByEmail('Si, quisiera');
}
function respondMaybe(){
  const m=document.getElementById('resp-msg');
  m.style.color='rgba(232,213,160,0.65)';
  m.innerHTML='<em>Está bien. Este libro seguirá aquí,<br>con la misma paciencia con que fue escrito.</em>';
  sendResponseByEmail('No');
}

function sendResponseByEmail(response){
  emailjs.send(EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_ID, {
    respuesta: response,
    answer: response,
    message: response,
    user_response: response
  }).catch(err => {
    console.error('No se pudo enviar la respuesta por correo:', err);
  });
}

showPage(1);
</script>
</body>
</html>
