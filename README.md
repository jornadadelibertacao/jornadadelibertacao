<button onclick="openModal()">Comprar Agora</button>

<div id="modal" style="display:none; position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.8);">
  <div style="background:#111; padding:30px; max-width:400px; margin:10% auto; color:#fff;">
    <h2>Finalizar Compra</h2>
    <p>Valor: R$97</p>
    <a href="SEU_LINK_DE_PAGAMENTO_AQUI">
      <button>Ir para Pagamento</button>
    </a>
    <br><br>
    <button onclick="closeModal()">Fechar</button>
  </div>
</div>

<script>
function openModal(){
  document.getElementById('modal').style.display = "block";
}

function closeModal(){
  document.getElementById('modal').style.display = "none";
}
</script>