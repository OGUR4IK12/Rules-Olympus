<!doctype html>
<html lang="ru">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Project_Olympus — Правила сервера</title>
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

  /* neon decorative */
  .glow-top{
    position:absolute;left:-10%;top:-8%;width:120%;height:220px;
    background:linear-gradient(90deg, transparent, var(--lime-weak), transparent);
    filter:blur(36px);opacity:.14;transform:rotate(-6deg);pointer-events:none;
  }

  header{display:flex;align-items:center;gap:16px;margin-bottom:18px}
  .logo{
    width:72px;height:72px;border-radius:14px;display:flex;align-items:center;justify-content:center;
    background:conic-gradient(from 180deg at 50% 50%, rgba(183,255,58,0.12), rgba(62,240,255,0.06));
    border:1px solid rgba(183,255,58,0.12);
    box-shadow:0 6px 18px rgba(183,255,58,0.05) inset;
    flex:0 0 72px;
  }
  .logo h1{margin:0;color:var(--lime);text-shadow:0 0 10px rgba(183,255,58,0.25);font-size:20px}

  .title{display:flex;flex-direction:column}
  .title .name{color:var(--lime);font-size:20px;font-weight:700}
  .title .sub{color:rgba(232,240,221,0.75);font-size:13px}

  /* buttons (вкладки) */
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

  /* rules list */
  .rules{
    display:grid;grid-template-columns:1fr;gap:12px;
  }
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
    max-height:600px;opacity:1;transform:none;padding:10px 6px 6px 6px;
  }
  .detail p{margin:0 0 8px 0;color:rgba(232,240,221,0.95);line-height:1.45}

  /* footer */
  footer{display:flex;flex-direction:column;gap:6px;margin-top:18px;border-top:1px dashed rgba(183,255,58,0.06);padding-top:12px}
  .footer-main{display:flex;justify-content:space-between;align-items:center;gap:12px;flex-wrap:wrap}
  .creator{color:var(--lime);font-weight:700}
  .rights{color:rgba(232,240,221,0.85);font-weight:600}

  .small{font-size:12px;color:rgba(232,240,221,0.6)}

  /* responsive */
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
        <div class="sub">Создатель: Wizixc</div>
      </div>
    </header>

    <div class="top-controls" role="toolbar" aria-label="Навигация">
      <div class="tab cyan" onclick="showInfo()">ИНФОРМАЦИЯ</div>
      <div class="tab orange" onclick="showRules()">ПРАВИЛА</div>
      <div class="tab cyan" onclick="openTelegram()">НАШ ТГ</div>
    </div>

    <div id="info" style="display:block;margin-bottom:14px">
      <div style="padding:12px;border-radius:12px;background:linear-gradient(90deg, rgba(62,240,255,0.03), rgba(183,255,58,0.03));border:1px solid rgba(62,240,255,0.06);">
        <strong>О сервере:</strong> Project_Olympus — это дружелюбный майнкрафт-сервер с упором на честную игру и уважение. Следуйте правилам и получайте удовольствие!
      </div>
    </div>

    <section id="rules-section" class="rules" aria-label="Список правил">
      <!-- Rule 1 -->
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
          <p><strong>1.2</strong> Оскорбления, расизм, сексизм и любые угрозы караются предупреждением, временным или пожизненным баном в зависимости от тяжести.</p>
        </div>
      </article>

      <!-- Rule 2 -->
      <article class="card" data-i="2">
        <div class="head">
          <div class="num">2</div>
          <div class="meta">
            <div class="ttl">Запрет на читы и стороннее ПО</div>
            <div class="short">Полный запрет на все чит-моды и инструменты с преимуществом.</div>
          </div>
          <button class="toggle" aria-expanded="false">Развернуть ▾</button>
        </div>
        <div class="detail" id="d-2">
          <p>Использование X-Ray, автокликеров, макросов, хаков и любых модов, дающих преимущество — строго запрещено. Наказание: вечный бан при доказательствах.</p>
        </div>
      </article>

      <!-- Rule 3 -->
      <article class="card" data-i="3">
        <div class="head">
          <div class="num">3</div>
          <div class="meta">
            <div class="ttl">No grief — уважение к постройкам</div>
            <div class="short">Нельзя ломать или портить чужие постройки без разрешения.</div>
          </div>
          <button class="toggle" aria-expanded="false">Развернуть ▾</button>
        </div>
        <div class="detail" id="d-3">
          <p>Разрушение чужой собственности, кражи и саботаж караются восстановлением постройки за счёт нарушителя и баном/депортацией при повторе.</p>
        </div>
      </article>

      <!-- Rule 4 -->
      <article class="card" data-i="4">
        <div class="head">
          <div class="num">4</div>
          <div class="meta">
            <div class="ttl">Запрет на эксплойты и баги</div>
            <div class="short">Не используйте баги для выгоды — сообщайте администрации.</div>
          </div>
          <button class="toggle" aria-expanded="false">Развернуть ▾</button>
        </div>
        <div class="detail" id="d-4">
          <p>Если вы нашли баг — немедленно сообщите. Использование багов для личной выгоды приведёт к наказанию (депортация/бан) и возможной отмене незаконных достижений.</p>
        </div>
      </article>

      <!-- Rule 5 -->
      <article class="card" data-i="5">
        <div class="head">
          <div class="num">5</div>
          <div class="meta">
