<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>URGENTE: Juiz de Fora Precisa de Você</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        :root { --red: #d9534f; --green: #28a745; --dark: #1a1a1a; }
        body { font-family: 'Arial', sans-serif; margin: 0; background: #f4f4f4; color: #333; line-height: 1.6; }
        
        /* Seção Vendas Agressiva */
        .hero { background: var(--dark); color: white; padding: 40px 20px; text-align: center; }
        .alert-bar { background: var(--red); color: white; padding: 10px; font-weight: bold; text-transform: uppercase; font-size: 14px; }
        .headline { font-size: 28px; line-height: 1.2; margin: 20px 0; color: #fff; }
        .headline span { color: var(--red); }
        .video-placeholder { width: 100%; max-width: 600px; height: 337px; background: #000; margin: 20px auto; border: 3px solid #333; display: flex; align-items: center; justify-content: center; position: relative; }
        .btn-main { background: var(--green); color: white; padding: 20px 40px; border: none; border-radius: 50px; font-size: 20px; font-weight: bold; cursor: pointer; text-decoration: none; display: inline-block; margin: 20px 0; animation: pulse 1.5s infinite; }
        
        /* Checkout Style (Integrado) */
        .checkout-section { max-width: 500px; margin: -50px auto 50px; background: white; border-radius: 15px; padding: 25px; box-shadow: 0 10px 30px rgba(0,0,0,0.2); position: relative; z-index: 10; }
        .progress-container { background: #eee; border-radius: 20px; height: 20px; width: 100%; margin: 15px 0; overflow: hidden; }
        #progress-bar { background: linear-gradient(90deg, #28a745, #5cd65c); height: 100%; width: 4.8%; transition: width 1s; }
        
        .value-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 15px; margin: 20px 0; }
        .value-card { border: 2px solid #ddd; border-radius: 10px; padding: 10px; text-align: center; cursor: pointer; position: relative; }
        .value-card img { width: 100%; border-radius: 5px; }
        .value-card.featured { border-color: var(--green); background: #f0fff4; transform: scale(1.05); z-index: 2; }
        .badge { position: absolute; top: -10px; right: -5px; background: var(--green); color: white; padding: 2px 8px; font-size: 10px; border-radius: 5px; }
        
        .pix-box { background: #f9f9f9; padding: 15px; border-radius: 10px; text-align: center; border: 2px dashed #ccc; margin-top: 20px; }
        .pix-key { font-family: monospace; font-weight: bold; display: block; margin: 10px 0; color: #444; font-size: 13px; }
        
        #donation-popup { position: fixed; bottom: 20px; left: 20px; background: white; padding: 12px; border-radius: 8px; box-shadow: 0 5px 15px rgba(0,0,0,0.3); display: none; align-items: center; gap: 10px; z-index: 1000; border-left: 5px solid var(--green); }

        @keyframes pulse { 0% { transform: scale(1); } 50% { transform: scale(1.05); } 100% { transform: scale(1); } }
    </style>
</head>
<body>

<div class="alert-bar"><i class="fas fa-exclamation-triangle"></i> Calamidade Pública: Juiz de Fora precisa de ajuda imediata</div>

<section class="hero">
    <h1 class="headline">FAMÍLIAS PERDERAM TUDO EM <span>JUIZ DE FORA</span>. VOCÊ É A ÚNICA ESPERANÇA DELES AGORA!</h1>
    <div class="video-placeholder">
        <p style="color: #666;">[COLE AQUI O EMBED DO SEU VÍDEO OU IMAGEM DE IMPACTO]</p>
        </div>
    <p style="font-size: 18px; max-width: 600px; margin: 20px auto;">Milhares de pessoas estão sem água potável, comida e abrigo. Cada segundo conta para salvar uma vida.</p>
    <a href="#doar" class="btn-main">SIM, EU QUERO AJUDAR AGORA!</a>
</section>

<div class="checkout-section" id="doar">
    <h3 style="text-align:center; margin-top:0;">Faltam R$ 476.000 para a meta</h3>
    <div class="progress-container"><div id="progress-bar"></div></div>
    <div style="display:flex; justify-content:space-between; font-size:12px; font-weight:bold; margin-bottom:20px;">
        <span>ARRECADADO: <span id="current-amt">R$ 24.000</span></span>
        <span>META: R$ 500.000</span>
    </div>

    <div class="value-grid">
        <div class="value-card">
            <img src="LINK_QR_20" alt="QR 20">
            <strong>R$ 20,00</strong>
        </div>
        <div class="value-card">
            <img src="LINK_QR_30" alt="QR 30">
            <strong>R$ 30,00</strong>
        </div>
        <div class="value-card featured">
            <span class="badge">MAIS DOADO</span>
            <img src="LINK_QR_50" alt="QR 50">
            <strong>R$ 50,00</strong>
        </div>
        <div class="value-card">
            <img src="LINK_QR_100" alt="QR 100">
            <strong>R$ 100,00</strong>
        </div>
    </div>

    <input type="number" style="width:100%; padding:12px; border:2px solid #ddd; border-radius:10px; text-align:center; box-sizing:border-box;" placeholder="Outro valor (R$ 0,00)">

    <div class="pix-box">
        <span style="font-size:14px;">Copia e Cola (Qualquer valor):</span>
        <span class="pix-key" id="pixKey">SUA_CHAVE_PIX_AQUI</span>
        <button onclick="copyPix()" style="background:var(--green); color:white; border:none; padding:12px; width:100%; border-radius:5px; font-weight:bold; cursor:pointer;">COPIAR CÓDIGO PIX</button>
    </div>
</div>

<div id="donation-popup">
    <i class="fas fa-heart" style="color: #e74c3c;"></i>
    <div id="popup-text">Alguém acabou de doar!</div>
</div>

<script>
    let currentTotal = 24000;
    const goal = 500000;

    function updateProgress() {
        const percent = (currentTotal / goal) * 100;
        document.getElementById('progress-bar').style.width = percent + '%';
        document.getElementById('current-amt').innerText = 'R$ ' + currentTotal.toLocaleString('pt-BR');
    }

    function copyPix() {
        const key = document.getElementById('pixKey').innerText;
        navigator.clipboard.writeText(key).then(() => alert("Código copiado com sucesso!"));
    }

    updateProgress();

    setInterval(() => {
        const randomVal = Math.floor(Math.random() * 70) + 15;
        const names = ['Ricardo', 'Beatriz', 'Felipe', 'Helena', 'Thiago', 'Sonia'];
        const name = names[Math.floor(Math.random() * names.length)];
        
        document.getElementById('popup-text').innerText = `${name} doou R$ ${randomVal},00`;
        const popup = document.getElementById('donation-popup');
        popup.style.display = 'flex';
        
        currentTotal += randomVal;
        updateProgress();

        setTimeout(() => { popup.style.display = 'none'; }, 4000);
    }, 17000);
</script>

</body>
</html>
