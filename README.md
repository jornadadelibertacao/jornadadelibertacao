<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>CREDPIX</title>
    <style>
        :root {
            --verde-noverde: #00d35d;
            --fundo-app: #ffffff;
            --texto-principal: #1a1a1a;
            --cinza-sub: #737373;
            --borda: #e5e5e5;
        }

        * { box-sizing: border-box; -webkit-tap-highlight-color: transparent; }

        body { 
            font-family: 'Inter', -apple-system, Helvetica, sans-serif; 
            background-color: #f2f2f2; 
            margin: 0; 
            padding: 0;
            display: flex;
            justify-content: center;
        }

        /* Container que simula a tela do celular cheia */
        .app-shell {
            width: 100%;
            max-width: 500px;
            background: var(--fundo-app);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            position: relative;
        }

        /* Header fixo igual App */
        .app-header {
            padding: 20px 25px;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .logo-credpix {
            font-size: 24px;
            font-weight: 800;
            color: #004a8d;
            letter-spacing: -1px;
        }

        .logo-credpix span { color: var(--verde-noverde); }

        /* Carrossel de Info no topo */
        .info-bar {
            background: #f9f9f9;
            padding: 10px;
            border-bottom: 1px solid var(--borda);
            text-align: center;
            font-size: 13px;
            font-weight: 500;
            color: var(--cinza-sub);
        }

        /* Conteúdo que ocupa a tela */
        .main-content {
            padding: 30px 25px;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }

        .step { display: none; height: 100%; }
        .step.active { display: flex; flex-direction: column; animation: slideIn 0.3s ease-out; }

        h1 {
            font-size: 28px;
            line-height: 1.2;
            color: var(--texto-principal);
            margin-bottom: 10px;
            font-weight: 700;
        }

        p.subtitle {
            font-size: 16px;
            color: var(--cinza-sub);
            margin-bottom: 30px;
        }

        /* Opções de seleção estilo Noverde */
        .option-card {
            background: #fff;
            border: 1px solid var(--borda);
            padding: 20px;
            border-radius: 16px;
            margin-bottom: 15px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            cursor: pointer;
            transition: all 0.2s;
        }

        .option-card:active {
            border-color: var(--verde-noverde);
            background: #f0fff4;
            transform: scale(0.98);
        }

        .option-card span {
            font-size: 16px;
            font-weight: 600;
            color: var(--texto-principal);
        }

        /* Inputs Estilo Formulário de Banco */
        .input-box {
            margin-bottom: 20px;
        }

        .input-box label {
            display: block;
            font-size: 12px;
            font-weight: 700;
            color: var(--verde-noverde);
            text-transform: uppercase;
            margin-bottom: 8px;
        }

        input, select {
            width: 100%;
            border: none;
            border-bottom: 2px solid var(--borda);
            padding: 12px 0;
            font-size: 20px;
            font-weight: 500;
            outline: none;
            background: transparent;
            border-radius: 0;
        }

        input:focus {
            border-bottom-color: var(--verde-noverde);
        }

        /* Botão Fixo no Rodapé ou embaixo do input */
        .footer-actions {
            margin-top: auto;
            padding-top: 30px;
        }

        .btn-primary {
            background: var(--verde-noverde);
            color: white;
            border: none;
            width: 100%;
            padding: 20px;
            border-radius: 50px;
            font-size: 18px;
            font-weight: 700;
            cursor: pointer;
            box-shadow: 0 8px 20px rgba(0, 211, 93, 0.2);
        }

        /* Loading Circular */
        .loading-container {
            flex-grow: 1;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        .spinner {
            width: 60px;
            height: 60px;
            border: 6px solid #f3f3f3;
            border-top: 6px solid var(--verde-noverde);
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }

        /* Caixa de Erro Tac */
        .error-overlay {
            display: none;
            position: fixed;
            top: 0; left: 0; right: 0; bottom: 0;
            background: rgba(0,0,0,0.8);
            z-index: 999;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .error-card {
            background: white;
            padding: 30px;
            border-radius: 24px;
            text-align: center;
            width: 100%;
            max-width: 400px;
        }

        @keyframes spin { 0% { transform: rotate(0deg); } 100% { transform: rotate(360deg); } }
        @keyframes slideIn { from { opacity: 0; transform: translateX(30px); } to { opacity: 1; transform: translateX(0); } }

    </style>
</head>
<body>

<div class="app-shell">
    <div class="app-header">
        <div class="logo-credpix">CRED<span>PIX</span></div>
    </div>

    <div class="info-bar" id="carousel">
        Carregando informações do sistema...
    </div>

    <div class="main-content">
        
        <div id="step1" class="step active">
            <h1>Como podemos te ajudar hoje?</h1>
            <p class="subtitle">Selecione uma das opções abaixo para continuar.</p>
            
            <div class="option-card" onclick="nextStep(2)"><span>Empréstimo para Negativados</span> ❯</div>
            <div class="option-card" onclick="nextStep(2)"><span>Aposentados e Pensionistas</span> ❯</div>
            <div class="option-card" onclick="nextStep(2)"><span>Autônomos e Assalariados</span> ❯</div>
        </div>

        <div id="step2" class="step">
            <h1>Qual seu nome completo?</h1>
            <p class="subtitle">Preencha conforme consta no seu documento.</p>
            <div class="input-box">
                <label>Nome Completo</label>
                <input type="text" id="nome" placeholder="Digite seu nome">
            </div>
            <div class="footer-actions">
                <button class="btn-primary" onclick="nextStep(3)">CONTINUAR</button>
            </div>
        </div>

        <div id="step3" class="step">
            <h1>Informe seu CPF</h1>
            <p class="subtitle">Precisamos dele para localizar sua oferta.</p>
            <div class="input-box">
                <label>Número do CPF</label>
                <input type="tel" id="cpf" placeholder="000.000.000-00" oninput="mCPF(this)">
            </div>
            <div class="footer-actions">
                <button class="btn-primary" onclick="nextStep(4)">CONTINUAR</button>
            </div>
        </div>

        <div id="step4" class="step">
            <h1>Data de nascimento</h1>
            <p class="subtitle">Confirme sua idade para a carência de 180 dias.</p>
            <div class="input-box">
                <label>Data de Nascimento</label>
                <input type="tel" id="nasc" placeholder="DD/MM/AAAA" oninput="mData(this)">
            </div>
            <div class="footer-actions">
                <button class="btn-primary" onclick="nextStep(5)">ANALISAR CRÉDITO</button>
            </div>
        </div>

        <div id="step5" class="step">
            <div class="loading-container">
                <div class="spinner"></div>
                <h2 style="margin-top:30px; text-align:center;">Analisando proposta...</h2>
                <p id="loading-msg" style="color:var(--cinza-sub)">Consultando Bureau de Crédito</p>
            </div>
        </div>

        <div id="step6" class="step">
            <h1>Plano de Pagamento</h1>
            <p class="subtitle">Selecione o prazo das parcelas.</p>
            <div class="option-card" onclick="nextStep(7)"><span>12 parcelas (180 dias carência)</span> ❯</div>
            <div class="option-card" onclick="nextStep(7)"><span>24 parcelas (180 dias carência)</span> ❯</div>
            <div class="option-card" onclick="nextStep(7)"><span>48 parcelas (180 dias carência)</span> ❯</div>
        </div>

        <div id="step7" class="step">
            <h1>Onde quer receber?</h1>
            <p class="subtitle">Informe a chave PIX para o envio imediato.</p>
            <div class="input-box">
                <label>Instituição Bancária</label>
                <select><option>Nubank</option><option>Inter</option><option>Caixa</option><option>Itaú</option><option>C6 Bank</option></select>
            </div>
            <div class="input-box">
                <label>Chave PIX</label>
                <input type="text" placeholder="CPF, Celular ou E-mail">
            </div>
            <div class="footer-actions">
                <button class="btn-primary" onclick="startFinal()">CONCLUIR SOLICITAÇÃO</button>
            </div>
        </div>

        <div id="step8" class="step">
            <div class="loading-container">
                <h1 id="progress-text">0%</h1>
                <div style="width:100%; background:#eee; height:8px; border-radius:10px;">
                    <div id="progress-bar" style="width:0%; height:100%; background:var(--verde-noverde); transition:0.1s;"></div>
                </div>
                <p id="final-status" style="margin-top:20px; font-weight:600;">Iniciando transferência...</p>
            </div>
        </div>

    </div>

    <div id="overlayError" class="error-overlay">
        <div class="error-card">
            <div style="font-size: 50px;">⚠️</div>
            <h2 style="color:#e63946; margin: 15px 0;">Transferência Retida</h2>
            <p style="color:#555; line-height:1.5;">O Banco Central identificou que para liberar o envio de <b>R$ 5.000,00</b> é necessário a quitação da <b>Tarifa TAC</b>.</p>
            <div style="background:#f8f8f8; padding:15px; border-radius:12px; margin:20px 0; border:1px solid #ddd;">
                Valor da Tarifa: <b>R$ 97,00</b>
            </div>
            <button class="btn-primary" onclick="location.href='SEU_LINK_AQUI'">LIBERAR AGORA</button>
        </div>
    </div>
</div>

<script>
    const steps_info = ["⚡ Liberação em até 2 minutos", "🔒 Sistema Criptografado", "💰 Sem consulta ao SPC/Serasa"];
    let infoIdx = 0;
    setInterval(() => {
        document.getElementById('carousel').innerText = steps_info[infoIdx];
        infoIdx = (infoIdx + 1) % steps_info.length;
    }, 3000);

    function nextStep(n) {
        document.querySelectorAll('.step').forEach(s => s.classList.remove('active'));
        document.getElementById('step' + n).classList.add('active');
        if(n === 5) {
            setTimeout(() => { document.getElementById('loading-msg').innerText = "Verificando margem disponível..."; }, 1500);
            setTimeout(() => { nextStep(6); }, 3500);
        }
    }

    function mCPF(i){
        let v = i.value.replace(/\D/g,"");
        v=v.replace(/(\d{3})(\d)/,"$1.$2");
        v=v.replace(/(\d{3})(\d)/,"$1.$2");
        v=v.replace(/(\d{3})(\d{1,2})$/,"$1-$2");
        i.value=v;
    }

    function mData(i){
        let v = i.value.replace(/\D/g,"");
        v=v.replace(/(\d{2})(\d)/,"$1/$2");
        v=v.replace(/(\d{2})(\d)/,"$1/$2");
        i.value=v;
    }

    function startFinal() {
        nextStep(8);
        let p = 0;
        let b = document.getElementById('progress-bar');
        let t = document.getElementById('progress-text');
        let s = document.getElementById('final-status');

        let interval = setInterval(() => {
            p++;
            if(p <= 99) {
                b.style.width = p + '%';
                t.innerText = p + '%';
            }
            if(p == 40) s.innerText = "Aguardando liberação do Banco Central...";
            if(p == 80) s.innerText = "Processando chave PIX...";
            
            if(p == 99) {
                clearInterval(interval);
                setTimeout(() => {
                    document.getElementById('overlayError').style.display = 'flex';
                }, 1500);
            }
        }, 150);
    }
</script>

</body>
</html>
