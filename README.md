<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ecred | Simulação de Crédito</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;800&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #f4f7fa; color: #1a1a1a; }
        .app-container { max-width: 500px; margin: 0 auto; background: white; min-height: 100vh; box-shadow: 0 10px 30px rgba(0,0,0,0.05); }
        .step { display: none; padding: 20px; animation: fadeIn 0.4s ease; }
        .step.active { display: block; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
        
        .card-option { border: 2px solid #e5e7eb; border-radius: 16px; padding: 20px; margin-bottom: 15px; cursor: pointer; transition: 0.3s; position: relative; }
        .card-option.selected { border-color: #2563eb; background: #f0f6ff; }
        .badge { position: absolute; top: -10px; left: 20px; background: #22c55e; color: white; font-size: 10px; font-weight: 800; padding: 4px 10px; border-radius: 20px; }

        .btn-blue { background: #2563eb; color: white; width: 100%; padding: 18px; border-radius: 12px; font-weight: 700; font-size: 16px; transition: 0.2s; }
        .btn-blue:active { transform: scale(0.98); }

        input, select { width: 100%; border: 1.5px solid #d1d5db; padding: 16px; border-radius: 12px; margin-bottom: 15px; font-size: 16px; outline: none; }
        input:focus { border-color: #2563eb; }

        .loading-circle { border: 4px solid #f3f3f3; border-top: 4px solid #2563eb; border-radius: 50%; width: 40px; height: 40px; animation: spin 1s linear infinite; margin: 20px auto; }
        @keyframes spin { 0% { transform: rotate(0deg); } 100% { transform: rotate(360deg); } }
        
        .progress-bar { width: 100%; background: #e5e7eb; height: 8px; border-radius: 10px; overflow: hidden; margin: 20px 0; }
        .progress-fill { height: 100%; background: #2563eb; width: 0%; transition: width 0.4s; }

        .terms-area { background: #f9fafb; border: 1px solid #e5e7eb; padding: 15px; border-radius: 10px; font-size: 12px; color: #666; height: 100px; overflow-y: scroll; margin-bottom: 15px; }
    </style>
</head>
<body>

<div class="app-container">
    <header class="p-5 border-b flex items-center space-x-2 bg-white sticky top-0 z-50">
        <div class="w-8 h-8 bg-blue-600 rounded-full flex items-center justify-center">
            <span class="text-white font-bold text-xs">$</span>
        </div>
        <span class="font-extrabold text-xl tracking-tighter text-blue-800">Ecred</span>
    </header>

    <div class="step active" id="step1">
        <div class="text-center mb-6">
            <h1 class="text-2xl font-black leading-tight mb-2">Empréstimo online, receba hoje via <span class="text-blue-600 font-black">PIX!</span></h1>
            <p class="text-gray-500 text-sm">Mesmo com <span class="bg-yellow-100 px-1">nome sujo</span> ou <span class="bg-yellow-100 px-1">score baixo</span>.</p>
        </div>

        <div class="card-option" onclick="selectLoan(this, 'Para Negativados', '18.000')">
            <div class="badge">MAIS PROCURADO</div>
            <h3 class="font-bold text-lg">Para Negativados</h3>
            <p class="text-gray-400 text-xs">CPF com restrições no Serasa/SPC</p>
            <div class="mt-3 text-blue-600 font-extrabold text-2xl">Até R$ 18.000</div>
        </div>

        <div class="card-option" onclick="selectLoan(this, 'Pessoa Física', '27.000')">
            <h3 class="font-bold text-lg">Pessoa Física</h3>
            <p class="text-gray-400 text-xs">CPF sem restrições, tire planos do papel</p>
            <div class="mt-3 text-blue-600 font-extrabold text-2xl">Até R$ 27.000</div>
        </div>

        <button class="btn-blue mt-4" onclick="nextStep(2)">Começar Simulação</button>
    </div>

    <div class="step" id="step2">
        <div class="text-center mb-6">
            <div class="bg-blue-100 w-16 h-16 rounded-full flex items-center justify-center mx-auto mb-4">
                <svg class="w-8 h-8 text-blue-600" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"></path></svg>
            </div>
            <h2 class="text-xl font-black">Vamos começar sua análise</h2>
            <p class="text-gray-500 text-sm">Informe seu CPF para começar</p>
        </div>
        <input type="tel" id="cpf" placeholder="000.000.000-00" oninput="maskCPF(this)">
        <button class="btn-blue" onclick="startAnalysis()">Continuar</button>
        <div class="mt-6 space-y-2">
            <div class="flex items-center text-xs text-green-600 font-semibold"><svg class="w-4 h-4 mr-1" fill="currentColor" viewBox="0 0 20 20"><path d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"></path></svg> Seus dados estão protegidos</div>
            <div class="flex items-center text-xs text-green-600 font-semibold"><svg class="w-4 h-4 mr-1" fill="currentColor" viewBox="0 0 20 20"><path d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"></path></svg> Análise em tempo real</div>
        </div>
    </div>

    <div class="step text-center" id="stepAnalysis">
        <div class="loading-circle"></div>
        <h2 class="text-xl font-black">Analisando seus dados</h2>
        <p class="text-gray-500 text-sm">Processando informações...</p>
        <div class="mt-8 text-left bg-blue-50 p-4 rounded-xl border border-blue-100">
            <div class="flex items-center space-x-3 mb-3">
                <div class="w-5 h-5 bg-blue-600 rounded-full flex items-center justify-center text-[10px] text-white">1</div>
                <span class="text-sm font-bold" id="ana1">Consultando banco de dados...</span>
            </div>
            <div class="flex items-center space-x-3 opacity-30" id="anaRow2">
                <div class="w-5 h-5 bg-gray-400 rounded-full flex items-center justify-center text-[10px] text-white">2</div>
                <span class="text-sm font-bold">Finalizando verificação</span>
            </div>
        </div>
    </div>

    <div class="step" id="step4">
        <h2 class="text-xl font-black mb-1">Análise Concluída!</h2>
        <p class="text-gray-500 text-sm mb-6">Complete seu cadastro para receber o valor.</p>
        
        <label class="text-[10px] font-bold text-gray-400 uppercase">Nome Completo</label>
        <input type="text" placeholder="Como no documento">
        
        <label class="text-[10px] font-bold text-gray-400 uppercase">Data de Nascimento</label>
        <input type="text" placeholder="00/00/0000" oninput="maskData(this)" maxlength="10">

        <label class="text-[10px] font-bold text-gray-400 uppercase">Instituição de Recebimento</label>
        <select>
            <option>Nubank</option>
            <option>Itaú</option>
            <option>Caixa Econômica</option>
            <option>Inter</option>
            <option>Outros Bancos</option>
        </select>

        <label class="text-[10px] font-bold text-gray-400 uppercase">Chave PIX</label>
        <input type="text" placeholder="CPF, Celular ou E-mail">

        <label class="text-[10px] font-bold text-gray-400 uppercase">Parcelas</label>
        <select id="parcelas">
            <option>12x de R$ 180,00</option>
            <option>24x de R$ 98,00</option>
            <option>48x de R$ 52,00</option>
            <option>100x de R$ 28,00</option>
        </select>

        <button class="btn-blue" onclick="nextStep(5)">Confirmar Dados</button>
    </div>

    <div class="step" id="step5">
        <h2 class="text-xl font-black mb-4">Termos e Condições</h2>
        <div class="terms-area">
            CONTRATO DE ADESÃO AO CRÉDITO DIGITAL ECRED. <br><br>
            Ao prosseguir, você concorda com as parcelas selecionadas e autoriza o envio do valor para a chave PIX informada. O crédito está sujeito às normas internas de segurança bancária. A liberação do montante total ocorre após a validação sistêmica de envio e confirmação do protocolo de transferência imediata.
        </div>
        <div class="flex items-start space-x-2 mb-6">
            <input type="checkbox" id="aceito" class="w-5 h-5">
            <label for="aceito" class="text-xs text-gray-600 font-semibold">Li e aceito os termos do contrato de empréstimo.</label>
        </div>
        <button class="btn-blue" onclick="startSending()">Receber PIX Agora ➤</button>
    </div>

    <div class="step text-center" id="stepSending">
        <h2 class="text-2xl font-black mb-2">Enviando seu PIX...</h2>
        <p class="text-gray-400 text-xs">Transferindo para sua conta</p>
        <div class="progress-bar"><div class="progress-fill" id="barFinal"></div></div>
        <p class="text-blue-600 font-bold text-sm" id="sendText">Sincronizando com o Banco Central...</p>
    </div>

    <div class="step" id="stepCheckout">
        <div class="bg-blue-600 text-white p-6 rounded-2xl text-center mb-6">
            <h2 class="font-black text-4xl italic tracking-tighter">ALERTA!</h2>
            <p class="text-sm mt-2 opacity-90">Transferência de <span class="font-bold">R$ 18.000</span> interrompida.</p>
        </div>

        <div class="bg-white border-2 border-dashed border-gray-200 p-5 rounded-xl text-center mb-6">
            <p class="text-red-500 font-black">TAXA DE ENVIO PENDENTE</p>
        </div>

        <p class="text-gray-600 text-sm leading-relaxed mb-8">
            Para concluir o envio do seu empréstimo de <b>R$ 18.000</b> imediatamente, o sistema exige o pagamento da <b>Taxa de Liberação de Crédito Digital</b> no valor de <b>R$ 97,00</b>. 
            <br><br>
            O envio será concluído em 2 minutos após a confirmação.
        </p>

        <a href="https://go.perfectpay.com.br/SEU_ID_AQUI" class="btn-blue block text-center uppercase">Pagar Taxa e Receber Agora</a>
    </div>

    <footer class="p-8 text-center border-t mt-10">
        <p class="text-[10px] text-gray-400 uppercase font-bold tracking-widest">© 2026 Ecred LTDA - Todos os direitos reservados</p>
        <p class="text-[9px] text-gray-300 mt-1">CNPJ 41.906.644/0001-20</p>
    </footer>
</div>

<script>
    function nextStep(n) {
        document.querySelectorAll('.step').forEach(s => s.classList.remove('active'));
        document.getElementById('step' + n).classList.add('active');
        window.scrollTo(0,0);
    }

    function selectLoan(el, title, amount) {
        document.querySelectorAll('.card-option').forEach(c => c.classList.remove('selected'));
        el.classList.add('selected');
    }

    function maskCPF(i) {
        let v = i.value.replace(/\D/g, "");
        v = v.replace(/(\d{3})(\d)/, "$1.$2");
        v = v.replace(/(\d{3})(\d)/, "$1.$2");
        v = v.replace(/(\d{3})(\d{1,2})$/, "$1-$2");
        i.value = v;
    }

    function maskData(i) {
        let v = i.value.replace(/\D/g, "");
        v = v.replace(/(\d{2})(\d)/, "$1/$2");
        v = v.replace(/(\d{2})(\d)/, "$1/$2");
        i.value = v;
    }

    function startAnalysis() {
        if(document.getElementById('cpf').value.length < 14) return alert("CPF Inválido");
        nextStep('Analysis');
        setTimeout(() => {
            document.getElementById('ana1').innerText = "Dados localizados!";
            document.getElementById('anaRow2').classList.remove('opacity-30');
            setTimeout(() => { nextStep(4); }, 1500);
        }, 2000);
    }

    function startSending() {
        if(!document.getElementById('aceito').checked) return alert("Aceite os termos.");
        nextStep('Sending');
        let width = 0;
        let bar = document.getElementById('barFinal');
        let text = document.getElementById('sendText');
        
        let interval = setInterval(() => {
            width += 0.5;
            bar.style.width = width + '%';
            if(width > 30) text.innerText = "Preparando remessa PIX...";
            if(width > 60) text.innerText = "Validando chave de destino...";
            if(width > 90) text.innerText = "Finalizando envio 99%...";
            
            if(width >= 99) {
                clearInterval(interval);
                setTimeout(() => { nextStep('Checkout'); }, 1000);
            }
        }, 30);
    }
</script>

</body>
</html>
