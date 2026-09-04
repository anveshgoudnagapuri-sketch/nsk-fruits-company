<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>NSK FRUITS - Warangal</title>
</head>
<body style="margin:0;font-family:Arial;background:#f5f5f5">

<div style="background:#0a7a0a;color:white;padding:15px;text-align:center">
<h2 style="margin:0">NSK FRUITS COMPANY</h2>
<small>Laxmipuram - 9494110853 / 9390591252</small>
</div>

<div style="background:orange;color:white;padding:8px;text-align:center;font-weight:bold">
FREE DELIVERY - Warangal
</div>

<div style="padding:10px;display:grid;grid-template-columns:1fr 1fr;gap:10px">
<div style="background:white;padding:15px;border-radius:10px;text-align:center"><b>Mango</b><br>Rs.120/kg<br><button onclick="add('Mango',120)" style="background:green;color:white;border:0;padding:8px 20px;border-radius:20px;margin-top:8px">ADD +</button></div>
<div style="background:white;padding:15px;border-radius:10px;text-align:center"><b>Mozambi</b><br>Rs.60/kg<br><button onclick="add('Mozambi',60)" style="background:green;color:white;border:0;padding:8px 20px;border-radius:20px;margin-top:8px">ADD +</button></div>
<div style="background:white;padding:15px;border-radius:10px;text-align:center"><b>Orange</b><br>Rs.80/kg<br><button onclick="add('Orange',80)" style="background:green;color:white;border:0;padding:8px 20px;border-radius:20px;margin-top:8px">ADD +</button></div>
<div style="background:white;padding:15px;border-radius:10px;text-align:center"><b>Banana</b><br>Rs.50/doz<br><button onclick="add('Banana',50)" style="background:green;color:white;border:0;padding:8px 20px;border-radius:20px;margin-top:8px">ADD +</button></div>
<div style="background:white;padding:15px;border-radius:10px;text-align:center"><b>Coconut</b><br>Rs.30/pc<br><button onclick="add('Coconut',30)" style="background:green;color:white;border:0;padding:8px 20px;border-radius:20px;margin-top:8px">ADD +</button></div>
<div style="background:white;padding:15px;border-radius:10px;text-align:center"><b>Anar</b><br>Rs.180/kg<br><button onclick="add('Anar',180)" style="background:green;color:white;border:0;padding:8px 20px;border-radius:20px;margin-top:8px">ADD +</button></div>
</div>

<div style="background:white;margin:10px;padding:15px;border-radius:12px">
<h3>Your Order (<span id="c">0</span>)</h3>
<div id="list2">Empty - Add fruits top</div>
<input id="n" placeholder="Your Name *" style="width:100%;padding:12px;margin-top:10px;border:1px solid #ccc;border-radius:8px;box-sizing:border-box">
<input id="p" placeholder="Phone *" style="width:100%;padding:12px;margin-top:8px;border:1px solid #ccc;border-radius:8px;box-sizing:border-box">
<input id="a" placeholder="Address Warangal *" style="width:100%;padding:12px;margin-top:8px;border:1px solid #ccc;border-radius:8px;box-sizing:border-box">
<button onclick="order()" style="width:100%;background:#25D366;color:white;padding:15px;border:0;border-radius:10px;font-weight:bold;margin-top:12px;font-size:16px">BOOK ON WHATSAPP 94941</button>
<div style="display:flex;gap:8px;margin-top:8px">
<a href="tel:9494110853" style="flex:1;background:green;color:white;text-align:center;padding:10px;border-radius:8px;text-decoration:none;font-weight:bold">CALL 94941</a>
<a href="tel:9390591252" style="flex:1;background:orange;color:white;text-align:center;padding:10px;border-radius:8px;text-decoration:none;font-weight:bold">CALL 93905</a>
</div>
</div>

<script>
var cart=[];
function add(name,price){
var f=null;
for(var i=0;i<cart.length;i++){if(cart[i].n==name)f=cart[i]}
if(f)f.q++;else cart.push({n:name,pr:price,q:1});
show();
}
function show(){
document.getElementById('c').innerText=cart.length;
var h="";var tot=0;
if(cart.length==0)h="Empty - Add fruits top";
else{for(var i=0;i<cart.length;i++){tot+=cart[i].pr*cart[i].q;h+=cart[i].n+" x "+cart[i].q+" = Rs."+cart[i].pr*cart[i].q+" <span onclick='del("+i+")' style='color:red;font-weight:bold'> [X]</span><br>";}h+="<br><b>Total Rs."+tot+"</b>";}
document.getElementById('list2').innerHTML=h;
}
function del(i){cart.splice(i,1);show();}
function order(){
var name=document.getElementById('n').value;
var ph=document.getElementById('p').value;
var ad=document.getElementById('a').value;
if(cart.length==0){alert("Add fruit first");return;}
if(!name||!ph){alert("Name Phone pettandi");return;}
var tot=0;var msg="*NEW ORDER NSK FRUITS*%0AName:"+name+"%0APhone:"+ph+"%0AAddr:"+ad+"%0A%0A";
for(var i=0;i<cart.length;i++){tot+=cart[i].pr*cart[i].q;msg+=cart[i].n+" x "+cart[i].q+"%0A";}
msg+="%0ATotal Rs."+tot+" COD";
window.open("https://wa.me/919494110853?text="+msg,"_blank");
}
</script>

