<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>coquinha sensi PRO</title>

<style>
body{
    margin:0;
    font-family: Arial, sans-serif;
    background:#050505;
    color:#fff;
}

.container{
    max-width:420px;
    margin:40px auto;
    background:#0c0c0c;
    border-radius:15px;
    padding:20px;
    box-shadow:0 0 25px #ff000070;
}

h1{
    text-align:center;
    color:#ff0000;
    text-shadow:0 0 10px #ff0000;
}

input{
    width:100%;
    padding:12px;
    border:none;
    border-radius:8px;
    margin:10px 0;
    background:#111;
    color:white;
    font-size:16px;
}

button{
    width:100%;
    padding:14px;
    border:none;
    border-radius:10px;
    background:#ff0000;
    color:white;
    font-size:18px;
    font-weight:bold;
}

.result{
    margin-top:15px;
    background:#080808;
    padding:15px;
    border-radius:12px;
}

</style>
</head>

<body>

<div class="container">
<h1>COQUINHA SENSI</h1>

<p>Digite sua DPI (320 até 1450):</p>

<input type="number" id="dpi" placeholder="Ex: 420">

<button onclick="gerar()">GERAR SENSI</button>

<div class="result" id="resultado" style="display:none;">
<p>🎯 Geral: <b id="geral"></b></p>
<p>🔴 Red Dot: <b id="red"></b></p>
<p>🔍 Mira 2x: <b id="mira2"></b></p>
<p>🔭 Mira 4x: <b id="mira4"></b></p>
<p>📌 AWM: <b id="awm"></b></p>
<p>🕹️ Olhadinha: <b id="olhadinha"></b></p>
</div>
</div>

<script>
function gerar(){
    let dpi = Number(document.getElementById("dpi").value);

    if(dpi < 320 || dpi > 1450 || isNaN(dpi)){
        alert("Digite uma DPI válida entre 320 e 1450");
        return;
    }

    let base = (dpi - 320) / (1450 - 320);

    document.getElementById("geral").innerText = Math.round(180 - base * 70);
    document.getElementById("red").innerText = Math.round(170 - base * 65);
    document.getElementById("mira2").innerText = Math.round(160 - base * 60);
    document.getElementById("mira4").innerText = Math.round(150 - base * 55);
    document.getElementById("awm").innerText = Math.round(140 - base * 50);
    document.getElementById("olhadinha").innerText = Math.round(190 - base * 75);

    document.getElementById("resultado").style.display = "block";
}
</script>

</body>
</html>
