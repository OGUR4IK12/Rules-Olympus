<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Project_Olympus — Правила сервера (Нажмите  на кнопку *ПРАВИЛА*)</title>
<link rel="icon" href="favicon.ico" type="image/x-icon">
<style>
:root{
  --bg:#05060a;
  --panel:rgba(10,12,14,0.6);
  --lime:#b7ff3a;
  --lime-weak: rgba(183,255,58,0.12);
  --cyan:#3ef0ff;
  --orange:#ff8a2b;
  --glass: rgba(255,255,255,0.03);
  --radius:14px;
  --shadow: 0 10px 40px rgba(0,0,0,0.7);
  font-family: Inter, "Segoe UI", Roboto, Arial, sans-serif;
}
html,body{height:100%;margin:0}
body{
  background: radial-gradient(1200px 600px at 10% 10%, rgba(24,26,28,0.6), transparent),
              radial-gradient(800px 400px at 90% 90%, rgba(11,13,18,0.6), transparent),
              var(--bg);
  color:#e8f0dd;
  -webkit-font-smoothing:antialiased;
  padding:28px;
  display:flex;
  justify-content:center;
  align-items:flex-start;
  gap:20px;
}
.wrap{
  width:100%;
  max-width:1050px;
  background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
  border-radius:18px;
  padding:24px;
  box-shadow:var(--shadow);
  border:1px solid rgba(183,255,58,0.06);
  position:relative;
  overflow:hidden;
  backdrop-filter: blur(6px) saturate(120%);
}
.glow-top{
  position:absolute;left:-10%;top:-8%;width:120%;height:220px;
  background:linear-gradient(90deg, transparent, var(--lime-weak), transparent);
  filter:blur(36px);opacity:.14;transform:rotate(-6deg);pointer-events:none;
}
header{display:flex;align-items:center;gap:16px;margin-bottom:18px}
.logo{width:72px;height:72px;border-radius:14px;display:flex;align-items:center;justify-content:center;
  background:conic-gradient(from 180deg at 50% 50%, rgba(183,255,58,0.12), rgba(62,240,255,0.06));
  border:1px solid rgba(183,255,58,0.12);
  box-shadow:0 6px 18px rgba(183,255,58,0.05) inset;
  flex:0 0 72px;
}
.logo h1{margin:0;color:var(--lime);text-shadow:0 0 10px rgba(183,255,58,0.25);font-size:20px}
.title{display:flex;flex-direction:column}
.title .name{color:var(--lime);font-size:20px;font-weight:700}
.title .sub{color:rgba(232,240,221,0.75);font-size:13px}
.top-controls{display:flex;gap:12px;margin:12px 0 20px}
.tab{
  padding:10px 16px;border-radius:12px;font-weight:700;cursor:pointer;border:1px solid transparent;
  display:inline-flex;align-items:center;gap:10px;text-decoration:none;color:inherit;
  box-shadow:0 8px 20px rgba(0,0,0,0.45);
  transition:transform .18s ease, box-shadow .18s ease;
  user-select:none;
}
.tab:active{transform:translateY(1px)}
.tab.cyan{background:linear-gradient(90deg, rgba(62,240,255,0.12), rgba(62,240,255,0.06)); color:var(--cyan); border:1px solid rgba(62,240,255,0.12); text-shadow:0 0 8px rgba(62,240,255,0.06)}
.tab.orange{background:linear-gradient(90deg, rgba(255,138,43,0.12), rgba(255,138,43,0.06)); color:var(--orange); border:1px solid rgba(255,138,43,0.12)}
.rules{display:grid;grid-template-columns:1fr;gap:12px;}
.card{
  background: linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.015));
  border-radius:12px;padding:12px;border:1px solid rgba(183,255,58,0.06);
  overflow:hidden;position:relative;
}
.card .head{display:flex;align-items:center;gap:12px}
.num{
  width:56px;height:56px;border-radius:10px;display:flex;align-items:center;justify-content:center;
  background:linear-gradient(180deg, rgba(183,255,58,0.08), rgba(183,255,58,0.03));
  color:var(--lime);font-weight:800;box-shadow:0 6px 18px rgba(183,255,58,0.04);
}
.meta{flex:1}
.meta .ttl{font-weight:700;font-size:16px;color:var(--lime)}
.meta .short{font-size:13px;color:rgba(232,240,221,0.8)}
.toggle{
  all:unset;cursor:pointer;padding:8px 12px;border-radius:10px;background:transparent;color:var(--lime);
  border:1px solid rgba(183,255,58,0.06);font-weight:700;
}
.detail{
  max-height:0;opacity:0;transform:translateY(-8px);
  transition: max-height .36s cubic-bezier(.2,.9,.2,1), opacity .28s ease, transform .28s ease;
  overflow:hidden;margin-top:10px;padding:0 6px;
}
.detail.open{
  opacity:1;transform:none;padding:10px 6px 6px 6px;
}
.detail p{margin:0 0 8px 0;color:rgba(232,240,221,0.95);line-height:1.45}
footer{display:flex;flex-direction:column;gap:6px;margin-top:18px;border-top:1px dashed rgba(183,255,58,0.06);padding-top:12px}
.footer-main{display:flex;justify-content:space-between;align-items:center;gap:12px;flex-wrap:wrap}
.creator{color:var(--lime);font-weight:700}
.rights{color:rgba(232,240,221,0.85);font-weight:600}
.small{font-size:12px;color:rgba(232,240,221,0.6)}
@media (max-width:720px){
  .logo{width:58px;height:58px}
  .num{width:48px;height:48px}
  body{padding:16px}
}
</style>
</head>
<body>
<div class="wrap" role="main" aria-labelledby="title">
  <div class="glow-top" aria-hidden="true"></div>
  <header>
    <div class="logo" aria-hidden="true"><h1 style="font-size:18px;margin:0">PO</h1></div>
    <div class="title">
      <div id="title" class="name">Project_Olympus — Правила сервера</div>
      <div class="sub">Создатель: Wizixc1</div>
    </div>
  </header>

  <div class="top-controls" role="toolbar" aria-label="Навигация">
    <div class="tab cyan" onclick="showInfo()">ИНФОРМАЦИЯ</div>
    <div class="tab orange" onclick="showRules()">ПРАВИЛА</div>
    <div class="tab cyan" onclick="openTelegram()">НАШ ТГ</div>
  </div>

  <div id="info" style="display:block;margin-bottom:14px">
    <div style="padding:12px;border-radius:12px;background:linear-gradient(90deg, rgba(62,240,255,0.03), rgba(183,255,58,0.03));border:1px solid rgba(62,240,255,0.06);">
      <strong>О сервере:</strong> Project_Olympus — это дружелюбный майнкрафт-сервер с упором на честную игру и уважение. Следуйте правилам и получайте удовольствие от геймплея!
    </div>
  </div>

  <section id="rules-section" class="rules" aria-label="Список правил" style="display:none">

    <!-- Правило 1 -->
    <article class="card" data-i="1">
      <div class="head">
        <div class="num">1</div>
        <div class="meta">
          <div class="ttl">Уважение и вежливость</div>
          <div class="short">Никаких оскорблений, угроз или дискриминации.</div>
        </div>
        <button class="toggle" aria-expanded="false">Развернуть ▾</button>
      </div>
      <div class="detail" id="d-1">
        <p><strong>1.1</strong> Незнание правил не освобождает от ответственности.</p>
        <p><strong>1.2</strong> Оскорбления, расизм, сексизм и угрозы караются предупреждением, временным или пожизненным баном.</p>
      </div>
    </article>

    <!-- Правило 2 -->
    <article class="card" data-i="2">
      <div class="head">
        <div class="num">2</div>
        <div class="meta">
          <div class="ttl">Запрет на читы и стороннее ПО</div>
          <div class="short">Полный запрет на чит-моды и инструменты с преимуществом.</div>
        </div>
        <button class="toggle" aria-expanded="false">Развернуть ▾</button>
      </div>
      <div class="detail" id="d-2">
        <p>Использование X-Ray, автокликеров, макросов, хаков и любых модов, дающих преимущество — строго запрещено. Наказание: вечный бан.</p>
      </div>
    </article>

    <!-- Правило 3 -->
    <article class="card" data-i="3">
      <div class="head">
        <div class="num">3</div>
        <div class="meta">
          <div class="ttl">Запрет на эксплойты и баги</div>
          <div class="short">Не используйте баги для выгоды — сообщайте администрации.</div>
        </div>
        <button class="toggle" aria-expanded="false">Развернуть ▾</button>
      </div>
      <div class="detail" id="d-3">
        <p>Если вы нашли баг — немедленно сообщите. Использование багов для личной выгоды приведёт к наказанию и возможной отмене незаконных достижений.</p>
      </div>
    </article>

    <!-- Правило 4 -->
    <article class="card" data-i="4">
      <div class="head">
        <div class="num">4</div>
        <div class="meta">
          <div class="ttl">Честная торговля и обмены</div>
          <div class="short">Мошенничество на торговле запрещено.</div>
        </div>
        <button class="toggle" aria-expanded="false">Развернуть ▾</button>
      </div>
      <div class="detail" id="d-4">
        <p>Обман в торговле, фейки-предоплаты и мошенничество караются компенсацией пострадавшему и санкциями против нарушителя.</p>
      </div>
    </article>

    <!-- Правило 5 -->
    <article class="card" data-i="5">
      <div class="head">
        <div class="num">5</div>
        <div class="meta">
          <div class="ttl">Никакой рекламы и спама</div>
          <div class="short">Запрещена реклама других серверов, фальшивая реклама и спам в чатах.</div>
        </div>
        <button class="toggle" aria-expanded="false">Развернуть ▾</button>
      </div>
      <div class="detail" id="d-5">
        <p>Реклама без разрешения — кик/депортация. Повторный спам может привести к долгому бану.</p>
      </div>
    </article>

    <!-- Правило 6 -->
    <article class="card" data-i="6">
      <div class="head">
        <div class="num">6</div>
        <div class="meta">
          <div class="ttl">Нельзя выдавать себя за администрацию</div>
          <div class="short">Имитация модераторов/админов запрещена.</div>
        </div>
        <button class="toggle" aria-expanded="false">Развернуть ▾</button>
      </div>
      <div class="detail" id="d-6">
        <p>Выдача себя за сотрудника сервера для получения преимуществ карается баном и удалением всех неправомерных привилегий.</p>
      </div>
    </article>

    <!-- Правило 7 -->
    <article class="card" data-i="7">
      <div class="head">
        <div class="num">7</div>
        <div class="meta">
          <div class="ttl">Приватность и безопасность</div>
          <div class="short">Не публикуйте личные данные — свои или чужие.</div>
        </div>
        <button class="toggle" aria-expanded="false">Развернуть ▾</button>
      </div>
      <div class="detail" id="d-7">
        <p>Разглашение личной информации (телефоны, адреса, пароли) приведёт к немедленному удалению контента и возможному бану.</p>
      </div>
    </article>

    <!-- Правило 8 -->
    <article class="card" data-i="8">
      <div class="head">
        <div class="num">8</div>
        <div class="meta">
          <div class="ttl">Не создавайте лаги и разрушительные механизмы</div>
          <div class="short">Фарм-механизмы, вызывающие лаги, запрещены.</div>
        </div>
        <button class="toggle" aria-expanded="false">Развернуть ▾</button>
      </div>
      <div class="detail" id="d-8">
        <p>Массовые редстон-установки, циклические машины и конструкции, приводящие к падению производительности сервера — подлежат удалению; автор может быть наказан.</p>
      </div>
    </article>

    <!-- Правило 9 -->
    <article class="card" data-i="9">
      <div class="head">
        <div class="num">9</div>
        <div class="meta">
          <div class="ttl">Следуйте указаниям администрации</div>
          <div class="short">Решения модераторов обязательны к исполнению.</div>
        </div>
        <button class="toggle" aria-expanded="false">Развернуть ▾</button>
      </div>
      <div class="detail" id="d-9">
        <p>Если вы считаете решение несправедливым — подавайте апелляцию через официальный канал. Пока апелляция рассматривается, решение администрации действует.</p>
      </div>
    </article>

    <!-- Правило 10 -->
    <article class="card" data-i="10">
      <div class="head">
        <div class="num">10</div>
        <div class="meta">
          <div class="ttl">Будьте честны и справедливы</div>
          <div class="short">Обман и несправедливые действия в игре запрещены.</div>
        </div>
        <button class="toggle" aria-expanded="false">Развернуть ▾</button>
      </div>
      <div class="detail" id="d-10">
        <p>Нарушение честной игры может привести к предупреждению или бану. Всегда играйте по правилам сервера.</p>
      </div>
    </article>

  </section>

  <footer>
    <div class="footer-main">
      <div class="creator">© 2025 Project_Olympus — Создатель: Wizixc1 (Александ.К.С)</div>
      <div class="rights">Все права защищены. Любая копировка правил запрещена без согласия владельца.</div>
    </div>
    <div class="small">Обновлено: 31.10.2025</div>
     <div class="small">Уведомление: Project_Olympus не связан с Mojang или Microsoft. Все права на игры и логотипы принадлежат их владельцам.</div>
  </footer>
