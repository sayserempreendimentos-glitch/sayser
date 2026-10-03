<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0,maximum-scale=1.0,user-scalable=no">

<title>GES - Grupo Empresarial Sayser</title>

<style>
*{
box-sizing:border-box;
margin:0;
padding:0;
font-family:Arial,sans-serif;
}

body{
background:#000;
color:#fff;
padding:12px;
display:flex;
justify-content:center;
}

.mobile-container{
width:100%;
max-width:420px;
}

.header{
text-align:center;
padding:8px 0 12px;
border-bottom:1px solid #1b1b1b;
}

.logo-main{
color:#ffcc00;
font-size:24px;
font-weight:bold;
letter-spacing:2px;
}

.subtitle{
color:#777;
font-size:11px;
margin-top:3px;
}

.categories-menu{
display:flex;
gap:6px;
overflow-x:auto;
padding:12px 0;
scrollbar-width:none;
}

.categories-menu::-webkit-scrollbar{
display:none;
}

.tab-btn{
background:#0a0a0a;
color:#777;
border:1px solid #222;
padding:9px 15px;
border-radius:18px;
white-space:nowrap;
font-size:11px;
cursor:pointer;
font-weight:bold;
}

.tab-btn.active{
background:#ffcc00;
color:#000;
border-color:#ffcc00;
}

.tab-btn.contract-tab{
color:#00ff66;
border-color:#00ff66;
}

.tab-btn.contract-tab.active{
background:#00ff66;
color:#000;
}

.products-container{
min-height:260px;
}

.product-card{
background:#0a0a0a;
border:1px solid #202020;
border-radius:13px;
padding:14px;
display:flex;
flex-direction:column;
gap:9px;
}

.img-box{
width:100%;
height:190px;
background:#fff;
border-radius:9px;
display:flex;
align-items:center;
justify-content:center;
overflow:hidden;
}

.img-box img{
width:100%;
height:100%;
object-fit:contain;
}

.no-image{
color:#888;
font-size:11px;
}

.product-title{
font-size:16px;
font-weight:bold;
}

.product-desc{
font-size:12px;
color:#888;
line-height:1.4;
}

.price-row{
display:flex;
justify-content:space-between;
align-items:center;
padding:10px 0;
border-top:1px solid #222;
border-bottom:1px solid #222;
}

.price-block{
display:flex;
flex-direction:column;
gap:2px;
}

.label{
font-size:8px;
color:#555;
text-transform:uppercase;
font-weight:bold;
}

.val-main{
color:#ffcc00;
font-size:17px;
font-weight:bold;
}

.val-calc{
color:#00ff66;
font-size:15px;
font-weight:bold;
}

.btn-add{
background:#ffcc00;
color:#000;
border:0;
padding:13px;
border-radius:8px;
font-size:13px;
font-weight:bold;
cursor:pointer;
}

.contract-area{
display:none;
}

.contract-card{
background:#0a0a0a;
border:1px solid #00ff66;
border-radius:12px;
padding:13px;
}

.terms-box{
background:#000;
border:1px solid #222;
border-radius:7px;
padding:10px;
margin:10px 0;
max-height:180px;
overflow:auto;
color:#888;
font-size:11px;
line-height:1.45;
}

.checkbox-row{
display:flex;
gap:8px;
align-items:flex-start;
font-size:12px;
color:#ccc;
}

.cart-section{
background:#050505;
border:1px dashed #333;
border-radius:12px;
padding:12px;
margin-top:12px;
}

.cart-title{
color:#ffcc00;
font-size:12px;
font-weight:bold;
border-bottom:1px solid #222;
padding-bottom:7px;
margin-bottom:8px;
}

.cart-item{
display:flex;
justify-content:space-between;
align-items:center;
gap:8px;
font-size:11px;
color:#aaa;
padding:5px 0;
}

.remove-cart{
background:#ff3333;
color:#fff;
border:0;
border-radius:3px;
padding:3px 6px;
font-size:9px;
cursor:pointer;
}

