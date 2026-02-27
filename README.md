<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ajude Juiz de Fora - Corrente de Solidariedade</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        :root {
            --primary: #28a745;
            --secondary: #f8f9fa;
            --text: #333;
            --highlight: #ffc107;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #e9ecef;
            margin: 0;
            padding: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .container {
            max-width: 500px;
            background: white;
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }

        h2 { text-align: center; color: var(--text); margin-bottom: 5px; }
        p.subtitle { text-align: center; color: #666; font-size: 14px; margin-bottom: 25px; }

        /* Barra de Progresso */
        .progress-container {
            background: #eee;
            border-radius: 20px;
            height: 25px;
            width: 100%;
            margin-bottom: 10px;
            overflow: hidden;
            position: relative;
        }

        #progress-bar {
            background: linear-gradient(90deg, #28a745, #5cd65c);
            height: 100%;
            width: 4.8%; /* Começa em 24k de 500k */
            transition: width 1s ease-in-out;
        }

        .stats {
            display: flex;
            justify-content: space-between;
            font-size: 14px;
            font-weight: bold;
            margin-bottom: 30px;
        }

        /* Grid de Valores */
        .value-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-bottom: 20px;
        }

        .value-card {
            border: 2px solid #ddd;
            border-radius: 10px;
            padding: 15px;
            text-align: center;
            cursor: pointer;
            transition: 0.3s;
            position: relative;
        }

        .value-card img {
            width: 100%;
            border-radius: 5px;
            margin-bottom: 10px;
        }

        .value-card.featured {
            border-color: var(--primary);
            background: #f0fff4;
            transform: scale(1.05);
        }

        .badge {
            position: absolute;
            top: -10px;
            right: -5px;
            background: var(--primary);
            color: white;
            padding: 2px 8px;
            font-size: 10px;
            border-radius: 5px;
        }

        /* Input Custom */
        .custom-value {
            width: 100%;
            padding: 12px;
            border: 2px solid #ddd;
            border-radius: 10px;
            text-align: center;
            font-size: 18px;
            margin-bottom: 15px;
            box-sizing: border-box;
        }

        .pix-box {
            background: #f1f1f1;
            padding: 15px;
            border-radius: 10px;
            text-align: center;
            border: 1px dashed #999;
        }

        .pix-key {
            font-family: monospace;
            word-break: break-all;
            display: block;
            margin: 10px 0;
            font-weight: bold;
        }

        .copy-btn {
            background: var(--primary);
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            width: 100%;
            font-weight: bold;
        }

        /* Pop-up Doação */
        #donation-popup {
            position: fixed;
            bottom: 20px;
            left: 20px;
            background: white;
            padding: 15px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.2);
            display: none;
            align-items: center;
            gap: 10px;
            z-index: 1000;
            border-left: 5px solid var(--primary);
        }
    </style>
</head>
<body>

<div class="container">
    <h2>Ajude quem mais precisa</h2>
    <p class="subtitle">Faça parte dessa corrente de amor e solidariedade por Juiz de Fora.</p>

    <div class="progress-container">
        <div id="progress-bar"></div>
    </div>
    <div class="stats">
        <span>Arrecadado: <span id="current-amt">R$ 24.000</span></span>
        <span>Meta: R$ 500.000</span>
    </div>

    <div class="value-grid">
        <div class="value-card">
            <img src="COLE_LINK_QRCODE_20_AQUI" alt="QR Code 20">
            <strong>R$ 20,00</strong>
        </div>
        <div class="value-card">
            <img src="COLE_LINK_QRCODE_30_AQUI" alt="QR Code 30">
            <strong>R$ 30,00</strong>
        </div>
        <div class="value-card featured">
            <span class="badge">MAIS DOADO</span>
            <img src="COLE_LINK_QRCODE_50_AQUI" alt="QR Code 50">
            <strong>R$ 50,00</strong>
        </div>
        <div class="value-card">
            <img src="COLE_LINK_QRCODE_100_AQUI" alt="QR Code 100">
            <strong>R$ 100,00</strong>
        </div>
    </div>

    <input type="number" class="custom-value" placeholder="Outro valor (R$ 0,00)">

    <div class="pix-box">
        <span>Copia e Cola qualquer valor:</span>
        <span class="pix-key" id="pixKey">SUA_CHAVE_PIX_GERAL_AQUI</span>
        <button class="copy-btn" onclick="copyPix()">COPIAR CHAVE PIX</button>
    </div>
</div>

<div id="donation-popup">
    <i class="fas fa-heart" style="color: #e74c3c;"></i>
    <div id="popup-text">Alguém doou R$ 45,00</div>
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
        navigator.clipboard.writeText(key);
        alert("Chave Pix copiada!");
    }

    // Inicializa a barra
    updateProgress();

    // Sistema de Pop-up e Barra Dinâmica a cada 17 segundos
    setInterval(() => {
        const randomVal = Math.floor(Math.random() * 80) + 20; // Valor entre 20 e 100
        const names = ['João', 'Maria', 'Pedro', 'Ana', 'Lucas', 'Carla', 'Marcos', 'Julia'];
        const name = names[Math.floor(Math.random() * names.length)];
        
        // Atualiza Texto e Mostra Pop-up
        document.getElementById('popup-text').innerText = `${name} acabou de doar R$ ${randomVal},00`;
        const popup = document.getElementById('donation-popup');
        popup.style.display = 'flex';
        
        // Soma na barra
        currentTotal += randomVal;
        updateProgress();

        // Esconde pop-up após 5 segundos
        setTimeout(() => {
            popup.style.display = 'none';
        }, 5000);

    }, 17000);
</script>

</body>
</html>
