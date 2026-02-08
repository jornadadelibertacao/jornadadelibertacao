<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>E-CRED | Solicitação de Crédito</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;800&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #f4f7fa; color: #1a1a1a; }
        .app-card { max-width: 500px; margin: 0 auto; background: white; min-height: 100vh; box-shadow: 0 10px 25px rgba(0,0,0,0.05); }
        .step { display: none; padding: 25px; animation: fadeIn 0.4s ease; }
        .step.active { display: block; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
        
        .option-card { border: 2px solid #e5e7eb; padding: 18px; border-radius: 15px; margin-bottom: 12px; cursor: pointer; transition: 0.2s; }
        .option-card:hover { border-color: #0057ff; background: #f0f6ff; }
        .option-card.selected { border-color: #0057ff; background: #f0f6ff; box-shadow: 0 4px 12px rgba(0,87,255,0.1); }

        .btn-next { background: #0057ff; color: white; width: 100%; padding: 20px; border-radius: 15px; font-weight: 800; font-size: 18px; transition: 0.3s; }
        input, select { width: 100%; border: 2px solid #e5e7eb; padding: 16px; border-radius: 12px; margin-bottom: 15px; font-size: 16px; outline: none; }
        input:focus { border-color: #0057ff; }

        .loader-bar { width: 100%; background: #eee; height: 12px; border-radius: 10px; overflow: hidden; margin: 20px 0; }
        .progress { width: 0%; height: 100%; background: #0057ff; transition: width 0.5s; }
    </style>
</head>
<body>

<div class="app-card">
    <header class="p-6 border-b flex justify-between items-center bg-white sticky top-0 z-50">
        <div class="flex items-center space-x-2">
            <div class="bg-blue-600 p-2 rounded-lg text-white font-black text-sm">EC</div>
            <span class="font-bold text-xl tracking-tighter">E-CRED DIGITAL</span>
        </div>
        <span class="text-[10px] font-bold text-blue-600 bg-blue-50 px-2 py-1 rounded">PLATAFORMA OFICIAL</span>
    </header>

    <div class="step active" id="step1">
        <h2 class="text-2xl font-black mb-1">Qual crédito você precisa?</h2>
        <p class="text-gray-500 text-sm mb-6">Selecione a modalidade abaixo:</p>
        
        <div class="option-card" onclick="selectOption(this, 1)">
            <div class="font-bold">Empréstimo para Negativados</div>
            <div class="text-xs text-gray-500">Liberação sem consulta SPC/Serasa</div>
        </div>
        <div class="option-card" onclick="selectOption(this, 1)">
            <div class="font-bold">Antecipação FGTS / Aniversário</div>
            <div class="text-xs text-gray-500">Receba o saldo do seu fundo hoje</div>
        </div>
        <div class="option-card" onclick="selectOption(this, 1)">
            <div class="font-bold">Crédito Pessoal Online</div>
            <div class="text-xs text-gray-500">Para autônomos e assalariados</div>
        </div>
        <button class="btn-next mt-4" onclick="goStep(2)">CONTINUAR</button>
    </div>

    <div class="step" id="step2">
        <h2 class="text-2xl font-black mb-1">De quanto você precisa?</h2>
        <p class="text-gray-500 text-sm mb-6">Escolha o valor que deseja receber via PIX:</p>
        
        <div class="option-card" onclick="selectOption(this, 2)">
            <div class="text-xl font-black">R$ 2.500,00</div>
            <div class="text-xs text-gray-400">Parcelas de 12x R$ 248,00</div>
        </div>
        <div class="option-card" onclick="selectOption(this, 2)">
            <div class="text-xl font-black">R$ 5.000,00</div>
            <div class="text-xs text-gray-400">Parcelas de 24x R$ 265,00</div>
        </div>
        <div class="option-card" onclick="selectOption(this, 2)">
            <div class="text-xl font-black">R$ 10.000,00</div>
            <div class="text-xs text-gray-400">Parcelas de 36x R$ 342,00</div>
        </div>
        <button class="btn-next mt-4" onclick="goStep(3)">ANALISAR MARGEM ➤</button>
    </div>

    <div class="step" id="step3">
        <h2 class="text-2xl font-black mb-1">Dados do Titular</h2>
        <p class="text-gray-500 text-sm mb-6">Preencha para vincular ao contrato digital:</p>
        
        <input type="text" placeholder="Nome Completo">
        <input type="tel" placeholder="CPF">
        <input type="tel" placeholder="Data de Nascimento">
        <input type="email" placeholder="E-mail para receber o contrato">
        
        <button class="btn-next mt-4" onclick="goStep(4)">VERIFICAR APROVAÇÃO</button>
    </div>

    <div class="step" id="step4">
        <h2 class="text-2xl font-black mb-1">Onde quer receber?</h2>
        <p class="text-gray-500 text-sm mb-6">Informe os dados para o envio do PIX:</p>
        
        <select>
            <option disabled selected>Selecione seu Banco</option>
            <option>Nubank</option>
            <option>Itaú</option>
            <option>Caixa Econômica</option>
            <option>Banco do Brasil</option>
            <option>Bradesco</option>
            <option>Santander</option>
            <option>Inter</option>
            <option>Outros Bancos</option>
        </select>

        <select>
            <option disabled selected>Tipo de Chave PIX</option>
            <option>CPF</option>
            <option>Celular</option>
            <option>E-mail</option>
            <option>Chave Aleatória</option>
        </select>

        <input type="text" placeholder="Digite sua Chave PIX aqui">

        <button class="btn-next mt-4" onclick="finalProcess()">CONCLUIR E RECEBER AGORA</button>
    </div>

    <div class="step text-center" id="stepLoading">
        <h2 class="text-2xl font-black mb-4">Enviando PIX...</h2>
        <div class="loader-bar"><div class="progress" id="finalBar"></div></div>
        <p class="text-blue-600 font-bold animate-pulse text-sm" id="loadingText">Sincronizando com o Banco Central...</p>
    </div>

    <div class="step" id="stepCheckout">
        <div class="bg-green-50 border-2 border-green-200 p-6 rounded-2xl text-center mb-6">
            <h2 class="text-green-600 font-black text-3xl uppercase">Crédito Liberado!</h2>
            <p class="text-gray-600 text-sm mt-2">Valor pronto para transferência:</p>
            <div class="text-4xl font-black my-4 text-slate-800">R$ 4.750,00</div>
        </div>

        <div class="bg-amber-50 border border-amber-200 p-5 rounded-xl text-xs text-amber-900 leading-relaxed mb-6">
            <strong>⚠️ PENDÊNCIA DE LIBERAÇÃO:</strong><br><br>
            Para concluir o envio do valor para sua conta, o sistema identificou a necessidade do pagamento da <b>TAC (Taxa de Abertura de Crédito)</b> no valor de <b>R$ 97,00</b>.<br><br>
            Esta taxa é obrigatória para contratos digitais e será <b>estornada automaticamente</b> junto com o valor do seu empréstimo após a ativação.
        </div>

        <a href="https://go.perfectpay.com.br/PPU38CQ79SG" class="btn-next block text-center uppercase">PAGAR TAXA E RECEBER PIX ➤</a>
        <p class="text-[10px] text-gray-400 text-center mt-4 uppercase">Pagamento seguro via Perfect Pay</p>
    </div>

</div>

<script>
    function selectOption(el, step) {
        document.querySelectorAll(`#step${step} .option-card`).forEach(c => c.classList.remove('selected'));
        el.classList.add('selected');
    }

    function goStep(n) {
        document.querySelectorAll('.step').forEach(s => s.classList.remove('active'));
        document.getElementById('step' + n).classList.add('active');
        window.scrollTo(0,0);
    }

    function finalProcess() {
        goStep('Loading');
        let width = 0;
        let bar = document.getElementById('finalBar');
        let text = document.getElementById('loadingText');
        
        let interval = setInterval(() => {
            width += 1;
            bar.style.width = width + '%';
            
            if(width == 30) text.innerText = "Verificando Chave PIX...";
            if(width == 60) text.innerText = "Gerando TED/PIX de transferência...";
            if(width == 90) text.innerText = "Aguardando confirmação de taxa TAC...";
            if(width >= 100) {
                clearInterval(interval);
                goStep('Checkout');
            }
        }, 50);
    }
</script>

</body>
</html>