.cart-totals{
border-top:1px solid #222;
margin-top:6px;
padding-top:8px;
display:flex;
justify-content:space-between;
font-size:12px;
font-weight:bold;
}

.btn-email{
width:100%;
margin-top:10px;
padding:11px;
border:0;
border-radius:7px;
background:#00ff66;
color:#000;
font-size:12px;
font-weight:bold;
cursor:pointer;
}

.empty{
text-align:center;
color:#555;
padding:30px 10px;
font-size:12px;
}


/* ================= ADM ================= */

#admBtn{
position:fixed;
right:12px;
bottom:12px;
z-index:9999;
background:#ffcc00;
color:#000;
border:0;
border-radius:8px;
padding:10px 14px;
font-weight:bold;
font-size:11px;
box-shadow:0 3px 12px #000;
cursor:pointer;
}

#admLogin{
display:none;
position:fixed;
inset:0;
z-index:10000;
background:#000;
padding:25px 15px;
overflow:auto;
}

.adm-login-box{
max-width:350px;
margin:100px auto;
background:#0a0a0a;
border:1px solid #ffcc00;
border-radius:12px;
padding:20px;
}

.adm-title{
color:#ffcc00;
font-size:20px;
font-weight:bold;
margin-bottom:5px;
}

.adm-email{
color:#777;
font-size:10px;
margin-bottom:15px;
}

.adm-label{
display:block;
font-size:10px;
color:#888;
margin:10px 0 4px;
}

.adm-input,
.adm-select{
width:100%;
padding:11px;
background:#000;
color:#fff;
border:1px solid #333;
border-radius:6px;
font-size:13px;
}

.adm-save{
width:100%;
margin-top:15px;
padding:12px;
background:#00ff66;
color:#000;
border:0;
border-radius:7px;
font-weight:bold;
cursor:pointer;
}

.adm-close{
width:100%;
margin-top:8px;
padding:10px;
background:#222;
color:#fff;
border:1px solid #444;
border-radius:7px;
cursor:pointer;
}

.adm-error{
color:#ff3333;
font-size:11px;
margin-top:8px;
display:none;
}

#admPanel{
display:none;
position:fixed;
inset:0;
z-index:10000;
background:#000;
color:#fff;
padding:15px;
overflow:auto;
}

.adm-box{
max-width:420px;
margin:auto;
background:#0a0a0a;
border:1px solid #ffcc00;
border-radius:12px;
padding:15px;
}

.adm-status{
color:#00ff66;
font-size:10px;
margin-top:8px;
display:none;
}

</style>
</head>

<body>

<div class="mobile-container">

<header class="header">

<div class="logo-main">
GES
</div>

<div class="subtitle">
Grupo Empresarial Sayser
</div>

</header>


<div class="categories-menu">

<button class="tab-btn active"
onclick="switchTab(event,'cosmeticos')">
Cosméticos
</button>

<button class="tab-btn"
onclick="switchTab(event,'alimento')">
Alimento
</button>

<button class="tab-btn"
onclick="switchTab(event,'hidraulico')">
Hidráulico
</button>

<button class="tab-btn"
onclick="switchTab(event,'eletrons')">
Elétrons
</button>

<button class="tab-btn"
onclick="switchTab(event,'eletronico')">
Eletrônico
</button>

<button class="tab-btn"
onclick="switchTab(event,'construcao')">
Construção
</button>

<button class="tab-btn"
onclick="switchTab(event,'bairroquiz')">
Bairro Quiz
</button>

<button class="tab-btn"
onclick="switchTab(event,'eletricas')">
Elétricas
</button>

<button class="tab-btn contract-tab"
onclick="switchTab(event,'contrato')">
📜 Contrato
</button>

</div>


<div id="productDisplayArea"
class="products-container">
</div>


<div id="contractArea"
class="contract-area">

<div class="contract-card">

<div class="product-title"
style="color:#00ff66">
Termos e Contrato GES
</div>

<div class="terms-box">

