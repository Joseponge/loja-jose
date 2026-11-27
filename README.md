# loja-jose
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Loja José Renato – Felicidade com curadoria</title>
<style>
:root{
  --bg:#f5f6f8;--card:#ffffff;--ink:#1d1a22;--muted:#6b6672;--line:#e0dce4;
  --gold:#b08a43;--goldtxt:#8a6a2c;--accent:#6e1b3a;--onaccent:#ffffff;
  box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px);
}
@media (prefers-color-scheme:dark){
  :root:not([data-theme="light"]){--bg:#141016;--card:#1e1822;--ink:#f2edf4;--muted:#a79fae;--line:#3a3140;--gold:#d2ad66;--goldtxt:#d2ad66;--accent:#b8456f}
}
:root[data-theme="dark"]{--bg:#141016;--card:#1e1822;--ink:#f2edf4;--muted:#a79fae;--line:#3a3140;--gold:#d2ad66;--goldtxt:#d2ad66;--accent:#b8456f}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
*{box-sizing:border-box}
body{margin:0;background:var(--bg);color:var(--ink);font:16px/1.5 system-ui,-apple-system,"Helvetica Neue",sans-serif;padding-bottom:140px}
h1,h2,.name,.price,.mono,.med,.n{font-family:"Iowan Old Style","Palatino Linotype",Palatino,Georgia,serif}
button{font:inherit;color:inherit;cursor:pointer}
button:focus-visible{outline:2px solid var(--accent);outline-offset:3px}

header{text-align:center;padding:38px 20px 4px}
.mono{width:56px;height:56px;margin:0 auto 14px;border:1.5px solid var(--gold);border-radius:50%;display:grid;place-items:center;color:var(--goldtxt);font-size:1.15rem;letter-spacing:1px}
h1{margin:0;font-size:2.7rem;font-weight:500;letter-spacing:-.5px;line-height:1.1}
.tag{margin:8px 0 0;font-family:Georgia,serif;font-style:italic;color:var(--muted);font-size:1.1rem}
.rule{width:64px;height:1px;background:var(--gold);margin:22px auto 0}

.wrap{max-width:640px;margin:0 auto;padding:0 20px}
h2{font-size:1.4rem;font-weight:500;margin:28px 0 8px}
.steps{list-style:none;margin:0;padding:0;display:grid;gap:12px}
.steps li{display:grid;grid-template-columns:28px 1fr;gap:12px;align-items:start;color:var(--muted);font-size:.95rem}
.steps b{color:var(--ink);font-weight:600}
.n{width:26px;height:26px;border-radius:50%;border:1px solid var(--gold);display:grid;place-items:center;font-size:.85rem;color:var(--goldtxt)}

ul.list{list-style:none;margin:0;padding:0}
.item{display:grid;grid-template-columns:52px 1fr;gap:14px;padding:18px 0;border-bottom:1px solid var(--line)}
.med{width:52px;height:52px;border-radius:50%;border:1.5px solid var(--gold);display:grid;place-items:center;font-size:1.1rem;color:var(--goldtxt)}
.top{display:flex;align-items:baseline;gap:8px}
.name{font-size:1.25rem}
.dots{flex:1;min-width:12px;border-bottom:2px dotted var(--gold);opacity:.55}
.price{font-size:1.15rem;font-weight:600}
.desc{margin:2px 0 0;color:var(--muted);font-size:.92rem}
.foot{display:flex;justify-content:space-between;align-items:center;gap:10px;margin-top:12px}
.pts{font-size:.85rem;color:var(--goldtxt)}
.act{display:flex;align-items:center;gap:10px}
.act span{min-width:1.2em;text-align:center;font-weight:600}
.add,.go{background:var(--accent);color:var(--onaccent);border:0;border-radius:10px;padding:9px 16px;font-weight:600}
.rb{width:32px;height:32px;border-radius:50%;border:1px solid var(--accent);background:transparent;color:var(--accent);font-size:1.15rem;line-height:1}
.alt{background:transparent;border:1px solid var(--ink);border-radius:10px;padding:9px 16px;font-weight:600}

.bar{position:fixed;left:0;right:0;bottom:0;background:var(--card);border-top:1px solid var(--line);padding:12px 20px calc(12px + env(safe-area-inset-bottom,0px))}
.bar .in{max-width:640px;margin:0 auto;display:grid;grid-template-columns:1fr auto;gap:8px 12px;align-items:center}
.meter{grid-column:1/-1;height:6px;border-radius:999px;background:var(--line);overflow:hidden}
.fill{height:100%;width:0;background:var(--gold);transition:width .35s}
.msg strong{display:block;font-weight:600;font-size:.95rem}
.msg small{color:var(--muted);font-size:.8rem}
.go:disabled{opacity:.4;cursor:default}

.shade{position:fixed;inset:0;background:rgba(10,6,14,.6);display:none;align-items:flex-end;justify-content:center;z-index:5}
.shade.open{display:flex}
.sheet{width:100%;max-width:640px;max-height:88%;overflow:auto;background:var(--card);border-radius:20px 20px 0 0;padding:20px 20px calc(20px + env(safe-area-inset-bottom,0px))}
.sheet h2{margin:0 0 10px}
.line{display:flex;justify-content:space-between;gap:10px;padding:10px 0;border-bottom:1px solid var(--line)}
.total{display:flex;justify-content:space-between;font-family:Georgia,serif;font-size:1.3rem;margin:14px 0}
.row{display:flex;gap:10px}
.row button{flex:1;padding:12px}
.pix,.thanks{text-align:center;padding:4px 0}
.pix .val{font-family:Georgia,serif;font-size:1.8rem;margin:2px 0 12px}
.key{background:var(--bg);border:1px dashed var(--gold);border-radius:12px;padding:12px;font-size:1.2rem;font-weight:600;letter-spacing:.5px;word-break:break-all;user-select:all;-webkit-user-select:all}
.hint{color:var(--muted);font-size:.9rem;margin:10px 0}
.pix .go,.pix .alt,.thanks .go{margin:4px 4px 0}
.thanks .med{margin:0 auto 12px}
@media (prefers-reduced-motion:reduce){.fill{transition:none}}
</style>
</head>
<body>
<header>
  <div class="mono">JR</div>
  <h1>José Renato</h1>
  <p class="tag">Felicidade, com curadoria.</p>
  <div class="rule"></div>
</header>

<div class="wrap">
  <h2>Como funciona</h2>
  <ol class="steps">
    <li><span class="n">1</span><span><b>Escolha.</b> Toque em Adicionar nos itens que quiser. Cada um soma pontos de felicidade no medidor.</span></li>
    <li><span class="n">2</span><span><b>Confira.</b> Abra a sacola para ver o total da compra.</span></li>
    <li><span class="n">3</span><span><b>Pague.</b> Use o Pix e toque em “Já fiz o Pix”.</span></li>
  </ol>

  <h2>Coleção</h2>
  <ul class="list" id="list"></ul>
</div>

<div class="bar">
  <div class="in">
    <div class="meter"><div class="fill" id="fill"></div></div>
    <div class="msg" id="msg"></div>
    <button class="go" id="open" disabled>Ver sacola</button>
  </div>
</div>

<div class="shade" id="shade"><div class="sheet" id="sheet" role="dialog" aria-modal="true" aria-label="Sua sacola"></div></div>

<script>
const P=[
 {id:1,m:"IM",n:"Igor Menezes",d:"Bom humor em tamanho grande.",p:39.9,h:25},
 {id:2,m:"T",n:"Talles",d:"Edição especial, companhia premium.",p:44.5,h:28},
 {id:3,m:"P",n:"Pedro",d:"Leve, divertido e fácil de conviver.",p:27.3,h:18},
 {id:4,m:"PG",n:"Pg",d:"Versão compacta, a mesma alegria.",p:12,h:8}
];
const GOAL=60;
const NIVEIS=[[0,"Sua sacola ainda está vazia."],[1,"Bom começo."],[40,"Já está ficando bom."],[80,"Quase no máximo."],[100,"Felicidade no máximo."]];
const PIX="16177187692";
const cart={};
const $=s=>document.querySelector(s);
const brl=v=>v.toLocaleString("pt-BR",{style:"currency",currency:"BRL"});
let sheetState="closed";

function totals(){
  let total=0,hap=0,count=0;
  for(const p of P){const q=cart[p.id]||0;total+=p.p*q;hap+=p.h*q;count+=q}
  return {total,hap,count};
}
function drawList(){
  $("#list").innerHTML=P.map(p=>{
    const q=cart[p.id]||0;
    const act=q
      ?`<button class="rb" data-a="-1" data-id="${p.id}" aria-label="Tirar um">−</button><span>${q}</span><button class="rb" data-a="1" data-id="${p.id}" aria-label="Adicionar mais um">+</button>`
      :`<button class="add" data-a="1" data-id="${p.id}">Adicionar</button>`;
    return `<li class="item"><div class="med">${p.m}</div><div><div class="top"><span class="name">${p.n}</span><span class="dots"></span><span class="price">${brl(p.p)}</span></div><p class="desc">${p.d}</p><div class="foot"><span class="pts">+${p.h} pontos de felicidade</span><div class="act">${act}</div></div></div></li>`;
  }).join("");
}
function drawBar(){
  const t=totals();
  const pct=Math.min(100,t.hap/GOAL*100);
  $("#fill").style.width=pct+"%";
  let m=NIVEIS[0][1];
  for(const [min,txt] of NIVEIS){if(pct>=min)m=txt}
  $("#msg").innerHTML=`<strong>${m}</strong><small>${Math.min(t.hap,GOAL)} de ${GOAL} pontos de felicidade</small>`;
  const b=$("#open");
  b.disabled=t.count===0;
  b.textContent=t.count?`Ver sacola (${t.count})`:"Ver sacola";
}
function drawSheet(){
  const t=totals();
  const linhas=P.filter(p=>cart[p.id]).map(p=>`<div class="line"><span>${cart[p.id]}× ${p.n}</span><strong>${brl(p.p*cart[p.id])}</strong></div>`).join("");
  $("#sheet").innerHTML=`<h2>Sua sacola</h2>${linhas}<div class="total"><span>Total</span><span>${brl(t.total)}</span></div>
  <div class="row"><button class="alt" id="back">Continuar comprando</button><button class="go" id="buy">Pagar com Pix</button></div>`;
}
function drawPix(){
  $("#sheet").innerHTML=`<div class="pix"><h2>Pagamento via Pix</h2>
  <div class="val">${brl(totals().total)}</div>
  <div class="key" id="key">${PIX}</div>
  <p class="hint" id="hint">Abra o app do seu banco, escolha Pix, cole a chave acima e digite o valor da compra.</p>
  <button class="go" id="copy">Copiar chave Pix</button>
  <button class="alt" id="paid">Já fiz o Pix</button>
  <button class="alt" id="back">Voltar</button></div>`;
}
function drawThanks(){
  $("#sheet").innerHTML=`<div class="thanks"><div class="med">✓</div><h2>Obrigado pela compra</h2>
  <p class="hint">Sua compra na Loja José Renato foi registrada. Boa felicidade!</p>
  <button class="go" id="again">Voltar à loja</button></div>`;
}
function copiar(){
  const h=$("#hint");
  const ok=()=>{h.textContent="Chave copiada! Agora é só colar no app do banco."};
  const falha=()=>{
    try{const r=document.createRange();r.selectNodeContents($("#key"));const s=getSelection();s.removeAllRanges();s.addRange(r);
      h.textContent="Chave selecionada. Segure nela e toque em Copiar."}catch(e){h.textContent="Segure na chave para copiar."}
  };
  try{navigator.clipboard.writeText(PIX).then(ok,falha)}catch(e){falha()}
}
function update(){
  drawList();drawBar();
  if(sheetState==="open"){
    if(totals().count===0){closeSheet()}else{drawSheet()}
  }
}
function openSheet(){sheetState="open";drawSheet();$("#shade").classList.add("open")}
function closeSheet(){sheetState="closed";$("#shade").classList.remove("open")}

document.addEventListener("click",e=>{
  const b=e.target.closest("button");
  if(!b)return;
  if(b.dataset.a){
    const id=+b.dataset.id;
    cart[id]=Math.max(0,(cart[id]||0)+ +b.dataset.a);
    if(!cart[id])delete cart[id];
    update();
  }else if(b.id==="open"){openSheet()}
  else if(b.id==="back"){closeSheet()}
  else if(b.id==="buy"){sheetState="done";drawPix()}
  else if(b.id==="copy"){copiar()}
  else if(b.id==="paid"){drawThanks()}
  else if(b.id==="again"){for(const k in cart)delete cart[k];closeSheet();update()}
});
$("#shade").addEventListener("click",e=>{if(e.target.id==="shade"&&sheetState!=="done")closeSheet()});

update();
</script>
</body>
</html>