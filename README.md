<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PIXCRED - Empréstimo Instantâneo</title>
    <style>
        body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; background-color: #f0f2f5; margin: 0; padding: 0; display: flex; justify-content: center; }
        .container { width: 100%; max-width: 450px; background: white; min-height: 100vh; box-shadow: 0 0 20px rgba(0,0,0,0.1); position: relative; }
        
        /* Header Estilo Banco */
        .header { background: #004a8d; color: white; padding: 20px; text-align: center; font-weight: bold; font-size: 20px; border-bottom: 4px solid #00d35d; }
        
        .content { padding: 20px; text-align: center; }
        
        /* Etapas */
        .step { display: none; animation: fadeIn 0.5s; }
        .step.active { display: block; }

        /* Estilo dos Inputs */
        .input-group { text-align: left; margin-bottom: 15px; }
        label { font-size: 14px; color: #555; font-weight: bold; }
        input, select { width: 100%; padding: 12px; margin-top: 5px; border: 1px solid #ddd; border-radius: 8px; box-sizing: border-box; font-size: 16px; }

        /* Botões */
        .btn-next { background: #00d35d; color: white; border: none; padding: 18px; width: 100%; border-radius: 8px; font-size: 18px; font-weight: bold; cursor: pointer; margin-top: 20px; }
        
        /* Barra de Progresso */
        .progress-container { width: 100%; background: #eee; height: 10px; border-radius: 5px; margin: 20px 0; overflow: hidden; }
        .progress-bar { width: 0%; height: 100%; background: #00d35d; transition: width 0.3s; }

        /* Card de Aprovação */
        .card-approval { background: #e8f5e9; border: 2px solid #2e7d32; padding: 20px; border-radius: 15px; margin-top: 20px; }
        .approved-value { font-size: 32px; color: #2e7d32; font-weight: bold; margin: 10px 0; }

        /* Loading */
        .spinner { border: 4px solid rgba(0, 0, 0, 0.1); width: 36px; height: 36px; border-radius: 50%; border-left-color: #00d35d; animation: spin 1s linear infinite; display: inline-block; }
        @keyframes spin { to { transform: rotate(360deg); } }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        .footer-secure { font-size: 11px; color: #999; margin-top: 40px; border-top: 1px solid #eee; padding-top: 10px; }
    </style>
</head>
<body>

<div class="container">
    <div class="header">PIXCRED</div>
    
    <div class="content">
        
        <div id="step1" class="step active">
            <h3>Quanto você precisa?</h3>
            <p style="color: #666; font-size: 14px;">Liberação imediata via PIX</p>
            
            <div class="input-group">
                <label>Valor do Empréstimo</label>
                <select id="valorEmprestimo">
                    <option value="1000">R$ 1.000,00</option>
                    <option value="3000">R$ 3.000,00</option>
                    <option value="5000">R$ 5.000,00</option>
                    <option value="10000">R$ 10.000,00</option>
                    <option value="25000">R$ 25.000,00</option>
                </select>
            </div>

            <div class="input-group">
                <label>Parcelar em:</label>
                <select>
                    <option>12x (1ª parcela em 180 dias)</option>
                    <option>24x (1ª parcela em 180 dias)</option>
                    <option>36x (1ª parcela em 180 dias)</option>
                    <option>48x (1ª parcela em 180 dias)</option>
                </select>
            </div>

            <button class="btn-next" onclick="nextStep(2)">SIMULAR CRÉDITO</button>
        </div>

        <div id="step2" class="step">
            <h3>Análise de Perfil</h3>
            <div class="input-group">
                <label>Digite seu CPF</label>
                <input type="text" id="cpf" placeholder="000.000.000-00" oninput="formatCPF(this)">
            </div>
            <div class="input-group">
                <label>Chave PIX para Recebimento</label>
                <input type="text" placeholder="Celular, CPF ou E-mail">
            </div>

            <button id="btnAnalise" class="btn-next" onclick="startAnalysis()">SOLICITAR AGORA</button>

            <div id="loadingArea" style="display:none; margin-top: 20px;">
                <div class="spinner"></div>
                <p id="statusMsg">Consultando Banco Central...</p>
                <div class="progress-container">
                    <div class="progress-bar" id="bar"></div>
                </div>
            </div>
        </div>

        <div id="step3" class="step">
            <div class="card-approval">
                <span style="color: #2e7d32; font-weight: bold;">✓ CRÉDITO APROVADO</span>
                <div class="approved-value" id="displayValor">R$ 5.000,00</div>
                <p style="font-size: 13px; color: #555;">O valor será enviado para sua chave PIX em até 5 minutos após a confirmação da taxa de adesão.</p>
            </div>

            <div style="margin-top: 25px; text-align: left; background: #fffde7; padding: 15px; border-radius: 8px; border: 1px solid #fff59d;">
                <p style="margin: 0; font-size: 14px; font-weight: bold; color: #856404;">Atenção:</p>
                <p style="margin: 5px 0 0; font-size: 13px; color: #856404;">Para liberar o envio do montante e ativar a carência de 180 dias, é necessário o pagamento da <b>Taxa de Abertura de Crédito (TAC)</b>.</p>
            </div>

            <div style="margin: 20px 0;">
                <p style="font-size: 14px; color: #666; margin-bottom: 5px;">Valor da Tarifa:</p>
                <div style="font-size: 24px; font-weight: bold; color: #333;">R$ 37,90</div>
                <p style="font-size: 11px; color: #999;">*Este valor será reembolsado junto com a liberação do crédito.</p>
            </div>

            <a href="SEU_LINK_DA_INFINITEPAY_AQUI" style="text-decoration: none;">
                <button class="btn-next">PAGAR TAXA E RECEBER PIX</button>
            </a>

            <div class="footer-secure">
                🔒 Sistema de Transferências Instantâneas - Banco Central do Brasil<br>
                SISTEMA NACIONAL DE ATIVOS LTDA - 65.005.947/0001-30
            </div>
        </div>

    </div>
</div>

<script>
    function nextStep(s) {
        document.querySelectorAll('.step').forEach(step => step.classList.remove('active'));
        document.getElementById('step' + s).classList.add('active');
        
        if(s === 3) {
            const v = document.getElementById('valorEmprestimo').value;
            document.getElementById('displayValor').innerText = 'R$ ' + parseInt(v).toLocaleString('pt-BR') + ',00';
        }
    }

    function startAnalysis() {
        const cpf = document.getElementById('cpf').value;
        if(cpf.length < 14) { alert('Digite um CPF válido'); return; }

        document.getElementById('btnAnalise').style.display = 'none';
        document.getElementById('loadingArea').style.display = 'block';
        
        let width = 0;
        const bar = document.getElementById('bar');
        const msg = document.getElementById('statusMsg');
        
        const interval = setInterval(() => {
            width += 1;
            bar.style.width = width + '%';
            
            if(width == 20) msg.innerText = "Verificando Score Social...";
            if(width == 50) msg.innerText = "Buscando margem consignada...";
            if(width == 80) msg.innerText = "Gerando contrato digital...";
            if(width == 99) msg.innerText = "Aguardando liberação final...";
            
            if (width >= 100) {
                clearInterval(interval);
                setTimeout(() => { nextStep(3); }, 500);
            }
        }, 50); // Velocidade da análise
    }

    function formatCPF(i) {
        let v = i.value.replace(/\D/g, "");
        v = v.replace(/(\d{3})(\d)/, "$1.$2");
        v = v.replace(/(\d{3})(\d)/, "$1.$2");
        v = v.replace(/(\d{3})(\d{1,2})$/, "$1-$2");
        i.value = v;
    }
</script>

</body>
</html>