<strong>REGULAMENTO ADMINISTRATIVO SAYSER</strong>

<br><br>

Os bônus de indicação serão conferidos mediante
faturamento final confirmado.

<br><br>

A participação e as condições comerciais deverão
ser observadas conforme os termos vigentes da
SAYSER Empreendimentos.

</div>

<div class="checkbox-row">

<input
type="checkbox"
id="agreeTerms">

<label for="agreeTerms">
Declaro que li e aceito as condições.
</label>

</div>

</div>
</div>


<div class="cart-section">

<div class="cart-title">
🛒 Conferência do Pedido
</div>

<div id="cartItemsList">

<div class="empty">
Carrinho vazio.
</div>

</div>

<div class="cart-totals">

<span>

Produtos:

<span id="totalPrice"
style="color:#ffcc00">
R$ 0,00
</span>

</span>

<span>

Bônus:

<span id="totalBonus"
style="color:#00ff66">
R$ 0,00
</span>

</span>

</div>

<button
class="btn-email"
onclick="sendOrderEmail()">

📩 Confirmar e Enviar por E-mail

</button>

</div>

</div>


<!-- ================= BOTÃO ADM ================= -->

<button
id="admBtn"
onclick="openADM()">

⚙ ADM

</button>


<!-- ================= LOGIN ADM ================= -->

<div id="admLogin">

<div class="adm-login-box">

<div class="adm-title">
ADM SAYSER
</div>

<div class="adm-email">
01sayser@gmail.com
</div>

<label class="adm-label">
SENHA
</label>

<input
id="admPassword"
class="adm-input"
type="password"
inputmode="numeric"
placeholder="Digite a senha">

<div
id="admError"
class="adm-error">

Senha incorreta.

</div>

<button
class="adm-save"
onclick="loginADM()">

ENTRAR

</button>

<button
class="adm-close"
onclick="closeADMLogin()">

CANCELAR

</button>

</div>

</div>


<!-- ================= PAINEL ADM ================= -->

<div id="admPanel">

<div class="adm-box">

<div class="adm-title">
EDITOR SAYSER
</div>

<div class="adm-email">
ADM: 01sayser@gmail.com
</div>


<label class="adm-label">
CATEGORIA
</label>

<select
id="admCategory"
class="adm-select"
onchange="loadADMProduct()">

<option value="cosmeticos">
Cosméticos
</option>

<option value="alimento">
Alimento
</option>

<option value="hidraulico">
Hidráulico
</option>

<option value="eletrons">
Elétrons
</option>

<option value="eletronico">
Eletrônico
</option>

<option value="construcao">
Construção
</option>

<option value="bairroquiz">
Bairro Quiz
</option>

<option value="eletricas">
Elétricas
</option>

</select>


<label class="adm-label">
NOME DO PRODUTO
</label>

<input
id="admName"
class="adm-input"
type="text">


<label class="adm-label">
DESCRIÇÃO
</label>

<input
id="admDesc"
class="adm-input"
type="text">


<label class="adm-label">
PREÇO
</label>

<input
id="admPrice"
class="adm-input"
type="number"
step="0.01">


<label class="adm-label">
BÔNUS (%)
</label>

<input
id="admBonus"
class="adm-input"
type="number"
step="0.01">


<label class="adm-label">
IMAGEM — URL
</label>

<input
id="admImg"
class="adm-input"
type="text"
placeholder="https://...">


<button
class="adm-save"
onclick="saveADMProduct()">

💾 SALVAR PRODUTO

</button>

<div
id="admStatus"
class="adm-status">

Produto salvo com sucesso.

</div>


<button
class="adm-close"
onclick="closeADM()">

VOLTAR AO SITE

</button>

</div>

</div>


<script>


/* ================= PRODUTOS PADRÃO ================= */

