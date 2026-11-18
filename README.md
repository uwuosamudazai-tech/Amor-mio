
<!doctype html>
<html lang="es">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="theme-color" content="#eaf2ff">
<title>A little place for you ♡</title>

<style>
:root{
 --sky:#dcecff;
 --sky2:#edf5ff;
 --lav:#e9e1ff;
 --lav2:#f4efff;
 --blue:#7899c7;
 --purple:#927fbd;
 --ink:#5d6288;
 --white:#fff;
}

*{box-sizing:border-box}

body{
 margin:0;
 min-height:100vh;
 padding:22px 14px;
 display:flex;
 justify-content:center;
 font-family:Georgia,serif;
 color:var(--ink);
 background:linear-gradient(145deg,#eaf4ff 0%,#f1edff 55%,#e4edff 100%);
 overflow-x:hidden;
}

main{
 width:min(100%,540px);
 margin:auto;
 position:relative;
 z-index:1;
}

.hearts{
 position:fixed;
 inset:0;
 pointer-events:none;
 overflow:hidden;
 z-index:0;
}

.heart{
 position:absolute;
 bottom:-35px;
 color:#a9b8e8;
 opacity:.45;
 animation:float 13s linear infinite;
}

.heart:nth-child(2n){
 color:#b9a8e8;
 animation-duration:16s;
}

.heart:nth-child(3n){
 animation-duration:19s;
}

@keyframes float{
 from{transform:translateY(0) rotate(0deg);opacity:0}
 15%{opacity:.5}
 to{transform:translateY(-115vh) rotate(28deg);opacity:0}
}

.card{
 background:#ffffffdf;
 border:1px solid #dce2f5;
 border-radius:27px;
 padding:26px 21px;
 box-shadow:0 14px 38px #7785b51c;
 text-align:center;
 backdrop-filter:blur(8px);
}

h1{
 font-size:clamp(30px,8vw,43px);
 font-weight:normal;
 margin:8px 0;
 color:#7772a9;
}

h2{
 font-size:25px;
 font-weight:normal;
 margin:8px 0 14px;
 color:#7772a9;
}

p{
 font-family:Arial,sans-serif;
 line-height:1.7;
 font-size:15px;
 color:#6e7398;
}

.small{
 font-size:11px;
 letter-spacing:2px;
 text-transform:uppercase;
 color:#91a0c7;
}

.symbol{
 font-size:35px;
 letter-spacing:8px;
 margin:5px 0 17px;
 color:#a39bd5;
}

button{
 border:0;
 border-radius:999px;
 padding:13px 20px;
 margin:7px 4px;
 background:linear-gradient(100deg,#9bbbe6,#b3a5df);
 color:white;
 font-size:15px;
 cursor:pointer;
 box-shadow:0 4px 0 #899bc7;
}

button.secondary{
 background:#edf0ff;
 color:#7378a4;
 box-shadow:0 4px 0 #d9def4;
}

button:active{
 transform:translateY(3px);
 box-shadow:none;
}

.options{
 display:grid;
 gap:9px;
 margin:18px 0;
}

.options button{
 width:100%;
 margin:0;
 background:#eef1ff;
 color:#6c709b;
 box-shadow:none;
 border:1px solid #dfe3f7;
}

.options button:hover{
 background:#e4e9ff;
}

.hidden{
 display:none;
}

.note{
 background:linear-gradient(145deg,#f1f6ff,#f4efff);
 border:1px solid #e3e5f8;
 border-radius:19px;
 padding:17px;
 margin:16px 0;
 text-align:left;
}

.note p{
 margin:8px 0;
}

.footer{
 font-size:12px;
 color:#9ba4c8;
 margin-top:18px;
}

.progress{
 height:6px;
 background:#e9eafd;
 border-radius:99px;
 overflow:hidden;
 margin:17px 0 21px;
}

.progress span{
 display:block;
 height:100%;
 background:linear-gradient(90deg,#9fc5ed,#b4a3df);
 transition:width .3s;
}

.counter{
 font:12px Arial,sans-serif;
 color:#9ba4c8;
}
</style>
</head>

<body>

<div class="hearts" aria-hidden="true">
 <span class="heart" style="left:7%;font-size:20px">♡</span>
 <span class="heart" style="left:19%;font-size:14px;animation-delay:3s">♥</span>
 <span class="heart" style="left:37%;font-size:23px;animation-delay:7s">♡</span>
 <span class="heart" style="left:58%;font-size:16px;animation-delay:1s">♥</span>
 <span class="heart" style="left:77%;font-size:24px;animation-delay:5s">♡</span>
 <span class="heart" style="left:91%;font-size:15px;animation-delay:9s">♥</span>
</div>

<main>

<!-- BIENVENIDA -->
<section class="card" id="welcome">
 <div class="symbol">♡ ˚₊‧ 🩵 ‧₊˚ ♡</div>

 <div class="small">a little adventure made for you</div>

 <h1>A little place for you</h1>

 <p>
 Preparé un pequeño rincón para ti. Hay preguntas,
 recuerdos y algunas palabras que quiero regalarte.
 Todo está aquí por una razón: tú. ♡
 </p>

 <button onclick="show('level1')">
 Comenzar nuestra aventura ♡
 </button>

 <div class="footer">
 hecho con cariño, solo para ti · 11:11
 </div>
</section>

<!-- NIVEL 1 -->
<section class="card hidden" id="level1">

 <div class="symbol">♡ 🩵 ♡</div>

 <div class="small">nivel 1 · una pregunta</div>

 <div class="progress">
  <span style="width:20%"></span>
 </div>

 <h2>Una pequeña elección</h2>

 <p>
 Si pudieras elegir un plan para compartir conmigo,
 ¿cuál sería?
 </p>

 <div class="options">

  <button onclick="next('¡Ese plan suena precioso! Lo importante sería compartirlo contigo. ♡','feedback','level2')">
   Una noche mirando las estrellas
  </button>

  <button onclick="next('Un día tranquilo también puede convertirse en un recuerdo precioso. ♡','feedback','level2')">
   Una tarde tranquila, sin preocupaciones
  </button>

  <button onclick="next('JAJA, cualquier aventura contigo tendría su encanto. ♡','feedback','level2')">
   Una aventura improvisada
  </button>

 </div>

 <p id="feedback"></p>

</section>

<!-- NIVEL 2 -->
<section class="card hidden" id="level2">

 <div class="symbol">♡ ♥︎ ♡</div>

 <div class="small">nivel 2 · primer mensaje</div>

 <div class="progress">
  <span style="width:40%"></span>
 </div>

 <h2>Un mensajito para ti</h2>

 <div class="note">
  <p>
  Hay personas que llegan a nuestros días y,
  sin hacer demasiado ruido, terminan ocupando
  un lugar muy especial. Me gusta poder compartir
  contigo mis momentos, mis ocurrencias y hasta
  las cosas más pequeñas. ♡
  </p>
 </div>

 <p>
 Y todavía quedan más cositas por descubrir...
 </p>

 <button onclick="show('level3')">
 Seguir explorando ♡
 </button>

</section>

<!-- NIVEL 3 -->
<section class="card hidden" id="level3">

 <div class="symbol">♡ ✧ ♡</div>

 <div class="small">nivel 3 · ¿qué recuerdas?</div>

 <div class="progress">
  <span style="width:60%"></span>
 </div>

 <h2>Una pregunta sobre nosotros</h2>

 <p>
 ¿Qué crees que hace especial un recuerdo?
 </p>

 <div class="options">

  <button onclick="next('Puede ser. A veces los detalles pequeños se quedan con nosotros. ♡','feedback2','level4')">
   Los pequeños detalles
  </button>

  <button onclick="next('Compartirlo con alguien especial puede cambiarlo todo. ♡','feedback2','level4')">
   La persona con quien lo compartes
  </button>

  <button onclick="next('Yo creo que puede ser una mezcla de ambas cosas. ♡','feedback2','level4')">
   Las dos cosas juntas
  </button>

 </div>

 <p id="feedback2"></p>

</section>

<!-- NIVEL 4 -->
<section class="card hidden" id="level4">

 <div class="symbol">♡ ✿ ♡</div>

 <div class="small">nivel 4 · una pausa</div>

 <div class="progress">
  <span style="width:80%"></span>
 </div>

 <h2>Antes de llegar al final...</h2>

 <div class="note">
  <p>
  Quiero que sepas que no hice esto porque
  necesitara una ocasión especial. A veces
  simplemente me nace recordarte lo importante
  que eres para mí, y esta vez quise hacerlo
  de una manera un poquito diferente.
  </p>
 </div>

 <p>
 La última sorpresa te está esperando.
 </p>

 <button onclick="show('ending')">
 Abrir mi última sorpresa ♡
 </button>

</section>

<!-- FINAL -->
<section class="card hidden" id="ending">

 <div class="symbol">♡ ✮ ✩ ♡</div>

 <div class="small">
 el final de este pequeño recorrido
 </div>

 <h1>Para ti, Adir ♡</h1>

 <div class="note">

  <p>Mi amor:</p>

  <p>
  Quería hacerte algo distinto esta vez. Ya te he
  escrito muchas cartitas, pero tenía ganas de
  preparar un pequeño lugar que pudieras recorrer,
  con preguntitas, mensajes y detalles que me
  recordaran a nosotros.
  </p>

  <p>
  Ojalá cada parte de este juego te haya sacado
  aunque sea una pequeña sonrisa. No sé si unas
  cuantas pantallas puedan expresar todo lo que
  quisiera decirte, pero sí sé que cada una fue
  hecha pensando en ti.
  </p>

  <p>
  Gracias por estar en mi vida, por compartir
  conmigo tus días y por permitirme guardar tantos
  momentos bonitos a tu lado. Me hace feliz tenerte
  y seguir construyendo recuerdos contigo, incluso
  en las cosas más sencillas.
  </p>

  <p>
  Quiero seguir encontrando motivos para elegirte,
  para reír contigo y para recordarte lo mucho
  que significas para mí.
  </p>

  <p>Con todo mi cariño,</p>

  <p><strong>Tu hermoso novio. ♡</strong></p>

 </div>

 <p class="counter">
 fin de la aventura · pero no de nuestra historia
 </p>

 <button class="secondary" onclick="show('welcome')">
 Volver al inicio ↻
 </button>

</section>

</main>

<script>

// CAMBIAR DE PANTALLA
function show(id){

 document.querySelectorAll('main section').forEach(section=>{
  section.classList.add('hidden');
 });

 const selected = document.getElementById(id);

 if(selected){
  selected.classList.remove('hidden');
 }

 window.scrollTo({
  top:0,
  behavior:'smooth'
 });

}

// MOSTRAR RESPUESTA Y AVANZAR
function next(message, target, nextLevel){

 const feedback = document.getElementById(target);

 if(!feedback){
  console.error('No se encontró el elemento:', target);
  return;
 }

 feedback.textContent = message;

 setTimeout(()=>{
  show(nextLevel);
 },1200);

}

</script>

</body>
</html>
