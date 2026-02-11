<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Programação na Era da IA</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet">

<style>
body{
    margin:0;
    font-family:'Inter',sans-serif;
    background:#0f1115;
    color:#fff;
}

.container{
    max-width:1100px;
    margin:auto;
    padding:40px 20px;
}

.hero{
    text-align:center;
    padding:60px 20px;
    background:linear-gradient(180deg,#0f1115,#111827);
}

.hero img{
    width:300px;
    max-width:90%;
    margin-bottom:30px;
}

h1{
    font-size:38px;
    font-weight:800;
}

.subtitle{
    font-size:18px;
    color:#bdbdbd;
    max-width:700px;
    margin:20px auto;
}

.button{
    background:#2563eb;
    padding:15px 35px;
    border:none;
    border-radius:6px;
    font-size:18px;
    color:#fff;
    cursor:pointer;
    margin-top:20px;
}

.vagas{
    margin-top:15px;
    color:#f87171;
    font-weight:600;
}

.section{
    padding:60px 0;
}

.grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
    gap:20px;
}

.card{
    background:#1a1f2b;
    padding:25px;
    border-radius:8px;
}

.footer{
    background:#0c0e12;
    text-align:center;
    padding:30px;
    font-size:14px;
    color:#777;
}

/* Modal */

.modal{
    display:none;
    position:fixed;
    z-index:1000;
    left:0;
    top:0;
    width:100%;
    height:100%;
    background:rgba(0,0,0,0.8);
}

.modal-content{
    background:#1a1f2b;
    padding:40px;
    max-width:400px;
    margin:10% auto;
    border-radius:8px;
    text-align:center;
}

.close{
    float:right;
    cursor:pointer;
    color:#aaa;
}
</style>
</head>
<body>

<div class="hero">
    <img src="INSTQ_LINK_AQUI" alt="Robô IA">
    <h1>Programação Prática para a Era da IA</h1>
    <p class="subtitle">
        Aprenda a criar automações e agentes inteligentes antes que isso vire obrigatório no mercado.
    </p>
    <button class="button" onclick="abrirModal()">Quero Começar Agora</button>
    <div class="vagas">Vagas restantes: <span id="contador">25</span></div>
</div>

<div class="container section">
    <h2>O que você vai aprender</h2>
    <div class="grid">
        <div class="card">
            <h3>Fundamentos</h3>
            <p>Lógica simples para começar mesmo do zero.</p>
        </div>
        <div class="card">
            <h3>Automação</h3>
            <p>Como criar agentes que executam tarefas reais.</p>
        </div>
        <div class="card">
            <h3>IA na prática</h3>
            <p>Integração com ferramentas atuais do mercado.</p>
        </div>
        <div class="card">
            <h3>Vantagem Profissional</h3>
            <p>Como aplicar isso no trabalho e ganhar diferencial.</p>
        </div>
    </div>
</div>

<div class="container section">
    <h2>Garantia</h2>
    <p>
        7 dias de garantia. Se não fizer sentido para você, devolvemos seu dinheiro.
    </p>
</div>

<div class="footer">
    © 2026 Programação na Era da IA
</div>

<!-- Modal -->

<div id="modal" class="modal">
  <div class="modal-content">
    <span class="close" onclick="fecharModal()">X</span>
    <h2>Finalizar Compra</h2>
    <p>Valor: R$97</p>
    <a href="SEU_LINK_DE_PAGAMENTO_AQUI">
        <button class="button" onclick="diminuirVagas()">Ir para Pagamento</button>
    </a>
  </div>
</div>

<script>

function abrirModal(){
    document.getElementById("modal").style.display = "block";
}

function fecharModal(){
    document.getElementById("modal").style.display = "none";
}

function diminuirVagas(){
    var contador = document.getElementById("contador");
    var valor = parseInt(contador.innerText);
    if(valor > 1){
        contador.innerText = valor - 1;
    }
}

</script>

</body>
</html>