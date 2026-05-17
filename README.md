<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Khushi 💖 Final Boss</title>

<style>
body{
margin:0;
font-family:sans-serif;
background:black;
overflow:hidden;
color:white;
text-align:center;
}

/* SPLASH */
#splash{
position:fixed;
width:100%;
height:100%;
background:linear-gradient(135deg,#ff4b5c,#ff9a9e);
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
z-index:10;
animation:fadeOut 2.5s forwards;
animation-delay:2s;
}

@keyframes fadeOut{
to{opacity:0; visibility:hidden;}
}

/* LOGIN */
#login{
position:absolute;
top:50%;
left:50%;
transform:translate(-50%,-50%);
padding:20px;
background:rgba(255,255,255,0.1);
backdrop-filter:blur(10px);
border-radius:15px;
z-index:5;
}

input{
padding:10px;
border:none;
border-radius:10px;
margin-top:10px;
}

button{
padding:10px 20px;
margin-top:10px;
border:none;
border-radius:10px;
background:#ff4b5c;
color:white;
cursor:pointer;
}

/* MAIN */
.container{
padding:20px;
display:none;
}

h1{
text-shadow:0 0 15px pink;
}

img{
width:90%;
max-width:280px;
border-radius:15px;
margin-top:10px;
}

/* hearts */
.heart{
position:absolute;
color:pink;
animation:floatUp 5s linear infinite;
}

@keyframes floatUp{
0%{transform:translateY(100vh);}
100%{transform:translateY(-10vh); opacity:0;}
}

/* stars */
.star{
position:absolute;
width:2px;
height:2px;
background:white;
animation:twinkle 2s infinite;
}

@keyframes twinkle{
0%{opacity:0;}
50%{opacity:1;}
100%{opacity:0;}
}

/* END */
#end{
display:none;
position:absolute;
top:50%;
left:50%;
transform:translate(-50%,-50%);
}
</style>
</head>

<body>

<!-- SPLASH -->
<div id="splash">
<h1>💖 Loading Surprise...</h1>
<p>For Khushi 🎂</p>
</div>

<!-- LOGIN -->
<div id="login">
<h2>Enter Password 💖</h2>
<input type="password" id="pass">
<br>
<button onclick="check()">Unlock</button>
</div>

<!-- MAIN -->
<div class="container" id="main">
<h1>🎂 Happy Birthday Khushi 💖</h1>

<div id="text"></div>

<img id="img" src="https://images.unsplash.com/photo-1524504388940-b1c1722653e1">

<br>
<button onclick="final()">Open Surprise 🎁</button>
</div>

<!-- END -->
<div id="end">
<h2>💖 Final Message 💖</h2>
<p>
Tu meri bestie hai... aur hamesha special rahegi 🫶<br><br>
Teri smile meri duniya hai 😊<br><br>
— Noman ❤️
</p>
</div>

<script>

function check(){
let pass=document.getElementById("pass").value;

if(pass==="Shonaaaa"){
document.getElementById("login").style.display="none";
document.getElementById("main").style.display="block";
type();
hearts();
stars();
}else{
alert("Wrong Password 😜");
}
}

/* typing */
let msg="Tu meri bestie hai... aur tu hamesha special rahegi 💖";
let i=0;

function type(){
if(i<msg.length){
document.getElementById("text").innerHTML+=msg[i];
i++;
setTimeout(type,40);
}
}

/* hearts */
setInterval(()=>{
let h=document.createElement("div");
h.className="heart";
h.innerHTML="❤️";
h.style.left=Math.random()*100+"%";
document.body.appendChild(h);
setTimeout(()=>h.remove(),5000);
},300);

/* stars */
function stars(){
for(let i=0;i<50;i++){
let s=document.createElement("div");
s.className="star";
s.style.left=Math.random()*100+"%";
s.style.top=Math.random()*100+"%";
document.body.appendChild(s);
}
}
stars();

/* final */
function final(){
document.getElementById("main").style.display="none";
document.getElementById("end").style.display="block";
}

</script>

</body>
</html>
