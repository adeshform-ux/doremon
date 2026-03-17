```html id="doraemon-movie"
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Doraemon Movie 💙</title>
<meta name="viewport" content="width=device-width, initial-scale=1">

<style>

body{
margin:0;
font-family:Comic Sans MS, cursive;
background:#000;
color:white;
overflow:hidden;
text-align:center;
}

/* screens */

.screen{
position:absolute;
width:100%;
height:100vh;
display:flex;
justify-content:center;
align-items:center;
flex-direction:column;
transition:1.2s;
}

.hidden{
opacity:0;
pointer-events:none;
}

/* cinematic text */

.big{
font-size:40px;
animation:fade 2s;
}

@keyframes fade{
from{opacity:0; transform:translateY(40px);}
to{opacity:1;}
}

/* card */

.card{
background:rgba(0,0,0,0.7);
padding:30px;
border-radius:20px;
max-width:420px;
}

/* button */

button{
padding:12px 25px;
border:none;
border-radius:25px;
background:#0072ff;
color:white;
font-size:18px;
margin-top:15px;
cursor:pointer;
}

/* floating */

.float{
position:absolute;
font-size:28px;
animation:rise 10s linear infinite;
}

@keyframes rise{
0%{transform:translateY(100vh)}
100%{transform:translateY(-10vh)}
}

video{
position:absolute;
width:100%;
height:100%;
object-fit:cover;
z-index:-1;
}

.overlay{
position:absolute;
width:100%;
height:100%;
background:rgba(0,0,0,0.5);
z-index:-1;
}

</style>
</head>

<body>

<!-- INTRO -->

<div class="screen" id="intro">

<video autoplay muted loop>
<source src="https://www.w3schools.com/howto/rain.mp4">
</video>

<div class="overlay"></div>

<div class="big">
🎬 Doraemon Movie 💙
</div>

<p>Starring Adesh & Rupashree ❤️</p>

<button onclick="next('scene1')">Start Movie 🎥</button>

</div>

<!-- SCENE 1 -->

<div class="screen hidden" id="scene1">

<div class="card">

<h2>👦 Adesh (Nobita)</h2>

<p>
Main Nobita jaisa hoon 😅  
Thoda irritating... thoda careless 🙈  
</p>

<button onclick="next('scene2')">Next ▶</button>

</div>

</div>

<!-- SCENE 2 -->

<div class="screen hidden" id="scene2">

<div class="card">

<h2>👧 Rupashree (Shizuka 💙)</h2>

<p>
Tum meri Shizuka ho ❤️  
Smart, kind aur sabse special 🥺  
</p>

<button onclick="next('scene3')">Next ▶</button>

</div>

</div>

<!-- SCENE 3 -->

<div class="screen hidden" id="scene3">

<div class="card">

<h2>💔 The Mistake</h2>

<p>
Kabhi kabhi main tumhe irritate karta hoon 😅  
Aur shayad hurt bhi kar deta hoon 🥺  
</p>

<button onclick="next('scene4')">Next ▶</button>

</div>

</div>

<!-- SCENE 4 -->

<div class="screen hidden" id="scene4">

<div class="card">

<h2>💌 The Real Feeling</h2>

<p>
But sach mein...  
Main tumhe kabhi hurt nahi karna chahta ❤️  
Tum mere liye bahut important ho 💖  
</p>

<button onclick="next('question')">Next ▶</button>

</div>

</div>

<!-- QUESTION -->

<div class="screen hidden" id="question">

<div class="card">

<h2>🥺 Final Scene</h2>

<p>Will you forgive me?</p>

<button onclick="next('final')">Yes 💙</button>
<button id="noBtn" onmouseover="moveNo()">No 😤</button>

</div>

</div>

<!-- FINAL -->

<div class="screen hidden" id="final">

<div class="card">

<h1>💍 Happy Ending 💙</h1>

<p>
Jaise Doraemon Nobita ko kabhi chhodta nahi ❤️  
Waise hi please tum bhi mujhe mat chhodna 🥺  
I promise I’ll be better 😅  
</p>

</div>

</div>

<script>

/* navigation */

function next(id){
document.querySelectorAll(".screen").forEach(s=>s.classList.add("hidden"))
document.getElementById(id).classList.remove("hidden")
}

/* no button */

function moveNo(){
let btn=document.getElementById("noBtn")
btn.style.position="absolute"
btn.style.left=Math.random()*80+"vw"
btn.style.top=Math.random()*80+"vh"
}

/* floating emojis */

let emojis=["💙","❤️","🥺","✨","🎬"]

setInterval(()=>{

let e=document.createElement("div")
e.className="float"
e.innerHTML=emojis[Math.floor(Math.random()*emojis.length)]
e.style.left=Math.random()*100+"vw"

document.body.appendChild(e)

setTimeout(()=>e.remove(),8000)

},300)

</script>

</body>
</html>
```
