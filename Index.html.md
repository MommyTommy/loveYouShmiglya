Index.html  
  
  
<!DOCTYPE html>  
<html lang="ru">  
<head>  
<meta charset="UTF-8" />  
<title>Будешь моей валентинкой? ❤️</title>  
  
<style>  
body{  
  margin:0;  
  overflow:hidden;  
  height:100vh;  
  
  /* РОЗОВЫЙ ФОН ВСЕГДА */  
  background: linear-gradient(135deg,#ffd6e0,#ffc2d1,#ffe5ec);  
  
  font-family:"Comic Sans MS", cursive;  
  display:flex;  
  justify-content:center;  
  align-items:center;  
  flex-direction:column;  
  text-align:center;  
}  
  
/* заголовок */  
h1{  
  color:#ff2e63;  
  font-size:38px;  
  text-shadow:0 0 12px #ff8fab;  
}  
  
/* фразы */  
#phrase{  
  height:30px;  
  font-size:20px;  
  margin:10px;  
}  
  
/* гифка */  
img{  
  width:260px;  
  border-radius:20px;  
  margin:20px;  
  box-shadow:0 10px 25px rgba(0,0,0,0.15);  
}  
  
/* кнопки */  
.buttons{  
  display:flex;  
  gap:20px;  
}  
  
button{  
  padding:15px 35px;  
  font-size:22px;  
  border:none;  
  border-radius:15px;  
  cursor:pointer;  
  transition:0.25s;  
}  
  
#yes{  
  background:#ff4d6d;  
  color:white;  
}  
  
#no{  
  background:#999;  
  color:white;  
}  
  
/* ❤️ сердечки */  
.heart{  
  position:fixed;  
  top:-20px;  
  pointer-events:none;  
  opacity:0.45;  
  animation:fall linear forwards;  
  z-index:9999;  
}  
  
@keyframes fall{  
  to{  
    transform:translateY(120vh);  
    opacity:0;  
  }  
}  
</style>  
</head>  
  
  
  
<body>  
  
<h1>Ты будешь моей валентинкой? 💘</h1>  
  
<div id="phrase"></div>  
  
<img src="https://media3.giphy.com/media/v1.Y2lkPTZjMDliOTUyb3l4aDhrbzltMjF4bWxmNjN3dDlwYjF5bXBqZmZhYjdqbXVxZmN6NiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/XjXXDwkTMtl1S/giphy.gif">  
  
<div class="buttons">  
  <button id="yes">Да ❤️</button>  
  <button id="no">Нет</button>  
</div>  
  
  
  
<script>  
const noBtn = document.getElementById("no");  
const yesBtn = document.getElementById("yes");  
const phrase = document.getElementById("phrase");  
  
let noCount = 0;  
let yesScale = 1;  
let noScale = 1;  
  
const phrases = [  
"тока попробуй -_-",  
"ну эй 😡",  
"ты угораешь что ли, шмыгля блин",  
"Я щас прилечу, буду бить тебя",  
"ТЫ РЕАЛЬНО НА СТОЛЬКО МЕНЯ НЕ ЛЮБИШЬ?!",  
"я обидевся"  
];  
  
  
// ❤️ НЕТ уменьшается  
noBtn.addEventListener("click", () => {  
  
  if(noCount < phrases.length){  
    phrase.innerText = phrases[noCount];  
  }  
  
  noCount++;  
  
  // ДА растёт  
  yesScale += 0.25;  
  yesBtn.style.transform = `scale(${yesScale})`;  
  
  // НЕТ сжимается  
  noScale -= 0.15;  
  
  if(noScale <= 0.25){  
    noBtn.innerText = "🥺";  
    noScale = 0.25;  
  }  
  
  noBtn.style.transform = `scale(${noScale})`;  
});  
  
  
// ❤️ ДА — финал + сердечный дождь  
yesBtn.addEventListener("click", () => {  
  
  document.body.innerHTML = `  
    <div style="  
      height:100vh;  
      display:flex;  
      flex-direction:column;  
      justify-content:center;  
      align-items:center;  
      text-align:center;  
      background: linear-gradient(135deg,#ffd6e0,#ffc2d1,#ffe5ec);  
    ">  
      <h1 style="color:#ff2e63;font-size:34px">  
      УРААА, Я ЗНАЛА ЧТО ТЫ МЕНЯ ЛЮБИШЬ,<br>  
      МОЙ САМЫЙ СЛАДКИЙ, КРАСИВЫЙ И ЛЮБИМЫЙ МУЖЧИНА НА СВЕТЕ.<br>  
      Люблю тебя!! ❤️❤️❤️❤️  
      </h1>  
  
      <img src="https://media0.giphy.com/media/v1.Y2lkPTZjMDliOTUyejJ5NG02eTl6cjlmMXhxdzBxMTJvZXZyb2JtcTU3Z3N3bHdueTV2ZyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/uKvAWApE3vWL1MAASf/giphy.gif" width="300">  
    </div>  
  `;  
  
  startHearts(); // запускаем дождик  
});  
  
  
// ❤️ дождь сердечек ПО ВСЕМУ ЭКРАНУ  
function startHearts(){  
  setInterval(() => {  
  
    const heart = document.createElement("div");  
    heart.className = "heart";  
    heart.innerText = "❤️";  
  
    heart.style.left = Math.random()*100 + "vw";  
    heart.style.fontSize = (14 + Math.random()*30) + "px";  
    heart.style.animationDuration = (3 + Math.random()*4) + "s";  
  
    document.body.appendChild(heart);  
  
    setTimeout(() => heart.remove(), 7000);  
  
  }, 100);  
}  
</script>  
  
</body>  
</html>  
