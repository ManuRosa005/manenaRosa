<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Protótipo Login Bem Feito</title>
<link rel="stylesheet" href="style.css" />
</head>
<body>

<div class="container">
  <!-- Tela 01 -->
  <div class="screen active" id="screen1">
    <div class="hamburger">
      <div class="bar"></div>
      <div class="bar"></div>
      <div class="bar"></div>
    </div>
    <button onclick="goToScreen(2)">Próximo</button>
  </div>

  <!-- Tela 02 -->
  <div class="screen" id="screen2">
    <div class="hamburger">
      <div class="bar"></div>
      <div class="bar"></div>
      <div class="bar"></div>
    </div>
    <h2>Bem Feito</h2>
    <button onclick="goToScreen(3)">Próximo</button>
  </div>

  <!-- Tela 03 -->
  <div class="screen" id="screen3">
    <h2>Login</h2>
    <input type="text" placeholder="Usuário" />
    <input type="password" placeholder="Senha" />
    <button onclick="alert('Entrando...')">Entrar</button>
  </div>
</div>

<script src="script.js"></script>
</body>
</html>
body, html {
  margin: 0; padding: 0; height: 100%; font-family: Arial, sans-serif;
  background: #fff3f8;
  display: flex; justify-content: center; align-items: center;
}
.container {
  width: 320px; height: 480px; background: white; border-radius: 10px;
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
  overflow: hidden; position: relative;
}
.screen {
  position: absolute; width: 100%; height: 100%; top: 0; left: 0;
  display: flex; flex-direction: column; justify-content: center; align-items: center;
  transition: opacity 0.6s ease;
}
.screen:not(.active) {
  opacity: 0; pointer-events: none;
}
.hamburger {
  width: 60px; height: 50px; margin-bottom: 40px;
  position: relative;
}
.bar {
  height: 6px; background-color: #f06292; margin: 6px 0; border-radius: 3px;
}
h2 {
  color: #d81b60; margin-bottom: 40px; font-weight: 700;
}
input[type="text"], input[type="password"] {
  width: 80%; padding: 12px; margin-bottom: 20px;
  border: 2px solid #f06292; border-radius: 6px;
  font-size: 16px;
}
button {
  background-color: #d81b60; border: none; color: white;
  padding: 12px 30px; border-radius: 6px;
  font-size: 16px; cursor: pointer;
  transition: background-color 0.3s ease;
}
button:hover {
  background-color: #b0144a;
}
function goToScreen(num) {
  const screens = document.querySelectorAll('.screen');
  screens.forEach(screen => screen.classList.remove('active'));
  document.getElementById('screen' + num).classList.add('active');
}
