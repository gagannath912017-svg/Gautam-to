# Gautam-to
Gautam
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>GOD MODE 4.0 NEW YEAR 🔥🎆</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
*{margin:0;padding:0}
body{
  height:100vh;
  background:black;
  overflow:hidden;
  font-family:Arial, sans-serif;
  animation:shake 0.08s infinite;
  cursor:none;
}
@keyframes shake{
  0%{transform:translate(0,0)}
  25%{transform:translate(5px,5px)}
  50%{transform:translate(-5px,5px)}
  75%{transform:translate(5px,-5px)}
  100%{transform:translate(0,0)}
}
h1{
  position:fixed;
  top:25%;
  width:100%;
  text-align:center;
  font-size:44px;
  color:white;
  text-shadow:
    0 0 15px red,
    0 0 30px pink,
    0 0 60px yellow,
    0 0 120px cyan;
  z-index:9999;
  animation:pulse 1s infinite alternate;
}
@keyframes pulse{from{transform:scale(1)}to{transform:scale(1.08)}}
.layer{position:absolute;will-change:transform,opacity;animation:fly linear infinite;}
@keyframes fly{0%{transform:translateY(120vh) translateX(0) scale(0.2) rotate(0deg); opacity:1;}100%{transform:translateY(-50vh) translateX(50px) scale(3) rotate(720deg); opacity:0;}}
@keyframes disco{0%{background:#000}25%{background:#120012}50%{background:#00121a}75%{background:#120900}100%{background:#000}}
body{animation:disco 1.5s infinite}
canvas{position:absolute; top:0; left:0; width:100%; height:100%; pointer-events:none;}
</style>
</head>
<body>
<h1 id="wishText">
❤️ I WISH YOU HAPPY NEW YEAR ❤️<br>
🎉 2026 🎉<br>
— GAUTAM KI TARAF SE 💖
</h1>
<canvas id="firework"></canvas>
<audio autoplay loop>
  <source src="song.mp3" type="audio/mpeg">
</audio>

<script>
// Name from URL
const params = new URLSearchParams(window.location.search);
const name = params.get('name');
if(name) document.getElementById("wishText").innerHTML=
  `❤️ I WISH YOU HAPPY NEW YEAR ${name} ❤️<br>🎉 2026 🎉<br>— GAUTAM KI TARAF SE 💖`;

// Vibration
if(navigator.vibrate) setInterval(()=>navigator.vibrate([100,50,100,50]),1200);

// Particle Engine GOD MODE 4.0
const icons=["❤️","🔥","✨","🎉","💥","💖","🌟","🎆","🎇","💫","💎"];
function spawn(batch,every){
  setInterval(()=>{
    for(let i=0;i<batch;i++){
      const e=document.createElement("div");
      e.className="layer";
      e.innerHTML=icons[Math.floor(Math.random()*icons.length)];
      e.style.left=Math.random()*100+"vw";
      e.style.fontSize=(20+Math.random()*120)+"px";
      e.style.animationDuration=(0.6+Math.random()*3)+"s";
      e.style.filter="drop-shadow(0 0 15px rgba(255,80,180,.95))";
      document.body.appendChild(e);
      setTimeout(()=>e.remove(),5000);
    }
  },every);
}

// Illusion of 100 Billion
spawn(200,50);
spawn(180,70);
spawn(150,100);
spawn(120,150);

// Mouse trail
document.addEventListener("mousemove",e=>{
  const p=document.createElement("div");
  p.className="layer";
  p.innerHTML=icons[Math.floor(Math.random()*icons.length)];
  p.style.left=(e.clientX+Math.random()*50-25)+"px";
  p.style.top=(e.clientY+Math.random()*50-25)+"px";
  p.style.fontSize=(15+Math.random()*80)+"px";
  p.style.animationDuration=(1+Math.random()*2)+"s";
  p.style.filter="drop-shadow(0 0 15px rgba(255,200,180,.95))";
  document.body.appendChild(p);
  setTimeout(()=>p.remove(),2500);
});

// Flash
setInterval(()=>{
  document.body.style.filter="brightness(1.3) invert(1)";
  setTimeout(()=>document.body.style.filter="brightness(1) invert(0)",150);
},800);

// Fireworks Canvas
const canvas=document.getElementById("firework");
const ctx=canvas.getContext("2d");
canvas.width=window.innerWidth;
canvas.height=window.innerHeight;

function random(min,max){return Math.random()*(max-min)+min;}
let particles=[];
function createFirework(){
  const x=random(0,canvas.width);
  const y=random(0,canvas.height/2);
  for(let i=0;i<60;i++){
    particles.push({x:x,y:y,vx:random(-3,3),vy:random(-4,0),alpha:1,color:`hsl(${Math.random()*360},100%,50%)`});
  }
}
function animate(){
  ctx.fillStyle='rgba(0,0,0,0.2)';
  ctx.fillRect(0,0,canvas.width,canvas.height);
  for(let i=particles.length-1;i>=0;i--){
    let p=particles[i];
    p.x+=p.vx;
    p.y+=p.vy;
    p.vy+=0.05;
    p.alpha-=0.02;
    ctx.fillStyle=p.color;
    ctx.globalAlpha=p.alpha;
    ctx.beginPath();
    ctx.arc(p.x,p.y,random(2,6),0,Math.PI*2);
    ctx.fill();
    if(p.alpha<=0) particles.splice(i,1);
  }
  requestAnimationFrame(animate);
}
animate();
setInterval(createFirework,200);
</script>
</body>
</html>
