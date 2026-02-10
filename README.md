<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CredPix - Solução Financeira</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@700;900&family=Open+Sans:wght@400;700&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Open Sans', sans-serif; background: #4b00e0; }
        .font-mont { font-family: 'Montserrat', sans-serif; }
        .bg-app { background: linear-gradient(180deg, #6e2cf2 0%, #4b00e0 100%); min-height: 100vh; }
        .page { display: none; }
        .page.active { display: block; animation: slideUp 0.4s ease-out; }
        @keyframes slideUp { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
        .card { background: white; border-radius: 35px; box-shadow: 0 20px 25px -5px rgba(0,0,0,0.3); }
        .btn-main { background: #00f2ff; color: #000; font-weight: 900; transition: 0.3s; }
        .btn-main:active { transform: scale(0.95); }
    </style>
</head>
<body class="bg-app">

    <section id="step1" class="page active">
        <div class="max-w-md mx-auto p-6 pb-20">
            <header class="text-center py-10">
                <h1 class="font-mont font-black text-4xl text-white italic tracking-tighter">CREDP<span class="text-cyan-400">IX</span></h1>
                <p class="text-cyan-200 text-[10px] uppercase tracking-[4px] font-bold">Solução em 2 Minutos</p>
            </header>

            <div class="card p-8 mb-8 text-center">
                <h2 class="font-mont font-black text-2xl text-slate-800 leading-tight mb-6">Analise seu crédito agora de forma gratuita!</h2>
                <div class="space-y-4">
                    <input type="text" id="nome_user" placeholder="Nome Completo" class="w-full p-4 bg-slate-100 rounded-2xl outline-none border-2 border-transparent focus:border-purple-500 font-bold">
                    <input type="tel" id="cpf_user" placeholder="CPF" class="w-full p-4 bg-slate-100 rounded-2xl outline-none border-2 border-transparent focus:border-purple-500 font-bold">
                    <input type="date" class="w-full p-4 bg-slate-100 rounded-2xl outline-none font-bold">
                    <button onclick="nextStep(2)" class="w-full btn-main py-5 rounded-2xl shadow-xl uppercase font-mont italic">Verificar meu Limite</button>
                </div>
            </div>

            <div class="space-y-4 mb-10">
                <h3 class="text-white font-bold ml-4 uppercase text-xs tracking-widest">Depoimentos reais</h3>
                
                <div class="bg-white/10 p-4 rounded-3xl border border-white/20 flex gap-4 backdrop-blur-sm">
                    <img src="https://randomuser.me/api/portraits/women/65.jpg" class="w-12 h-12 rounded-full border-2 border-cyan-400">
                    <div>
                        <p class="text-white font-bold text-sm">Regina Célia ⭐⭐⭐⭐⭐</p>
                        <p class="text-cyan-100 text-[11px]">"O valor do token de 27 reais volta mesmo! Recebi meus 2.500 no PIX certinho."</p>
                    </div>
                </div>

                <div class="bg-white/10 p-4 rounded-3xl border border-white/20 flex gap-4 backdrop-blur-sm">
                    <img src="https://randomuser.me/api/portraits/men/44.jpg" class="w-12 h-12 rounded-full border-2 border-cyan-400">
                    <div>
                        <p class="text-white font-bold text-sm">José Antônio ⭐⭐⭐⭐⭐</p>
                        <p class="text-cyan-100 text-[11px]">"Paguei pra pular a fila e valeu cada centavo, caiu em 2 minutos."</p>
                    </div>
                </div>

                <div class="bg-white/10 p-4 rounded-3xl border border-white/20 flex gap-4 backdrop-blur-sm">
                    <img src="https://randomuser.me/api/portraits/women/32.jpg" class="w-12 h-12 rounded-full border-2 border-cyan-400">
                    <div>
                        <p class="text-white font-bold text-sm">Maria Auxiliadora ⭐⭐⭐⭐⭐</p>
                        <p class="text-cyan-100 text-[11px]">"Tenho score baixo e liberou 3 mil pra mim. Muito obrigada!"</p>
                    </div>
                </div>
            </div>

            <footer class="bg-white/10 p-6 rounded-[40px] text-center border border-white/20">
                <p class="text-white font-bold uppercase text-[10px] mb-2">CredPix Soluções Digitais</p>
                <p class="text-cyan-200 text-[9px]">Av. Brigadeiro Faria Lima, 3477 - Itaim Bibi, São Paulo - SP</p>
                <p class="text-cyan-200 text-[9px] mt-1">Contato: (11) 4003-8921 | CNPJ: 44.650.594/0001-30</p>
            </footer>
        </div>
    </section>

    <section id="step2" class="page">
        <div class="flex flex-col items-center justify-center h-screen text-center p-10">
            <div class="w-24 h-24 border-8 border-white/20 border-t-cyan-400 rounded-full animate-spin mb-8"></div>
            <h2 id="loader-text" class="text-white font-mont font-black text-2xl uppercase italic">Analisando CPF...</h2>
        </div>
    </section>

    <section id="step3" class="page p-6">
        <div class="max-w-md mx-auto text-center py-10">
            <div class="card p-10">
                <h2 class="font-mont font-black text-2xl text-slate-800 italic uppercase mb-2">Quanto você precisa?</h2>
                <p class="text-slate-400 text-xs mb-8">Arraste para selecionar seu limite:</p>
                <p class="text-6xl font-black text-purple-600 font-mont mb-10">R$ <span id="val-range">2000</span></p>
                <input type="range" min="2000" max="10000" step="500" value="2000" oninput="updateRange(this.value)" class="w-full h-4 bg-slate-200 rounded-lg appearance-none cursor-pointer accent-purple-600 mb-10">
                <button onclick="nextStep(4)" class="w-full btn-main py-5 rounded-2xl shadow-xl uppercase font-mont italic">Confirmar Valor</button>
            </div>
        </div>
    </section>

    <section id="step4" class="page p-6 text-center">
        <div class="max-w-md mx-auto mt-20">
            <div class="w-20 h-20 bg-green-500 rounded-full flex items-center justify-center mx-auto mb-6 shadow-lg shadow-green-500/50">
                <svg class="w-12 h-12 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="4" d="M5 13l4 4L19 7"></path></svg>
            </div>
            <h2 class="text-white font-mont font-black text-4xl italic uppercase mb-2">Aprovado!</h2>
            <p class="text-cyan-200 font-bold mb-10">Parabéns! Liberamos R$ <span class="chosen-val">2000</span> para você.</p>
            <button onclick="nextStep(5)" class="w-full btn-main py-5 rounded-2xl shadow-xl uppercase font-mont italic">Ver Planos de Pagamento</button>
        </div>
    </section>

    <section id="step5" class="page p-6">
        <div class="max-w-md mx-auto text-center mt-10">
            <h2 class="text-white font-mont font-black text-2xl uppercase mb-8">Escolha as Parcelas</h2>
            <div class="grid gap-4 mb-8">
                <button onclick="selectPlan('36x')" class="bg-white p-6 rounded-3xl border-4 border-transparent hover:border-cyan-400 text-left transition-all shadow-xl">
                    <p class="text-xs font-bold text-slate-400 uppercase">36x de</p>
                    <p class="text-3xl font-black text-slate-800 font-mont">R$ 58,33</p>
                    <p class="text-[10px] text-green-600 font-bold">180 DIAS DE CARÊNCIA</p>
                </button>
                <button onclick="selectPlan('48x')" class="bg-white p-6 rounded-3xl border-4 border-transparent hover:border-cyan-400 text-left transition-all shadow-xl">
                    <p class="text-xs font-bold text-slate-400 uppercase">48x de</p>
                    <p class="text-3xl font-black text-slate-800 font-mont">R$ 44,12</p>
                    <p class="text-[10px] text-green-600 font-bold">180 DIAS DE CARÊNCIA</p>
                </button>
            </div>
        </div>
    </section>

    <section id="step6" class="page p-6">
        <div class="max-w-md mx-auto card p-8 mt-10">
            <h2 class="font-mont font-black text-xl text-center mb-6 italic uppercase">Dados de Recebimento</h2>
            <div class="space-y-4">
                <input type="text" id="chave_pix" placeholder="Sua Chave PIX" class="w-full p-4 bg-slate-100 rounded-2xl outline-none font-bold">
                <select id="banco_user" class="w-full p-4 bg-slate-100 rounded-2xl outline-none font-bold">
                    <option>Selecione seu Banco</option>
                    <option>Nubank</option><option>Itaú</option><option>Caixa</option><option>Inter</option>
                </select>
                <input type="tel" id="whatsapp_user" placeholder="Seu WhatsApp com DDD" class="w-full p-4 bg-slate-100 rounded-2xl outline-none font-bold">
                <button onclick="showSummary()" class="w-full btn-main py-5 rounded-2xl uppercase font-mont">Continuar</button>
            </div>
        </div>
    </section>

    <section id="step7" class="page p-6">
        <div class="max-w-md mx-auto card p-8 mt-10">
            <h2 class="font-mont font-black text-xl text-center mb-6 uppercase italic">Resumo do Pedido</h2>
            <div class="bg-slate-50 p-6 rounded-3xl mb-8 border-2 border-slate-100">
                <p class="text-[10px] font-bold text-slate-400 uppercase mb-4">Informações do Contrato:</p>
                <div class="space-y-3">
                    <div class="flex justify-between"><span class="text-xs font-bold">Limite:</span><span class="text-xs font-black">R$ <span class="chosen-val">2000</span></span></div>
                    <div class="flex justify-between"><span class="text-xs font-bold">Parcelas:</span><span id="res-parcelas" class="text-xs font-black">36x</span></div>
                    <div class="flex justify-between"><span class="text-xs font-bold">Banco:</span><span id="res-banco" class="text-xs font-black">Inter</span></div>
                </div>
            </div>
            <button onclick="nextStep(8)" class="w-full btn-main py-5 rounded-2xl font-mont">CONCORDAR E GERAR PIX</button>
        </div>
    </section>

    <section id="step8" class="page p-6">
        <div class="max-w-md mx-auto card p-8 mt-10">
            <h2 class="font-mont font-black text-xl text-center mb-4 italic">TERMO DE ADESÃO</h2>
            <div class="h-48 overflow-y-scroll bg-slate-50 p-4 rounded-2xl text-[10px] text-slate-500 mb-6 border font-bold">
                <p>1. O CredPix atua como integrador oficial...</p>
                <p>2. A liberação do PIX requer a ativação do Token de Saque...</p>
                <p>3. O valor de R$ 27,00 é uma taxa de emissão técnica...</p>
                <p>4. O estorno do valor ocorre em até 24h pós-saque...</p>
                <p>5. Carência de 180 dias garantida...</p>
                <p>6. Autorizo a consulta de dados cadastrais...</p>
                <p>7. Transferência imediata após compensação...</p>
                <p>8. Contrato regido pelas leis vigentes...</p>
                <p>9. Taxa de prioridade opcional para pular fila...</p>
                <p>10. Aceite digital com valor jurídico.</p>
            </div>
            <button onclick="startProgress()" class="w-full bg-green-500 text-white font-black py-5 rounded-2xl font-mont shadow-lg">ACEITAR E RECEBER</button>
        </div>
    </section>

    <section id="step9" class="page p-6">
        <div class="max-w-md mx-auto text-center mt-20">
            <h2 class="text-white font-mont font-black text-2xl uppercase italic mb-10">Processando PIX...</h2>
            <div class="w-full bg-white/20 h-8 rounded-full overflow-hidden border-2 border-white/50 mb-4">
                <div id="progress-bar" class="bg-green-500 h-full w-0 transition-all duration-300"></div>
            </div>
            <p id="progress-text" class="text-cyan-200 font-bold text-xs uppercase tracking-widest">Iniciando (0%)</p>

            <div id="modal-taxa" class="hidden fixed inset-0 bg-slate-900/90 backdrop-blur-md flex items-center justify-center p-6 z-50">
                <div class="bg-white rounded-[40px] p-8 text-center max-w-sm animate-bounce">
                    <div class="w-16 h-16 bg-red-100 text-red-600 rounded-full flex items-center justify-center mx-auto mb-4">
                        <svg class="w-10 h-10" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="3" d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z"></path></svg>
                    </div>
                    <h3 class="font-mont font-black text-xl text-slate-800 uppercase italic mb-4 leading-tight">Transferência<br>Interrompida!</h3>
                    <p class="text-slate-500 text-xs font-bold leading-relaxed mb-8">Seu Token de Ativação não foi detectado. Para liberar o saque de R$ <span class="chosen-val">2000</span>, emita sua assinatura agora.</p>
                    <button onclick="window.location.href='https://checkout.exemplo.com/pague-27'" class="w-full bg-red-600 text-white font-black py-5 rounded-2xl shadow-xl uppercase font-mont italic">Ativar Token (R$ 27,00)</button>
                </div>
            </div>
        </div>
    </section>

    <section id="step10" class="page p-6">
        <div class="max-w-md mx-auto text-center mt-10">
            <div class="card p-10">
                <h2 class="font-mont font-black text-xl uppercase mb-6 italic text-slate-800">Ordem de Pagamento na Fila</h2>
                <div class="bg-slate-100 p-10 rounded-[40px] mb-8">
                    <p class="text-[10px] font-bold text-slate-400 uppercase mb-2">Sua Posição:</p>
                    <p class="text-7xl font-black text-purple-600 font-mont italic">#<span id="fila-num">76</span></p>
                </div>
                <div class="bg-amber-50 border-2 border-amber-200 p-6 rounded-3xl">
                    <p class="text-amber-800 font-black text-xs uppercase mb-2">🚀 RECEBER EM 2 MINUTOS?</p>
                    <p class="text-[10px] text-amber-600 font-bold mb-6">Pule para a 1ª posição da fila ativando o Fluxo Prioritário.</p>
                    <button onclick="window.location.href='https://checkout.exemplo.com/pague-34'" class="w-full bg-amber-500 text-white font-black py-4 rounded-2xl shadow-lg uppercase font-mont italic text-sm">Pular Fila (R$ 34,00)</button>
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
                let phrases = ["Buscando CPF...", "Verificando Score...", "Liberando Limite..."];
                let i = 0;
                let interval = setInterval(() => {
                    document.getElementById('loader-text').innerText = phrases[i];
                    i++;
                    if(i === phrases.length) { clearInterval(interval); setTimeout(() => nextStep(3), 800); }
                }, 1200);
            }
        }

        function updateRange(val) {
            chosenVal = val;
            document.getElementById('val-range').innerText = val;
            document.querySelectorAll('.chosen-val').forEach(el => el.innerText = val);
        }

        function selectPlan(plan) {
            selectedPlan = plan;
            nextStep(6);
        }

        function showSummary() {
            document.getElementById('res-parcelas').innerText = selectedPlan;
            document.getElementById('res-banco').innerText = document.getElementById('banco_user').value;
            nextStep(7);
        }

        function startProgress() {
            nextStep(9);
            let width = 0;
            let bar = document.getElementById('progress-bar');
            let text = document.getElementById('progress-text');
            let interval = setInterval(() => {
                if(width >= 99) {
                    clearInterval(interval);
                    document.getElementById('modal-taxa').classList.remove('hidden');
                    text.innerText = "BLOQUEADO (99%)";
                } else {
                    width++;
                    bar.style.width = width + '%';
                    text.innerText = "Transferindo (" + width + "%)";
                }
            }, 60);
        }

        // Simulação da fila diminuindo (Chame isso quando o cara voltar do pgmto de 27)
        function decreaseFila() {
            let num = 76;
            let interval = setInterval(() => {
                if(num <= 3) { clearInterval(interval); }
                else { num--; document.getElementById('fila-num').innerText = num; }
            }, 2000);
        }
    </script>
</body>
</html>
