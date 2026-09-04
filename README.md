<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NSK Fruits - Warangal</title>
<script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-50">
<!-- HEADER -->
<div class="bg-white p-4 sticky top-0 z-20 shadow flex justify-between items-center">
<div><b class="text-green-700 text-lg">NSK FRUITS COMPANY</b><p class="text-xs text-gray-500">Laxmipuram, Warangal - 9390591252</p></div>
<button onclick="showCart()" class="bg-green-600 text-white px-4 py-2 rounded-full">🛒 <span id="cCount">0</span></button>
</div>
<!-- PRODUCTS -->
<div id="productList" class="grid grid-cols-2 gap-3 p-3"></div>
<!-- CART -->
<div id="cartPage" class="fixed inset-0 bg-white z-50 hidden overflow-auto p-4"></div>

<script>
const WA="919390591252";
let products=[
{id:1,n:"Banganapalli Mango",p:120,u:"1 KG",e:"🥭",img:"https://images.unsplash.com/photo-1553279768-865429fa0078?w=500"},
{id:2,n:"Mozambi",p:60,u:"1 KG",e:"🍋",img:"https://images.unsplash.com/photo-1582979512210-99b6a53386f9?w=500"},
{id:3,n:"Santra",p:80,u:"1 KG",e:"🍊",img:"https://images.unsplash.com/photo-1580052614034-c55d20bfee3b?w=500"},
{id:4,n:"Banana",p:50,u:"12 pcs",e:"🍌",img:"https://images.unsplash.com/photo-1571771894821-ce9b6c11b08e?w=500"},
{id:5,n:"Coconut",p:30,u:"1 Pc",e:"🥥",img:"https://images.unsplash.com/photo-1581008728153-2ae4d32f96cc?w=500"},
{id:6,n:"Anaar",p:180,u:"1 KG",e:"🍎",img:"https://images.unsplash.com/photo-1615484477778-9a8a4d9dba0f?w=500"},
{id:7,n:"Watermelon",p:40,u:"1 Pc",e:"🍉",img:"https://images.unsplash.com/photo-1589984662646-e7b2e4962f18?w=500"},
{id:8,n:"Grapes",p:90,u:"500g",e:"🍇",img:"https://images.unsplash.com/photo-1596363505729-4190a9506133?w=500"}
];
let cart=JSON.parse(localStorage.getItem('nsk_cart')||'[]');
function save(){localStorage.setItem('nsk_cart',JSON.stringify(cart));document.getElementById('cCount').innerText=cart.reduce((a,b)=>a+b.q,0);}
function render(){
let h="";products.forEach(pr=>{h+=`<div class="bg-white rounded-2xl p-3 shadow border"><div class="h-28 bg-gray-50 rounded-xl overflow-hidden flex items-center justify-center"><img src="${pr.img}" class="w-full h-full object-cover" onerror="this.parentElement.innerHTML='${pr.e}'" style="font-size:50px"></div><div class="mt-2"><div class="text-xs text-green-600 font-bold">${pr.u}</div><b class="text-sm">${pr.n}</b><div class="text-green-700 font-bold mt-1">₹${pr.p}</div><button onclick="add(${pr.id})" class="w-full mt-2 bg-green-600 text-white py-2 rounded-full text-sm font-bold">ADD TO CART +</button></div></div>`});document.getElementById('productList').innerHTML=h;save();
}
function add(id){let pr=products.find(x=>x.id==id);let ex=cart.find(x=>x.id==id);if(ex)ex.q++;else cart.push({...pr,q:1});save();alert(pr.n+" Added!");}
function showCart(){
let tot=0;let html=`<div class="flex items-center gap-3 mb-4"><span onclick="document.getElementById('cartPage').classList.add('hidden')" class="text-2xl">←</span><b>My Bookings / Cart</b></div>`;
if(cart.length==0){html+=`<div class="text-center mt-20"><div class="text-6xl">🛒</div><p class="mt-4">Cart Empty - Add Fruits!</p><button onclick="document.getElementById('cartPage').classList.add('hidden')" class="mt-4 bg-green-600 text-white px-6 py-2 rounded-full">Shop Now</button></div>`}
else{
cart.forEach(c=>{tot+=c.p*c.q;html+=`<div class="flex justify-between items-center bg-gray-50 p-3 rounded-xl mb-2"><div class="flex gap-3 items-center"><span class="text-2xl">${c.e}</span><div><b class="text-sm">${c.n}</b><div class="text-xs">${c.u} x ${c.q} = ₹${c.p*c.q}</div></div></div><div class="flex gap-2 items-center"><button onclick="qty(${c.id},-1)" class="w-8 h-8 border rounded-full">-</button><b>${c.q}</b><button onclick="qty(${c.id},1)" class="w-8 h-8 border rounded-full">+</button><button onclick="removeItem(${c.id})" class="ml-2 text-red-500 text-xs">X</button></div></div>`});
html+=`<div class="bg-white p-4 rounded-xl border mt-4">
<h3 class="font-bold">Customer Booking Details</h3>
<input id="name" placeholder="Your Name *" class="w-full p-3 border rounded-xl mt-3">
<input id="phone" placeholder="Phone Number *" class="w-full p-3 border rounded-xl mt-2">
<textarea id="addr" placeholder="Full Address, Warangal *" class="w-full p-3 border rounded-xl mt-2"></textarea>
<input id="date" type="date" class="w-full p-3 border rounded-xl mt-2">
<input id="time" type="time" class="w-full p-3 border rounded-xl mt-2">
<div class="flex justify-between font-bold text-lg mt-4 border-t pt-3"><span>Total to Pay (COD)</span><span>₹${tot}</span></div>
<button onclick="bookNow(${tot})" class="w-full bg-[#25D366] text-white py-4 rounded-xl font-bold mt-4 text-lg">✅ CONFIRM BOOKING ON WHATSAPP</button>
<a href="tel:+919390591252" class="block text-center w-full border-2 border-green-600 text-green-600 py-3 rounded-xl font-bold mt-2">📞 CALL NOW</a>
</div>`;
}
document.getElementById('cartPage').innerHTML=html;document.getElementById('cartPage').classList.remove('hidden');
}
function qty(id,v){let ex=cart.find(x=>x.id==id);if(ex){ex.q+=v;if(ex.q<=0)cart=cart.filter(x=>x.id!=id);}save();showCart();}
function removeItem(id){cart=cart.filter(x=>x.id!=id);save();showCart();}
function bookNow(total){
let n=document.getElementById('name').value, p=document.getElementById('phone').value, a=document.getElementById('addr').value, d=document.getElementById('date').value, t=document.getElementById('time').value;
if(!n||!p||!a){alert("Name, Phone, Address fill cheyandi");return;}
let msg=`*NEW BOOKING - NSK FRUITS*%0AName:${n}%0APhone:${p}%0AAddr:${a}%0ADate:${d}%0ATime:${t}%0A%0A*Items:*%0A`;cart.forEach(c=>{msg+=`${c.n} x ${c.q} = ₹${c.p*c.q}%0A`});msg+=`%0A*Total:₹${total} COD*`;
window.open(`https://wa.me/${WA}?text=${msg}`,"_blank");cart=[];save();document.getElementById('cartPage').classList.add('hidden');alert("Booking WhatsApp ki vellindi!");
}
render();
</script>
</body>
</html><img width="554" height="202" alt="1000014857" src="https://github.com/user-attachments/assets/a71804ce-0e73-43e8-ad09-2f58d7944fa7" />

