# rslfhasion
Uma loja de roupa feminino
<title>RSL Fashion</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Bodoni+Moda:ital,opsz,wght@0,6..96,500;0,6..96,700;1,6..96,500&family=DM+Sans:wght@400;500;700&display=swap">
<style>
/* Layout: faixa de aviso, cabeçalho fixo com logo, hero em duas colunas, catálogo filtrável em grade, gaveta de sacola */
:root{
  --bg:#fff4f8;
  --surface:#ffffff;
  --fg:#3b1226;
  --muted:#8a5a70;
  --pink:#e8457f;
  --pink-deep:#b81f5b;
  --blush:#ffd6e5;
  --line:#f4c9da;
  --on-pink:#ffffff;
  --display:"Bodoni Moda","Didot","Times New Roman",serif;
  --body:"DM Sans",system-ui,-apple-system,"Segoe UI",sans-serif;
}
@media (prefers-color-scheme: dark){
  :root:not([data-theme="light"]){
    --bg:#1d0c15;--surface:#2a1220;--fg:#ffe9f1;--muted:#d19ab3;--pink:#ff6aa0;--pink-deep:#ff9ec1;--blush:#4a1d33;--line:#47203a;--on-pink:#2a0a18;color-scheme:dark;
  }
}
:root[data-theme="dark"]{
  --bg:#1d0c15;--surface:#2a1220;--fg:#ffe9f1;--muted:#d19ab3;--pink:#ff6aa0;--pink-deep:#ff9ec1;--blush:#4a1d33;--line:#47203a;--on-pink:#2a0a18;color-scheme:dark;
}
*{box-sizing:border-box}
body{background:var(--bg);color:var(--fg);font-family:var(--body);font-size:16px;line-height:1.55;padding-inline:0}
h1,h2,h3{font-family:var(--display);font-weight:500;margin:0;text-wrap:balance;line-height:1.1}
a{color:inherit}
button{font:inherit;cursor:pointer}
:focus-visible{outline:3px solid var(--pink);outline-offset:2px}
.wrap{max-width:1160px;margin-inline:auto;padding-inline:20px}

.notice{background:var(--pink);color:var(--on-pink);text-align:center;font-size:13px;letter-spacing:.06em;padding:8px 16px}

header.top{position:sticky;top:env(safe-area-inset-top,0px);z-index:20;background:var(--bg);border-bottom:1px solid var(--line)}
.bar{display:flex;align-items:center;gap:16px;padding-block:12px}
.logo{display:flex;align-items:center;gap:12px;text-decoration:none}
.logo svg{width:46px;height:46px;flex:none}
.logo .name{font-family:var(--display);font-size:24px;font-weight:700;letter-spacing:.04em;line-height:1}
.logo .name small{display:block;font-family:var(--body);font-size:10px;font-weight:500;letter-spacing:.32em;text-transform:uppercase;color:var(--pink-deep);margin-top:4px}
nav{margin-left:auto;display:flex;gap:22px;align-items:center;flex:none}
nav a{text-decoration:none;font-size:14px;font-weight:500;color:var(--muted)}
nav a:hover{color:var(--pink-deep)}
.bag-btn{display:flex;align-items:center;gap:8px;background:var(--fg);color:var(--bg);border:0;border-radius:999px;padding:10px 16px;font-weight:500;font-size:14px}
.bag-btn .count{background:var(--pink);color:var(--on-pink);border-radius:999px;min-width:22px;height:22px;display:grid;place-items:center;font-size:12px;font-weight:700;padding-inline:6px}
.links{display:flex;gap:22px}
@media(max-width:640px){nav .links{display:none}nav{gap:10px}.bar{gap:10px}.logo .name{font-size:21px;white-space:nowrap}.logo svg{width:40px;height:40px}.bag-btn{padding:9px 14px}}

.hero{display:grid;grid-template-columns:1.1fr .9fr;gap:40px;align-items:center;padding-block:56px 40px}
.hero>*{min-width:0}
.eyebrow{font-size:12px;letter-spacing:.28em;text-transform:uppercase;color:var(--pink-deep);font-weight:700}
.hero h1{font-size:clamp(40px,7vw,78px);margin-block:14px 18px}
.hero h1 em{color:var(--pink);font-style:italic}
.hero p{max-width:46ch;color:var(--muted);font-size:17px;margin:0 0 26px}
.cta-row{display:flex;gap:12px;flex-wrap:wrap}
.btn{border:0;border-radius:999px;padding:14px 26px;font-weight:700;font-size:15px;text-decoration:none;display:inline-block}
.btn.primary{background:var(--pink);color:var(--on-pink)}
.btn.primary:hover{background:var(--pink-deep);color:var(--on-pink)}
.btn.ghost{border:2px solid var(--fg);background:transparent;color:var(--fg)}
.hero-art{background:var(--blush);border-radius:200px 200px 24px 24px;aspect-ratio:4/5;max-width:100%;display:grid;place-items:center;position:relative;overflow:hidden}
.hero-art svg{width:78%;height:auto}
.hero-art .tag{position:absolute;bottom:18px;left:50%;transform:translateX(-50%);background:var(--surface);color:var(--fg);border-radius:999px;padding:8px 16px;font-size:13px;font-weight:500;white-space:nowrap;border:1px solid var(--line)}
@media(max-width:820px){.hero{grid-template-columns:1fr;padding-block:36px 24px}.hero-art{max-width:360px;margin-inline:auto;width:100%}}

.perks{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:12px 24px;padding-block:20px;border-block:1px solid var(--line);font-size:14px;color:var(--muted)}
.perks b{color:var(--fg);display:block;font-size:15px}

section.catalog{padding-block:64px 24px}
.sec-head{display:flex;justify-content:space-between;align-items:end;gap:16px;flex-wrap:wrap;margin-bottom:24px}
.sec-head h2{font-size:clamp(30px,5vw,46px)}
.sec-head p{margin:6px 0 0;color:var(--muted)}
.filters{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:28px}
.chip{border:1.5px solid var(--line);background:var(--surface);color:var(--fg);border-radius:999px;padding:8px 18px;font-size:14px;font-weight:500}
.chip[aria-pressed="true"]{background:var(--pink);border-color:var(--pink);color:var(--on-pink)}
.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(240px,1fr));gap:28px 20px}
.card{display:flex;flex-direction:column;gap:12px;min-width:0}
.thumb{background:var(--c,var(--blush));border-radius:18px;aspect-ratio:4/5;display:grid;place-items:center;position:relative;overflow:hidden;max-width:100%}
.thumb svg{width:68%;height:auto;transition:transform .35s ease}
.card:hover .thumb svg{transform:translateY(-4px) scale(1.03)}
.badge{position:absolute;top:12px;left:12px;background:var(--surface);color:var(--pink-deep);font-size:11px;font-weight:700;letter-spacing:.1em;text-transform:uppercase;padding:5px 10px;border-radius:999px}
.card h3{font-size:21px}
.meta{display:flex;justify-content:space-between;gap:8px;align-items:baseline;color:var(--muted);font-size:13px}
.price{font-family:var(--display);font-size:22px;color:var(--fg);font-weight:700}
.price s{font-family:var(--body);font-size:13px;color:var(--muted);font-weight:400;margin-left:6px}
.sizes{display:flex;gap:6px;flex-wrap:wrap}
.size{min-width:36px;height:34px;border:1.5px solid var(--line);background:var(--surface);color:var(--fg);border-radius:8px;font-size:13px;font-weight:500}
.size[aria-pressed="true"]{border-color:var(--pink-deep);background:var(--blush);color:var(--pink-deep);font-weight:700}
.add{background:var(--fg);color:var(--bg);border:0;border-radius:999px;padding:12px;font-weight:700;font-size:14px}
a.add{display:block;text-align:center;text-decoration:none}
.add:hover{background:var(--pink-deep);color:var(--on-pink)}

