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
</html>https://nsk-fruits-company.vercel.app
