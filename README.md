<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CREDPIX - Liberação Imediata</title>
    <style>
        :root { --primary-green: #00d35d; --dark-blue: #004a8d; --bg-gray: #f4f7fa; }
        body { font-family: 'Segoe UI', sans-serif; background-color: var(--bg-gray); margin: 0; display: flex; justify-content: center; }
        .app-container { width: 100%; max-width: 500px; background: white; min-height: 100vh; position: relative; display: flex; flex-direction: column; box-shadow: 0 0 20px rgba(0,0,0,0.05); }
        
        /* Header Superior Left */
        .header { padding: 20px; text-align: left; background: white; }
        .logo { color: var(--dark-blue); font-weight: 900; font-size: 24px; letter-spacing: -1.5px; }
        .logo span { color: var(--primary-green); }

        /* Carrossel Animado (3 etapas) */
        .carousel-banner { background: var(--primary-green); color: white; padding: 12px; height: 25px; overflow: hidden; font-size: 14px; text-align: center; font-weight: bold; }
        .carousel-text { animation: slideUp 9s infinite; position: relative; }
        @keyframes slideUp {
            0%, 30% { top: 0; }
            33%, 63% { top: -25px; }
            66%, 96% { top: -50px; }
            100% { top: 0; }
        }

        .content { padding: 30px 20px; flex-grow: 1; }
        .step { display: none; animation: fadeIn 0.3s ease-in-out; }
        .step.active { display: block; }

        /* Estilo das Opções (Cards Verdes) */
        .option-button { border: 2px solid #e0e0e0; padding: 18px; border-radius: 15px; margin-bottom: 12px; cursor: pointer; display: flex; justify-content: space-between; align-items: center; transition: 0.2s; }
        .option-button:active { background: #f0fff4; border-color: var(--primary-green); }
        .option-button h4 { margin: 0; color: #333; font-size: 16px; }

        /* Inputs Modernos */
        .input-label { font-size: 13px; color: #666; font-weight: bold; margin-bottom: 8px; display: block; }
        input, select { width: 100%; padding: 16px; border: 2px solid #eee; border-radius: 12px; font-size: 16px; box-sizing: border-box; outline: none; transition: 0.3s; }
        input:focus { border-color: var(--primary-green); }

        .btn-continue { background: var(--primary-green); color: white; border: none; padding: 20px; width: 100%; border-radius: 12px; font-size: 18px; font-weight: bold; cursor: pointer; margin-top: 25px; box-shadow: 0 4px 15px rgba(0, 211, 93, 0.3); }

        /* Progress Bar Final */
        .progress-container { margin-top: 40px; text-align: center; }
        .bar-outer { background: #eee; height: 14px; border-radius: 10px; overflow: hidden; margin: 15px 0; }
        .bar-inner { width: 0%; height: 100%; background: var(--primary-green); transition: 0.1s; }
        
        /* Box de Erro TAC */
        .error-tac { display: none; background: #fff; border: 2px solid #ff4444; border-radius: 20px; padding: 25px; margin-top: 20px; text-align: center; animation: bounce 0.5s; }
        @keyframes bounce { 0%, 100% {transform: scale(1);} 50% {transform: scale(1.05);} }
        @keyframes fadeIn { from { opacity: 0; transform: translateX(20px); } to { opacity: 1; transform: translateX(0); } }

        .footer { padding: 20px; font-size: 11px; color: #aaa; text-align: center; }
    </style>
</head>
<body>

<div class="app-container">
    <div class="header">
        <div class="logo">CRED<span>PIX</span></div>
    </div>

    <div class="carousel-banner">
        <div class="carousel-text">
            <div style="height:25px;">⚡ Solicitação em 2 minutos</div>
            <div style="height:25px;">🔍 Análise Instantânea</div>
            <div style="height:25px;">💰 Recebimento via PIX</div>
        </div>
    </div>

    <div class="content">
        
        <div id="step1" class="step active">
            <h2 style="font-size: 22px;">Olá! Qual seu perfil hoje?</h2>
            <div class="option-button" onclick="nextStep(2)"><h4>Negativado / Nome Sujo</h4> <span>🟢</span></div>
            <div class="option-button" onclick="nextStep(2)"><h4>Aposentado / Pensionista</h4> <span>🟢</span></div>
            <div class="option-button" onclick="nextStep(2)"><h4>Autônomo / Assalariado</h4> <span>🟢</span></div>
        </div>

        <div id="step2" class="step">
            <h2>Para começar, qual seu nome completo?</h2>
            <span class="input-label">NOME DO BENEFICIÁRIO</span>
            <input type="text" id="nome" placeholder="Seu nome aqui...">
            <button class="btn-continue" onclick="nextStep(3)">PRÓXIMO</button>
        </div>

        <div id="step3" class="step">
            <h2>Informe seu CPF</h2>
            <p style="color:#888; font-size: 14px;">A análise é feita em tempo real.</p>
            <span class="input-label">CPF</span>
            <input type="tel" id="cpf" placeholder="000.000.000-00" oninput="mCPF(this)">
            <button class="btn-continue" onclick="nextStep(4)">CONSULTAR AGORA</button>
        </div>

        <div id="step4" class="step">
            <h2>Sua data de nascimento</h2>
            <span class="input-label">DIA / MÊS / ANO</span>
            <input type="tel" id="data" placeholder="00/00/0000" oninput="mData(this)">
            <button class="btn-continue" onclick="nextStep(5)">CONTINUAR</button>
        </div>

        <div id="step5" class="step">
            <h2>Escolha como pagar</h2>
            <p>Carência de <b>180 dias</b> para a 1ª parcela.</p>
            <div class="option-button" onclick="nextStep(6)"><h4>12x Fixas</h4> <span>➔</span></div>
            <div class="option-button" onclick="nextStep(6)"><h4>24x Fixas</h4> <span>➔</span></div>
            <div class="option-button" onclick="nextStep(6)"><h4>48x Fixas</h4> <span>➔</span></div>
        </div>

        <div id="step6" class="step">
            <h2>Contrato Digital</h2>
            <div style="background:#f9f9f9; padding:15px; border-radius:10px; font-size:12px; color:#666; height:120px; overflow-y:scroll; border:1px solid #ddd;">
                <p>Ao clicar em aceitar, você autoriza o CREDPIX a realizar a transferência do valor solicitado via TED/PIX. O valor possui carência de 6 meses para início do pagamento. Tarifas extras podem ser aplicadas conforme o volume da transação.</p>
            </div>
            <label style="display:flex; align-items:center; margin-top:20px;">
                <input type="checkbox" id="check" style="width:20px; margin-right:10px;"> Declaro que li e aceito.
            </label>
            <button class="btn-continue" onclick="validaCheck()">ACEITAR E PROSSEGUIR</button>
        </div>

        <div id="step7" class="step">
            <h2>Onde deseja receber?</h2>
            <span class="input-label">QUAL SEU BANCO?</span>
            <select><option>Nubank</option><option>Itaú</option><option>Caixa</option><option>Bradesco</option></select>
            <br><br>
            <span class="input-label">SUA CHAVE PIX</span>
            <input type="text" placeholder="CPF, Celular ou E-mail">
            <button class="btn-continue" onclick="startLoading()">SOLICITAR ENVIO</button>
        </div>

        <div id="step8" class="step">
            <h2 id="L-Title">Processando Envio...</h2>
            <div class="progress-container">
                <div class="bar-outer"><div class="bar-inner" id="L-Bar"></div></div>
                <div id="L-Percent" style="font-weight:bold; font-size:20px;">0%</div>
            </div>
            <p id="L-Msg" style="color:#666">Comunicando com o Banco Central...</p>

            <div id="error-box" class="error-tac">
                <h3 style="color:#ff4444; margin-top:0;">⚠️ TRANSFERÊNCIA RETIDA</h3>
                <p style="font-size:14px; color:#444;">Para concluir o envio de <b>R$ 5.000,00</b> via TED Prioritário, é necessário o pagamento da <b>Taxa TAC (Tarifa de Abertura de Crédito)</b>.</p>
                <div style="background:#fefefe; padding:10px; border:1px dashed #ccc; margin:15px 0;">
                    Valor da Taxa: <b>R$ 97,00</b>
                </div>
                <button class="btn-continue" onclick="goCheckout()">LIBERAR MEU PIX AGORA</button>
            </div>
        </div>

    </div>

    <div class="footer">
        SISTEMA NACIONAL DE ATIVOS LTDA - CNPJ: 65.005.947/0001-30<br>
        🔒 Ambiente Seguro Banco Central
    </div>
</div>

<script>
    function nextStep(n) {
        document.querySelectorAll('.step').forEach(s => s.classList.remove('active'));
        document.getElementById('step'+n).classList.add('active');
        window.scrollTo(0,0);
    }

    function mCPF(i) {
        let v = i.value.replace(/\D/g, "");
        v = v.replace(/(\d{3})(\d)/, "$1.$2");
        v = v.replace(/(\d{3})(\d)/, "$1.$2");
        v = v.replace(/(\d{3})(\d{1,2})$/, "$1-$2");
        i.value = v;
    }

    function mData(i) {
        let v = i.value.replace(/\D/g, "");
        v = v.replace(/(\d{2})(\d)/, "$1/$2");
        v = v.replace(/(\d{2})(\d)/, "$1/$2");
        i.value = v;
    }

    function validaCheck() {
        if(document.getElementById('check').checked) nextStep(7);
        else alert("Aceite os termos para continuar.");
    }

    function startLoading() {
        nextStep(8);
        let bar = document.getElementById('L-Bar');
        let pct = document.getElementById('L-Percent');
        let msg = document.getElementById('L-Msg');
        let val = 0;

        let timer = setInterval(() => {
            val++;
            if(val <= 99) {
                bar.style.width = val + "%";
                pct.innerText = val + "%";
            }
            if(val == 30) msg.innerText = "Verificando autenticidade...";
            if(val == 70) msg.innerText = "Preparando remessa PIX...";
            
            if(val == 99) {
                clearInterval(timer);
                setTimeout(() => {
                    document.getElementById('L-Title').innerText = "PENDÊNCIA ENCONTRADA";
                    document.getElementById('L-Title').style.color = "#ff4444";
                    bar.style.background = "#ff4444";
                    document.getElementById('error-box').style.display = "block";
                    msg.style.display = "none";
                }, 1500);
            }
        }, 130);
    }

    function goCheckout() {
        window.location.href = "SEU_LINK_AQUI"; // COLOQUE SEU LINK DA INFINITE PAY AQUI
    }
</script>

</body>
</html>
