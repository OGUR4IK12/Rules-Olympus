<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Project_Olympus — Правила сервера</title>
  <style>
    body {
      margin: 0;
      font-family: "Orbitron", sans-serif;
      background: radial-gradient(circle at center, #001100 10%, #000000 90%);
      color: #bfff00;
      overflow-x: hidden;
    }

    h1, h2 {
      text-align: center;
      text-shadow: 0 0 15px #00ff66, 0 0 25px #00ff33;
    }

    h1 {
      font-size: 40px;
      margin-top: 40px;
      letter-spacing: 2px;
      animation: neonPulse 3s infinite;
    }

    h2 {
      font-size: 20px;
      margin-bottom: 25px;
      color: #aaffaa;
    }

    .buttons {
      display: flex;
      justify-content: center;
      gap: 20px;
      margin: 25px 0;
    }

    .button {
      background: rgba(0, 255, 100, 0.1);
      border: 2px solid #00ff66;
      color: #00ff66;
      padding: 12px 25px;
      border-radius: 12px;
      font-weight: bold;
      cursor: pointer;
      transition: 0.3s;
      text-transform: uppercase;
      text-shadow: 0 0 10px #00ff66;
    }

    .button:hover {
      background: #00ff66;
      color: black;
      box-shadow: 0 0 20px #00ff66, 0 0 40px #00ff66;
      transform: scale(1.05);
    }

    details.card {
      background: rgba(0, 20, 0, 0.8);
      border: 1px solid #00ff66;
      border-radius: 15px;
      padding: 20px;
      margin: 15px auto;
      width: 85%;
      max-width: 700px;
      color: #bfff00;
      box-shadow: 0 0 15px #00ff66;
      transition: 0.4s;
    }

    details.card summary {
      cursor: pointer;
      font-size: 20px;
      font-weight: bold;
      text-shadow: 0 0 10px #00ff33;
      outline: none;
    }

    details.card[open] {
      box-shadow: 0 0 30px #00ff66;
      transform: scale(1.02);
    }

    details.card p {
      margin-top: 10px;
      color: #dfff9f;
      line-height: 1.6;
    }

    footer {
      margin-top: 60px;
      text-align: center;
      color: #66ff99;
      font-size: 14px;
      text-shadow: 0 0 10px #00ff66;
    }

    @keyframes neonPulse {
      0%, 100% { text-shadow: 0 0 10px #00ff66, 0 0 20px #00ff66; }
      50% { text-shadow: 0 0 30px #00ff66, 0 0 50px #00ff33; }
    }
  </style>
</head>
<body>
  <h1>Project_Olympus</h1>
  <h2>АНАРХИЯ — ПРАВИЛА СЕРВЕРА</h2>

  <div class="buttons">
    <div class="button" onclick="showError()">ТЕЛЕГРАМ</div>
  </div>

  <details class="card"><summary>1. Незнание правил</summary><p>Незнание правил не освобождает от ответственности. Играй с умом.</p></details>

  <details class="card"><summary>2. Уважение к игрокам</summary><p>Анархия не значит токсичность. Не оскорбляй игроков и не переходи на личности.</p></details>

  <details class="card"><summary>3. Использование читов</summary><p>Читеры не уважаются. Любые читы = бан навсегда.</p></details>

  <details class="card"><summary>4. Использование багов</summary><p>Запрещено использовать баги ядра, дюпы и лаг-машины. Всё ради стабильности сервера.</p></details>

  <details class="card"><summary>5. Реклама и спам</summary><p>Реклама других серверов или флуда в чате — мгновенный мут/бан.</p></details>

  <details class="card"><summary>6. Лаг-машины и крашеры</summary><p>Создание устройств, вызывающих лаги или краш сервера — бан без разбора.</p></details>

  <details class="card"><summary>7. DDoS и угрозы</summary><p>Любые попытки DDoS или угрозы в адрес сервера — моментальный перманентный бан.</p></details>

  <details class="card"><summary>8. Использование альте-аккаунтов</summary><p>Запрещено использовать альты для обхода наказаний. Все аккаунты будут забанены.</p></details>

  <details class="card"><summary>9. Эксплойты и модификации клиента</summary><p>Разрешены только визуальные моды (оптимизация, шейдеры, миникарта без рентгена).</p></details>

</details>

  <footer>
    © 2025 Project_Olympus. Создатель: Wizixc.<br>
    Все права защищены. Любое копирование правил запрещено.
  </footer>

  <script>
    function showError() {
      alert("❌ Телеграм ещё не готов. Попробуй позже 😢");
    }
  </script>
</body>
</html>
