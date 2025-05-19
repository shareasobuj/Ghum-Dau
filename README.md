# Ghum-Dau



<html lang="bn">
<head>
<meta charset="UTF-8">
<title>ঘুম দাও</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+Bengali:wght@400;700&display=swap');
*{box-sizing:border-box;padding:0;margin:0;font-family:'Noto Sans Bengali', sans-serif;}
body{display:flex;flex-direction:column;justify-content:center;align-items:center;height:100vh;background:linear-gradient(135deg,#0f2027,#203a43,#2c5364);color:#fff;text-align:center;}
h1{font-size:2.5rem;margin-bottom:1rem;}
button{background:#6A82FB;border:none;padding:0.75rem 2rem;border-radius:9999px;font-size:1rem;cursor:pointer;transition:transform 0.2s,box-shadow 0.2s;}
button:hover{transform:translateY(-2px);box-shadow:0 4px 12px rgba(0,0,0,0.3);}
button:active{transform:translateY(0);}
#breath-circle{width:200px;height:200px;border-radius:50%;background:rgba(255,255,255,0.1);display:flex;justify-content:center;align-items:center;margin:2rem auto;font-size:1.5rem;animation:breath 8s ease-in-out infinite;opacity:0;pointer-events:none;}
@keyframes breath{0%{transform:scale(0.7);}50%{transform:scale(1);}100%{transform:scale(0.7);}}
.controls{display:flex;gap:1rem;margin-top:1rem;}
footer{position:absolute;bottom:1rem;font-size:0.75rem;opacity:0.6;}
</style>
</head>
<body>
<h1>ঘুম দাও</h1>
<p>শান্তময় শব্দ ও শ্বাস-প্রশ্বাস ব্যায়ামের মাধ্যমে নিদ্রা সহায়ক অ্যাপ।</p>

<div id="breath-circle">শ্বাস নিন</div>

<div class="controls">
<button id="play">শব্দ চালু করুন</button>
<button id="breath">শ্বাস ব্যায়াম</button>
<button id="stop">বন্ধ করুন</button>
</div>

<footer>© 2025 ঘুম দাও</footer>

<audio id="audio" loop preload="auto">
  <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
</audio>


<script>
const audio=document.getElementById('audio');
const playBtn=document.getElementById('play');
const stopBtn=document.getElementById('stop');
const breathBtn=document.getElementById('breath');
const circle=document.getElementById('breath-circle');
let breathOn=false;

playBtn.onclick=()=>{audio.volume=0.5;audio.play();};
stopBtn.onclick=()=>{audio.pause();audio.currentTime=0;circle.style.opacity=0;breathOn=false;};
breathBtn.onclick=()=>{
  breathOn=!breathOn;
  circle.style.opacity=breathOn?1:0;
  circle.textContent='শ্বাস নিন';
  if(breathOn){
    let inhale=true;
    setInterval(()=>{
      circle.textContent=inhale?'শ্বাস নিন':'শ্বাস ছাড়ুন';
      inhale=!inhale;
    },4000);
  }
};
</script>
</body>
</html>