const defaultProducts={

cosmeticos:{
name:"Perfume Premium GES",
desc:"Fragrância de alta fixação corporativa.",
price:150,
bonusPercent:10,
img:""
},

alimento:{
name:"Cesta de Alimentos Premium",
desc:"Mantimentos essenciais.",
price:150,
bonusPercent:15,
img:""
},

hidraulico:{
name:"Torneira Luxo Inox",
desc:"Material inoxidável com vedação de alta durabilidade.",
price:120,
bonusPercent:15,
img:""
},

eletrons:{
name:"Kit Componentes Elétrons",
desc:"Placas e conectores para pequenos circuitos.",
price:75,
bonusPercent:15,
img:""
},

eletronico:{
name:"DRONE V88 CÂMERA HD",
desc:"Giroscópio embutido e transmissão de imagens.",
price:180,
bonusPercent:15,
img:""
},

construcao:{
name:"Argamassa Interna AC1",
desc:"Rendimento ideal para pisos cerâmicos.",
price:28,
bonusPercent:15,
img:""
},

bairroquiz:{
name:"Produto Bairro Quiz",
desc:"Produto cadastrado pelo administrador.",
price:50,
bonusPercent:10,
img:""
},

eletricas:{
name:"Produto Elétrico",
desc:"Produto cadastrado pelo administrador.",
price:80,
bonusPercent:10,
img:""
}

};


/* ================= CARREGAMENTO ================= */

let products=
JSON.parse(
localStorage.getItem("SAYSER_GES_PRODUCTS")
)||defaultProducts;

let cart=[];


/* ================= FUNÇÕES DO SITE ================= */

function money(value){

return Number(value||0).toLocaleString(
"pt-BR",
{
style:"currency",
currency:"BRL"
}
);

}


function calculateBonus(product){

return Number(product.price||0)*
(Number(product.bonusPercent||0)/100);

}


function switchTab(event,category){

document
.querySelectorAll(".tab-btn")
.forEach(btn=>{
btn.classList.remove("active");
});

event.currentTarget.classList.add("active");


if(category==="contrato"){

document.getElementById(
"productDisplayArea"
).style.display="none";

document.getElementById(
"contractArea"
).style.display="block";

return;

}


document.getElementById(
"contractArea"
).style.display="none";

document.getElementById(
"productDisplayArea"
).style.display="block";

showProduct(category);

}


function showProduct(category){

const area=
document.getElementById(
"productDisplayArea"
);

const product=products[category];


if(!product){

area.innerHTML=
`<div class="empty">
Nenhum produto cadastrado nesta categoria.
</div>`;

return;

}


const bonus=
calculateBonus(product);


area.innerHTML=`

<div class="product-card">

<div class="img-box">

${
product.img
?
`<img
src="${escapeHTML(product.img)}"
alt="${escapeHTML(product.name)}"
onerror="this.style.display='none';this.parentElement.innerHTML='<span class=no-image>IMAGEM NÃO ENCONTRADA</span>'">`
:
`<span class="no-image">SEM IMAGEM</span>`
}

</div>


<div class="product-title">
${escapeHTML(product.name)}
</div>


<div class="product-desc">
${escapeHTML(product.desc)}
</div>


<div class="price-row">

<div class="price-block">

<span class="label">
PREÇO
</span>

<span class="val-main">
${money(product.price)}
</span>

</div>


<div class="price-block">

<span class="label">
BÔNUS
</span>

<span class="val-calc">
${money(bonus)}
</span>

</div>

</div>


<button
class="btn-add"
onclick="addToCart('${category}')">

ADICIONAR AO PEDIDO

</button>

</div>
`;

}


