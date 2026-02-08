<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>E-CRED | Consulta de Crédito 2026</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;800&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #f3f4f6; color: #111; }
        .app-container { max-width: 500px; margin: 0 auto; background: white; min-height: 100vh; position: relative; box-shadow: 0 0 20px rgba(0,0,0,0.05); }
        .step { display: none; padding: 25px; animation: slideIn 0.3s ease-out; }
        .step.active { display: block; }
        @keyframes slideIn { from { opacity: 0; transform: translateX(20px); } to { opacity: 1; transform: translateX(0); } }
        
        .btn-primary { background: #0057ff; color: white; width: 100%; padding: 18px; border-radius: 12px; font-weight: 700; transition: 0.2s; }
        .btn-primary:active { transform: scale(0.98); background: #0046cc; }
        
        .progress-bar { height: 6px; background: #e5e7eb; border-radius: 10px; margin-bottom: 30px; overflow: hidden; }
        .progress-fill { height: 100%; background: #0057ff; width: 0%; transition: width 0.4s; }
        
        input { width: 100%; border: 1.5px solid #e5e7eb; padding: 16px; border-radius: 10px; margin-bottom: 15px; font-size: 16px; outline: none; transition: 0.3s; }
        input:focus { border-color: #0057ff; }
        
        .bank-card { border: 1.5px solid #e5e7eb; padding: 15px; border-radius: 12px; margin-bottom: 10px; display: flex; align-items: center; cursor: pointer; }
        .bank-card.selected { border-color: #0057ff; background: #f0f6ff; }

        /* LOADING ANIMATION */
        .loader { border: 4px solid #f3f3f3; border-top: 4px solid #0057ff; border-radius: 50%; width: 40px; height: 40px; animation: spin 1s linear infinite; margin: 20px auto; }
        @keyframes spin { 0% { transform: rotate(0deg); } 100% { transform: rotate(360deg); } }
    </style>
</head>
<body>

<div class="app-container">
    <header class="p-5 flex items-center justify-between border-b">
        <div class="flex items-center">
            <div class="w-8 h-8 bg-blue-600 rounded-lg flex items-center justify-center mr-2">
                <span class="text-white font-black text-xs italic">EC</span>
            </div>
            <span class="font-extrabold text-xl tracking-tighter">E-CRED</span>
        </div>
        <div class="text-[10px] bg-green-100 text-green-700 px-2 py-1 rounded font-bold">● SISTEMA OPERACIONAL</div>
    </header>

    <div class="progress-bar mx-5 mt-4">
        <div class="progress-fill" id="progressFill"></div>
    </div>

    <div class="step active" id="step1">
        <h2 class="text-2xl font-extrabold mb-2">Bem-vindo(a)!</h2>
        <p class="text-gray-500 mb-6 text-sm">Para começar, como deseja ser chamado(a)?</p>
        <input type="text" id="userName" placeholder="Nome Completo">
        <button class="btn-primary mt-4" onclick="nextStep(2, '25%')">CONTINUAR</button>
    </div>

    <div class="step" id="step2">
        <h2 class="text-2xl font-extrabold mb-2">Ótimo, <span id="displayName" class="text-blue-600"></span>!</h2>
        <p class="text-gray-500 mb-6 text-sm">Precisamos do seu CPF e data de nascimento para verificar o limite disponível no IP da sua rede.</p>
        <input type="tel" id="userCPF" placeholder="000.000.000-00">
        <input type="tel" placeholder="Data de Nascimento (DD/MM/AAAA)">
        <button class="btn-primary mt-4" onclick="nextStep(3, '50%')">ANALISAR CRÉDITO</button>
    </div>

    <div class="step" id="step3">
        <h2 class="text-2xl font-extrabold mb-2">Onde recebe?</h2>
        <p class="text-gray-500 mb-6 text-sm">Selecione a instituição onde deseja receber o PIX do empréstimo.</p>
        <div class="bank-card" onclick="selectBank(this)">
            <img src="https://cdn-icons-png.flaticon.com/512/584/584067.png" width="24" class="mr-3">
            <span class="font-bold">Nubank</span>
        </div>
        <div class="bank-card" onclick="selectBank(this)">
            <img src="https://cdn-icons-png.flaticon.com/512/584/584067.png" width="24" class="mr-3">
            <span class="font-bold">Itaú</span>
        </div>
        <div class="bank-card" onclick="selectBank(this)">
            <img src="https://cdn-icons-png.flaticon.com/512/584/584067.png" width="24" class="mr-3">
            <span class="font-bold">Caixa Econômica</span>
        </div>
        <div class="bank-card" onclick="selectBank(this)">
            <span class="font-bold">Outros Bancos</span>
        </div>
        <button class="btn-primary mt-6" onclick="startAnalysis()">SOLICITAR ANÁLISE ➤</button>
    </div>

    <div class="step text-center" id="stepLoading">
        <h2 class="text-2xl font-extrabold mb-4">Consultando Servidores...</h2>
        <div class="loader"></div>
        <p class="text-gray-500 text-sm animate-pulse" id="loadingText">Rastreando margem via IP...</p>
    </div>

    <div class="step" id="stepResult">
        <div class="bg-green-50 p-6 rounded-2xl border-2 border-green-100 text-center mb-6">
            <h2 class="text-green-600 font-black text-3xl uppercase">Crédito Aprovado!</h2>
            <p class="text-gray-600 text-sm mt-1">Limite localizado para o seu Perfil Bancário:</p>
            <div class="text-4xl font-black my-4">R$ 4.750,00</div>
            <p class="text-[10px] text-gray-400">DISPONÍVEL PARA ENVIO VIA PIX IMEDIATO</p>
        </div>

        <div class="bg-blue-50 p-4 rounded-xl text-xs text-blue-800 mb-6 leading-relaxed">
            <strong>⚠️ INFORMAÇÃO IMPORTANTE:</strong><br>
            Devido ao protocolo de segurança 892, para liberar o envio do valor para sua conta, é necessária a ativação da sua <b>Chave de Custódia Digital</b>. A taxa de ativação é de <b>R$ 97,00</b> e será 100% estornada (devolvida) junto com o valor do empréstimo.
        </div>

        <a href="https://go.perfectpay.com.br/PPU38CQ79SG" class="btn-primary block text-center uppercase tracking-tighter">
            LIBERAR MEU CRÉDITO AGORA
        </a>
    </div>

    <div class="p-6 border-t mt-10">
        <div class="flex items-center mb-4">
            <div class="flex -space-x-2">
                <img class="w-8 h-8 rounded-full border-2 border-white" src="https://randomuser.me/api/portraits/women/1.jpg">
                <img class="w-8 h-8 rounded-full border-2 border-white" src="https://randomuser.me/api/portraits/men/2.jpg">
                <img class="w-8 h-8 rounded-full border-2 border-white" src="https://randomuser.me/api/portraits/women/3.jpg">
            </div>
            <span class="text-[10px] text-gray-500 ml-4 font-bold uppercase tracking-widest">+1.420 PESSOAS RECEBERAM HOJE</span>
        </div>
    </div>
</div>

<script>
    function nextStep(step, progress) {
        if(step === 2) {
            const name = document.getElementById('userName').value;
            if(!name) return alert('Por favor, digite seu nome');
            document.getElementById('displayName').innerText = name.split(' ')[0];
        }
        
        document.querySelectorAll('.step').forEach(s => s.classList.remove('active'));
        document.getElementById('step' + step).classList.add('active');
        document.getElementById('progressFill').style.width = progress;
    }

    function selectBank(el) {
        document.querySelectorAll('.bank-card').forEach(c => c.classList.remove('selected'));
        el.classList.add('selected');
    }

    function startAnalysis() {
        nextStep('Loading', '85%');
        const phrases = [
            "Autenticando via Endereço de IP...",
            "Localizando margem no Banco Central...",
            "Aplicando Protocolo 892...",
            "Finalizando liberação de saldo..."
        ];
        
        let i = 0;
        const interval = setInterval(() => {
            document.getElementById('loadingText').innerText = phrases[i];
            i++;
            if(i >= phrases.length) {
                clearInterval(interval);
                nextStep('Result', '100%');
            }
        }, 1500);
    }
</script>

</body>
</html>