</body>
</html>https://nsk-fruits-company.vercel.app<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NSK Fruits Company - Warangal</title>
<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:Arial}
body{background:#f8fff8}
.topbar{background:#16823b;color:white;padding:12px 15px;display:flex;justify-content:space-between;align-items:center;position:sticky;top:0;z-index:100}
.cart-btn{background:white;color:#16823b;border:0;padding:9px 16px;border-radius:25px;font-weight:bold;cursor:pointer}
.hero{background:linear-gradient(135deg,#e8f5e9,#ffffff);padding:28px 15px;text-align:center}
.hero h2{font-size:28px;color:#0a4a1f}
.filters{display:flex;gap:8px;padding:12px;overflow:auto;background:white;position:sticky;top:56px;z-index:90;border-bottom:1px solid #eee}
.filters button{white-space:nowrap;padding:7px 15px;border-radius:20px;border:1px solid #16823b;background:white;color:#16823b;cursor:pointer}
.filters button.active{background:#16823b;color:white}
.grid{display:grid;grid-template-columns:1fr 1fr;gap:12px;padding:15px}
@media(min-width:600px){.grid{grid-template-columns:1fr 1fr 1fr 1fr}}
.card{background:white;border-radius:16px;padding:12px;text-align:center;box-shadow:0 2px 10px rgba(0,0,0,.07)}
.card .im{font-size:42px}
.card h3{font-size:15px;margin:6px 0}
.card .pr{color:#16823b;font-weight:bold}
.card button{width:100%;margin-top:8px;background:#16823b;color:white;border:0;padding:8px;border-radius:20px;font-weight:bold;cursor:pointer}
#cartModal{position:fixed;inset:0;background:rgba(0,0,0,.6);display:none;place-items:center;z-index:200;padding:15px}
#cartModal.show{display:grid}
.modal-card{background:white;width:100%;max-width:420px;border-radius:16px;padding:16px;max-height:90vh;overflow:auto}
.full{width:100%;padding:12px;border-radius:10px;text-align:center;display:block;margin-top:8px;text-decoration:none;font-weight:bold;border:0;cursor:pointer}
.whatsapp{background:#25D366;color:white}
.call{background:#16823b;color:white}
input,textarea,select{width:100%;padding:10px;margin-top:4px;border-radius:8px;border:1px solid #ccc}
</style>
</head>
<body>
<header class="topbar">
<div><b>🍎 NSK Fruits</b><br><small style="font-size:11px">Laxmipuram, Warangal</small></div>
<button class="cart-btn" onclick="openCart()">🛒 <span id="cartCount">0</span></button>
</header>

<div class="hero">
<h2>Fresh Fruits Daily</h2>
<p>Free Delivery in Warangal - 9494110853 / 9390591252</p>
</div>

<div class="filters">
<button class="active" onclick="filterF('all',this)">All</button>
<button onclick="filterF('daily',this)">Daily</button>
<button onclick="filterF('seasonal',this)">Seasonal</button>
<button onclick="filterF('local',this)">Local</button>
<input id="search" placeholder="Search..." oninput="render()" style="margin-left:10px;max-width:140px;padding:6px 12px;border-radius:20px">
</div>

<div id="grid" class="grid"></div>

<div id="cartModal"><div class="modal-card">
<div style="display:flex;justify-content:space-between;align-items:center"><h3>🛒 Your Cart</h3><button onclick="closeCart()" style="border:0;background:#eee;width:30px;height:30px;border-radius:50%">✕</button></div>
<div id="cartItems" style="margin:12px 0"></div>
<div id="cartTotal" style="font-weight:bold;border-top:1px solid #eee;padding-top:10px"></div>
<button class="full call" onclick="showCheckout()">Proceed to Book</button>
</div></div>

<div id="checkoutModal" style="position:fixed;inset:0;background:rgba(0,0,0,.6);display:none;place-items:center;z-index:201;padding:15px"><div class="modal-card">
<h3>📦 Book Order</h3>
<form onsubmit="placeOrder(event)">
<label>Name<input id="cName" required></label>
<label>Phone<input id="cPhone" required></label>
<label>Address<textarea id="cAddr" required></textarea></label>
<div id="sum" style="background:#f5f5f5;padding:10px;border-radius:8px;margin:10px 0;font-size:13px"></div>
<button class="full whatsapp" type="submit">💬 Send WhatsApp to 9494110853</button>
<a class="full whatsapp" href="https://wa.me/919390591252" style="background:#128C7E;display:block;text-align:center">💬 WhatsApp 9390591252</a>
<div style="display:flex;gap:8px"><a class="full call" href="tel:+919494110853">📞 94941</a><a class="full call" href="tel:+919390591252" style="background:orange">📞 93905</a></div>
<button type="button" onclick="document.getElementById('checkoutModal').style.display='none'" class="full" style="background:#eee">Close</button>
</form>
</div></div>

<footer style="background:#0a4a1f;color:white;text-align:center;padding:20px;margin-top:20px">
<b>NSK Fruits Company</b><br>Girmajipet Market, Warangal<br>9494110853 | 9390591252
</footer>

<script>
let products=[
{id:1,name:"Banana",price:50,emoji:"🍌",cat:"daily"},
{id:2,name:"Coconut",price:30,emoji:"🥥",cat:"daily"},
{id:3,name:"Kobaribonda",price:40,emoji:"🥥",cat:"daily"},
{id:4,name:"Mango",price:120,emoji:"🥭",cat:"seasonal"},
{id:5,name:"Watermelon",price:25,emoji:"🍉",cat:"seasonal"},
{id:6,name:"Muskmelon",price:35,emoji:"🍈",cat:"seasonal"},
{id:7,name:"Orange",price:80,emoji:"🍊",cat:"daily"},
{id:8,name:"Apple",price:200,emoji:"🍎",cat:"daily"},
{id:9,name:"Grapes",price:100,emoji:"🍇",cat:"daily"},
{id:10,name:"Pineapple",price:60,emoji:"🍍",cat:"local"},
{id:11,name:"Papaya",price:40,emoji:"🍈",cat:"local"},
{id:12,name:"Guava",price:60,emoji:"🍈",cat:"local"},
{id:13,name:"Pomegranate",price:180,emoji:"🍎",cat:"daily"},
{id:14,name:"Mosambi",price:60,emoji:"🍊",cat:"daily"},
{id:15,name:"Sapota",price:70,emoji:"🍈",cat:"local"},
{id:16,name:"Custard Apple",price:90,emoji:"🍈",cat:"seasonal"},
{id:17,name:"Jackfruit",price:50,emoji:"🍈",cat:"seasonal"},
{id:18,name:"Strawberry",price:250,emoji:"🍓",cat:"seasonal"},
{id:19,name:"Dragon Fruit",price:150,emoji:"🍎",cat:"seasonal"},
{id:20,name:"Litchi",price:200,emoji:"🍒",cat:"seasonal"}
];
let curCat='all';
let cart=JSON.parse(localStorage.getItem('nsk20')||'[]');
function save(){localStorage.setItem('nsk20',JSON.stringify(cart));document.getElementById('cartCount').innerText=cart.reduce((s,i)=>s+i.qty,0)}
function filterF(c,btn){curCat=c;document.querySelectorAll('.filters button').forEach(b=>b.classList.remove('active'));btn.classList.add('active');render()}
function render(){
let q=document.getElementById('search').value.toLowerCase();
let g=document.getElementById('grid');g.innerHTML='';
products.filter(p=>(curCat=='all'||p.cat==curCat)&&p.name.toLowerCase().includes(q)).forEach(p=>{
g.innerHTML+=`<div class="card"><div class="im">${p.emoji}</div><h3>${p.name}</h3><div class="pr">Rs.${p.price}</div><small>${p.cat}</small><br><button onclick="addCart(${p.id})">ADD +</button></div>`
});save()}
function addCart(id){let f=cart.find(c=>c.id==id);if(f)f.qty++;else{let p=products.find(x=>x.id==id);cart.push({...p,qty:1})}save();openCart()}
function openCart(){let b=document.getElementById('cartItems');let t=0;b.innerHTML='';if(!cart.length)b.innerHTML='Empty - Add fruits!';cart.forEach((c,i)=>{let s=c.price*c.qty;t+=s;b.innerHTML+=`${c.emoji} ${c.name} x${c.qty}=Rs.${s} <span onclick="cart.splice(${i},1);save();openCart()" style="color:red;cursor:pointer">[X]</span><br>`});document.getElementById('cartTotal').innerText='Total: Rs.'+t;document.getElementById('cartModal').classList.add('show');document.getElementById('cartModal').style.display='grid'}
function closeCart(){document.getElementById('cartModal').classList.remove('show');document.getElementById('cartModal').style.display='none'}
function showCheckout(){if(!cart.length){alert('Add fruit');return}closeCart();let t=0,h='';cart.forEach(c=>{t+=c.price*c.qty;h+=c.name+' x'+c.qty+'<br>'});document.getElementById('sum').innerHTML=h+'<b>Total Rs.'+t+'</b>';document.getElementById('checkoutModal').style.display='grid'}
function placeOrder(e){e.preventDefault();let name=document.getElementById('cName').value;let ph=document.getElementById('cPhone').value;let ad=document.getElementById('cAddr').value;let tot=0,items='';cart.forEach(c=>{tot+=c.price*c.qty;items+=c.name+' x'+c.qty+'=Rs.'+c.price*c.qty+'%0A'});let msg=`*NSK FRUITS NEW ORDER*%0AName:${name}%0APh:${ph}%0AAddr:${ad}%0A%0A${items}%0ATotal Rs.${tot} COD`;window.open('https://wa.me/919494110853?text='+msg,'_blank');setTimeout(()=>window.open('https://wa.me/919390591252?text='+msg,'_blank'),1200);cart= open [];save();document.getElementById('checkoutModal').style.display='none'}
render();
</script>
</body>
</html>
