<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Project_Olympus — Правила сервера</title>
<style>
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: url(https://pbs.twimg.com/media/F8a5aqAXcAAMEAh.jpg:large) no-repeat center center fixed;
  background-size: cover;
  color: #bfff00;
}

.overlay {
  background: rgba(0, 0, 0, 0.6);
  padding: 40px 20px;
  min-height: 100vh;
}

h1 {
  font-size: 36px;
  margin-bottom: 10px;
  text-align: center;
  text-shadow: 0 0 10px #00ff66, 0 0 20px #00ff33;
  animation: neonPulse 3s infinite;
}

h2 {
  font-size: 20px;
  color: #ccc;
  text-align: center;
}

@keyframes neonPulse {
  0%,100% { text-shadow: 0 0 10px #00ff66, 0 0 20px #00ff33; }
  50% { text-shadow: 0 0 30px #00ff66, 0 0 40px #00ff33; }
}

.buttons {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin: 20px 0;
}

.button {
  background-color: rgba(0,255,100,0.1);
  padding: 10px 20px;
  border-radius: 8px;
  text-transform: uppercase;
  font-weight: bold;
  cursor: pointer;
  border: 2px solid #00ff66;
  color: #00ff66;
  text-shadow: 0 0 5px #00ff66;
  transition: 0.3s;
}

.button:hover {
  background-color: #00ff66;
  color: black;
  box-shadow: 0 0 20px #00ff66, 0 0 40px #00ff33;
  transform: scale(1.05);
}

details.card {
  background: rgba(0, 20, 0, 0.8);
  color: #bfff00;
  padding: 20px;
  width: 90%;
  max-width: 700px;
  border-radius: 15px;
  box-shadow: 0 5px 15px rgba(0,255,100,0.3);
  font-size: 16px;
  margin: 15px auto;
  cursor: pointer;
  transition: 0.3s;
}

details.card summary {
  font-weight: bold;
  font-size: 18px;
  cursor: pointer;
  outline: none;
}

details.card[open] {
  box-shadow: 0 0 30px #00ff66;
  transform: scale(1.02);
}

details.card p {
  margin-top: 10px;
  font-weight: normal;
  color: #dfff9f;
}

footer {
  margin-top: 40px;
  font-size: 12px;
  color: #aaa;
  text-align: center;
  text-shadow: 0 0 5px #00ff66;
}
</style>
</head>
<body>
<div class="overlay">
  <h1>Project_Olympus</h1>
  <h2>Правила сервера</h2>

  <div class="buttons">
    <div class="button" onclick="showError()">ТЕЛЕГРАМ</div>
  </div>

  <details class="card"><summary>1. Незнание правил</summary><p>Незнание правил не освобождает вас от ответственности.</p></details>

  <details class="card"><summary>2. Образа администрации и игроков</summary><p>Буллинг и оскорбления запрещены. Наказание: депортация 4 дня.</p></details>

  <details class="card"><summary>3. Использование читов</summary><p>Использование читов или стороннего ПО запрещено. Депортация навсегда.</p></details>

  <details class="card"><summary>4. Использование багов</summary><p>Использование багов и недоработок сервера запрещено. Наказание: депортация 2 дня.</p></details>

  <details class="card"><summary>5. PvP без причины</summary><p>Рандомное убийство игроков без RP-сцены запрещено. Наказание: депортация 12 часов.</p></details>

  <details class="card"><summary>6. Анархия и хаос</summary><p>Можно атаковать и разрушать без ограничений, кроме читов и багов. Свобода действий в рамках игры.</p></details>

  <details class="card"><summary>7. Реклама и спам</summary><p>Любая реклама и спам запрещены. Штраф: депортация 4 дня.</p></details>

  <details class="card"><summary>8. Нон-РП поведение</summary><p>Все действия игрока должны быть логичными в рамках игры, но сервер анархичный — полная свобода действий.</p></details>

  <details class="card"><summary>9. Использование чужих аккаунтов</summary><p>Использование чужих аккаунтов запрещено. Наказание: бан.</p></details>

  <details class="card"><summary>10. Уважение к другим игрокам</summary><p>Хотя сервер анархичный, не переходи на личности вне игрового процесса. Помни о базовой вежливости.</p></details>

  <footer>© 2025 Project_Olympus. Создатель: Wizixc. Все права защищены. Любая копировка правил запрещена.</footer>
</div>

<script>
function showError() {
  alert("❌ Телеграм ещё не готов. Попробуй позже 😢");
}
</script>
</body>
</html>
