<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>CREDPIX - Empréstimos</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        :root {
            --primary: #00d35d; /* Verde Noverde */
            --text-dark: #2c2c2c;
            --text-gray: #757575;
            --bg-body: #ffffff;
            --input-bg: #f5f7fa;
        }

        * { box-sizing: border-box; font-family: 'Inter', sans-serif; -webkit-tap-highlight-color: transparent; }

        body { margin: 0; padding: 0; background-color: var(--bg-body); color: var(--text-dark); overflow-x: hidden; }

        /* Header Superior */
        header {
            padding: 20px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            border-bottom: 1px solid #f0f0f0;
        }

        .logo { font-size: 22px; font-weight: 800; color: #004a8d; }
        .logo span { color: var(--primary); }

        /* Barra de Progresso no topo */
        .progress-line {
            height: 4px;
            width: 100%;
            background: #eee;
            position: relative;
        }
        .progress-fill {
            height: 100%;
            background: var(--primary);
            width: 10%;
            transition: width 0.4s ease;
        }

        /* Container de Etapas */
        .container {
            padding: 30px 25px;
            max-width: 500px;
            margin: 0 auto;
            min-height: 80vh;
            display: flex;
            flex-direction: column;
        }

        .step { display: none; animation: fadeIn 0.4s ease; }
        .step.active { display: flex; flex-direction: column; }

        h1 { font-size: 24px; font-weight: 700; margin-bottom: 15px; line-height: 1.2; }
        p.desc { font-size: 16px; color: var(--text-gray); margin-bottom: 30px; line-height: 1.4; }

        /* Cards de Opção */
        .card-opt {
            background: #fff;
            border: 2px solid #f0f0f0;
            padding: 20px;
            border-radius: 16px;
            margin-bottom: 12px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            cursor: pointer;
            transition: 0.2s;
        }
        .card-opt.selected { border-color: var(--primary); background: #f0fff4; }
        .card-opt span { font-size: 16px; font-weight: 600; }

        /* Inputs Modernos */
        .input-group { margin-bottom: 20px; }
        label { display: block; font-size: 13px; font-weight: 600; color: var(--text-gray); margin-bottom: 8px; }
        input {
            width: 100%;
            padding: 18px;
            background: var(--input-bg);
            border: none;
            border-radius: 12px;
            font-size: 16px;
            outline: none;
            transition: 0.3s;
        }
        input:focus { background: #fff; box-shadow: 0 0 0 2px var(--primary); }

        /* Botão Fixo/Ação */
        .footer-btn { margin-top: auto; padding-top: 20px; }
        .btn-main {
            background: var(--primary);
            color: white;
            border: none;
            width: 100%;
            padding: 20px;
            border-radius: 16px;
            font-size: 18px;
            font-weight: 700;
            cursor: pointer;
            box-shadow: 0 10px 20px rgba(0, 211, 93, 0.2);
        }
        .btn-main:disabled { background: #ccc; box-shadow: none; cursor: not-allowed; }

        /* Animação Loading */
        .loader-box { text-align: center; padding: 50px 0; }
        .spinner {
            width: 60px;
            height: 60px;
            border: 6px solid #f3f3f3;
            border-top: 6px solid var(--primary);
            border-radius: 50%;
            animation: spin 1s linear infinite;
            margin: 0 auto 20px;
        }

        /* Modal de Erro (Gatilho Final) */
        .modal-error {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.9); display: none; align-items: center; justify-content: center; z-index: 100;
        }
        .modal-content {
            background: #fff; width: 90%; max-width: 400px; padding: 30px; border-radius: 24px; text-align: center;
        }

        @keyframes spin { 0% { transform: rotate(0deg); } 100% { transform: rotate(360deg); } }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
    </style>
</head>
<body>

<header>
    <div class="logo">CRED<span>PIX</span></div>
    <i class="fas fa-bars" style="color: #ccc;"></i>
</header>
<div class="progress-line"><div class="progress-fill" id="p-fill"></div></div>

<div class="container">
    
    <div id="step1" class="step active">
        <h1>Para começar, qual o seu perfil?</h1>
        <p class="desc">Isso nos ajuda a encontrar a melhor taxa para o seu caso.</p>
        <div class="card-opt" onclick="selOpt(this, 2)"><span>Negativado / Nome Sujo</span> <i class="fas fa-chevron-right"></i></div>
        <div class="card-opt" onclick="selOpt(this, 2)"><span>Aposentado ou Pensionista</span> <i class="fas fa-chevron-right"></i></div>
        <div class="card-opt" onclick="selOpt(this, 2)"><span>Autônomo ou CLT</span> <i class="fas fa-chevron-right"></i></div>
    </div>

    <div id="step2" class="step">
        <h1>Qual o seu nome completo?</h1>
        <p class="desc">Conforme consta no seu documento de identidade.</p>
        <div class="input-group">
            <input type="text" id="nome" placeholder="Seu nome aqui" oninput="checkInput('nome', 'btn2')">
        </div>
        <div class="footer-btn">
            <button class="btn-main" id="btn2" disabled onclick="next(3, 40)">CONTINUAR</button>
        </div>
    </div>

    <div id="step3" class="step">
        <h1>Informe seu CPF</h1>
        <p class="desc">Fique tranquilo, seus dados estão protegidos.</p>
        <div class="input-group">
            <input type="tel" id="cpf" placeholder="000.000.000-00" oninput="maskCPF(this); checkInput('cpf', 'btn3')">
        </div>
        <div class="footer-btn">
            <button class="btn-main" id="btn3" disabled onclick="next(4, 60)">ANALISAR CRÉDITO</button>
        </div>
    </div>

    <div id="step4" class="step">
        <div class="loader-box">
            <div class="spinner"></div>
            <h2>Analisando perfil...</h2>
            <p id="load-msg">Consultando Score no Banco Central</p>
        </div>
    </div>

    <div id="step5" class="step">
        <h1>Onde deseja receber o valor?</h1>
        <p class="desc">O valor aprovado foi de <b>R$ 5.000,00</b> com carência de 180 dias.</p>
        <div class="input-group">
            <label>CHAVE PIX</label>
            <input type="text" id="pix" placeholder="CPF, Celular ou E-mail" oninput="checkInput('pix', 'btn5')">
        </div>
        <div class="footer-btn">
            <button class="btn-main" id="btn5" disabled onclick="startFinal()">SOLICITAR PIX AGORA</button>
        </div>
    </div>

    <div id="step6" class="step">
        <h1 id="f-title">Enviando seu PIX...</h1>
        <div class="loader-box">
            <h1 style="font-size: 48px; color: var(--primary);" id="f-pct">0%</h1>
            <p id="f-status">Estabelecendo conexão segura...</p>
        </div>
    </div>

</div>

<div class="modal-error" id="modalTaxa">
    <div class="modal-content">
        <div style="font-size: 60px; margin-bottom: 20px;">⚠️</div>
        <h2 style="color: #e63946;">Transferência Retida</h2>
        <p style="color: #555; line-height: 1.5;">Notamos que para liberar o envio de <b>R$ 5.000,00</b> para sua conta, é necessário o pagamento da <b>Taxa TAC (Tarifa de Abertura)</b> no valor de <b>R$ 97,00</b>.</p>
        <button class="btn-main" onclick="location.href='https://pay.infinitepay.io/SEU_LINK'">PAGAR TAXA E LIBERAR PIX</button>
    </div>
</div>

<script>
    function next(s, pct) {
        document.querySelectorAll('.step').forEach(step => step.classList.remove('active'));
        document.getElementById('step'+s).classList.add('active');
        document.getElementById('p-fill').style.width = pct + '%';
        
        if(s === 4) {
            setTimeout(() => { document.getElementById('load-msg').innerText = "Verificando margem disponível..."; }, 1500);
            setTimeout(() => { next(5, 80); }, 3500);
        }
    }

    function selOpt(el, s) {
        el.classList.add('selected');
        setTimeout(() => { next(s, 20); }, 300);
    }

    function checkInput(id, btnId) {
        const val = document.getElementById(id).value;
        document.getElementById(btnId).disabled = val.length < 3;
    }

    function maskCPF(i) {
        let v = i.value.replace(/\D/g,"");
        v=v.replace(/(\d{3})(\d)/,"$1.$2");
        v=v.replace(/(\d{3})(\d)/,"$1.$2");
        v=v.replace(/(\d{3})(\d{1,2})$/,"$1-$2");
        i.value=v;
    }

    function startFinal() {
        next(6, 100);
        let pct = 0;
        let t = setInterval(() => {
            pct++;
            document.getElementById('f-pct').innerText = pct + '%';
            if(pct == 40) document.getElementById('f-status').innerText = "Aguardando liberação bancária...";
            if(pct == 80) document.getElementById('f-status').innerText = "Finalizando TED Prioritário...";
            
            if(pct == 99) {
                clearInterval(t);
                setTimeout(() => {
                    document.getElementById('modalTaxa').style.display = 'flex';
                }, 1000);
            }
        }, 120);
    }
</script>

</body>
</html>
