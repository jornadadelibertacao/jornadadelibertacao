<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Finalize seu Pagamento</title>
    <style>
        body { font-family: Arial, sans-serif; background-color: #f4f4f7; margin: 0; padding: 0; display: flex; justify-content: center; }
        .container { width: 100%; max-width: 450px; background: white; min-height: 100vh; box-shadow: 0 0 10px rgba(0,0,0,0.1); }
        .header { background: #1a1a1a; color: white; padding: 15px; text-align: center; font-size: 14px; }
        .timer { color: #ffcc00; font-weight: bold; }
        .content { padding: 20px; text-align: center; }
        .product-info { margin-bottom: 20px; }
        .product-name { font-size: 18px; font-weight: bold; color: #333; }
        .price { font-size: 24px; color: #28a745; font-weight: bold; margin: 10px 0; }
        .qr-box { background: #fff; border: 2px dashed #ccc; padding: 20px; border-radius: 15px; margin: 20px 0; }
        .qr-image { width: 200px; height: 200px; }
        .pix-code-box { background: #f8f9fa; border: 1px solid #ddd; padding: 15px; border-radius: 8px; font-size: 12px; word-break: break-all; margin-top: 10px; color: #666; }
        .btn-copy { background: #007bff; color: white; border: none; padding: 15px; width: 100%; border-radius: 8px; font-size: 16px; font-weight: bold; cursor: pointer; margin-top: 15px; transition: 0.3s; }
        .btn-copy:active { background: #0056b3; }
        .steps { text-align: left; font-size: 14px; color: #555; margin-top: 25px; }
        .step-item { margin-bottom: 10px; display: flex; align-items: center; }
        .step-num { background: #1a1a1a; color: white; width: 20px; height: 20px; border-radius: 50%; display: inline-flex; justify-content: center; align-items: center; margin-right: 10px; font-size: 12px; }
        .footer-secure { margin-top: 30px; padding-bottom: 20px; border-top: 1px solid #eee; padding-top: 15px; font-size: 12px; color: #999; }
    </style>
</head>
<body>

<div class="container">
    <div class="header">
        Sua vaga está reservada por: <span class="timer" id="countdown">10:00</span>
    </div>

    <div class="content">
        <div class="product-info">
            <div class="product-name">Método: R$ 10 MIL EM 15 DIAS</div>
            <div class="price">R$ 97,00</div>
        </div>

        <div class="qr-box">
            <p style="font-weight: bold; margin-top: 0;">Escaneie o QR Code abaixo:</p>
            <img src="1000073547.png" alt="QR Code Pix" class="qr-image">
        </div>

        <p style="font-size: 14px; color: #666;">Ou copie o código abaixo:</p>
        <div class="pix-code-box" id="pixCode">
            SEU_CODIGO_PIX_AQUI
        </div>

        <button class="btn-copy" onclick="copyPix()">COPIAR CÓDIGO PIX</button>

        <div class="steps">
            <div class="step-item"><span class="step-num">1</span> Abra o app do seu banco.</div>
            <div class="step-item"><span class="step-num">2</span> Escolha a opção Pix Copia e Cola.</div>
            <div class="step-item"><span class="step-num">3</span> Cole o código e finalize o pagamento.</div>
        </div>

        <div class="footer-secure">
            🔒 Pagamento processado com segurança via Banco Central.
        </div>
    </div>
</div>

<script>
    // Função para copiar o código
    function copyPix() {
        const code = document.getElementById('pixCode').innerText;
        navigator.clipboard.writeText(code).then(() => {
            alert("Código Pix copiado com sucesso!");
        });
    }

    // Cronômetro
    let time = 600;
    const display = document.getElementById('countdown');
    setInterval(() => {
        let minutes = Math.floor(time / 60);
        let seconds = time % 60;
        seconds = seconds < 10 ? '0' + seconds : seconds;
        display.innerHTML = `${minutes}:${seconds}`;
        if (time > 0) time--;
    }, 1000);
</script>

</body>
</html>