.about{margin-block:64px;background:var(--blush);border-radius:28px;padding:44px 28px;display:grid;grid-template-columns:1fr 1fr;gap:32px;align-items:center}
.about>*{min-width:0}
.about h2{font-size:clamp(28px,4.5vw,42px)}
.about p{color:var(--muted);margin:0 0 12px;max-width:52ch}
.about .stats{display:grid;grid-template-columns:repeat(2,1fr);gap:16px}
.stat{background:var(--surface);border-radius:18px;padding:20px}
.stat b{font-family:var(--display);font-size:34px;color:var(--pink-deep);display:block;line-height:1}
.stat span{font-size:13px;color:var(--muted)}
@media(max-width:760px){.about{grid-template-columns:1fr;padding:32px 20px}}

footer{border-top:1px solid var(--line);padding-block:36px 48px;color:var(--muted);font-size:14px}
footer .row{display:flex;justify-content:space-between;gap:24px;flex-wrap:wrap}
footer .name{font-family:var(--display);font-size:22px;color:var(--fg);font-weight:700}

.scrim{position:fixed;inset:0;background:rgba(40,8,24,.45);z-index:30;opacity:0;pointer-events:none;transition:opacity .25s}
.scrim.on{opacity:1;pointer-events:auto}
.drawer{position:fixed;top:0;right:0;bottom:0;width:min(420px,100%);background:var(--bg);z-index:31;transform:translateX(100%);transition:transform .3s ease;display:flex;flex-direction:column;padding:calc(18px + env(safe-area-inset-top,0px)) 20px calc(18px + env(safe-area-inset-bottom,0px));border-left:1px solid var(--line)}
.drawer.on{transform:none}
.drawer header{display:flex;justify-content:space-between;align-items:center;margin-bottom:12px}
.drawer h2{font-size:28px}
.x{background:none;border:0;font-size:28px;line-height:1;color:var(--fg);padding:4px 10px}
.items{flex:1;overflow-y:auto;display:flex;flex-direction:column;gap:14px;padding-block:8px}
.line{display:grid;grid-template-columns:64px 1fr auto;gap:12px;align-items:center}
.line .mini{background:var(--c);border-radius:12px;aspect-ratio:4/5;display:grid;place-items:center}
.line .mini svg{width:70%}
.line h4{margin:0;font-family:var(--display);font-size:17px;font-weight:500}
.line small{color:var(--muted)}
.qty{display:flex;align-items:center;gap:8px;margin-top:4px}
.qty button{width:26px;height:26px;border-radius:50%;border:1.5px solid var(--line);background:var(--surface);color:var(--fg);line-height:1}
.empty{color:var(--muted);text-align:center;padding:48px 12px}
.total{border-top:1px solid var(--line);padding-top:14px;display:flex;flex-direction:column;gap:12px}
.total .sum{display:flex;justify-content:space-between;font-size:18px}
.total .sum b{font-family:var(--display);font-size:26px}
.msg{background:var(--blush);color:var(--fg);border-radius:12px;padding:12px 14px;font-size:14px}
.pay{padding-block:24px 8px}
.pay-card{display:grid;grid-template-columns:220px 1fr;gap:28px;align-items:center;background:var(--surface);border:1px solid var(--line);border-radius:24px;padding:24px}
.pay-card>*{min-width:0}
.qr{background:#fff;border-radius:16px;padding:10px;width:100%;max-width:220px;aspect-ratio:1}
.qr svg{display:block;width:100%;height:100%}
.pay-info h3{font-size:30px;margin-block:6px 10px}
.pay-info p{margin:0 0 6px;color:var(--muted)}
.key{font-family:var(--display);font-size:clamp(24px,5vw,34px);font-weight:700;color:var(--pink-deep);letter-spacing:.04em;margin-bottom:16px;overflow-wrap:anywhere}
.pay-info .small{font-size:13px;margin-top:14px}
@media(max-width:640px){.pay-card{grid-template-columns:1fr;justify-items:center;text-align:center}.pay-info .cta-row{justify-content:center}}
.payview{display:flex;flex-direction:column;align-items:center;gap:10px;text-align:center}
.payview .qr{max-width:240px}
.payview b{font-family:var(--display);font-size:28px}
.payview small{color:var(--muted)}
.field{display:flex;flex-direction:column;gap:4px;width:100%;text-align:left;font-size:13px;color:var(--muted)}
.field input{font:inherit;font-size:16px;color:var(--fg);background:var(--surface);border:1.5px solid var(--line);border-radius:10px;padding:10px 12px;width:100%}
.alert{background:var(--blush);color:var(--fg);border-radius:14px;padding:14px 16px;text-align:left;font-size:14px;border:1.5px solid var(--pink)}
.alert b{font-family:var(--body);font-size:15px;display:block;margin-bottom:4px}
.sum-list{width:100%;text-align:left;font-size:14px;color:var(--muted);margin:0;padding:0;list-style:none;display:flex;flex-direction:column;gap:4px}
.orders{padding-block:40px 8px}
.table-wrap{overflow-x:auto;background:var(--surface);border:1px solid var(--line);border-radius:18px}
.table-wrap table{border-collapse:collapse;width:100%;min-width:640px;font-size:14px}
.table-wrap th{text-align:left;font-size:12px;letter-spacing:.1em;text-transform:uppercase;color:var(--muted);padding:12px 14px;border-bottom:1px solid var(--line)}
.table-wrap td{padding:12px 14px;border-bottom:1px solid var(--line);vertical-align:top}
.table-wrap tr:last-child td{border-bottom:0}
.table-wrap td.num{font-variant-numeric:tabular-nums;white-space:nowrap;font-weight:700}
.orders-note{color:var(--muted);font-size:13px;margin:0 0 14px}
.wa{position:fixed;right:16px;bottom:calc(16px + env(safe-area-inset-bottom,0px));z-index:25;display:flex;align-items:center;gap:8px;background:#25d366;color:#0b2e17;text-decoration:none;font-weight:700;font-size:14px;padding:12px 18px;border-radius:999px;box-shadow:0 6px 18px rgba(0,0,0,.2)}
.wa svg{width:20px;height:20px;flex:none}
.toast{position:fixed;left:50%;bottom:calc(20px + env(safe-area-inset-bottom,0px));transform:translate(-50%,40px);background:var(--fg);color:var(--bg);padding:12px 20px;border-radius:999px;font-size:14px;font-weight:500;opacity:0;transition:.3s;z-index:40;pointer-events:none;max-width:calc(100% - 32px);text-align:center}
.toast.on{opacity:1;transform:translate(-50%,0)}
@media(prefers-reduced-motion:reduce){*{transition:none!important}}
</style>

<div class="notice">Todas as calças por R$ 80,00 · Frete grátis acima de R$ 299</div>

<header class="top">
  <div class="wrap bar">
    <a class="logo" href="#topo" aria-label="RSL Fashion">
      <svg viewBox="0 0 64 64" aria-hidden="true">
        <circle cx="32" cy="32" r="30" fill="var(--pink)"/>
        <circle cx="32" cy="32" r="26" fill="none" stroke="var(--on-pink)" stroke-width="1.2"/>
        <path d="M22 8 Q32 20 42 8" fill="none" stroke="var(--on-pink)" stroke-width="1.6" stroke-linecap="round"/>
        <text x="32" y="40" text-anchor="middle" font-family="Bodoni Moda, Didot, serif" font-weight="700" font-size="22" fill="var(--on-pink)">RSL</text>
      </svg>
      <span class="name">RSL Fashion<small>Moda feminina</small></span>
    </a>
    <nav>
      <span class="links">
        <a href="#catalogo">Catálogo</a><a href="#pedidos" id="navOrders" hidden>Pedidos</a><a href="#sobre">Sobre</a><a href="#contato">Contato</a>
      </span>
      <button class="bag-btn" id="openBag" aria-label="Abrir sacola">Sacola <span class="count" id="count">0</span></button>
    </nav>
  </div>
</header>

<main id="topo">
  <div class="wrap">
    <div class="hero">
      <div>
        <div class="eyebrow">Coleção de calças</div>
        <h1>Vista o seu <em>rosa</em> favorito.</h1>
        <p>Calças pantalona, de alfaiataria, skinny e legging com caimento leve e acabamento cuidadoso, todas por R$ 80,00.</p>
        <div class="cta-row">
          <a class="btn primary" href="#catalogo">Ver catálogo</a>
          <a class="btn ghost" href="#sobre">Conheça a RSL</a>
        </div>
      </div>
      <div class="hero-art" aria-hidden="true">
        <div id="heroSvg" style="display:contents"><svg viewBox="0 0 200 240" role="img" aria-label="Ilustração da peça"><path d="M62 30 L138 30 L170 214 L112 214 L100 96 L88 214 L30 214 Z" fill="#e8457f"/><rect x="62" y="24" width="76" height="14" rx="3" fill="#b53663"/><path d="M100 38 L100 96" stroke="#ba3766" stroke-width="2"/><path d="M76 60 L50 214 M124 60 L150 214" stroke="#ef7da5" stroke-width="2" opacity=".5"/></svg></div>
        <span class="tag">Calça Pantalona Rosé · R$ 80,00</span>
      </div>
    </div>

    <div class="perks">
      <div><b>Tamanhos P ao GG</b>Tabela de medidas em cada peça</div>
      <div><b>Troca em até 30 dias</b>Sem complicação</div>
      <div><b>Entrega para todo o Brasil</b>Envio em até 2 dias úteis</div>
    </div>

    <section class="catalog" id="catalogo">
      <div class="sec-head">
        <div><h2>Catálogo</h2><p id="resultInfo">10 peças na coleção</p></div>
      </div>
      <div class="filters" id="filters" role="group" aria-label="Filtrar por categoria"><button class="chip" aria-pressed="true" data-cat="Todos">Todos</button><button class="chip" aria-pressed="false" data-cat="Pantalona">Pantalona</button><button class="chip" aria-pressed="false" data-cat="Alfaiataria">Alfaiataria</button><button class="chip" aria-pressed="false" data-cat="Skinny">Skinny</button><button class="chip" aria-pressed="false" data-cat="Legging">Legging</button></div>
      <div class="grid" id="grid"><article class="card"><div class="thumb" style="--c:#ffcfe0"><span class="badge">Mais vendida</span><svg viewBox="0 0 200 240" role="img" aria-label="Ilustração da peça"><path d="M62 30 L138 30 L170 214 L112 214 L100 96 L88 214 L30 214 Z" fill="#9c1850"/><rect x="62" y="24" width="76" height="14" rx="3" fill="#7a133e"/><path d="M100 38 L100 96" stroke="#7d1340" stroke-width="2"/><path d="M76 60 L50 214 M124 60 L150 214" stroke="#ba5d85" stroke-width="2" opacity=".5"/></svg></div><div><h3>Calça Pantalona Dália</h3><div class="meta"><span>Pantalona fluida, cintura alta</span></div></div><div class="price">R$ 80,00</div><div class="sizes" role="group" aria-label="Tamanho de Calça Pantalona Dália"><button class="size" aria-pressed="false" data-id="1" data-size="P">P</button><button class="size" aria-pressed="true" data-id="1" data-size="M">M</button><button class="size" aria-pressed="false" data-id="1" data-size="G">G</button><button class="size" aria-pressed="false" data-id="1" data-size="GG">GG</button></div><button class="add" data-add="1">Adicionar à sacola</button></article><article class="card"><div class="thumb" style="--c:#ffe6ef"><svg viewBox="0 0 200 240" role="img" aria-label="Ilustração da peça"><path d="M62 30 L138 30 L170 214 L112 214 L100 96 L88 214 L30 214 Z" fill="#f6a1bf"/><rect x="62" y="24" width="76" height="14" rx="3" fill="#c07e95"/><path d="M100 38 L100 96" stroke="#c58199" stroke-width="2"/><path d="M76 60 L50 214 M124 60 L150 214" stroke="#f9bdd2" stroke-width="2" opacity=".5"/></svg></div><div><h3>Calça Pantalona Pétala</h3><div class="meta"><span>Pantalona leve, tecido macio</span></div></div><div class="price">R$ 80,00</div><div class="sizes" role="group" aria-label="Tamanho de Calça Pantalona Pétala"><button class="size" aria-pressed="false" data-id="2" data-size="P">P</button><button class="size" aria-pressed="true" data-id="2" data-size="M">M</button><button class="size" aria-pressed="false" data-id="2" data-size="G">G</button><button class="size" aria-pressed="false" data-id="2" data-size="GG">GG</button></div><button class="add" data-add="2">Adicionar à sacola</button></article><article class="card"><div class="thumb" style="--c:#ffd6e5"><span class="badge">Novo</span><svg viewBox="0 0 200 240" role="img" aria-label="Ilustração da peça"><path d="M62 30 L138 30 L170 214 L112 214 L100 96 L88 214 L30 214 Z" fill="#e8457f"/><rect x="62" y="24" width="76" height="14" rx="3" fill="#b53663"/><path d="M100 38 L100 96" stroke="#ba3766" stroke-width="2"/><path d="M76 60 L50 214 M124 60 L150 214" stroke="#ef7da5" stroke-width="2" opacity=".5"/></svg></div><div><h3>Calça Pantalona Rosé</h3><div class="meta"><span>Pantalona com cós largo</span></div></div><div class="price">R$ 80,00</div><div class="sizes" role="group" aria-label="Tamanho de Calça Pantalona Rosé"><button class="size" aria-pressed="false" data-id="3" data-size="P">P</button><button class="size" aria-pressed="true" data-id="3" data-size="M">M</button><button class="size" aria-pressed="false" data-id="3" data-size="G">G</button><button class="size" aria-pressed="false" data-id="3" data-size="GG">GG</button></div><button class="add" data-add="3">Adicionar à sacola</button></article><article class="card"><div class="thumb" style="--c:#ffdce9"><svg viewBox="0 0 200 240" role="img" aria-label="Ilustração da peça"><path d="M62 30 L138 30 L152 214 L110 214 L100 96 L90 214 L48 214 Z" fill="#ec6c9a"/><rect x="62" y="24" width="76" height="14" rx="3" fill="#b85478"/><path d="M100 38 L100 96" stroke="#bd567b" stroke-width="2"/><path d="M72 60 L66 214 M128 60 L134 214" stroke="#f298b8" stroke-width="2" opacity=".5"/></svg></div><div><h3>Calça Alfaiataria Luna</h3><div class="meta"><span>Corte reto, vinco frontal</span></div></div><div class="price">R$ 80,00</div><div class="sizes" role="group" aria-label="Tamanho de Calça Alfaiataria Luna"><button class="size" aria-pressed="false" data-id="4" data-size="P">P</button><button class="size" aria-pressed="true" data-id="4" data-size="M">M</button><button class="size" aria-pressed="false" data-id="4" data-size="G">G</button><button class="size" aria-pressed="false" data-id="4" data-size="GG">GG</button></div><button class="add" data-add="4">Adicionar à sacola</button></article><article class="card"><div class="thumb" style="--c:#f8b9d1"><svg viewBox="0 0 200 240" role="img" aria-label="Ilustração da peça"><path d="M62 30 L138 30 L152 214 L110 214 L100 96 L90 214 L48 214 Z" fill="#fde4ee"/><rect x="62" y="24" width="76" height="14" rx="3" fill="#c5b2ba"/><path d="M100 38 L100 96" stroke="#cab6be" stroke-width="2"/><path d="M72 60 L66 214 M128 60 L134 214" stroke="#feecf3" stroke-width="2" opacity=".5"/></svg></div><div><h3>Calça Alfaiataria Pérola</h3><div class="meta"><span>Alfaiataria clara, cintura alta</span></div></div><div class="price">R$ 80,00</div><div class="sizes" role="group" aria-label="Tamanho de Calça Alfaiataria Pérola"><button class="size" aria-pressed="false" data-id="5" data-size="P">P</button><button class="size" aria-pressed="true" data-id="5" data-size="M">M</button><button class="size" aria-pressed="false" data-id="5" data-size="G">G</button><button class="size" aria-pressed="false" data-id="5" data-size="GG">GG</button></div><button class="add" data-add="5">Adicionar à sacola</button></article><article class="card"><div class="thumb" style="--c:#fbc4d8"><svg viewBox="0 0 200 240" role="img" aria-label="Ilustração da peça"><path d="M62 30 L138 30 L152 214 L110 214 L100 96 L90 214 L48 214 Z" fill="#b81f5b"/><rect x="62" y="24" width="76" height="14" rx="3" fill="#901847"/><path d="M100 38 L100 96" stroke="#931949" stroke-width="2"/><path d="M72 60 L66 214 M128 60 L134 214" stroke="#cd628c" stroke-width="2" opacity=".5"/></svg></div><div><h3>Calça Alfaiataria Camélia</h3><div class="meta"><span>Corte reto, forro leve</span></div></div><div class="price">R$ 80,00</div><div class="sizes" role="group" aria-label="Tamanho de Calça Alfaiataria Camélia"><button class="size" aria-pressed="false" data-id="6" data-size="P">P</button><button class="size" aria-pressed="true" data-id="6" data-size="M">M</button><button class="size" aria-pressed="false" data-id="6" data-size="G">G</button><button class="size" aria-pressed="false" data-id="6" data-size="GG">GG</button></div><button class="add" data-add="6">Adicionar à sacola</button></article><article class="card"><div class="thumb" style="--c:#ffdbe8"><svg viewBox="0 0 200 240" role="img" aria-label="Ilustração da peça"><path d="M66 30 L134 30 L140 214 L108 214 L100 92 L92 214 L60 214 Z" fill="#d6336c"/><rect x="66" y="24" width="68" height="14" rx="3" fill="#a72854"/><path d="M100 38 L100 92" stroke="#ab2956" stroke-width="2"/><path d="M78 60 L72 214 M122 60 L128 214" stroke="#e27098" stroke-width="2" opacity=".5"/></svg></div><div><h3>Calça Skinny Bella</h3><div class="meta"><span>Modelagem justa com elastano</span></div></div><div class="price">R$ 80,00</div><div class="sizes" role="group" aria-label="Tamanho de Calça Skinny Bella"><button class="size" aria-pressed="false" data-id="7" data-size="P">P</button><button class="size" aria-pressed="true" data-id="7" data-size="M">M</button><button class="size" aria-pressed="false" data-id="7" data-size="G">G</button><button class="size" aria-pressed="false" data-id="7" data-size="GG">GG</button></div><button class="add" data-add="7">Adicionar à sacola</button></article><article class="card"><div class="thumb" style="--c:#ffe3ee"><span class="badge">Novo</span><svg viewBox="0 0 200 240" role="img" aria-label="Ilustração da peça"><path d="M66 30 L134 30 L140 214 L108 214 L100 92 L92 214 L60 214 Z" fill="#f48fb1"/><rect x="66" y="24" width="68" height="14" rx="3" fill="#be708a"/><path d="M100 38 L100 92" stroke="#c3728e" stroke-width="2"/><path d="M78 60 L72 214 M122 60 L128 214" stroke="#f7b1c8" stroke-width="2" opacity=".5"/></svg></div><div><h3>Calça Skinny Flora</h3><div class="meta"><span>Cintura alta, conforto o dia todo</span></div></div><div class="price">R$ 80,00</div><div class="sizes" role="group" aria-label="Tamanho de Calça Skinny Flora"><button class="size" aria-pressed="false" data-id="8" data-size="P">P</button><button class="size" aria-pressed="true" data-id="8" data-size="M">M</button><button class="size" aria-pressed="false" data-id="8" data-size="G">G</button><button class="size" aria-pressed="false" data-id="8" data-size="GG">GG</button></div><button class="add" data-add="8">Adicionar à sacola</button></article><article class="card"><div class="thumb" style="--c:#fbc9db"><svg viewBox="0 0 200 240" role="img" aria-label="Ilustração da peça"><path d="M66 30 L134 30 L140 214 L108 214 L100 92 L92 214 L60 214 Z" fill="#c2185b"/><rect x="66" y="24" width="68" height="14" rx="3" fill="#971347"/><path d="M100 38 L100 92" stroke="#9b1349" stroke-width="2"/><path d="M78 60 L72 214 M122 60 L128 214" stroke="#d45d8c" stroke-width="2" opacity=".5"/></svg></div><div><h3>Calça Legging Lis</h3><div class="meta"><span>Legging grossa, não marca</span></div></div><div class="price">R$ 80,00</div><div class="sizes" role="group" aria-label="Tamanho de Calça Legging Lis"><button class="size" aria-pressed="false" data-id="9" data-size="P">P</button><button class="size" aria-pressed="true" data-id="9" data-size="M">M</button><button class="size" aria-pressed="false" data-id="9" data-size="G">G</button><button class="size" aria-pressed="false" data-id="9" data-size="GG">GG</button></div><button class="add" data-add="9">Adicionar à sacola</button></article><article class="card"><div class="thumb" style="--c:#fff0f6"><svg viewBox="0 0 200 240" role="img" aria-label="Ilustração da peça"><path d="M66 30 L134 30 L140 214 L108 214 L100 92 L92 214 L60 214 Z" fill="#fbb6cf"/><rect x="66" y="24" width="68" height="14" rx="3" fill="#c48ea1"/><path d="M100 38 L100 92" stroke="#c992a6" stroke-width="2"/><path d="M78 60 L72 214 M122 60 L128 214" stroke="#fcccdd" stroke-width="2" opacity=".5"/></svg></div><div><h3>Calça Legging Aurora</h3><div class="meta"><span>Legging com cós alto</span></div></div><div class="price">R$ 80,00</div><div class="sizes" role="group" aria-label="Tamanho de Calça Legging Aurora"><button class="size" aria-pressed="false" data-id="10" data-size="P">P</button><button class="size" aria-pressed="true" data-id="10" data-size="M">M</button><button class="size" aria-pressed="false" data-id="10" data-size="G">G</button><button class="size" aria-pressed="false" data-id="10" data-size="GG">GG</button></div><button class="add" data-add="10">Adicionar à sacola</button></article></div>
    </section>

    <section class="orders" id="pedidos" hidden>
      <div class="sec-head"><div><h2>Pedidos recebidos</h2><p id="ordersInfo">Área do dono da loja.</p></div></div>
      <p class="orders-note">Aqui aparecem os pedidos concluídos por clientes conectados ao Claude. Os demais pedidos chegam pelo WhatsApp, junto com o comprovante.</p>
      <div class="table-wrap"><table>
        <thead><tr><th>Data</th><th>Cliente</th><th>WhatsApp</th><th>Itens</th><th>Total</th></tr></thead>
        <tbody id="ordersBody"></tbody>
      </table></div>
    </section>

    <section class="about" id="sobre">
      <div>
        <div class="eyebrow">Sobre a loja</div>
        <h2 style="margin-block:12px 16px">Moda que cabe na sua rotina</h2>
        <p>A RSL Fashion nasceu para vestir mulheres que gostam de se sentir bonitas todos os dias. Selecionamos tecidos confortáveis, modelagens que valorizam diferentes corpos e cores que combinam entre si.</p>
        <p>Cada peça é conferida antes do envio e embalada com carinho.</p>
      </div>
      <div class="stats">
        <div class="stat"><b>P–GG</b><span>Grade completa de tamanhos</span></div>
        <div class="stat"><b>30 dias</b><span>Para trocar sua peça</span></div>
        <div class="stat"><b>6x</b><span>Sem juros no cartão</span></div>
        <div class="stat"><b>2 dias</b><span>Para postar seu pedido</span></div>
      </div>
    </section>
  </div>
</main>

<footer id="contato">
  <div class="wrap row">
    <div><div class="name">RSL Fashion</div>Moda feminina · Todos os direitos reservados</div>
    <div>Atendimento: segunda a sábado, das 9h às 18h<br>WhatsApp: <a href="https://wa.me/5585997538992" target="_blank" rel="noopener" style="color:var(--pink-deep);font-weight:700">(85) 99753-8992</a><br>Instagram: <a href="https://www.instagram.com/rslcollectionfashion?vrfl=aTViZW9vMzZrb2cz&amp;utm_source=qr" target="_blank" rel="noopener" style="color:var(--pink-deep);font-weight:700">@rslcollectionfashion</a></div>
  </div>
</footer>

<div class="scrim" id="scrim"></div>
<aside class="drawer" id="drawer" aria-label="Sacola de compras" aria-hidden="true">
  <header><h2>Sua sacola</h2><button class="x" id="closeBag" aria-label="Fechar sacola">×</button></header>
  <div class="items" id="items"></div>
  <div class="total" id="totalBox">
    <div class="sum"><span>Total</span><b id="total">R$ 0,00</b></div>
    <div class="msg" id="shipMsg"></div>
    <button class="btn primary" id="checkout">Pagar com Pix</button>
    <button class="btn ghost" id="backBag" hidden>Voltar à sacola</button>
  </div>
</aside>
<a class="wa" href="https://wa.me/5585997538992" target="_blank" rel="noopener" aria-label="Falar com a RSL Fashion no WhatsApp">
  <svg viewBox="0 0 24 24" aria-hidden="true"><path fill="currentColor" d="M12 2a10 10 0 0 0-8.6 15.1L2 22l5-1.3A10 10 0 1 0 12 2Zm0 18.2a8.2 8.2 0 0 1-4.2-1.2l-.3-.2-3 .8.8-2.9-.2-.3A8.2 8.2 0 1 1 12 20.200Zm4.500-6.100c-.2-.1-1.500-.7-1.700-.8-.2-.1-.4-.1-.6.100l-.8 1c-.1.200-.3.200-.5.100a6.700 6.700 0 0 1-3.300-2.900c-.2-.4.200-.4.700-1.300.1-.2 0-.3 0-.5l-.8-1.800c-.2-.5-.4-.4-.6-.4h-.5c-.2 0-.5.100-.7.300-.2.300-.9.900-.9 2.200s.9 2.500 1.100 2.700c.1.200 1.800 2.800 4.400 3.900 1.600.7 2.300.7 3.100.6.500-.1 1.500-.6 1.700-1.200.2-.6.2-1.100.2-1.200-.1-.1-.3-.2-.5-.3Z"/></svg>
  WhatsApp
</a>
<div class="toast" id="toast" role="status"></div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcode-generator/1.4.4/qrcode.min.js"></script>
<script>
(function(){
  var money=function(v){return "R$ "+v.toFixed(2).replace(".",",").replace(/\B(?=(\d{3})+(?!\d))/g,".")};
  var shade=function(hex,amt){
    var n=parseInt(hex.slice(1),16),r=n>>16,g=(n>>8)&255,b=n&255;
    var f=function(c){return Math.max(0,Math.min(255,Math.round(c+(amt>0?(255-c)*amt:c*amt))))};
    return "#"+[f(r),f(g),f(b)].map(function(c){return c.toString(16).padStart(2,"0")}).join("");
  };
  var SHAPES={
    dress:function(c){return '<path d="M72 18 L88 18 Q100 44 112 18 L128 18 L138 74 L124 84 L152 222 L48 222 L76 84 L62 74 Z" fill="'+c+'"/><path d="M76 84 L124 84 L128 98 L72 98 Z" fill="'+shade(c,-.18)+'"/><path d="M100 98 L100 222" stroke="'+shade(c,.3)+'" stroke-width="2" opacity=".6"/><path d="M80 120 L72 222 M120 120 L128 222" stroke="'+shade(c,-.15)+'" stroke-width="2" opacity=".5"/>'},
    blouse:function(c){return '<path d="M62 28 L86 22 Q100 44 114 22 L138 28 L176 82 L150 102 L140 86 L140 192 L60 192 L60 86 L50 102 L24 82 Z" fill="'+c+'"/><path d="M86 22 Q100 44 114 22 L108 18 Q100 30 92 18 Z" fill="'+shade(c,-.2)+'"/><path d="M100 40 L100 192" stroke="'+shade(c,.35)+'" stroke-width="2" opacity=".6"/><circle cx="100" cy="70" r="2.5" fill="'+shade(c,-.3)+'"/><circle cx="100" cy="100" r="2.5" fill="'+shade(c,-.3)+'"/><circle cx="100" cy="130" r="2.5" fill="'+shade(c,-.3)+'"/>'},
    skirt:function(c){return '<path d="M66 38 L134 38 L166 206 L34 206 Z" fill="'+c+'"/><rect x="66" y="30" width="68" height="14" rx="3" fill="'+shade(c,-.22)+'"/><path d="M84 44 L64 206 M100 44 L100 206 M116 44 L136 206" stroke="'+shade(c,.3)+'" stroke-width="2" opacity=".55"/>'},
    pants:function(c){return '<path d="M62 30 L138 30 L152 214 L110 214 L100 96 L90 214 L48 214 Z" fill="'+c+'"/><rect x="62" y="24" width="76" height="14" rx="3" fill="'+shade(c,-.22)+'"/><path d="M100 38 L100 96" stroke="'+shade(c,-.2)+'" stroke-width="2"/><path d="M72 60 L66 214 M128 60 L134 214" stroke="'+shade(c,.3)+'" stroke-width="2" opacity=".5"/>'},
    set:function(c){return '<path d="M70 20 L88 20 Q100 38 112 20 L130 20 L142 62 L128 70 L128 108 L72 108 L72 70 L58 62 Z" fill="'+c+'"/><path d="M74 122 L126 122 L152 218 L48 218 Z" fill="'+shade(c,-.14)+'"/><rect x="74" y="116" width="52" height="10" rx="3" fill="'+shade(c,-.3)+'"/><path d="M100 36 L100 108" stroke="'+shade(c,.35)+'" stroke-width="2" opacity=".6"/>'},
    wide:function(c){return '<path d="M62 30 L138 30 L170 214 L112 214 L100 96 L88 214 L30 214 Z" fill="'+c+'"/><rect x="62" y="24" width="76" height="14" rx="3" fill="'+shade(c,-.22)+'"/><path d="M100 38 L100 96" stroke="'+shade(c,-.2)+'" stroke-width="2"/><path d="M76 60 L50 214 M124 60 L150 214" stroke="'+shade(c,.3)+'" stroke-width="2" opacity=".5"/>'},
    skinny:function(c){return '<path d="M66 30 L134 30 L140 214 L108 214 L100 92 L92 214 L60 214 Z" fill="'+c+'"/><rect x="66" y="24" width="68" height="14" rx="3" fill="'+shade(c,-.22)+'"/><path d="M100 38 L100 92" stroke="'+shade(c,-.2)+'" stroke-width="2"/><path d="M78 60 L72 214 M122 60 L128 214" stroke="'+shade(c,.3)+'" stroke-width="2" opacity=".5"/>'},
    blazer:function(c){return '<path d="M60 26 L90 20 L100 60 L110 20 L140 26 L178 90 L150 108 L142 92 L142 200 L58 200 L58 92 L50 108 L22 90 Z" fill="'+c+'"/><path d="M90 20 L100 60 L110 20 L122 24 L100 120 L78 24 Z" fill="'+shade(c,-.22)+'"/><circle cx="100" cy="130" r="3" fill="'+shade(c,-.4)+'"/><circle cx="100" cy="158" r="3" fill="'+shade(c,-.4)+'"/>'}
  };
  var art=function(type,color){return '<svg viewBox="0 0 200 240" role="img" aria-label="Ilustração da peça">'+SHAPES[type](color)+'</svg>'};

  var P=[
    {id:1,n:"Calça Pantalona Dália",t:"wide",cat:"Pantalona",p:80,col:"#9c1850",bg:"#ffcfe0",tag:"Mais vendida",d:"Pantalona fluida, cintura alta"},
    {id:2,n:"Calça Pantalona Pétala",t:"wide",cat:"Pantalona",p:80,col:"#f6a1bf",bg:"#ffe6ef",d:"Pantalona leve, tecido macio"},
    {id:3,n:"Calça Pantalona Rosé",t:"wide",cat:"Pantalona",p:80,col:"#e8457f",bg:"#ffd6e5",tag:"Novo",d:"Pantalona com cós largo"},
    {id:4,n:"Calça Alfaiataria Luna",t:"pants",cat:"Alfaiataria",p:80,col:"#ec6c9a",bg:"#ffdce9",d:"Corte reto, vinco frontal"},
    {id:5,n:"Calça Alfaiataria Pérola",t:"pants",cat:"Alfaiataria",p:80,col:"#fde4ee",bg:"#f8b9d1",d:"Alfaiataria clara, cintura alta"},
    {id:6,n:"Calça Alfaiataria Camélia",t:"pants",cat:"Alfaiataria",p:80,col:"#b81f5b",bg:"#fbc4d8",d:"Corte reto, forro leve"},
    {id:7,n:"Calça Skinny Bella",t:"skinny",cat:"Skinny",p:80,col:"#d6336c",bg:"#ffdbe8",d:"Modelagem justa com elastano"},
    {id:8,n:"Calça Skinny Flora",t:"skinny",cat:"Skinny",p:80,col:"#f48fb1",bg:"#ffe3ee",tag:"Novo",d:"Cintura alta, conforto o dia todo"},
    {id:9,n:"Calça Legging Lis",t:"skinny",cat:"Legging",p:80,col:"#c2185b",bg:"#fbc9db",d:"Legging grossa, não marca"},
    {id:10,n:"Calça Legging Aurora",t:"skinny",cat:"Legging",p:80,col:"#fbb6cf",bg:"#fff0f6",d:"Legging com cós alto"}
  ];
  var SIZES=["P","M","G","GG"];
  var sel={},cart=[],cat="Todos",paying=false;
  var KEY="06983718364";
  function tlv(id,v){return id+("0"+v.length).slice(-2)+v}
  function crc16(str){var c=0xFFFF;for(var i=0;i<str.length;i++){c^=str.charCodeAt(i)<<8;for(var j=0;j<8;j++){c=(c&0x8000)?((c<<1)^0x1021):(c<<1);c&=0xFFFF}}return("000"+c.toString(16).toUpperCase()).slice(-4)}
  function pix(amount){
    var p=tlv("00","01")+tlv("01","11")+tlv("26",tlv("00","br.gov.bcb.pix")+tlv("01",KEY))+tlv("52","0000")+tlv("53","986")+(amount>0?tlv("54",amount.toFixed(2)):"")+tlv("58","BR")+tlv("59","RSL FASHION")+tlv("60","FORTALEZA")+tlv("62",tlv("05","***"))+"6304";
    return p+crc16(p);
  }
  function qrSvg(text){
    try{
      var q=qrcode(0,"M");q.addData(text);q.make();
      var n=q.getModuleCount(),d="";
      for(var r=0;r<n;r++)for(var c=0;c<n;c++)if(q.isDark(r,c))d+="M"+(c+4)+" "+(r+4)+"h1v1h-1z";
      return '<svg viewBox="0 0 '+(n+8)+' '+(n+8)+'" role="img" aria-label="QR Code Pix" shape-rendering="crispEdges"><rect width="100%" height="100%" fill="#fff"/><path d="'+d+'" fill="#000"/></svg>';
    }catch(err){return '<div class="empty">Não foi possível gerar o QR Code. Use a chave Pix '+KEY+'.</div>'}
  }
  function cartTotal(){return cart.reduce(function(a,l){return a+l.q*l.p.p},0)}
  var WA="5585997538992";
  var done=null,db=null,uid=null,isOwner=false;
  function esc(v){return String(v==null?"":v).replace(/[&<>"']/g,function(c){return {"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c]})}
  function payView(tot){
    return '<div class="payview"><div class="qr">'+qrSvg(pix(tot))+'</div><b>'+money(tot)+'</b><small>Escaneie o QR Code ou copie o código Pix.</small><button class="btn primary" data-copy="cart">Copiar Pix copia e cola</button><small>Chave Pix: '+KEY+'</small>'+
    '<div class="alert"><b>Depois de pagar, envie o comprovante</b>Mande o comprovante do Pix pelo WhatsApp (85) 99753-8992 para confirmarmos seu pedido.</div>'+
    '<label class="field" for="cName">Seu nome<input id="cName" type="text" autocomplete="name" maxlength="80"></label>'+
    '<label class="field" for="cPhone">Seu WhatsApp (opcional)<input id="cPhone" type="tel" autocomplete="tel" maxlength="30"></label></div>';
  }
  function waLink(o){
    var lines=["Olá! Fiz o pedido "+o.id+" na RSL Fashion.","Nome: "+o.name,""].concat(o.items.map(function(i){return i.q+"x "+i.n+" (tam. "+i.s+") - "+money(i.p*i.q)}),["","Total: "+money(o.total),"Segue o comprovante do Pix."]);
    return "https://wa.me/"+WA+"?text="+encodeURIComponent(lines.join("\n"));
  }
  function doneView(o){
    return '<div class="payview"><h3 style="font-size:28px">Pedido registrado</h3>'+
    '<div class="alert"><b>Envie o comprovante pelo WhatsApp</b>Para confirmar o pedido '+esc(o.id)+', mande o comprovante do Pix para o WhatsApp (85) 99753-8992.</div>'+
    '<a class="btn primary" href="'+waLink(o)+'" target="_blank" rel="noopener">Enviar comprovante no WhatsApp</a>'+
    '<ul class="sum-list">'+o.items.map(function(i){return '<li>'+i.q+'x '+esc(i.n)+' (tam. '+esc(i.s)+') · '+money(i.p*i.q)+'</li>'}).join("")+'<li><b style="font-size:16px;color:var(--fg)">Total: '+money(o.total)+'</b></li></ul></div>';
  }
  function saveOrder(o){
    if(!db||!uid)return Promise.resolve(false);
    var ref=db.doc("orders/"+uid);
    return ref.get().then(function(sn){
      var prev=(sn.exists&&sn.data().orders)||[];
      return ref.set({orders:prev.concat([o])});
    }).then(function(){return true},function(){return false});
  }
  function renderOrders(list){
    list.sort(function(x,y){return String(y.at).localeCompare(String(x.at))});
    $("ordersInfo").textContent=list.length?list.length+(list.length===1?" pedido":" pedidos"):"Nenhum pedido ainda.";
    $("ordersBody").innerHTML=list.map(function(o){
      var d="";try{d=new Date(o.at).toLocaleString("pt-BR",{timeZone:"America/Fortaleza",day:"2-digit",month:"2-digit",hour:"2-digit",minute:"2-digit"})}catch(e){}
      return '<tr><td>'+esc(d)+'<br><small>'+esc(o.id)+'</small></td><td>'+esc(o.name)+'</td><td>'+esc(o.phone||"-")+'</td><td>'+(o.items||[]).map(function(i){return esc(i.q+"x "+i.n+" (tam. "+i.s+")")}).join("<br>")+'</td><td class="num">'+money(+o.total||0)+'</td></tr>';
    }).join("");
  }
  function watchOrders(){
    db.collection("orders").onSnapshot(function(snap){
      var all=[];snap.docs.forEach(function(d){((d.data()||{}).orders||[]).forEach(function(o){all.push(o)})});
      renderOrders(all);
    },function(){$("ordersInfo").textContent="Não foi possível carregar os pedidos agora."});
  }
  function initCaps(){
    if(!(window.claude&&window.claude.use))return;
    Promise.resolve().then(function(){return window.claude.use("user")}).then(function(u){
      if(!u)return;
      return Promise.all([u.isOwner(),u.id()]).then(function(r){
        isOwner=r[0];uid=r[1];
        if(isOwner){$("pedidos").hidden=false;$("navOrders").hidden=false;$("ordersInfo").textContent="Carregando pedidos..."}
        return window.claude.use("db");
      });
    }).then(function(d){
      db=d||null;
      if(isOwner){if(db)watchOrders();else $("ordersInfo").textContent="O armazenamento de pedidos não está disponível nesta visualização."}
    }).catch(function(){});
  }
  function copyText(t,msg){
    var done=function(){toast(msg)};
    try{navigator.clipboard.writeText(t).then(done,function(){toast("Não foi possível copiar. Selecione e copie manualmente.")})}
    catch(err){toast("Não foi possível copiar. Selecione e copie manualmente.")}
  }

  var $=function(i){return document.getElementById(i)};
  var heroSvg=$("heroSvg");heroSvg.innerHTML=art("wide","#e8457f");

  var cats=["Todos"].concat(P.map(function(x){return x.cat}).filter(function(v,i,a){return a.indexOf(v)===i}));
  function drawFilters(){
    $("filters").innerHTML=cats.map(function(c){return '<button class="chip" aria-pressed="'+(c===cat)+'" data-cat="'+c+'">'+c+'</button>'}).join("");
  }
  function drawGrid(){
    var list=P.filter(function(x){return cat==="Todos"||x.cat===cat});
    $("resultInfo").textContent=list.length+(list.length===1?" peça":" peças")+(cat==="Todos"?" na coleção":" em "+cat);
    $("grid").innerHTML=list.map(function(x){
      var s=sel[x.id]||"M";
      return '<article class="card"><div class="thumb" style="--c:'+x.bg+'">'+(x.tag?'<span class="badge">'+x.tag+'</span>':'')+art(x.t,x.col)+'</div>'+
      '<div><h3>'+x.n+'</h3><div class="meta"><span>'+x.d+'</span></div></div>'+
      '<div class="price">'+money(x.p)+(x.o?'<s>'+money(x.o)+'</s>':'')+'</div>'+
      '<div class="sizes" role="group" aria-label="Tamanho de '+x.n+'">'+SIZES.map(function(z){return '<button class="size" aria-pressed="'+(z===s)+'" data-id="'+x.id+'" data-size="'+z+'">'+z+'</button>'}).join("")+'</div>'+
      '<button class="add" data-add="'+x.id+'">Adicionar à sacola</button></article>';
    }).join("");
  }
  var toastT;
  function toast(m){var t=$("toast");t.textContent=m;t.classList.add("on");clearTimeout(toastT);toastT=setTimeout(function(){t.classList.remove("on")},2200)}

  function drawCart(){
    var n=cart.reduce(function(a,l){return a+l.q},0);
    var tot=cart.reduce(function(a,l){return a+l.q*l.p.p},0);
    if(!n)paying=false;
    $("totalBox").hidden=!!done;
    $("count").textContent=n;
    $("total").textContent=money(tot);
    $("checkout").disabled=!n;$("checkout").style.opacity=n?1:.5;
    $("shipMsg").textContent=!n?"Adicione peças para começar.":(tot>=299?"Você ganhou frete grátis.":"Faltam "+money(299-tot)+" para o frete grátis.");
    $("items").innerHTML=done?doneView(done):paying?payView(tot):n?cart.map(function(l,i){
      return '<div class="line"><div class="mini" style="--c:'+l.p.bg+'">'+art(l.p.t,l.p.col)+'</div><div><h4>'+l.p.n+'</h4><small>Tamanho '+l.s+' · '+money(l.p.p)+'</small><div class="qty"><button data-q="-1" data-i="'+i+'" aria-label="Diminuir">−</button><span>'+l.q+'</span><button data-q="1" data-i="'+i+'" aria-label="Aumentar">+</button></div></div><b>'+money(l.p.p*l.q)+'</b></div>';
    }).join(""):'<div class="empty">Sua sacola está vazia.</div>';
    $("checkout").textContent=paying?"Concluir pedido":"Pagar com Pix";
    $("backBag").hidden=!paying;
  }
  function bag(open){
    $("drawer").classList.toggle("on",open);$("scrim").classList.toggle("on",open);
    $("drawer").setAttribute("aria-hidden",String(!open));
    if(open)$("closeBag").focus();
  }

  document.addEventListener("click",function(e){
    var t=e.target.closest("button");if(!t)return;
    if(t.dataset.cat){cat=t.dataset.cat;drawFilters();drawGrid();return}
    if(t.dataset.size){sel[t.dataset.id]=t.dataset.size;drawGrid();return}
    if(t.dataset.add){
      var p=P.filter(function(x){return x.id==t.dataset.add})[0],s=sel[p.id]||"M";
      var f=cart.filter(function(l){return l.p.id===p.id&&l.s===s})[0];
      if(f)f.q++;else cart.push({p:p,s:s,q:1});
      drawCart();toast(p.n+" (tam. "+s+") na sacola");return;
    }
    if(t.dataset.q){
      var l=cart[+t.dataset.i];l.q+=+t.dataset.q;
      if(l.q<1)cart.splice(+t.dataset.i,1);
      drawCart();return;
    }
    if(t.id==="openBag"){done=null;drawCart();bag(true)}
    if(t.id==="closeBag")bag(false);
    if(t.dataset.copy){
      if(t.dataset.copy==="key")copyText(KEY,"Chave Pix copiada");
      else if(t.dataset.copy==="code")copyText(pix(0),"Código Pix copiado");
      else copyText(pix(cartTotal()),"Código Pix copiado");
      return;
    }
    if(t.id==="backBag"){paying=false;drawCart();return}
    if(t.id==="checkout"&&cart.length){
      if(!paying){paying=true;drawCart();return}
      var nm=$("cName")?$("cName").value.trim():"",ph=$("cPhone")?$("cPhone").value.trim():"";
      if(!nm){toast("Informe seu nome para concluir o pedido.");if($("cName"))$("cName").focus();return}
      var order={id:"RSL-"+Date.now().toString(36).toUpperCase(),at:new Date().toISOString(),name:nm,phone:ph,total:cartTotal(),
        items:cart.map(function(l){return {n:l.p.n,s:l.s,q:l.q,p:l.p.p}})};
      cart=[];paying=false;done=order;drawCart();
      saveOrder(order);
    }
  });
  $("scrim").addEventListener("click",function(){bag(false)});
  document.addEventListener("keydown",function(e){if(e.key==="Escape")bag(false)});

  drawFilters();drawGrid();drawCart();
  try{initCaps()}catch(err){}
})();
</script>
