<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>DZ Store</title>

<style>
body{
  margin:0;
  font-family:Arial, sans-serif;
  background:#000;
  color:#fff;
}

header{
  padding:20px;
  text-align:center;
  font-size:24px;
  font-weight:bold;
  letter-spacing:3px;
  border-bottom:1px solid #222;
}

.container{
  max-width:1100px;
  margin:50px auto;
  padding:20px;
  display:flex;
  flex-wrap:wrap;
  gap:50px;
  align-items:center;
  justify-content:center;
}

.produto-img{
  max-width:450px;
  width:100%;
  border-radius:10px;
  transition:0.3s;
}

.info{
  max-width:450px;
}

h2{
  font-size:30px;
  margin-bottom:15px;
}

.descricao{
  color:#ccc;
  line-height:1.6;
}

.preco{
  font-size:28px;
  color:#00ff88;
  margin:25px 0;
  font-weight:bold;
}

button{
  background:#ff0000;
  color:#fff;
  border:none;
  padding:15px 30px;
  font-size:18px;
  border-radius:6px;
  cursor:pointer;
  font-weight:bold;
  transition:0.3s;
}

button:hover{
  background:#cc0000;
}

.popup{
  position:fixed;
  bottom:-100%;
  left:0;
  width:100%;
  background:#111;
  border-radius:20px 20px 0 0;
  padding:30px;
  transition:0.4s;
  box-shadow:0 -5px 20px rgba(0,0,0,0.5);
}

.popup.active{
  bottom:0;
}

.popup h3{
  margin-top:0;
}

.cores{
  display:flex;
  gap:15px;
  margin:25px 0;
  flex-wrap:wrap;
}

.cor{
  padding:12px 25px;
  border-radius:30px;
  border:1px solid #fff;
  cursor:pointer;
  transition:0.3s;
}

.cor.selected{
  background:#ff0000;
  border:none;
}

.fechar{
  background:#333;
  margin-top:15px;
}
</style>
</head>

<body>

<header>DZ STORE</header>

<div class="container">

<img src="site/branco.jpg"
     id="imagemProduto"
     class="produto-img">

<div class="info">
<h2>Fone Bluetooth Tube 510BT</h2>

<p class="descricao">
Fone Bluetooth Tube 510BT com microfone, sem fio.
Leve, confortável, bateria de longa duração e graves potentes.
Ideal para música, jogos e chamadas.
</p>

<p class="preco">R$ 149,90</p>

<button onclick="abrirPopup()">COMPRAR</button>
</div>

</div>

<div class="popup" id="popup">
<h3>Escolha a cor</h3>

<div class="cores">

<div class="cor" onclick="selecionarCor(this,'Vermelho','site/vermelho.jpg')">
Vermelho
</div>

<div class="cor" onclick="selecionarCor(this,'Rosa','site/rosa.jpg')">
Rosa
</div>

<div class="cor" onclick="selecionarCor(this,'Preto','site/preto.jpg')">
Preto
</div>

<div class="cor selected" onclick="selecionarCor(this,'Branco','site/branco.jpg')">
Branco
</div>

</div>

<button onclick="irParaPagamento()">FINALIZAR COMPRA</button>
<br>
<button class="fechar" onclick="fecharPopup()">Cancelar</button>

</div>

<script>

let corSelecionada = "Branco";
let linkPagamento = "#";

function abrirPopup(){
  document.getElementById("popup").classList.add("active");
}

function fecharPopup(){
  document.getElementById("popup").classList.remove("active");
}

function selecionarCor(elemento, cor, imagem){
  document.querySelectorAll(".cor").forEach(c => c.classList.remove("selected"));
  elemento.classList.add("selected");
  corSelecionada = cor;
  document.getElementById("imagemProduto").src = imagem;
}

function irParaPagamento(){
  if(linkPagamento === "#"){
    alert("Pagamento ainda não configurado.");
  } else {
    window.location.href = linkPagamento;
  }
}

</script>

</body>
</html>
