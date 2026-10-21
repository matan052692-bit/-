# זו גרסה בלי התמונות. אפשר להדביק אותה בקובץ בשם `index.html`. אם משתמשים בה, צריך להעלות לצד הקובץ את `logo.jpg` ואת `pizza.jpg`. ב-`IMG` שבקוד אפשר להחליף תמונה לכל פריט (`t1` טוסט, `pz` פיצה, `d1` קינוח).

```html
<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Dooshi PIZZA</title>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Rubik:wght@400;500;700;800&display=swap">
<style>
:root{--bg:#f1f9fb;--blue:#92d2df;--surface:#fff;--ink:#2b1b14;--mute:#7a6558;--red:#12183a;--green:#12183a;--gold:#f2b134;--line:#cfe4ea;--onred:#fff;
box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){--bg:#0e1530;--surface:#172044;--ink:#eaf6fa;--mute:#9db4c0;--red:#92d2df;--onred:#0e1530;--line:#2a3763}}
*{box-sizing:border-box}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
body{margin:0;background:var(--bg);color:var(--ink);font-family:Rubik,Arial,sans-serif;line-height:1.5;padding-bottom:90px}
.safe{background:var(--blue);color:#12183a;text-align:center;font-size:14px;padding:8px 12px}
.hero{padding:16px 16px 4px;max-width:760px;margin:auto;text-align:center}
.logo{width:100%;max-width:420px;border-radius:18px;display:block;margin:0 auto}
.hero p{margin:12px 0 0;color:var(--mute)}
.th{width:84px;height:84px;object-fit:cover;border-radius:12px;flex:none}
.lead{display:flex;gap:12px;align-items:center}
main{max-width:760px;margin:auto;padding:0 16px}
.tabs{display:flex;gap:8px;overflow-x:auto;padding:12px 0;position:sticky;top:env(safe-area-inset-top,0px);background:var(--bg);z-index:5}
.tab{flex:none;border:1.5px solid var(--line);background:var(--surface);color:var(--ink);font:inherit;padding:8px 18px;border-radius:99px;cursor:pointer}
.tab[aria-selected=true]{background:var(--red);border-color:var(--red);color:var(--onred);font-weight:700}
.item{display:flex;justify-content:space-between;align-items:center;gap:12px;padding:16px 0;border-bottom:1px solid var(--line)}
.item h3{margin:0;font-size:18px}.item p{margin:2px 0 0;color:var(--mute);font-size:14px}
.price{font-weight:700;white-space:nowrap}
button{font:inherit;cursor:pointer}
.add{background:var(--ink);color:var(--bg);border:0;border-radius:10px;padding:9px 16px;font-weight:700;white-space:nowrap}
:focus-visible{outline:3px solid var(--gold);outline-offset:2px}
.info{margin:28px 0;padding:18px;background:var(--surface);border:1px solid var(--line);border-radius:14px;display:grid;gap:6px;font-size:15px}
.info a{color:var(--red);font-weight:700}
footer{text-align:center;color:var(--mute);font-size:13px;padding:10px 16px 30px}
.bar{position:fixed;inset:auto 0 0 0;padding:12px 16px calc(12px + env(safe-area-inset-bottom,0px));background:var(--bg);border-top:1px solid var(--line);z-index:6}
.bar button{width:100%;max-width:728px;display:flex;justify-content:space-between;margin:auto;background:var(--red);color:var(--onred);border:0;border-radius:14px;padding:14px 18px;font-weight:700;font-size:17px}
.bar button:disabled{opacity:.45}
.sheet{position:fixed;inset:0;background:#000a;z-index:20;display:none;align-items:flex-end;justify-content:center}
.sheet.on{display:flex}
.panel{background:var(--bg);width:100%;max-width:560px;max-height:92%;overflow:auto;border-radius:22px 22px 0 0;padding:20px 20px calc(20px + env(safe-area-inset-bottom,0px))}
.panel h2{margin:0 0 4px;font-size:22px}
.x{float:left;background:none;border:0;font-size:28px;color:var(--mute);line-height:1}
.opt{display:flex;justify-content:space-between;padding:10px 12px;border:1.5px solid var(--line);border-radius:12px;margin:6px 0;background:var(--surface);cursor:pointer}
.opt input{accent-color:var(--red);margin-left:8px}
.opt:has(input:checked){border-color:var(--red)}
.opt label{flex:1;display:flex;justify-content:space-between;cursor:pointer}
h4{margin:16px 0 4px}
.row{display:flex;justify-content:space-between;padding:5px 0}
.big{font-size:20px;font-weight:800}
.cta{width:100%;background:var(--red);color:var(--onred);border:0;border-radius:14px;padding:14px;font-weight:700;font-size:17px;margin-top:14px}
.q{display:flex;align-items:center;gap:8px}
.q button{width:30px;height:30px;border-radius:50%;border:1.5px solid var(--line);background:var(--surface);color:var(--ink);font-size:18px;line-height:1}
.ci{padding:10px 0;border-bottom:1px solid var(--line);display:flex;justify-content:space-between;gap:10px}
.ci small{color:var(--mute);display:block}
.seg{display:flex;gap:6px;margin:12px 0}
.seg label{flex:1;text-align:center;border:1.5px solid var(--line);border-radius:12px;padding:9px;background:var(--surface);cursor:pointer}
.seg label:has(input:checked){border-color:var(--red);background:var(--red);color:var(--onred);font-weight:700}
.seg input{display:none}
input[type=text],input[type=tel],textarea{width:100%;font:inherit;padding:11px;border:1.5px solid var(--line);border-radius:10px;background:var(--surface);color:var(--ink);margin:4px 0 10px}
.err{color:var(--red);font-size:14px;min-height:18px}
.ok{text-align:center}.ok .big{font-size:26px;margin:10px 0}
</style>
</head>
<body>
<div class="safe">🛡️ יש מרחב מוגן צמוד לפיצרייה · משלוחים חמים · זמן משלוח לפי המרחק מקיבוץ מחניים</div>
<header class="hero"><img class="logo" src="logo.jpg" alt="Dooshi PIZZA"><p>הפיצה והטוסט הכי טעימים באזור. חומרי גלם טריים, גבינה איכותית ובצק פריך.</p></header>
<main>
<div class="tabs" role="tablist" id="tabs"></div>
<section id="list"></section>
<section class="info">
<strong>פיצה דושי, קיבוץ מחניים</strong>
<span>אפשר לאסוף חם וטרי או לשבת אצלנו.</span>
<span>טלפון: <a href="tel:0525001002">052-5001002</a></span>
<a href="https://www.google.com/maps/search/?api=1&query=%D7%A4%D7%99%D7%A6%D7%94+%D7%93%D7%95%D7%A9%D7%99+%D7%A7%D7%99%D7%91%D7%95%D7%A5+%D7%9E%D7%97%D7%A0%D7%99%D7%99%D7%9D" target="_blank" rel="noopener">פתח בגוגל מפות</a>
<span>מרחב מוגן תקני ונגיש צמוד לפיצרייה.</span>
</section>
</main>
<footer>© 2026 Pizza Dooshi · order@pizzadooshi.co.il</footer>
<div class="bar"><button id="cartBtn" onclick="openCart()" disabled><span>עגלה (<b id="cnt">0</b>)</span><span id="barTot">₪0</span></button></div>
<div class="sheet" id="sheet"><div class="panel" id="panel"></div></div>
<script>
const SIZES=[{n:'בינונית (זוגית)',p:40,x:3},{n:'משפחתית',p:60,x:5}];
const TOP=['זיתים','בצל','תירס','פלפל','עגבנייה','פטריות','בולגרית','טונה','פרמזן','בזיליקום','שמן זית'];
const TT=[...TOP,'רוטב עגבניות'];
const MENU={
'פיצות':[{id:'pz',name:'פיצה דושי',d:'בצק פריך, רוטב ייחודי וגבינה איכותית. בחרו גודל ותוספות.',pizza:1}],
'טוסטים':[{id:'t1',name:'טוסט',d:'גבינה צהובה עם כל התוספות שתרצו, בחינם',toast:1,p:30}],
'קינוחים':[{id:'d1',name:'זיווה שוקולד',d:'בצק חם עם שוקולד חלב ולבן וסוכר אבקה',p:35}],
'שתייה קלה':[{id:'s1',name:'קולה',d:'',p:10},{id:'s2',name:'זירו קולה',d:'',p:10},{id:'s3',name:'מיץ ענבים',d:'',p:10},{id:'s4',name:'מיץ תפוזים',d:'',p:10},{id:'s5',name:'ספרייט',d:'',p:10},{id:'s6',name:'פאנטה',d:'',p:10}]};
const IMG={t1:'pizza.jpg',pz:'pizza.jpg',d1:'pizza.jpg'};
const WA='972525001002';
let cart=[],mode='delivery',cat='פיצות',cur=null;
const $=id=>document.getElementById(id);
const sh=n=>'₪'+n;
const total=()=>cart.reduce((s,i)=>s+i.price*i.qty,0);
function tabs(){$('tabs').innerHTML=Object.keys(MENU).map(k=>`<button class="tab" role="tab" aria-selected="${k==cat}" onclick="cat='${k}';tabs();list()">${k}</button>`).join('')}
function list(){$('list').innerHTML=MENU[cat].map(i=>`<div class="item"><div class="lead">${IMG[i.id]?`<img class="th" src="${IMG[i.id]}" alt="${i.name}">`:''}<div><h3>${i.name}</h3><p>${i.d}</p></div></div><div style="text-align:left"><div class="price">${i.pizza?'מ-'+sh(SIZES[0].p):sh(i.p)}</div><button class="add" onclick="pick('${i.id}')">${i.pizza?'התאמת מנה':'הוסף'}</button></div></div>`).join('')}
function find(id){for(const k in MENU){const f=MENU[k].find(i=>i.id==id);if(f)return f}}
function pick(id){const it=find(id);if(it.toast){cur={tops:[],toast:1};pizzaSheet();openS();return}if(!it.pizza){push({key:id,name:it.name,price:it.p,note:''});return}cur={size:0,tops:[]};pizzaSheet();openS()}
function pPrice(){if(cur.toast)return 30;return SIZES[cur.size].p+Math.max(0,cur.tops.length-1)*SIZES[cur.size].x}
function pizzaSheet(){
const T=!!cur.toast;
$('panel').innerHTML=`<button class="x" onclick="closeS()" aria-label="סגור">×</button><h2>${T?'טוסט':'פיצה דושי'}</h2><p style="color:var(--mute);margin:0">${T?'כל התוספות בחינם, בחרו כמה שרוצים':'בחרו גודל ותוספות'}</p>${T?`<img src="${IMG.t1}" alt="" style="width:100%;height:170px;object-fit:cover;border-radius:14px;margin-top:10px">`:`<img src="${IMG.pz}" alt="" style="width:100%;height:170px;object-fit:cover;border-radius:14px;margin-top:10px">
<h4>גודל</h4>${SIZES.map((s,i)=>`<div class="opt"><label><span><input type="radio" name="sz" ${i==cur.size?'checked':''} onchange="rs(${i})">${s.n}</span><span>${sh(s.p)}</span></label></div>`).join('')}`}
<h4>תוספות ${T?'':`<small style="font-weight:400;color:var(--mute)">(הראשונה בחינם, כל נוספת ₪${SIZES[cur.size].x})</small>`}</h4>
${(T?TT:TOP).map(t=>`<div class="opt"><label><span><input type="checkbox" ${cur.tops.includes(t)?'checked':''} onchange="tg('${t}',this.checked)">${t}</span><span>${T?'חינם':cur.tops.length&&!cur.tops.includes(t)?'+₪'+SIZES[cur.size].x:cur.tops.length?'':'חינם'}</span></label></div>`).join('')}
<button class="cta" onclick="addPizza()">הוסף לעגלה · <span id="pp">${sh(pPrice())}</span></button>`}
function rs(i){cur.size=i;const y=$('panel').scrollTop;pizzaSheet();$('panel').scrollTop=y}
function tg(t,on){cur.tops=on?[...cur.tops,t]:cur.tops.filter(x=>x!=t);const y=$('panel').scrollTop;pizzaSheet();$('panel').scrollTop=y}
function upd(){$('pp').textContent=sh(pPrice())}
function addPizza(){const n=cur.toast?'':SIZES[cur.size].n;push({key:(cur.toast?'ts':'pz'+cur.size)+cur.tops.join(),name:cur.toast?'טוסט':'פיצה דושי '+n,price:pPrice(),note:cur.tops.length?'תוספות: '+cur.tops.join(', '):'ללא תוספות'});closeS()}
function push(o){const e=cart.find(c=>c.key==o.key);e?e.qty++:cart.push({...o,qty:1});sync()}
function sync(){$('cnt').textContent=cart.reduce((s,i)=>s+i.qty,0);$('barTot').textContent=sh(total());$('cartBtn').disabled=!cart.length}
function openS(){$('sheet').classList.add('on')}
function closeS(){$('sheet').classList.remove('on')}
$('sheet').addEventListener('click',e=>{if(e.target.id=='sheet')closeS()});
function qty(i,d){cart[i].qty+=d;if(cart[i].qty<1)cart.splice(i,1);sync();cart.length?openCart():closeS()}
function fee(){return mode=='delivery'?15:0}
function openCart(){
$('panel').innerHTML=`<button class="x" onclick="closeS()" aria-label="סגור">×</button><h2>העגלה שלך</h2>
${cart.map((c,i)=>`<div class="ci"><div>${c.name}<small>${c.note}</small><div class="q" style="margin-top:6px"><button onclick="qty(${i},1)" aria-label="הוסף">+</button><b>${c.qty}</b><button onclick="qty(${i},-1)" aria-label="הסר">−</button></div></div><div class="price">${sh(c.price*c.qty)}</div></div>`).join('')}
<div class="seg"><label><input type="radio" name="m" ${mode=='delivery'?'checked':''} onchange="mode='delivery';openCart()">משלוח (+₪15)</label><label><input type="radio" name="m" ${mode=='pickup'?'checked':''} onchange="mode='pickup';openCart()">איסוף עצמי</label></div>
<div class="row"><span>סכום ביניים</span><span>${sh(total())}</span></div><div class="row"><span>דמי משלוח</span><span>${sh(fee())}</span></div>
<div class="row big"><span>סה״כ לתשלום</span><span>${sh(total()+fee())}</span></div>
<button class="cta" onclick="checkout()">המשך להזמנה</button>`;openS()}
function checkout(){
$('panel').innerHTML=`<button class="x" onclick="closeS()" aria-label="סגור">×</button><h2>פרטי הזמנה ותשלום</h2>
<label>שם מלא *<input type="text" id="nm" autocomplete="name"></label>
<label>מספר טלפון *<input type="tel" id="ph" autocomplete="tel"></label>
${mode=='delivery'?`<label>כתובת למשלוח (ישוב, רחוב ומספר בית) *<input type="text" id="ad" autocomplete="street-address"></label><p style="color:var(--mute);font-size:14px;margin:-4px 0 10px">זמן המשלוח יחושב לפי המרחק מקיבוץ מחניים.</p>`:''}
<label>הערות להזמנה<textarea id="nt" rows="2"></textarea></label>
<div class="seg"><label><input type="radio" name="pay" value="מזומן" checked>מזומן</label><label><input type="radio" name="pay" value="Bit">Bit</label></div>
<p id="bitn" style="color:var(--mute);font-size:14px">לתשלום ב-Bit: 052-5001002</p>
<div class="err" id="err"></div>
<button class="cta" onclick="send()">שלח הזמנה בוואטסאפ · ${sh(total()+fee())}</button>`;
}
function send(){
const v=id=>($(id)?$(id).value.trim():'');const nm=v('nm'),ph=v('ph'),ad=v('ad');
if(!nm||!ph||(mode=='delivery'&&!ad)){$('err').textContent='נא למלא שם, טלפון'+(mode=='delivery'?' וכתובת':'')+'.';return}
const pay=document.querySelector('input[name=pay]:checked').value;
let t='*הזמנה חדשה - Dooshi PIZZA*\n';
cart.forEach(c=>{t+=`\n• ${c.qty}× ${c.name}${c.note?' ('+c.note+')':''} - ${sh(c.price*c.qty)}`});
t+=`\n\nסוג: ${mode=='delivery'?'משלוח':'איסוף עצמי'}\nסה״כ: ${sh(total()+fee())}\nתשלום: ${pay}\nשם: ${nm}\nטלפון: ${ph}`;
if(ad)t+='\nכתובת: '+ad;if(v('nt'))t+='\nהערות: '+v('nt');
const u='https://wa.me/'+WA+'?text='+encodeURIComponent(t),sm='sms:0525001002?&body='+encodeURIComponent(t);window.open(u,'_blank');
$('panel').innerHTML=`<div class="ok"><div style="font-size:48px">🍕</div><div class="big">עוד צעד אחד: שליחה לפיצרייה</div><p>ההזמנה לא נשלחת עד שלוחצים שליחה. אם וואטסאפ לא נפתח, לחצו על הכפתור.</p><a class="cta" style="display:block;text-decoration:none;text-align:center" href="${u}" target="_blank" rel="noopener">שלח בוואטסאפ</a><a class="cta" style="display:block;text-decoration:none;text-align:center;background:var(--surface);color:var(--ink);border:1.5px solid var(--line)" href="${sm}">שלח בהודעת SMS</a><p>זמן המשלוח נקבע לפי המרחק מקיבוץ מחניים. נעדכן אותך בהודעה.</p><button class="add" onclick="cart=[];sync();closeS()">חזרה לתפריט</button></div>`}
tabs();list();sync();
</script>
</body>
</html>
```