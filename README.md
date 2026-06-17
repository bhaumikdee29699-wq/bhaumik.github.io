<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>For My Love ❤️</title>

<style>
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: linear-gradient(135deg, #ff4d6d, #ffb3c1);
  height: 100vh;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
}

.card {
  text-align: center;
  color: white;
  max-width: 500px;
}

h1 {
  font-size: 2.2rem;
}

p {
  font-size: 1.1rem;
}

.btn {
  padding: 12px 25px;
  border: none;
  border-radius: 25px;
  margin: 10px;
  cursor: pointer;
  font-size: 16px;
}

.yes {
  background: #00c853;
  color: white;
}

.no {
  background: #ff1744;
  color: white;
  position: absolute;
}

.heart {
  position: absolute;
  color: white;
  font-size: 20px;
  animation: float 6s linear infinite;
}

@keyframes float {
  0% { transform: translateY(100vh); opacity: 0; }
  50% { opacity: 1; }
  100% { transform: translateY(-10vh); opacity: 0; }
}
</style>
</head>

<body>

<div class="card">
  <h1>Hey My Love ❤️</h1>
  <p>I made this just for you. Will you stay mine forever?</p>

  <button class="btn yes" onclick="yesClick()">Yes 💖</button>
  <button class="btn no" id="noBtn" onmouseover="moveBtn()">No 💔</button>
</div>

<script>
function yesClick() {
  document.body.innerHTML = `
    <div style="text-align:center;color:white;">
      <h1>YAY!! ❤️</h1>
      <p>You just made me the happiest person alive 💕</p>
    </div>
  `;
}

// moving NO button
function moveBtn() {
  let x = Math.random() * (window.innerWidth - 100);
  let y = Math.random() * (window.innerHeight - 100);
  let btn = document.getElementById("noBtn");
  btn.style.left = x + "px";
  btn.style.top = y + "px";
}

// floating hearts
setInterval(() => {
  let heart = document.createElement("div");
  heart.innerHTML = "❤️";
  heart.className = "heart";
  heart.style.left = Math.random() * window.innerWidth + "px";
  heart.style.fontSize = (10 + Math.random() * 20) + "px";
  document.body.appendChild(heart);

  setTimeout(() => heart.remove(), 6000);
}, 300);
</script>

</body>
</html>
