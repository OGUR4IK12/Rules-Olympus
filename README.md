<!doctype html>
<html lang="ru">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Project_Olympus — Правила сервера</title>
  <style>
    :root{
      --bg:#05060a;
      --panel:#0b0d12cc;
      --neon: #b7ff3a; /* лаймовый */
      --neon-weak: rgba(183,255,58,0.15);
      --glass: rgba(255,255,255,0.02);
      --accent: linear-gradient(90deg, rgba(183,255,58,0.12), rgba(255,255,58,0.05));
      --radius:16px;
      --shadow: 0 6px 30px rgba(0,0,0,0.7), 0 0 30px rgba(183,255,58,0.06);
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, 'Helvetica Neue', Arial;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      min-height:100vh;
      background: radial-gradient(800px 400px at 10% 10%, rgba(24,26,28,0.6), transparent),
                  radial-gradient(600px 300px at 90% 90%, rgba(11,13,18,0.6), transparent),
                  var(--bg);
      color:#dfe6d0;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      padding:32px;
      display:flex;
      align-items:center;
      justify-content:center;
    }

    .container{
      width:100%;
      max-width:980px;
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border-radius:24px;
      padding:28px;
      box-shadow:var(--shadow);
      border:1px solid rgba(183,255,58,0.08);
      position:relative;
      overflow:hidden;
      backdrop-filter: blur(6px) saturate(120%);
    }

    header{
      display:flex;
      gap:16px;
      align-items:center;
      margin-bottom:18px;
    }
    .logo{
      width:64px;height:64px;border-radius:12px;
      background: conic-gradient(from 180deg at 50% 50%, rgba(183,255,58,0.18), rgba(255,255,58,0.05));
      display:flex;align-items:center;justify-content:center;
      box-shadow:0 6px 18px rgba(183,255,58,0.06) inset;
      border:1px solid rgba(183,255,58,0.12);
      flex:0 0 64px;
    }
    .logo h1{font-size:18px;margin:0;color:var(--neon);text-shadow:0 0 10px rgba(183,255,58,0.35)}

    .title{
      display:flex;flex-direction:column;gap:4px;
    }
    .title .name{font-size:20px;color:var(--neon);letter-spacing:0.6px}
    .title .sub{font-size:12px;color:rgba(223,230,208,0.6)}

    .rules-wrap{
      display:grid;grid-template-columns: 1fr;gap:12px;
    }

    /* Accordion */
    .rule{
      background: linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.015));
      border-radius:14px;padding:12px;border:1px solid rgba(183,255,58,0.06);
      display:flex;gap:12px;align-items:flex-start;overflow:hidden;
    }
    .rule .left{
      width:64px;flex:0 0 64px;display:flex;flex-direction:column;align-items:center;
    }
    .rule .num{
      background:linear-gradient(180deg, rgba(183,255,58,0.12), rgba(183,255,58,0.06));
      border-radius:10px;padding:8px 10px;font-weight:700;color:var(--neon);
      box-shadow:0 6px 18px rgba(183,255,58,0.04);
      text-shadow:0 0 8px rgba(183,255,58,0.12);
    }
    .rule .titleline{font-weight:600;margin:0 0 6px 0}
    .rule .desc{color:rgba(223,230,208,0.85);margin:0}

    .rule button.toggle{
      all:unset;cursor:pointer;margin-left:auto;padding:8px;border-radius:10px;
      display:flex;align-items:center;gap:8px;font-weight:700;color:var(--neon);
      background:transparent;border:1px solid
