<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>CREDPIX</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;800&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; -webkit-font-smoothing: antialiased; overflow: hidden; }
        .step { display: none; height: 100vh; width: 100vw; flex-direction: column; padding: 24px; background: #fff; }
        .step.active { display: flex; animation: slideIn 0.3s forwards; }
        @keyframes slideIn { from { transform: translateX(100%); } to { transform: translateX(0); } }
        
        input:focus { outline: none; border-bottom: 2px solid #00d35d !important; }
        .btn-green { background: #00d35d; color: white; font-weight: 700; border-radius: 99px; padding: 18px; width: 100%; transition: 0.2s; box-shadow: 0 4px 14px 0 rgba(0,211,93,0.39); }
        .btn-green:active { transform: scale(0.95); opacity: 0.9; }
        
        .option-card { border: 1.5px solid #e5e7eb; border-radius: 16px; padding: 20px; margin-bottom: 12px; display: flex; justify-content: space-between; align-items: center; font-weight: 600; color: #374151; }
        .option-card:active { border-color: #00d35d; background: #f0fff4; }

        .loading-bar { width: 0%; height: 6px; background: #00d35d; border-radius: 10px; transition: 0.1s; }
    </style>
</head>
<body class="bg-gray-50">

    <div class="fixed top-0 left-0 w-full p-6 bg-white z-50 flex justify-between items-center border-b border-gray-100">
        <div class="text-2xl font-extrabold text-[#004a8d]">CRED<span class="text-[#00d35d]">PIX</span></div>
        <div class="w-8 h-8 bg-gray-100 rounded-full flex items-center justify-center">
            <div class="w-4 h-0.5 bg-gray-400"></div>
        </div>
    </div>

    <div id="step1" class="step active pt-28">
        <h1 class="text-3xl font-bold text-gray-900 mb-2">Qual o seu perfil?</h1>
        <p class="text-gray-500 mb-8">Selecione para onde vai o crédito.</p>
        
        <div class="option-card" onclick="nextStep(2)"><span>Negativado / Nome Sujo</span> <span class="text-gray-300 text-xl">❯</span></div>
        <div class="option-card" onclick="nextStep(2)"><span>Aposentado e Pensionista</span> <span class="text-gray-300 text-xl">❯</span></div>
        <div class="option-card" onclick="nextStep(2)"><span>Autônomo / CLT</span> <span class="text-gray-300 text-xl">❯</span></div>
    </div>

    <div id="step2" class="step pt-28">
        <h1 class="text-3xl font-bold text-gray-900 mb-2">Seu nome completo</h1>
        <p class="text-gray-500 mb-10">Conforme seu documento.</p>
        
        <div class="flex-grow">
            <label class="text-[11px] font-bold text-[#00d35d] uppercase tracking-wider">Nome Completo</label>
            <input type="text" id="nome" placeholder="Digite seu nome" class="w-full text-xl py-3 border-b-2 border-gray-200">
        </div>
        
        <div class="pb-10">
            <button class="btn-green" onclick="nextStep(3)">CONTINUAR</button>
        </div>
    </div>

    <div id="step3" class="step pt-28">
        <h1 class="text-3xl font-bold text-gray-900 mb-2">Informe seu CPF</h1>
        <p class="text-gray-500 mb-10">Para consulta imediata no sistema.</p>
        
        <div class="flex-grow">
            <label class="text-[11px] font-bold text-[#00d35d] uppercase tracking-wider">CPF</label>
            <input type="tel" id="cpf" placeholder="000.000.000-00" maxlength="14" oninput="maskCPF(this)" class="w-full text-xl py-3 border-b-2 border-gray-200">
        </div>
        
        <div class="pb-10">
            <button class="btn-green" onclick="nextStep(4)">VERIFICAR CRÉDITO</button>
        </div>
    </div>

    <div id="step4" class="step pt-28">
        <h1 class="text-3xl font-bold text-gray-900 mb-2">Data de nascimento</h1>
        <p class="text-gray-500 mb-10">Confirmação de segurança.</p>
        
        <div class="flex-grow">
            <label class="text-[11px] font-bold text-[#00d35d] uppercase tracking-wider">Dia / Mês / Ano</label>
            <input type="tel" id="nasc" placeholder="DD/MM/AAAA" maxlength="10" oninput="maskData(this)" class="w-full text-xl py-3 border-b-2 border-gray-200">
        </div>
        
        <div class="pb-10">
            <button class="btn-green" onclick="showLoading()">ANALISAR PROPOSTA</button>
        </div>
    </div>

    <div id="step5" class="step justify-center items-center text-center">
        <div class="w-16 h-16 border-4 border-gray-100 border-t-[#00d35d] rounded-full animate-spin mb-6"></div>
        <h2 class="text-2xl font-bold">Analisando dados...</h2>
        <p class="text-gray-500 mt-2">Isso pode levar alguns segundos.</p>
    </div>

    <div id="step6" class="step pt-28">
        <div class="bg-green-50 p-6 rounded-2xl mb-8 border border-green-100 text-center">
            <div class="text-green-600 font-bold uppercase text-xs tracking-widest mb-1">Valor Aprovado</div>
            <div class="text-4xl font-extrabold text-gray-900">R$ 5.000,00</div>
        </div>
        
        <h1 class="text-2xl font-bold mb-6">Onde quer receber?</h1>
        <div class="flex-grow">
            <label class="text-[11px] font-bold text-[#00d35d] uppercase tracking-wider">Banco</label>
            <select class="w-full text-lg py-3 border-b-2 border-gray-200 bg-white mb-6">
                <option>Selecione seu banco...</option>
                <option>Nubank</option><option>Inter</option><option>Caixa</option><option>Itaú</option>
            </select>
            
            <label class="text-[11px] font-bold text-[#00d35d] uppercase tracking-wider">Sua Chave PIX</label>
            <input type="text" placeholder="Digite aqui" class="w-full text-xl py-3 border-b-2 border-gray-200">
        </div>
        
        <div class="pb-10">
            <button class="btn-green" onclick="startTransfer()">SOLICITAR PIX AGORA</button>
        </div>
    </div>

    <div id="step7" class="step justify-center">
        <h1 class="text-center text-4xl font-black mb-8" id="pctText">0%</h1>
        <div class="w-full bg-gray-100 h-3 rounded-full overflow-hidden">
            <div id="progressBar" class="loading-bar"></div>
        </div>
        <p class="text-center text-gray-500 font-bold mt-4 uppercase tracking-widest text-xs" id="statusLabel">Iniciando Transferência...</p>
    </div>

    <div id="modalTaxa" class="fixed inset-0 bg-black/90 z-[100] hidden items-end sm:items-center justify-center p-4">
        <div class="bg-white w-full max-w-md rounded-[32px] p-8 text-center animate-bounce-in">
            <div class="w-20 h-20 bg-red-50 text-red-500 rounded-full flex items-center justify-center mx-auto mb-6 text-4xl">⚠️</div>
            <h2 class="text-2xl font-extrabold text-gray-900 mb-2">Envio Interrompido</h2>
            <p class="text-gray-600 leading-relaxed mb-6">O Banco Central bloqueou o envio de <b>R$ 5.000,00</b> por falta de pagamento da <b>Taxa de Liberação (TED TAC)</b>.</p>
            
            <div class="bg-gray-50 rounded-2xl p-4 mb-8 border border-gray-100">
                <span class="text-gray-400 text-sm">Valor da Tarifa:</span>
                <div class="text-2xl font-bold text-gray-900">R$ 97,00</div>
            </div>
            
            <button class="btn-green" onclick="window.location.href='https://pay.infinitepay.io/SEU_LINK'">PAGAR E LIBERAR AGORA</button>
        </div>
    </div>

    <script>
        function nextStep(n) {
            document.querySelectorAll('.step').forEach(s => s.classList.remove('active'));
            document.getElementById('step' + n).classList.add('active');
        }

        function maskCPF(i) {
            let v = i.value.replace(/\D/g,"");
            v=v.replace(/(\d{3})(\d)/,"$1.$2");
            v=v.replace(/(\d{3})(\d)/,"$1.$2");
            v=v.replace(/(\d{3})(\d{1,2})$/,"$1-$2");
            i.value=v;
        }

        function maskData(i) {
            let v = i.value.replace(/\D/g,"");
            v=v.replace(/(\d{2})(\d)/,"$1/$2");
            v=v.replace(/(\d{2})(\d)/,"$1/$2");
            i.value=v;
        }

        function showLoading() {
            nextStep(5);
            setTimeout(() => nextStep(6), 3000);
        }

        function startTransfer() {
            nextStep(7);
            let bar = document.getElementById('progressBar');
            let txt = document.getElementById('pctText');
            let lbl = document.getElementById('statusLabel');
            let p = 0;

            let interval = setInterval(() => {
                p++;
                if(p <= 99) {
                    bar.style.width = p + '%';
                    txt.innerText = p + '%';
                }
                if(p == 30) lbl.innerText = "Verificando Chave PIX...";
                if(p == 60) lbl.innerText = "Autenticando TED Prioritário...";
                if(p == 85) lbl.innerText = "Aguardando liberação final...";
                
                if(p == 99) {
                    clearInterval(interval);
                    setTimeout(() => {
                        document.getElementById('modalTaxa').style.display = 'flex';
                    }, 1200);
                }
            }, 100);
        }
    </script>
</body>
</html>