function escapeHTML(text){

return String(text||"")
.replace(/&/g,"&amp;")
.replace(/</g,"&lt;")
.replace(/>/g,"&gt;")
.replace(/"/g,"&quot;")
.replace(/'/g,"&#039;");

}


function addToCart(category){

const product=products[category];

if(!product)return;

cart.push({

name:product.name,

price:Number(product.price),

bonus:calculateBonus(product)

});

updateCart();

}


function updateCart(){

const list=
document.getElementById(
"cartItemsList"
);

let total=0;
let bonus=0;


if(cart.length===0){

list.innerHTML=
`<div class="empty">
Carrinho vazio.
</div>`;

}else{

list.innerHTML="";


cart.forEach((item,index)=>{

total+=item.price;
bonus+=item.bonus;


list.innerHTML+=`

<div class="cart-item">

<span>
${escapeHTML(item.name)}
</span>

<span>

${money(item.price)}

<button
class="remove-cart"
onclick="removeCartItem(${index})">

X

</button>

</span>

</div>

`;

});

}


document.getElementById(
"totalPrice"
).textContent=money(total);


document.getElementById(
"totalBonus"
).textContent=money(bonus);

}


function removeCartItem(index){

cart.splice(index,1);

updateCart();

}


function sendOrderEmail(){

if(cart.length===0){

alert("O pedido está vazio.");

return;

}


let body=
"PEDIDO GES - SAYSER%0A%0A";


cart.forEach(item=>{

body+=
encodeURIComponent(item.name)
+
" - "
+
encodeURIComponent(money(item.price))
+
"%0A";

});


const total=
cart.reduce(
(sum,item)=>sum+item.price,
0
);


const bonus=
cart.reduce(
(sum,item)=>sum+item.bonus,
0
);


body+=
"%0ATOTAL: "
+
encodeURIComponent(money(total));


body+=
"%0ABÔNUS: "
+
encodeURIComponent(money(bonus));


window.location.href=
"mailto:01sayser@gmail.com?subject="+
encodeURIComponent(
"Pedido GES - SAYSER"
)+
"&body="+body;

}


/* ================= ADM ================= */

function openADM(){

document.getElementById(
"admLogin"
).style.display="block";

document.getElementById(
"admPassword"
).value="";

document.getElementById(
"admError"
).style.display="none";

setTimeout(function(){

document.getElementById(
"admPassword"
).focus();

},100);

}


function closeADMLogin(){

document.getElementById(
"admLogin"
).style.display="none";

}


function loginADM(){

const senha=
document.getElementById(
"admPassword"
).value;


if(senha==="1234"){

document.getElementById(
"admLogin"
).style.display="none";

document.getElementById(
"admPanel"
).style.display="block";

loadADMProduct();

}else{

document.getElementById(
"admError"
).style.display="block";

}

}


function loadADMProduct(){

const category=
document.getElementById(
"admCategory"
).value;

const product=
products[category];


if(!product)return;


document.getElementById(
"admName"
).value=
product.name||"";


document.getElementById(
"admDesc"
).value=
product.desc||"";


document.getElementById(
"admPrice"
).value=
product.price||0;


document.getElementById(
"admBonus"
).value=
product.bonusPercent||0;


document.getElementById(
"admImg"
).value=
product.img||"";


document.getElementById(
"admStatus"
).style.display="none";

}


function saveADMProduct(){

const category=
document.getElementById(
"admCategory"
).value;


products[category]={

name:
document.getElementById(
"admName"
).value.trim(),

desc:
document.getElementById(
"admDesc"
).value.trim(),

price:
Number(
document.getElementById(
"admPrice"
).value
)||0,

bonusPercent:
Number(
document.getElementById(
"admBonus"
).value
)||0,

img:
document.getElementById(
"admImg"
).value.trim()

};


localStorage.setItem(
"SAYSER_GES_PRODUCTS",
JSON.stringify(products)
);


showProduct(category);


document.getElementById(
"admStatus"
).style.display="block";


}


function closeADM(){

document.getElementById(
"admPanel"
).style.display="none";

}


/* ================= INICIALIZAÇÃO ================= */

document.addEventListener(
"DOMContentLoaded",
function(){

if(!localStorage.getItem(
"SAYSER_GES_PRODUCTS"
)){

localStorage.setItem(
"SAYSER_GES_PRODUCTS",
JSON.stringify(
defaultProducts
)
);

}

showProduct("cosmeticos");

updateCart();

}
);

</script>

</body>
</html>
