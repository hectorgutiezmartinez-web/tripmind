
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#0b1220">
<title>TripMind Discover</title>
<style>
*{box-sizing:border-box}
body{margin:0;background:#0b1220;color:#f4f7fb;font-family:Arial,sans-serif}
header{padding:24px 7%;display:flex;justify-content:space-between;align-items:center}
.logo{font-size:23px;font-weight:bold}
.logo span{color:#8ef0c2}
nav a{color:#a8b5c8;text-decoration:none;margin-left:18px;font-size:14px}
main{max-width:1050px;margin:auto;padding:45px 22px}
.eyebrow{color:#8ef0c2;font-size:12px;font-weight:bold;letter-spacing:2px}
h1{font-size:clamp(40px,7vw,68px);line-height:1.05;letter-spacing:-2px;margin:17px 0}
.intro{color:#a8b5c8;line-height:1.7;max-width:650px}
.layout{display:grid;grid-template-columns:1fr 1fr;gap:22px;margin-top:35px}
.card{background:#142137;border:1px solid #293750;border-radius:20px;padding:25px}
h2{font-size:21px;margin-top:0}
.sub{font-size:13px;color:#a8b5c8;line-height:1.5}
label{display:block;margin:16px 0 8px;font-size:13px}
input,select{width:100%;padding:13px;border-radius:10px;border:1px solid #34445f;background:#0b1729;color:white;font-size:15px}
.fields{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.tags{display:flex;flex-wrap:wrap;gap:8px}
.tag{background:#0b1729;border:1px solid #34445f;border-radius:30px;padding:9px 12px;font-size:12px;cursor:pointer}
.tag.active{border-color:#8ef0c2;color:#8ef0c2;background:#173e39}
button{width:100%;padding:15px;border:0;border-radius:11px;background:#8ef0c2;color:#092018;font-weight:bold;font-size:15px;margin-top:22px;cursor:pointer}
.preview{background:linear-gradient(145deg,#244d58,#1b3154);height:180px;border-radius:15px;margin:20px 0}
.feature{padding:13px 0;border-top:1px solid #293750;color:#a8b5c8;font-size:13px}
.feature strong{display:block;color:white;margin-bottom:4px}
#results{display:none;margin-top:35px}
.trip-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:12px}
.trip{background:#142137;border:1px solid #293750;border-radius:16px;padding:18px}
.trip h3{font-size:20px}
.trip p{font-size:13px;color:#a8b5c8;line-height:1.5}
.price{font-size:24px;color:#8ef0c2;font-weight:bold}
.score{font-size:11px;color:#8bb8ff}
.note{font-size:11px;color:#8291a6;line-height:1.5;margin-top:15px}
footer{padding:30px 20px;text-align:center;color:#8291a6;font-size:11px}
@media(max-width:700px){.layout{grid-template-columns:1fr}.preview-card{display:none}.trip-grid{grid-template-columns:1fr}main{padding-top:30px}nav a{margin-left:8px}}
</style>
</head>
<body>
<header>
<div class="logo">tripmind<span>.</span></div>
<nav><a href="#discover">Discover</a><a href="#how">Cómo funciona</a></nav>
</header>

<main>
<section>
<div class="eyebrow">NO ELIJAS DESTINO. DESCÚBRELO.</div>
<h1>Tu presupuesto.<br>Un mundo de posibilidades.</h1>
<p class="intro">Dinos cuánto quieres gastar, desde dónde sales y qué experiencia buscas. TripMind te descubre viajes que quizá nunca habías imaginado.</p>
</section>

<section class="layout" id="discover">
<div class="card">
<h2>Descubre tu próximo viaje</h2>
<p class="sub">Completa los datos y encuentra nuevas posibilidades.</p>

<form id="tripForm">
<div class="fields">
<div>
<label>¿Desde dónde sales?</label>
<input id="origin" value="Madrid" required>
</div>
<div>
<label>Presupuesto total (€)</label>
<input id="budget" type="number" value="600" min="50" required>
</div>
<div>
<label>Personas</label>
<select id="people">
<option>1</option><option>2</option><option selected>4</option><option>5</option><option>6</option>
</select>
</div>
<div>
<label>Duración</label>
<select id="days">
<option>2</option><option>3</option><option>4</option><option selected>5</option><option>6</option><option>7</option><option>10</option>
</select>
</div>
</div>

<label>¿Cuándo quieres viajar?</label>
<select id="when">
<option>Fechas flexibles</option>
<option>Este mes</option>
<option>Próximo mes</option>
<option>En verano</option>
<option>En invierno</option>
</select>

<label>¿Qué tipo de viaje buscas?</label>
<div class="tags" id="tags">
<span class="tag active">Naturaleza</span>
<span class="tag">Playa</span>
<span class="tag">Montaña</span>
<span class="tag">Ciudades</span>
<span class="tag">Aventura</span>
<span class="tag">Tranquilidad</span>
<span class="tag">Cultura</span>
<span class="tag">Gastronomía</span>
</div>

<button type="submit">Descubrir mis viajes →</button>
<p class="note">Prototipo inicial. Los resultados son simulaciones, no precios reales.</p>
</form>
</div>

<div class="card preview-card" id="how">
<h2>Viajes que encajan contigo</h2>
<p class="sub">No queremos enseñarte siempre los mismos destinos. Queremos descubrir los que mejor se adaptan a ti.</p>
<div class="preview"></div>
<div class="feature"><strong>✦ Presupuesto inteligente</strong>Transporte, alojamiento, comida y actividades.</div>
<div class="feature"><strong>⌁ Destinos inesperados</strong>Tres alternativas para comparar.</div>
<div class="feature"><strong>↗ Decisiones claras</strong>Diferencia entre datos comprobados y estimaciones.</div>
</div>
</section>

<section id="results">
<div class="eyebrow">TUS PRIMERAS IDEAS</div>
<h2>Estos viajes podrían encajar contigo</h2>
<div class="trip-grid" id="tripGrid"></div>
<p class="note">Importes ficticios para demostrar el funcionamiento. No representan ofertas ni disponibilidad real.</p>
</section>
</main>

<footer>TripMind Discover · Prototipo v0.1</footer>

<script>
const tags=document.querySelectorAll(".tag");
tags.forEach(tag=>{
tag.addEventListener("click",()=>tag.classList.toggle("active"));
});

document.getElementById("tripForm").addEventListener("submit",function(e){
e.preventDefault();

const budget=Number(document.getElementById("budget").value)||600;
const people=Number(document.getElementById("people").value);
const days=Number(document.getElementById("days").value);

const destinations=[
{name:"Asturias",kind:"Naturaleza y costa",description:"Montañas, pueblos verdes y playas espectaculares.",base:470,score:92},
{name:"Cantabria",kind:"Desconexión",description:"Playas, paisajes, gastronomía y tranquilidad.",base:420,score:89},
{name:"Pirineo francés",kind:"Montaña y aventura",description:"Valles, lagos y pequeños pueblos de montaña.",base:520,score:84}
];

const factor=Math.min(1.35,Math.max(.55,budget/600));
const grid=document.getElementById("tripGrid");
grid.innerHTML="";

destinations.forEach((d,i)=>{
const estimate=Math.round(d.base*factor*(people/4)*(days/5)/10)*10;
const article=document.createElement("article");
article.className="trip";
article.innerHTML=`
<div class="score">Encaje orientativo ${d.score-i*2}/100</div>
<h3>${d.name}</h3>
<div class="score">${d.kind}</div>
<p>${d.description}</p>
<div class="price">≈ ${estimate.toLocaleString("es-ES")} €</div>
<div class="note">Ejemplo para ${people} personas · ${days} días</div>
`;
grid.appendChild(article);
});

document.getElementById("results").style.display="block";
document.getElementById("results").scrollIntoView({behavior:"smooth"});
});
</script>
</body>
</html>



