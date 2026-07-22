<!DOCTYPE html>
<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport"
content="width=device-width, initial-scale=1.0">

<title>Lela Sacks Cost Calculator</title>

<style>

*{

margin:0;

padding:0;

box-sizing:border-box;

font-family:-apple-system,
BlinkMacSystemFont,
"SF Pro Display",
Arial,
sans-serif;

}

body{

background:#eef2f6;

padding:12px;

}

.container{

max-width:390px;

margin:auto;

background:white;

border-radius:20px;

overflow:hidden;

box-shadow:0 10px 30px rgba(0,0,0,.18);

}

.header{

background:#003A70;

color:white;

padding:20px;

text-align:center;

}

.logo{

width:60px;

height:60px;

border-radius:50%;

background:white;

margin:auto;

display:flex;

align-items:center;

justify-content:center;

font-size:24px;

font-weight:bold;

color:#003A70;

margin-bottom:10px;

}

.header h1{

font-size:24px;

}

.header p{

font-size:13px;

opacity:.85;

margin-top:5px;

}

.content{

padding:15px;

}

table{

width:100%;

border-collapse:collapse;

table-layout:fixed;

}

th{

background:#003A70;

color:white;

padding:8px 3px;

font-size:12px;

}

td{

padding:7px 3px;

border-bottom:1px solid #ddd;

font-size:12px;

text-align:center;

}

td:first-child{

text-align:left;

font-weight:600;

}

input{

width:55px;

padding:5px;

font-size:12px;

text-align:center;

border-radius:5px;

border:1px solid #bbb;

outline:none;

}

input:focus{

border-color:#003A70;

}

.totalRow{

background:#f8f8f8;

font-weight:bold;

}

.green{

color:#008000;

font-weight:bold;

}

.footer{

padding:15px;

text-align:center;

font-size:11px;

color:#777;

}

</style>

</head>

<body>

<div class="container">

<div class="header">

<div class="logo">

LS

</div>

<h1>Lela Sacks</h1>

<p>PP Woven Sack Cost Calculator</p>

</div>

<div class="content">

<table>

<tr>

<th style="width:34%;">Material</th>

<th style="width:20%;">Rate</th>

<th style="width:18%;">Wt</th>

<th style="width:28%;">Price</th>

</tr><tr>

<td>PP</td>

<td>
<input
type="number"
id="ppRate"
value="3700"
oninput="calc()">
</td>

<td>
<input
type="number"
id="ppWt"
value="120"
oninput="calc()">
</td>

<td id="ppPrice">444.00</td>

</tr>

<tr>

<td>BOPP Front</td>

<td>
<input
type="number"
id="bfRate"
value="9500"
oninput="calc()">
</td>

<td>
<input
type="number"
id="bfWt"
value="10"
oninput="calc()">
</td>

<td id="bfPrice">95.00</td>

</tr>

<tr>

<td>BOPP Back</td>

<td>
<input
type="number"
id="bbRate"
value="9500"
oninput="calc()">
</td>

<td>
<input
type="number"
id="bbWt"
value="10"
oninput="calc()">
</td>

<td id="bbPrice">95.00</td>

</tr>

<tr class="totalRow">

<td>Total</td>

<td></td>

<td id="totalWeight">140</td>

<td class="green" id="bagPrice">634.00</td>

</tr>

<tr class="totalRow">

<td>Per Bale (NGN)</td>

<td colspan="2"></td>

<td class="green" id="balePrice">317,000.00</td>

</tr>

<tr class="totalRow">

<td>Bale Weight (Kg)</td>

<td colspan="2"></td>

<td class="green" id="baleWeight">70.00</td>

</tr>

</table>

</div>

<div class="footer">

© Lela Sacks Agro Ltd.

</div>

</div><script>

function calc(){

let ppRate=parseFloat(document.getElementById("ppRate").value)||0;
let ppWt=parseFloat(document.getElementById("ppWt").value)||0;

let bfRate=parseFloat(document.getElementById("bfRate").value)||0;
let bfWt=parseFloat(document.getElementById("bfWt").value)||0;

let bbRate=parseFloat(document.getElementById("bbRate").value)||0;
let bbWt=parseFloat(document.getElementById("bbWt").value)||0;

/* Material Costs */

let ppCost=(ppRate*ppWt)/1000;

let bfCost=(bfRate*bfWt)/1000;

let bbCost=(bbRate*bbWt)/1000;

/* Totals */

let totalWeight=ppWt+bfWt+bbWt;

let bagPrice=ppCost+bfCost+bbCost;

let balePrice=bagPrice*500;

let baleWeight=(totalWeight*500)/1000;

/* Display */

document.getElementById("ppPrice").innerHTML=
ppCost.toFixed(2);

document.getElementById("bfPrice").innerHTML=
bfCost.toFixed(2);

document.getElementById("bbPrice").innerHTML=
bbCost.toFixed(2);

document.getElementById("totalWeight").innerHTML=
totalWeight.toFixed(0);

document.getElementById("bagPrice").innerHTML=
bagPrice.toFixed(2);

document.getElementById("balePrice").innerHTML=
balePrice.toLocaleString(undefined,{
minimumFractionDigits:2,
maximumFractionDigits:2
});

document.getElementById("baleWeight").innerHTML=
baleWeight.toFixed(2);

}

/* Run when page opens */

window.onload=function(){

calc();

}

</script></body>

</html>
