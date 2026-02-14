<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vivi x Gloo</title>

<style>
body{
margin:0;
height:100vh;
display:flex;
justify-content:center;
align-items:center;
background:#240046;
font-family:Arial, sans-serif;
color:white;
text-align:center;
}

.container{
padding:20px;
}

h1{
margin-bottom:30px;
}

button{
padding:12px 25px;
font-size:16px;
border:none;
border-radius:25px;
cursor:pointer;
margin:10px;
}

#yesBtn{
background:#ffd60a;
color:black;
}

#noBtn{
background:#5a189a;
color:white;
position:relative;
}
</style>
</head>

<body>

<div class="container">
<h1 id="question">Vivi… can I be your Gloo forever? 💜</h1>

<button id="yesBtn">YES 💜</button>
<button id="noBtn">NO 😢</button>
</div>

<script>
var noBtn = document.getElementById("noBtn");
var yesBtn = document.getElementById("yesBtn");
var question = document.getElementById("question");

var clickCount = 0;

noBtn.onclick = function(){

if(clickCount === 0){
question.innerHTML = "Are we not Gloo? 🥹";
clickCount++;
} else {
question.innerHTML = "You can't escape Gloo 💜";
}

noBtn.style.position = "absolute";
noBtn.style.left = Math.random() * (window.innerWidth - 100) + "px";
noBtn.style.top = Math.random() * (window.innerHeight - 50) + "px";
};

yesBtn.onclick = function(){
question.innerHTML = "Vivi 💜 You're officially stuck with your Gloo forever!";
noBtn.style.display = "none";
yesBtn.style.display = "none";
};
</script>

</body>
</html>
}

.container{
z-index:2;
padding:20px;
max-width:400px;
}

h1{
font-size:24px;
margin-bottom:30px;
transition:0.3s;
text-shadow:0 0 10px rgba(255,255,255,0.4);
}

/* Buttons */
button{
padding:14px 30px;
font-size:16px;
border:none;
border-radius:40px;
cursor:pointer;
margin:10px;
transition:0.3s;
}

#yesBtn{
background:linear-gradient(45deg,#ffd60a,#ffea00);
color:black;
box-shadow:0 0 15px gold;
}

#yesBtn:hover{
box-shadow:0 0 25px gold;
transform:scale(1.05);
}

#noBtn{
background:#2d006e;
color:white;
position:relative;
box-shadow:0 0 10px #9d4edd;
}

/* Medal popup */
.medal{
position:absolute;
top:50%;
left:50%;
transform:translate(-50%,-50%) scale(0);
font-size:32px;
font-weight:bold;
color:#ffd60a;
text-shadow:0 0 20px gold;
animation:medalPop 1.2s forwards;
}

@keyframes medalPop{
0%{transform:translate(-50%,-50%) scale(0);opacity:0;}
50%{transform:translate(-50%,-50%) scale(1.6);opacity:1;}
100%{transform:translate(-50%,-50%) scale(1);opacity:0;}
}

/* Mythic banner*
cursor:pointer;
margin:10px;
transition:0.3s;
}

#yesBtn{
background:gold;
color:black;
}

#noBtn{
background:gray;
position:relative;
}

/* Medal popup */
.medal{
position:absolute;
top:50%;
left:50%;
transform:translate(-50%,-50%) scale(0);
font-size:32px;
font-weight:bold;
color:yellow;
animation:medalPop 1.2s forwards;
}

@keyframes medalPop{
0%{transform:translate(-50%,-50%) scale(0);opacity:0;}
50%{transform:translate(-50%,-50%) scale(1.5);opacity:1;}
100%{transform:translate(-50%,-50%) scale(1);opacity:0;}
}

/* Mythic banner */
.mythic{
position:absolute;
top:30%;
left:50%;
transform:translate(-50%,-50%) scale(0);
font-size:22px;
font-weight:bold;
color:#ff66ff;
animation:mythicAnim 2s forwards;
}

@keyframes mythicAnim{
0%{transform:translate(-50%,-50%) scale(0);}
50%{transform:translate(-50%,-50%) scale(1.3);}
100%{transform:translate(-50%,-50%) scale(1);}
}

/* Floating effects */
.float{
position:absolute;
font-size:20px;
animation:floatUp 4s linear forwards;
}

@keyframes floatUp{
0%{transform:translateY(0);opacity:1;}
100%{transform:translateY(-350px);opacity:0;}
}

/* Screen shake */
@keyframes shake{
0%{transform:translate(0);}
25%{transform:translate(-6px,4px);}
50%{transform:translate(6px,-4px);}
75%{transform:translate(-4px,6px);}
100%{transform:translate(0);}
}

.shake{
animation:shake 0.4s ease;
}

/* Footer */
.footer{
position:absolute;
bottom:12px;
width:100%;
font-size:13px;
opacity:0.7;
}
</style>
</head>

<body>

<div class="container">
<h1 id="text">Vivi… can I be your Gloo forever? 💜</h1>

<button id="yesBtn">YES 🏆</button>
<button id="noBtn">NO 😢</button>
</div>

<div class="footer">Made by your Gloo 💜</div>

<script>
var noBtn = document.getElementById("noBtn");
var yesBtn = document.getElementById("yesBtn");
var text = document.getElementById("text");
var body = document.body;

/* FIRST rejection is fixed */
var messages = [
"Are we not Gloo? 🥹",
"Vivi don’t split from me 🥺",
"Gloo sticks forever 😭",
"You can’t escape the slime 💜",
"We are permanently attached 😏"
];

var index = 0;
var scale = 1;

/* Move NO button */
function moveNo(){
noBtn.style.position = "absolute";
noBtn.style.left = Math.random() * (window.innerWidth - 100) + "px";
noBtn.style.top = Math.random() * (window.innerHeight - 60) + "px";

if(index < messages.length){
text.innerHTML = messages[index];
index++;
}

scale += 0.2;
yesBtn.style.transform = "scale(" + scale + ")";
}

noBtn.onclick = moveNo;
noBtn.ontouchstart = moveNo;

/* YES click */
yesBtn.onclick = function(){

text.innerHTML = "Vivi 💜 You’re officially stuck with your Gloo forever!";
noBtn.style.display = "none";
yesBtn.style.display = "none";

showMedal("SAVAGE");
body.classList.add("shake");
setTimeout(function(){ body.classList.remove("shake"); },400);

setTimeout(function(){ showMedal("LEGENDARY"); },1500);
setTimeout(function(){ showMedal("MVP"); },3000);
setTimeout(showMythic,4500);

burstEffects();
};

/* Medal */
function showMedal(word){
var medal = document.createElement("div");
medal.className = "medal";
medal.innerHTML = word;
document.body.appendChild(medal);

setTimeout(function(){
document.body.removeChild(medal);
},1200);
}

/* Mythic */
function showMythic(){
var myth = document.createElement("div");
myth.className = "mythic";
myth.innerHTML = "MYTHIC RANK UP 💜 GLOO FOREVER";
document.body.appendChild(myth);
}

/* Burst flowers & hearts */
function burstEffects(){
for(var i=0;i<60;i++){
var el = document.createElement("div");
el.className = "float";
el.innerHTML = Math.random()>0.5 ? "💜" : "🌸";
el.style.left = Math.random()*window.innerWidth + "px";
el.style.top = window.innerHeight + "px";
document.body.appendChild(el);

setTimeout(function(e){
return function(){
if(document.body.contains(e)){
document.body.removeChild(e);
}
}
}(el),4000);
}
}
</script>

</body>
</html>