</div>

<script>
  // Аккордеон
  document.querySelectorAll('.card').forEach(card=>{
    const btn = card.querySelector('.toggle');
    const detail = card.querySelector('.detail');
    btn.addEventListener('click', ()=>{
      const open = detail.classList.toggle('open');
      btn.setAttribute('aria-expanded', open);
      btn.textContent = open ? 'Свернуть ▴' : 'Развернуть ▾';
      detail.style.maxHeight = open ? detail.scrollHeight+'px' : '0px';
    });
  });

  // Открыть первое правило по умолчанию
  const first = document.querySelector('.card[data-i="1"]');
  if(first){
    const btn = first.querySelector('.toggle');
    const detail = first.querySelector('.detail');
    detail.classList.add('open');
    detail.style.maxHeight = detail.scrollHeight+'px';
    btn.setAttribute('aria-expanded','true');
    btn.textContent = 'Свернуть ▴';
  }

  // Кнопки сверху
  function showInfo(){
    document.getElementById('info').style.display='block';
    document.getElementById('rules-section').style.display='none';
  }
  function showRules(){
    document.getElementById('info').style.display='none';
    document.getElementById('rules-section').style.display='block';
    document.getElementById('rules-section').scrollIntoView({behavior:'smooth'});
  }
  function openTelegram(){
    window.open('https://t.me/Olympus_Project2025', '_blank');
  }

  // Поддержка клавиатуры
  document.querySelectorAll('.toggle').forEach(btn=>{
    btn.tabIndex=0;
    btn.addEventListener('keydown', e=>{
      if(e.key==='Enter'||e.key===' '){ e.preventDefault(); btn.click(); }
    });
  });
</script>
</body>
</html>
