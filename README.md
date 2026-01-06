
<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Yumrukla – Barış Oyunu</title>

<style>
body {
  background:#eee;
  font-family: Arial, sans-serif;
  text-align:center;
}

#container {
  margin-top:40px;
}

#face {
  width:220px;
  border-radius:50%;
  transition: filter 0.3s, transform 0.2s;
}

button {
  margin-top:25px;
  font-size:24px;
  padding:15px 30px;
}

#status {
  margin-top:15px;
  font-size:20px;
}
</style>
</head>

<body>

<h1>👊 Yumruk Oyunu</h1>

<div id="container">
  <img id="face" src="face.jpg">
</div>

<p id="status">Hazır mısın?</p>
<button onclick="punch()">👊 YUMRUK AT</button>

<audio id="sound">
  <source src="https://www.soundjay.com/human/punch-01.mp3" type="audio/mpeg">
</audio>

<script>
let count = 0;

function punch(){
  count++;
  const face = document.getElementById("face");
  const status = document.getElementById("status");
  const sound = document.getElementById("sound");

  sound.play();

  face.style.transform =
    "rotate("+(Math.random()*20-10)+"deg) scale(1.02)";

  let bruise = count * 8;
  face.style.filter =
    `brightness(${100-bruise}%) saturate(140%) hue-rotate(310deg)`;

  if(count < 5){
    status.textContent = count + ". yumruk! Ahh 😵";
  } else {
    status.textContent = "💖 Barış Modu Açıldı!";
    face.style.filter = "none";
  }
}
</script>

</body>
</html>
