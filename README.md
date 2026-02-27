<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SOS JUIZ DE FORA - AJUDA IMEDIATA</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        :root { --red: #cc0000; --green: #25d366; --dark: #0f0f0f; }
        body { font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; margin: 0; background: #f0f2f5; color: #1c1e21; }
        
        /* Headline e Alerta */
        .urgente-topo { background: var(--red); color: white; text-align: center; padding: 12px; font-weight: bold; font-size: 14px; text-transform: uppercase; letter-spacing: 1px; }
        .hero { background: var(--dark); color: white; padding: 40px 20px; text-align: center; border-bottom: 5px solid var(--red); }
        .headline { font-size: 32px; font-weight: 900; line-height: 1.1; margin-bottom: 20px; text-transform: uppercase; }
        .headline span { color: var(--red); }
        
        /* Texto Explicativo Agressivo */
        .contexto { max-width: 600px; margin: 30px auto; padding: 0 20px; text-align: left; background: white; border-radius: 8px; padding: 20px; border-left: 5px solid var(--red); box-shadow: 0 2px 10px rgba(0,0,0,0.1); }
        .contexto h3 { color: var(--red); margin-top: 0; }
        .contexto p { font-size: 16px; color: #444; }

        /* Checkout e Barra */
        .checkout-container { max-width: 480px; margin: -40px auto 40px; background: white; border-radius: 12px; padding: 25px; box-shadow: 0 15px 35px rgba(0,0,0,0.2); position: relative; }
        .progress-box { margin-bottom: 25px; }
        .progress-bar-bg { background: #e0e0e0; border-radius: 10px; height: 22px; overflow: hidden; position: relative; }
        #progress-fill { background: linear-gradient(90deg, #28a745, #85e085); height: 100%; width: 4.8%; transition: width 0.8s ease; }
        .stats { display: flex; justify-content: space-between; font-weight: 900; font-size: 14px; margin-top: 8px; color: #333; }

        /* Valores Grid */
        .value-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin: 20px 0; }
        .value-card { border: 2px solid #eee; border-radius: 10px; padding: 10px; text-align: center; cursor: pointer; transition: 0.2s; }
        .value-card img { width: 100%; border-radius: 4px; margin-bottom: 8px; }
        .value-card.featured { border-color: var(--green); background: #fafffa; transform: scale(1.03); box-shadow: 0 5px 15px rgba(37, 211, 102, 0.2); }
        .badge-destaque { background: var(--green); color: white; font-size: 10px; padding: 2px 8px; border-radius: 10px; position: absolute; top: -8px; right: 10px; font-weight: bold; }

        /* Depoimentos */
        .depoimentos { max-width: 600px; margin: 40px auto; padding: 0 20px; }
        .depoimento-card { background: white; border-radius: 10px; padding: 15px; margin-bottom: 15px; border: 1px solid #ddd; display: flex; gap: 15px; align-items: center; }
        .depoimento-card img { width: 50px; height: 50px; border-radius: 50%; object-fit: cover; }
        .depoimento-info b { display: block; font-size: 14px; }
        .depoimento-info p { margin: 5px 0 0; font-size: 13px; color: #555; font-style: italic; }

        /* Pix e CTA */
        .pix-area { background: #f8f9fa; border: 2px dashed #007bff; border-radius: 8px; padding: 15px; text-align: center; margin-top: 20px; }
        .pix-key { font-family: 'Courier New', Courier, monospace; font-size: 12px; font-weight: bold; word-break: break-all; color: #007bff; }
        .btn-pix { background: var(--green); color: white; border: none; padding: 15px; width: 100%; border-radius: 8px; font-weight: 900; font-size: 18px; cursor: pointer; margin-top: 10px; }

        /* Notificação */
        #notify { position: fixed; bottom: 20px; left: 20px; background: white; padding: 12px 20px; border-radius: 50px; box-shadow: 0 5px 20px rgba(0,0,0,0.3); display: none; align-items: center; gap: 10px; z-index: 1000; border-left: 6px solid var(--green); animation: slideIn 0.5s ease; }
        @keyframes slideIn { from { transform: translateX(-100%); } to { transform: translateX(0); } }
    </style>
</head>
<body>

<div class="urgente-topo">⚠️ ESTADO DE CALAMIDADE EM JUIZ DE FORA - RESTAM POUCAS HORAS PARA O PRÓXIMO RESGATE ⚠️</div>

<section class="hero">
    <h1 class="headline">O CENÁRIO É DE <span>GUERRA</span>. FAMÍLIAS ESTÃO SOTERRADAS E SEM COMIDA AGORA!</h1>
    <div style="background: #000; width: 100%; max-width: 600px; height: 300px; margin: 20px auto; border: 2px solid #444; display: flex; align-items: center; justify-content: center;">
        <span style="color: #666;">[COLE SEU VÍDEO OU IMAGEM DE IMPACTO AQUI]</span>
    </div>
</section>

<div class="contexto">
    <h3>O QUE ESTÁ ACONTECENDO?</h3>
    <p>Juiz de Fora foi atingida por chuvas devastadoras em Fevereiro de 2026. Bairros inteiros desapareceram sob a lama. O que você está vendo no jornal não é nem metade do pesadelo.</p>
    <p><b>Para que serve sua doação?</b> Cada centavo arrecadado nesta vaquinha será convertido em:</p>
    <ul>
        <li>Água potável (as tubulações estouraram)</li>
        <li>Cestas básicas emergenciais</li>
        <li>Colchões e cobertores para os desabrigados</li>
        <li>Kits de higiene para crianças e idosos</li>
    </ul>
    <p>Não estamos aqui para pedir, estamos aqui para <b>suplicar</b>. Se você tem R$ 20,00 sobrando, isso é o preço de uma vida hoje.</p>
</div>

<div class="checkout-container" id="fazer-doacao">
    <div class="progress-box">
        <div class="progress-bar-bg"><div id="progress-fill"></div></div>
        <div class="stats">
            <span>ARRECADADO: <span id="val-atual" style="color: var(--green);">R$ 24.000</span></span>
            <span>META: R$ 500.000</span>
        </div>
    </div>

    <div class="value-grid">
        <div class="value-card">
            <img src="LINK_QR_20" alt="Doar 20">
            <b>R$ 20,00</b>
        </div>
        <div class="value-card">
            <img src="LINK_QR_30" alt="Doar 30">
            <b>R$ 30,00</b>
        </div>
        <div class="value-card featured">
            <span class="badge-destaque">MAIS DOADO</span>
            <img src="LINK_QR_50" alt="Doar 50">
            <b>R$ 50,00</b>
        </div>
        <div class="value-card">
            <img src="LINK_QR_100" alt="Doar 100">
            <b>R$ 100,00</b>
        </div>
    </div>

    <input type="number" style="width:100%; padding:15px; border:2px solid #ddd; border-radius:8px; text-align:center; box-sizing:border-box; font-size:18px;" placeholder="Outro Valor (R$)">

    <div class="pix-area">
        <span style="font-size:12px; color:#666;">Copia e Cola (Qualquer valor):</span>
        <span class="pix-key" id="pixKey">SUA_CHAVE_PIX_AQUI</span>
        <button class="btn-pix" onclick="copyPix()">COPIAR PIX E DOAR AGORA</button>
    </div>
</div>

<div class="depoimentos">
    <h4 style="text-align:center; text-transform:uppercase; color:#666;">Quem já ajudou:</h4>
    <div class="depoimento-card">
        <img src="https://i.pravatar.cc/150?u=1" alt="User">
        <div class="depoimento-info">
            <b>Marcos S. (Juiz de Fora/MG)</b>
            <p>"Eu perdi minha casa, mas estou ajudando quem perdeu a família. Doe o que puder!"</p>
        </div>
    </div>
    <div class="depoimento-card">
        <img src="https://i.pravatar.cc/150?u=2" alt="User">
        <div class="depoimento-info">
            <b>Ana Paula (São Paulo/SP)</b>
            <p>"Vi as notícias e não consegui ficar parada. Doei R$ 100 e vou divulgar!"</p>
        </div>
    </div>
</div>

<div id="notify">
    <i class="fas fa-check-circle" style="color:var(--green)"></i>
    <span id="notify-text">Novo doador acabou de ajudar!</span>
</div>

<script>
    let current = 24000;
    const meta = 500000;

    function refresh() {
        let percent = (current / meta) * 100;
        document.getElementById('progress-fill').style.width = percent + '%';
        document.getElementById('val-atual').innerText = 'R$ ' + current.toLocaleString('pt-BR');
    }

    function copyPix() {
        const key = document.getElementById('pixKey').innerText;
        navigator.clipboard.writeText(key).then(() => alert("Pix Copiado! Abra seu banco e cole na opção Pix Copia e Cola."));
    }

    refresh();

    // Loop de doações simuladas e barra subindo
    setInterval(() => {
        const doacao = Math.floor(Math.random() * 80) + 10; // Entre 10 e 90 reais
        const nomes = ['Roberto', 'Luciana', 'Fernando', 'Camila', 'Gabriel', 'Marta', 'Bruno', 'Eliana'];
        const nome = nomes[Math.floor(Math.random() * nomes.length)];
        
        current += doacao; // Aumenta o valor real da barra
        refresh();

        const notify = document.getElementById('notify');
        document.getElementById('notify-text').innerText = `${nome} doou R$ ${doacao},00`;
        notify.style.display = 'flex';

        setTimeout(() => { notify.style.display = 'none'; }, 4500);
    }, 17000);
</script>

</body>
</html>
