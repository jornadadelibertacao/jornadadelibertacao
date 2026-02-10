<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CredPix - Solução Financeira</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@700;900&family=Open+Sans:wght@400;700&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Open Sans', sans-serif; overflow-x: hidden; }
        .font-mont { font-family: 'Montserrat', sans-serif; }
        .bg-gradient-cred { background: linear-gradient(135deg, #6e2cf2 0%, #4b00e0 100%); }
        .page { display: none; min-height: 100vh; }
        .page.active { display: block; animation: fadeIn 0.5s ease-out; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
        input[type=range] { width: 100%; accent-color: #6e2cf2; }
    </style>
</head>
<body class="bg-slate-50">

    <section id="step1" class="page active">
        <nav class="bg-gradient-cred p-6 text-white text-center shadow-lg">
            <h1 class="font-mont font-black text-2xl tracking-tighter">CREDP<span class="text-cyan-400">IX</span></h1>
            <p class="text-[10px] uppercase tracking-[3px] opacity-80">A solução financeira em 2 minutos</p>
        </nav>
        
        <div class="max-w-md mx-auto p-6">
            <div class="text-center my-8">
                <h2 class="font-mont font-black text-3xl text-slate-800 leading-tight italic">Dinheiro na conta via PIX em minutos.</h2>
                <p class="text-slate-500 mt-2 font-bold">Liberação imediata para negativados e baixo score.</p>
            </div>

            <div class="bg-white rounded-[30px] p-8 shadow-2xl border border-slate-100">
                <div class="space-y-4">
                    <input type="text" placeholder="Nome Completo" class="w-full p-4 bg-slate-50 border-2 border-slate-100 rounded-2xl focus:border-purple-500 outline-none">
                    <input type="tel" placeholder="CPF" class="w-full p-4 bg-slate-50 border-2 border-slate-100 rounded-2xl focus:border-purple-500 outline-none">
                    <input type="date" class="w-full p-4 bg-slate-50 border-2 border-slate-100 rounded-2xl focus:border-purple-500 outline-none">
                    <button onclick="nextStep(2)" class="w-full bg-cyan-400 text-slate-900 font-black py-5 rounded-2xl shadow-lg uppercase font-mont transition-all active:scale-95">Consultar Limite Grátis</button>
                </div>
            </div>

            <div class="mt-10 space-y-4">
                <p class="font-bold text-slate-400 uppercase text-[10px] tracking-widest ml-2">Depoimentos Recentes</p>
                <div class="bg-white p-4 rounded-2xl shadow-sm border border-slate-100 flex gap-3">
                    <div class="w-10 h-10 bg-purple-100 rounded-full flex items-center justify-center font-bold text-purple-600">M</div>
                    <div>
                        <p class="text-xs font-bold">Maria Auxiliadora</p>
                        <p class="text-[11px] text-slate-500">"Paguei o token de ativação e em 5 minutos o dinheiro tava na conta. Me salvou!"</p>
                    </div>
                </div>
            </div>

            <footer class="mt-12 text-center text-[10px] text-slate-400 pb-10">
                <p class="font-bold uppercase mb-2 text-slate-500">CredPix Soluções Digitais LTDA</p>
                <p>Av. Brigadeiro Faria Lima, 3477 - Itaim Bibi, São Paulo - SP</p>
                <p>CNPJ: 44.650.594/0001-30 | Contato: (11) 4003-8921</p>
            </footer>
        </div>
    </section>

    <section id="step2" class="page bg-white text-center p-10">
        <div class="flex flex-col items-center justify-center h-screen">
            <div class="w-20 h-20 border-8 border-slate-100 border-t-purple-600 rounded-full animate-spin mb-8"></div>
            <h2 id="loader-text" class="font-mont font-black text-xl text-slate-800 uppercase italic">Analisando CPF...</h2>
            <p class="text-slate-400 text-sm mt-4">Aguarde, não feche esta página.</p>
        </div>
    </section>

    <section id="step3" class="page p-6">
        <div class="max-w-md mx-auto text-center mt-10">
            <h2 class="font-mont font-black text-2xl text-slate-800 italic uppercase">Limite Pré-Aprovado!</h2>
            <p class="text-slate-500 text-sm mb-10">Arraste para selecionar o valor desejado:</p>
            
            <div class="bg-white p-10 rounded-[40px] shadow-2xl border border-slate-100">
                <p class="text-[10px] font-bold text-purple-600 uppercase tracking-[3px] mb-2">Valor Escolhido:</p>
                <p class="text-5xl font-black text-slate-800 font-mont mb-8">R$ <span id="val-range">2.000</span></p>
                <input type="range" min="2000" max="10000" step="500" value="2000" oninput="updateRange(this.value)" class="mb-10">
                <button onclick="nextStep(4)" class="w-full bg-purple-600 text-white font-black py-5 rounded-2xl shadow-lg uppercase font-mont">Confirmar Valor</button>
            </div>
        </div>
    </section>

    <section id="step4" class="page p-6">
        <div class="max-w-md mx-auto text-center mt-10">
            <h2 class="font-mont font-black text-2xl text-slate-800 italic uppercase">Plano de Pagamento</h2>
            <p class="text-slate-500 text-sm mb-6 underline">Primeira parcela para daqui a 180 dias</p>
            
            <div class="grid gap-4">
                <button onclick="nextStep(5)" class="bg-white p-6 rounded-3xl border-2 border-slate-100 hover:border-purple-600 text-left transition-all">
                    <p class="text-xs font-bold text-slate-400">36x de</p>
                    <p class="text-2xl font-black text-slate-800 font-mont">R$ 58,33</p>
                </button>
                <button onclick="nextStep(5)" class="bg-white p-6 rounded-3xl border-2 border-slate-100 hover:border-purple-600 text-left transition-all">
                    <p class="text-xs font-bold text-slate-400">48x de</p>
                    <p class="text-2xl font-black text-slate-800 font-mont">R$ 44,12</p>
                </button>
                <button onclick="nextStep(5)" class="bg-white p-6 rounded-3xl border-2 border-slate-100 hover:border-purple-600 text-left transition-all">
                    <p class="text-xs font-bold text-slate-400">64x de</p>
                    <p class="text-2xl font-black text-slate-800 font-mont">R$ 32,80</p>
                </button>
            </div>
        </div>
    </section>

    <section id="step5" class="page p-6">
        <div class="max-w-md mx-auto bg-white p-8 rounded-[40px] shadow-2xl mt-10">
            <h2 class="font-mont font-black text-xl mb-6 text-center uppercase italic">Onde quer receber?</h2>
            <div class="space-y-4">
                <input type="text" placeholder="Chave PIX (CPF, Celular ou Email)" class="w-full p-4 bg-slate-50 border-2 border-slate-100 rounded-2xl outline-none">
                <select class="w-full p-4 bg-slate-50 border-2 border-slate-100 rounded-2xl outline-none">
                    <option>Selecione seu Banco</option>
                    <option>Nubank</option>
                    <option>Itaú</option>
                    <option>Bradesco</option>
                    <option>Caixa Econômica</option>
                    <option>Inter</option>
                    <option>Santander</option>
                </select>
                <input type="tel" placeholder="WhatsApp para envio do contrato" class="w-full p-4 bg-slate-50 border-2 border-slate-100 rounded-2xl outline-none">
                <button onclick="nextStep(6)" class="w-full bg-purple-600 text-white font-black py-5 rounded-2xl shadow-lg uppercase font-mont mt-4">Gerar Contrato Digital</button>
            </div>
        </div>
    </section>

    <section id="step6" class="page p-6">
        <div class="max-w-md mx-auto bg-white p-8 rounded-[40px] shadow-2xl mt-10">
            <h2 class="font-mont font-black text-xl mb-4 text-center">TERMO DE ADESÃO</h2>
            <div class="h-48 overflow-y-scroll bg-slate-50 p-4 rounded-2xl text-[10px] text-slate-500 leading-relaxed mb-6 border border-slate-100">
                <p>1. O CredPix atua como integrador de crédito bancário...</p>
                <p>2. A liberação do saldo depende da validação do Token de Transferência...</p>
                <p>3. A taxa de ativação de R$ 27,00 é obrigatória para emissão do contrato...</p>
                <p>4. O valor da taxa será estornado ao cliente no primeiro resgate...</p>
                <p>5. Prazo de carência de 180 dias para a primeira parcela...</p>
                <p>6. O cliente autoriza a consulta ao Score de crédito...</p>
                <p>7. A transferência via PIX é realizada de forma imediata após a compensação da taxa...</p>
                <p>8. Cancelamentos podem ser feitos em até 7 dias...</p>
                <p>9. Fica eleito o foro de São Paulo para dirimir dúvidas...</p>
                <p>10. Ao clicar em aceito, você concorda com a emissão do Token de Saque.</p>
            </div>
            <button onclick="startProgress()" class="w-full bg-green-500 text-white font-black py-5 rounded-2xl shadow-lg uppercase font-mont">Li e Aceito os Termos</button>
        </div>
    </section>

    <section id="step7" class="page p-6">
        <div class="max-w-md mx-auto text-center mt-20">
            <h2 class="font-mont font-black text-xl text-slate-800 mb-8 uppercase italic">Enviando seu PIX...</h2>
            <div class="w-full bg-slate-200 h-8 rounded-full overflow-hidden shadow-inner border-2 border-white">
                <div id="progress-bar" class="bg-green-500 h-full w-0 transition-all duration-300"></div>
            </div>
            <p id="progress-text" class="text-xs font-bold text-slate-400 mt-4 uppercase tracking-[3px]">Iniciando transferência (0%)</p>
            
            <div id="error-box" class="hidden mt-10 bg-red-50 border-2 border-red-200 p-6 rounded-[30px] animate-bounce">
                <p class="text-red-600 font-black font-mont text-lg uppercase italic mb-2">Transferência Bloqueada!</p>
                <p class="text-red-500 text-xs font-bold leading-relaxed mb-6">Identificamos que seu Token de Ativação ainda não foi emitido. Para concluir o PIX de R$ <span class="chosen-val">2.000</span>, realize o pagamento da taxa de emissão (R$ 27,00).</p>
                <button onclick="window.location.href='https://checkout.exemplo.com/pague-27'" class="w-full bg-red-600 text-white font-black py-4 rounded-2xl uppercase text-sm shadow-lg">Ativar Token e Receber PIX</button>
            </div>
        </div>
    </section>

    <section id="step8" class="page p-6">
        <div class="max-w-md mx-auto text-center mt-10">
            <div class="bg-blue-600 text-white p-6 rounded-[40px] shadow-2xl mb-6">
                <h2 class="font-mont font-black text-xl uppercase italic mb-2 font-bold">Token Ativado!</h2>
                <p class="text-[10px] opacity-80 font-bold tracking-widest uppercase">Processando Ordem de Pagamento</p>
            </div>
            
            <div class="bg-white p-8 rounded-[40px] shadow-xl border border-slate-100">
                <p class="text-slate-400 text-[10px] font-bold uppercase mb-4 tracking-widest">Sua posição na fila de liberação:</p>
                <p class="text-7xl font-black text-slate-800 font-mont mb-4 italic">#<span id="fila-num">76</span></p>
                <p class="text-xs text-slate-500 mb-8">Devido à alta demanda, seu PIX será enviado em até 4 horas.</p>
                
                <div class="bg-amber-50 border-2 border-amber-100 p-6 rounded-3xl mb-6">
                    <p class="text-amber-700 font-black text-xs uppercase mb-2">🚀 Quer pular para os 20 primeiros?</p>
                    <p class="text-[10px] text-amber-600 font-bold mb-4 italic">Ative o Fluxo Prioritário (R$ 34,00) e receba seu PIX em menos de 2 minutos.</p>
                    <button onclick="window.location.href='https://checkout.exemplo.com/pague-34'" class="w-full bg-amber-500 text-white font-black py-4 rounded-2xl uppercase text-[11px] shadow-md">Pular Fila Agora</button>
                </div>
            </div>
        </div>
    </section>

    <script>
        function nextStep(step) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById('step' + step).classList.add('active');
            
            if(step === 2) {
                const phrases = ["Verificando Score...", "Consultando Receita...", "Liberando Ofertas..."];
                let i = 0;
                const interval = setInterval(() => {
                    document.getElementById('loader-text').innerText = phrases[i];
                    i++;
                    if(i === phrases.length) {
                        clearInterval(interval);
                        setTimeout(() => nextStep(3), 1000);
                    }
                }, 1500);
            }
        }

        function updateRange(val) {
            document.getElementById('val-range').innerText = val;
            document.querySelectorAll('.chosen-val').forEach(el => el.innerText = val);
        }

        function startProgress() {
            nextStep(7);
            let width = 0;
            const bar = document.getElementById('progress-bar');
            const text = document.getElementById('progress-text');
            const interval = setInterval(() => {
                if (width >= 99) {
                    clearInterval(interval);
                    document.getElementById('error-box').classList.remove('hidden');
                    text.innerText = "ERRO NA TRANSFERÊNCIA (99%)";
                    text.classList.add('text-red-500');
                } else {
                    width++;
                    bar.style.width = width + '%';
                    text.innerText = "Enviando PIX (" + width + "%)";
                }
            }, 50);
        }

        // Simulação da Fila (Para você testar a lógica da Seção 8)
        function startFila() {
            let num = 76;
            const interval = setInterval(() => {
                if(num <= 3) {
                    clearInterval(interval);
                } else {
                    num--;
                    document.getElementById('fila-num').innerText = num;
                }
            }, 3000); // Diminui a cada 3 segundos
        }
    </script>
</body>
</html>
