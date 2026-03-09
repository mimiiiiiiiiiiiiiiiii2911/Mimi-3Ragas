<!DOCTYPE html>
<html lang="en">
<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">

<title>Mimi and Ragas</title>

<style>

/* -------- THEME COLORS -------- */

:root{
--black:#0d0d0d;
--white:#ffffff;
--pink:#ff6ec7;
--pale:#fff6b3;
}

/* -------- BODY -------- */

body{
margin:0;
font-family: "Segoe UI", sans-serif;
background:var(--black);
color:var(--white);
text-align:center;
overflow-x:hidden;
}

/* -------- INTRO -------- */

#intro{
position:fixed;
width:100%;
height:100%;
background:black;
display:flex;
flex-direction:column;
align-items:center;
justify-content:center;
z-index:999;
}

#intro h1{
font-size:60px;
color:var(--pink);
text-shadow:0 0 25px var(--pink);
}

#enter{
padding:15px 40px;
border:none;
border-radius:30px;
font-size:18px;
background:var(--pale);
cursor:pointer;
}

/* -------- TITLE -------- */

.title{
font-size:58px;
margin-top:40px;
background:linear-gradient(45deg,var(--pink),var(--pale));
-webkit-background-clip:text;
-webkit-text-fill-color:transparent;
}

/* -------- PHOTO -------- */

.photoBox{
position:relative;
margin-top:30px;
}

.photo{
width:320px;
border-radius:20px;
box-shadow:0 20px 40px rgba(0,0,0,0.6);
}

/* -------- HEART -------- */

.heart{
position:absolute;
top:50%;
left:50%;
transform:translate(-50%,-50%);
font-size:50px;
cursor:pointer;
animation:beat 1.1s infinite;
}

@keyframes beat{

0%{transform:translate(-50%,-50%) scale(1)}
50%{transform:translate(-50%,-50%) scale(1.3)}
100%{transform:translate(-50%,-50%) scale(1)}

}

/* -------- LETTER -------- */

#letter{
display:none;
max-width:650px;
margin:auto;
margin-top:50px;
background:#151515;
padding:40px;
border-radius:18px;
line-height:1.8;
border:1px solid var(--pale);
}

/* -------- COUNTER -------- */

#counter{
font-size:22px;
margin-top:30px;
color:var(--pale);
}

/* -------- MAP -------- */

.map{
margin-top:40px;
font-size:22px;
}

.plane{
font-size:28px;
animation:fly 7s linear infinite;
}

@keyframes fly{
0%{transform:translateX(-200px)}
100%{transform:translateX(200px)}
}

/* -------- BEARS -------- */

.bears{
position:relative;
height:120px;
margin-top:60px;
font-size:70px;
}

#bear1{
position:absolute;
left:10%;
animation:bear1 6s infinite alternate;
}

#bear2{
position:absolute;
right:10%;
animation:bear2 6s infinite alternate;
}

@keyframes bear1{
from{left:10%}
to{left:40%}
}

@keyframes bear2{
from{right:10%}
to{right:40%}
}

/* -------- HORSE -------- */

.horseTrack{
position:fixed;
bottom:0;
width:100%;
height:60px;
}

.horse{
position:absolute;
font-size:40px;
animation:run 10s linear infinite;
}

@keyframes run{
0%{left:-100px}
100%{left:110%}
}

/* -------- STARS -------- */

.star{
position:fixed;
width:2px;
height:2px;
background:white;
animation:twinkle 2s infinite;
}

@keyframes twinkle{
0%{opacity:0}
50%{opacity:1}
100%{opacity:0}
}

/* -------- SHOOTING STAR -------- */

.shoot{
position:fixed;
width:3px;
height:3px;
background:white;
box-shadow:0 0 10px white;
animation:shoot 7s linear infinite;
}

@keyframes shoot{

0%{transform:translate(-200px,-200px)}
100%{transform:translate(120vw,120vh)}

}

</style>
</head>


<body>

<!-- INTRO -->

<div id="intro">

<h1>Welcome Ragas</h1>

<button id="enter" onclick="enterSite()">Enter</button>

</div>


<h1 class="title">Mimi and Ragas</h1>


<!-- PHOTO -->

<div class="photoBox">

<img src="photo.jpg" class="photo">

<div class="heart" onclick="openLetter()">❤️</div>

<p>Open it</p>

</div>


<!-- LETTER -->

<div id="letter">

<h2 style="color:var(--pale)">Dear Ragas</h2>

<p>

Thank you for staying with someone like me.  
Sometimes I can be chaotic, emotional and overthinking too much.  
But somehow you still stay.

</p>

<p>

Across the world, from Ho Chi Minh City to Zurich,  
there is a girl who smiles whenever she talks to you.

</p>

<p>

Different cities.  
Different time zones.  
But somehow we met.

</p>

<p>

And that makes you very special to me.

</p>

<p>

Love,  
Mimi 🧸

</p>

</div>


<!-- MAP -->

<div class="map">

📍 Ho Chi Minh City ✈ Zurich 📍

<div class="plane">✈️</div>

</div>


<!-- COUNTER -->

<div id="counter"></div>


<!-- BEARS -->

<div class="bears">

<div id="bear1">🧸</div>
<div id="bear2">🤍</div>

</div>


<!-- DOG -->

<div style="font-size:70px;margin-top:80px">🐕</div>


<!-- HORSE -->

<div class="horseTrack">

<div class="horse">🐴</div>

</div>


<!-- MUSIC -->

<iframe width="0" height="0"
src="https://www.youtube.com/embed/2nCj8cfgSLE?autoplay=1&loop=1&playlist=2nCj8cfgSLE">
</iframe>


<script>

/* INTRO */

function enterSite(){
document.getElementById("intro").style.display="none"
}

/* LETTER */

function openLetter(){
document.getElementById("letter").style.display="block"
}

/* COUNTER */

const start = new Date("2026-01-02T00:00:00")

function update(){

const now = new Date()

const diff = now - start

const days = Math.floor(diff/(1000*60*60*24))
const hours = Math.floor((diff/(1000*60*60))%24)
const minutes = Math.floor((diff/(1000*60))%60)
const seconds = Math.floor((diff/1000)%60)

document.getElementById("counter").innerHTML =
`❤️ Together for ${days} days ${hours}h ${minutes}m ${seconds}s`

}

setInterval(update,1000)

update()

/* STARS */

for(let i=0;i<120;i++){

let s=document.createElement("div")
s.className="star"
s.style.left=Math.random()*100+"vw"
s.style.top=Math.random()*100+"vh"

document.body.appendChild(s)

}

/* SHOOTING STAR */

setInterval(()=>{

let s=document.createElement("div")
s.className="shoot"

document.body.appendChild(s)

setTimeout(()=>s.remove(),3000)

},6000)

</script>

</body>
</html>
