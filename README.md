<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vivi x Gloo Forever</title>

<style>
body{
margin:0;
padding:0;
height:100vh;
display:flex;
justify-content:center;
align-items:center;
background:linear-gradient(135deg,#7b2cbf,#3c096c);
font-family:Arial, sans-serif;
color:white;
text-align:center;
overflow:hidden;
}

/* Main container */
.container{
z-index:2;
padding:20px;
}

h1{
font-size:24px;
margin-bottom:30px;
transition:0.3s;
}

/* Buttons */
button{
padding:12px 28px;
font-size:16px;
border:none;
border-radius:30px;
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
