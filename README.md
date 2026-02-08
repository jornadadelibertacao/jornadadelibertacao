<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>E-CRED | Crédito Digital Instantâneo</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;800&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #f9fafb; color: #111; }
        .container-app { max-width: 480px; margin: 0 auto; background: white; min-height: 100vh; box-shadow: 0 0 40px rgba(0,0,0,0.03); }
        .step { display: none; padding: 20px; animation: slideUp 0.4s ease; }
        .step.active { display: block; }
        @keyframes slideUp { from { opacity: 0; transform: translateY(15px); } to { opacity: 1; transform: translateY(0); } }
        
        .card-loan { border: 1.5px solid #e5e7eb; border-radius: 16px; padding: 20px; margin-bottom: 15px; cursor: pointer; transition: 0.2s; }
        .card-loan:hover { border-color: #2563eb; background: #f8faff; }
        .card-loan.selected { border-color: #2563eb; background: #f0f6ff; border-width: 2px; }

        .btn-main { background: #2563eb; color: white; width: 100%; padding: 18px; border-radius: 12px; font-weight: 700; font-size: 16px; }
        input, select { width: 100%; border: 1.5px solid #d1d5db; padding: 14px; border-radius: 10px; margin-bottom: 12px; font-size: 15px; }
        
        .progress-container { width: 100%; background: #eee; height: 8px; border-radius: 10px; overflow: hidden; margin: 20px 0; }
        .progress-bar { width: 0%; height: 100%; background: #2563eb; transition: width 0.3s; }
        
        .terms-box { background: #f3f4f6; border: 1px solid #e5e7eb; padding: 15px; border-radius: 10px; height: 120px; overflow-y: scroll; font-size: 11px; color: #666; line-height: 1.5; margin-bottom: 15px; }
    </style>
</head>
<body>

<div class="container-app">
    <header class="p-5 border-b flex items-center justify-between sticky top-0 bg-white z-50">
        <div class="flex items-center space-x-2">
            <img src="https://cdn-icons-png.flaticon.com/512/584/584067.png" width="28">
            <span class="font-extrabold text-xl tracking-tight text-blue-600">Ecred</span>
        </div>
        <div class="flex items-center space-x-1">
            <span class="w-2 h-2 bg-green-500 rounded-full animate-pulse"></span>
            <span class="text-[10px] font-bold text-gray-400">SISTEMA ATIVO</span>
        </div>
    </header>

    <div class="step active" id="step1">
        <div class="text-center mb-8">
            <h1 class="text-2xl font-extrabold mb-2">Empréstimo online, receba hoje via <span class="text-blue-600">PIX!</span></h1>
            <p class="text-gray-500 text-sm">Mesmo com <span class="bg-yellow-100 px-1">nome sujo</span> ou <span class="bg-yellow-100 px-1">score baixo</span>.</p>
        </div>

        <h2 class="font-bold text-gray-400 text-xs uppercase tracking-widest mb-4 text-center">Modalidades</h2>
        
        <div class="card-loan" onclick="selectLoan(this, 'Para Negativados', 'R$ 18.000', 'R$ 180,00')">
            <div class="bg-green-100 text-green-700 text-[10px] font-bold px-2 py-0.5 rounded w-fit mb-2">MAIS PROCURADO</div>
            <h3 class="font-bold text-lg">Para Negativados</h3>
            <p class="text-gray-400 text-xs mb-3">CPF com restrições no Serasa/SPC</p>
            <div class="text-blue-600 font-extrabold text-2xl">R$ 18.000</div>
            <div class="text-[10px] text-gray-400 mt-1">1ª parcela em 90 dias</div>
        </div>

        <div class="card-loan" onclick="selectLoan(this, 'Pessoa Física', 'R$ 27.000', 'R$ 270,00')">
            <h3 class="font-bold text-lg">Pessoa Física</h3>
            <p class="text-gray-400 text-xs mb-3">CPF sem restrições, tire planos do papel</p>
            <div class="text-blue-600 font-extrabold text-2xl">R$ 27.000</div>
            <div class="text-[10px] text-gray-400 mt-1">1ª parcela em 90 dias</div>
        </div>

        <button class="btn-main mt-4" onclick="nextStep(2)">COMEÇAR SIMULAÇÃO</button>
    </div>

    <div class="step" id="step2">
        <h2 class="text-xl font-bold mb-1">Dados Cadastrais</h2>
        <p class="text-gray-500 text-sm mb-6">Preencha corretamente para análise imediata.</p>
        
        <input type="text" id="nome" placeholder="Nome Completo">
        <input type="tel" id="cpf" placeholder="CPF">
        <input type="tel" placeholder="Data de Nascimento">
        <input type="tel" placeholder="Telefone (WhatsApp)">
        
        <button class="btn-main mt-4" onclick="nextStep(3)">CONTINUAR ➤</button>
    </div>

    <div class="step" id="step3">
        <h2 class="text-xl font-bold mb-1">Recebimento via PIX</h2>
        <p class="text-gray-500 text-sm mb-6">Onde você deseja receber o valor?</p>
        
        <label class="text-xs font-bold text-gray-400 uppercase">Instituição Bancária</label>
        <select>
            <option>Nubank</option>
            <option>Itaú Unibanco</option>
            <option>Caixa Econômica Federal</option>
            <option>Banco do Brasil</option>
            <option>Bradesco</option>
            <option>Santander</option>
            <option>Inter</option>
            <option>C6 Bank</option>
            <option>Outros Bancos</option>
        </select>

        <label class="text-xs font-bold text-gray-400 uppercase">Chave PIX</label>
        <input type="text" placeholder="Digite sua chave PIX">
        
        <div class="bg-blue-50 p-4 rounded-xl border border-blue-100 mb-6">
            <p class="text-blue-800 text-xs font-bold">PLANO DE PAGAMENTO:</p>
            <p class="text-blue-600 text-lg font-black" id="resumoPlano">100x de R$ 180,00</p>
            <p class="text-[10px] text-blue-400">Juros fixos de 1.2% a.m (Incluso)</p>
        </div>

        <button class="btn-main" onclick="nextStep(4)">VER TERMOS DE ADESÃO</button>
    </div>

    <div class="step" id="step4">
        <h2 class="text-xl font-bold mb-4">Contrato de Crédito</h2>
        <div class="terms-box">
            CONTRATO DE ADESÃO AO CRÉDITO DIGITAL E-CRED 2026. <br><br>
            1. OBJETO: Liberação de crédito pessoal imediato via PIX. <br>
            2. JUROS: Taxa fixa de 1.2% ao mês aplicada sobre o saldo devedor. <br>
            3. LIBERAÇÃO: O crédito será enviado após a validação da Chave de Segurança de Envio. <br>
            4. ESTORNO: Taxas de liberação são 100% reembolsáveis no ato do depósito. <br>
            5. PAGAMENTO: As parcelas serão enviadas mensalmente via boleto ou débito automático.
        </div>
        
        <div class="flex items-start space-x-2 mb-6">
            <input type="checkbox" id="checkTerms" class="w-5 h-5 mt-1">
            <label for="checkTerms" class="text-xs text-gray-600 font-semibold">Li e estou de acordo com os termos de liberação e as parcelas baixas.</label>
        </div>

        <button class="btn-main" onclick="startSending()">CONCORDAR E RECEBER PIX ➤</button>
    </div>

    <div class="step text-center" id="stepLoading">
        <h2 class="text-2xl font-black mb-2">Processando Envio...</h2>
        <p class="text-gray-400 text-xs">Não feche esta página</p>
        <div class="progress-container"><div class="progress-bar" id="barFinal"></div></div>
        <p class="text-blue-600 font-bold text-sm animate-pulse" id="statusText">Estabelecendo conexão com o Banco Central...</p>
    </div>

    <div class="step" id="stepFinal">
        <div class="bg-blue-600 text-white p-6 rounded-2xl text-center mb-6">
            <h2 class="font-black text-3xl uppercase italic tracking-tighter">Atenção!</h2>
            <div class="w-16 h-1 bg-white mx-auto my-3 opacity-30"></div>
            <p class="text-sm opacity-90">O envio do seu PIX de <span class="font-bold" id="finalValor">R$ 18.000</span> foi interrompido.</p>
        </div>

        <div class="bg-white border-2 border-dashed border-gray-200 p-5 rounded-xl text-center mb-6">
            <p class="text-gray-500 text-xs font-bold uppercase mb-2">Motivo da Retenção:</p>
            <p class="text-red-500 font-bold text-sm leading-tight">NECESSÁRIA ATIVAÇÃO DA TAXA DE ENVIO (T.E.D)</p>
        </div>

        <div class="text-gray-600 text-xs leading-relaxed mb-8">
            Para que o sistema conclua a transferência dos seus <b>R$ 18.000</b> hoje, é necessário efetuar o pagamento da taxa de envio de <b>R$ 97,00</b>. <br><br>
            <span class="text-black font-bold">⚠️ IMPORTANTE:</span> Este valor de R$ 97 é <span class="text-green-600 uppercase font-black">estornado automaticamente</span> para sua conta junto com o valor do empréstimo.
        </div>

        <a href="https://go.perfectpay.com.br/PPU38CQ79SG" class="btn-main block text-center shadow-xl shadow-blue-200">
            PAGAR TAXA E LIBERAR PIX AGORA
        </a>
    </div>

    <footer class="p-8 text-center border-t mt-10">
        <p class="text-[10px] text-gray-400 uppercase font-bold tracking-widest">© 2026 Ecred LTDA - Todos os direitos reservados</p>
        <p class="text-[9px] text-gray-300 mt-2">CNPJ 41.906.644/0001-20</p>
    </footer>
</div>

<script>
    let selectedAmount = "R$ 18.000";
    let selectedInstallment = "100x de R$ 180,00";

    function selectLoan(el, title, amount, installment) {
        document.querySelectorAll('.card-loan').forEach(c => c.classList.remove('selected'));
        el.classList.add('selected');
        selectedAmount = amount;
        selectedInstallment = `100x de ${installment}`;
        document.getElementById('resumoPlano').innerText = selectedInstallment;
        document.getElementById('finalValor').innerText = selectedAmount;
    }

    function nextStep(n) {
        if(n === 4 && !document.getElementById('nome').value) return alert("Preencha seus dados.");
        document.querySelectorAll('.step').forEach(s => s.classList.remove('active'));
        document.getElementById('step' + n).classList.add('active');
        window.scrollTo(0,0);
    }

    function startSending() {
        if(!document.getElementById('checkTerms').checked) return alert("Você precisa aceitar os termos.");
        
        nextStep('Loading');
        let width = 0;
        let bar = document.getElementById('barFinal');
        let status = document.getElementById('statusText');
        
        let interval = setInterval(() => {
            width += 0.5;
            bar.style.width = width + '%';
            
            if(width > 20) status.innerText = "Preparando remessa PIX...";
            if(width > 50) status.innerText = "Autenticando chave de segurança...";
            if(width > 85) status.innerText = "ERRO: Taxa de Envio não identificada...";
            
            if(width >= 99) {
                clearInterval(interval);
                setTimeout(() => { nextStep('Final'); }, 800);
            }
        }, 30);
    }
</script>

</body>
</html>
