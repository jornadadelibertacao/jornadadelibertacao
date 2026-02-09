<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CREDPIX - Crédito Facilitado</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background: #f8fafc; overflow-x: hidden; }
        .step { display: none; }
        .step.active { display: block; animation: fadeIn 0.4s ease-out; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
        .btn-green { background: #00d35d; color: white; font-weight: 800; border-radius: 12px; padding: 20px; width: 100%; transition: 0.3s; box-shadow: 0 10px 15px -3px rgba(0, 211, 93, 0.4); }
        .card-shadow { box-shadow: 0 20px 25px -5px rgb(0 0 0 / 0.1), 0 8px 10px -6px rgb(0 0 0 / 0.1); }
        .no-scrollbar::-webkit-scrollbar { display: none; }
    </style>
</head>
<body>

    <header class="bg-white border-b p-4 sticky top-0 z-50">
        <div class="max-w-md mx-auto flex justify-between items-center">
            <div class="text-2xl font-black text-[#004a8d]">CRED<span class="text-[#00d35d]">PIX</span></div>
            <div class="flex items-center gap-2">
                <span class="w-2 h-2 bg-green-500 rounded-full animate-pulse"></span>
                <span class="text-[10px] font-bold text-gray-400">SISTEMA ATIVO</span>
            </div>
        </div>
    </header>

    <div class="max-w-md mx-auto pb-10 px-4">

        <div id="step1" class="step active py-6">
            <div class="text-center mb-8">
                <h1 class="text-3xl font-black text-gray-900 leading-tight">Receba seu crédito agora via <span class="text-[#00d35d]">PIX.</span></h1>
                <p class="text-gray-500 mt-2">Dinheiro na conta para negativados e CLT.</p>
            </div>

            <div class="bg-white rounded-3xl p-5 card-shadow mb-8 border-2 border-green-50">
                <h2 class="font-bold text-gray-800 mb-5 text-center">Selecione o valor desejado:</h2>
                <div class="space-y-4">
                    <button onclick="nextStep(2)" class="w-full p-5 border-2 border-gray-100 rounded-2xl flex justify-between items-center hover:border-green-400 transition">
                        <span class="font-extrabold text-lg text-gray-800">R$ 2.500</span>
                        <span class="text-[9px] font-bold text-green-500 bg-green-50 px-2 py-1 rounded">LIBERAÇÃO IMEDIATA</span>
                    </button>
                    <button onclick="nextStep(2)" class="w-full p-5 border-2 border-gray-100 rounded-2xl flex justify-between items-center hover:border-green-400 transition">
                        <span class="font-extrabold text-lg text-gray-800">R$ 5.000</span>
                        <span class="text-[9px] font-bold text-green-500 bg-green-50 px-2 py-1 rounded">MAIS SOLICITADO</span>
                    </button>
                    <button onclick="nextStep(2)" class="w-full p-5 border-2 border-gray-100 rounded-2xl flex justify-between items-center hover:border-green-400 transition">
                        <span class="font-extrabold text-lg text-gray-800">R$ 15.000</span>
                        <span class="text-[9px] font-bold text-gray-400 bg-gray-50 px-2 py-1 rounded">ANÁLISE DE SCORE</span>
                    </button>
                    <button onclick="nextStep(2)" class="w-full p-5 border-2 border-gray-100 rounded-2xl flex justify-between items-center hover:border-green-400 transition text-left">
                        <span class="font-extrabold text-lg text-gray-800">R$ 30.000</span>
                        <div class="text-right">
                            <span class="block text-[9px] font-bold text-gray-500 uppercase">Aposentado/Pensionista</span>
                            <span class="block text-[9px] font-bold text-gray-400">OU TRABALHADOR CLT</span>
                        </div>
                    </button>
                </div>
            </div>

            <div class="mb-8 overflow-hidden">
                <h3 class="font-bold text-gray-700 mb-4 px-2">Depoimentos Recentes:</h3>
                <div class="flex gap-4 overflow-x-auto pb-4 no-scrollbar px-2">
                    <div class="min-w-[280px] bg-white p-4 rounded-2xl shadow-sm border border-gray-100">
                        <div class="flex gap-1 text-yellow-400 mb-2 text-xs">★★★★★</div>
                        <p class="text-[13px] text-gray-600 italic">"Consegui limpar minhas dívidas. Paguei a taxa TAC e o dinheiro caiu em 10 minutos."</p>
                        <p class="text-[10px] font-bold mt-2 text-gray-400">Marcos Oliveira, SP</p>
                    </div>
                    <div class="min-w-[280px] bg-white p-4 rounded-2xl shadow-sm border border-gray-100">
                        <div class="flex gap-1 text-yellow-400 mb-2 text-xs">★★★★★</div>
                        <p class="text-[13px] text-gray-600 italic">"O melhor é que a primeira parcela ficou pra daqui a 6 meses. Deu tempo de me organizar!"</p>
                        <p class="text-[10px] font-bold mt-2 text-gray-400">Julia Mendes, RJ</p>
                    </div>
                    <div class="min-w-[280px] bg-white p-4 rounded-2xl shadow-sm border border-gray-100">
                        <div class="flex gap-1 text-yellow-400 mb-2 text-xs">★★★★★</div>
                        <p class="text-[13px] text-gray-600 italic">"Sou autônomo e nenhum banco aprovava. Aqui foi rápido e prático."</p>
                        <p class="text-[10px] font-bold mt-2 text-gray-400">Pedro Santos, MG</p>
                    </div>
                    <div class="min-w-[280px] bg-white p-4 rounded-2xl shadow-sm border border-gray-100">
                        <div class="flex gap-1 text-yellow-400 mb-2 text-xs">★★★★★</div>
                        <p class="text-[13px] text-gray-600 italic">"Atendimento top no suporte e dinheiro na conta sem burocracia."</p>
                        <p class="text-[10px] font-bold mt-2 text-gray-400">Carla Farias, RS</p>
                    </div>
                    <div class="min-w-[280px] bg-white p-4 rounded-2xl shadow-sm border border-gray-100">
                        <div class="flex gap-1 text-yellow-400 mb-2 text-xs">★★★★★</div>
                        <p class="text-[13px] text-gray-600 italic">"Achei que era mentira, mas a CREDPIX realmente cumpre o que promete."</p>
                        <p class="text-[10px] font-bold mt-2 text-gray-400">Luiz Henrique, GO</p>
                    </div>
                </div>
            </div>

            <button onclick="nextStep(2)" class="btn-green uppercase">COMEÇAR MINHA ANÁLISE</button>
        </div>

        <div id="step2" class="step py-6">
            <h2 class="text-2xl font-black mb-6 leading-tight">Preencha seus dados para <br>receber o contrato:</h2>
            <div class="space-y-4">
                <input type="text" placeholder="Nome Completo" class="w-full p-4 bg-white border-2 border-gray-100 rounded-xl outline-none focus:border-green-500">
                <input type="tel" id="cpf" placeholder="CPF" oninput="mask(this, '###.###.###-##')" class="w-full p-4 bg-white border-2 border-gray-100 rounded-xl outline-none focus:border-green-500">
                <input type="tel" id="zap" placeholder="WhatsApp (DDD + Número)" oninput="mask(this, '(##) #####-####')" class="w-full p-4 bg-white border-2 border-gray-100 rounded-xl outline-none focus:border-green-500">
                <p class="text-[10px] text-gray-400 px-1 italic">* Enviaremos a cópia do seu contrato via WhatsApp após a aprovação.</p>
            </div>
            <button onclick="startAnalysis()" class="btn-green mt-8 uppercase">CONSULTAR LIBERAÇÃO</button>
        </div>

        <div id="step3" class="step p-10 text-center">
            <div class="w-20 h-20 border-4 border-gray-100 border-t-[#00d35d] rounded-full animate-spin mx-auto mb-8"></div>
            <h2 class="text-xl font-black mb-2" id="analysis-title">Iniciando análise...</h2>
            <p class="text-xs text-gray-400 uppercase tracking-tighter" id="analysis-msg">Conectando ao banco de dados...</p>
            <div class="w-full bg-gray-100 h-2 rounded-full mt-10 overflow-hidden">
                <div id="analysis-bar" class="bg-[#00d35d] h-full transition-all duration-500" style="width: 0%"></div>
            </div>
        </div>

        <div id="step4" class="step py-6 text-center">
            <div class="bg-white border-2 border-green-500 p-8 rounded-[40px] mb-8 card-shadow">
                <div class="w-12 h-12 bg-green-500 text-white rounded-full flex items-center justify-center mx-auto mb-4 font-bold text-xl">✓</div>
                <h3 class="text-green-500 font-bold uppercase text-xs">Crédito Pré-Aprovado</h3>
                <div class="text-4xl font-black text-gray-900 mt-2">R$ 5.000,00</div>
            </div>

            <p class="font-bold text-gray-700 mb-6">Em quantas vezes deseja pagar?</p>
            <div class="space-y-4 text-left">
                <div onclick="selectP(this)" class="p-5 border-2 border-green-500 bg-green-50 rounded-2xl flex justify-between items-center cursor-pointer">
                    <div>
                        <div class="font-extrabold text-lg text-gray-800">24x de R$ 284,30</div>
                        <div class="text-[10px] text-green-600 font-bold uppercase mt-1">Primeira parcela só daqui a 180 dias</div>
                    </div>
                    <span class="w-5 h-5 border-4 border-green-500 rounded-full"></span>
                </div>
                <div onclick="selectP(this)" class="p-5 border-2 border-gray-100 bg-white rounded-2xl flex justify-between items-center cursor-pointer">
                    <div>
                        <div class="font-extrabold text-lg text-gray-800">48x de R$ 162,15</div>
                        <div class="text-[10px] text-gray-400 font-bold uppercase mt-1">Primeira parcela só daqui a 180 dias</div>
                    </div>
                </div>
            </div>
            <button onclick="nextStep(5)" class="btn-green mt-8 uppercase">PRÓXIMO PASSO</button>
        </div>

        <div id="step5" class="step py-6">
            <h2 class="text-2xl font-black mb-4">Termos e Condições</h2>
            <div class="bg-gray-100 p-4 rounded-2xl text-[11px] text-gray-500 h-60 overflow-y-auto mb-6 leading-relaxed">
                <p class="mb-3"><strong>1. DO PRAZO:</strong> O contratante terá um prazo de 180 dias (6 meses) de carência total. O primeiro pagamento só ocorrerá após este período.</p>
                <p class="mb-3"><strong>2. DA TARIFA TAC:</strong> Para a liberação de valores via PIX Prioritário, é obrigatória a quitação da Tarifa de Abertura de Crédito (TAC), conforme normas de segurança para prevenção de fraudes.</p>
                <p><strong>3. DO ESTORNO:</strong> O valor da tarifa TAC será 100% reembolsado, sendo depositado junto com o valor do empréstimo na conta do cliente.</p>
            </div>
            <label class="flex items-center gap-3 mb-8 cursor-pointer">
                <input type="checkbox" id="checkT" class="w-6 h-6 accent-[#00d35d]">
                <span class="text-sm font-bold text-gray-700">Li e aceito as condições de pagamento.</span>
            </label>
            <button onclick="validarT()" class="btn-green uppercase">ACEITAR E RECEBER</button>
        </div>

        <div id="step6" class="step py-6">
            <h2 class="text-2xl font-black mb-6">Onde quer receber o PIX?</h2>
            <div class="space-y-4">
                <select class="w-full p-4 bg-white border-2 border-gray-100 rounded-xl outline-none focus:border-green-500">
                    <option>Selecione seu Banco...</option>
                    <option>Nubank</option><option>Itaú</option><option>Caixa</option><option>Inter</option><option>C6 Bank</option>
                </select>
                <input type="text" placeholder="Sua Chave PIX" class="w-full p-4 bg-white border-2 border-gray-100 rounded-xl outline-none focus:border-green-500">
            </div>
            <button onclick="startFinal()" class="btn-green mt-8 uppercase">SOLICITAR PIX AGORA</button>
        </div>

        <div id="step7" class="step py-6 text-center">
            <div class="text-6xl font-black mb-6" id="final-pct">0%</div>
            <div class="w-full bg-gray-100 h-4 rounded-full overflow-hidden mb-6">
                <div id="final-bar" class="bg-[#00d35d] h-full" style="width: 0%"></div>
            </div>
            <p class="text-gray-400 font-bold uppercase tracking-widest text-xs" id="final-status">Preparando envio prioritário...</p>

            <div id="error-card" class="hidden mt-10 bg-white rounded-[32px] p-8 border-2 border-red-500 card-shadow">
                <div class="text-red-500 text-6xl mb-4">⚠️</div>
                <h3 class="text-2xl font-black text-gray-900 mb-3 uppercase">Envio Retido</h3>
                <p class="text-gray-500 text-sm leading-relaxed mb-6">O Banco Central identificou que sua conta necessita da validação da <b>Tarifa TAC</b> para liberar o depósito de R$ 5.000,00.</p>
                <div class="bg-red-50 text-red-600 p-5 rounded-2xl mb-8 font-black text-3xl">R$ 97,00</div>
                <button onclick="window.location.href='SEU_LINK_AQUI'" class="btn-green bg-red-600 shadow-none hover:bg-red-700">PAGAR TARIFA E RECEBER AGORA</button>
            </div>
        </div>

    </div>

    <script>
        function nextStep(n) {
            document.querySelectorAll('.step').forEach(s => s.classList.remove('active'));
            document.getElementById('step' + n).classList.add('active');
            window.scrollTo(0,0);
        }

        function mask(i, m) {
            let v = i.value.replace(/\D/g, "");
            let k = 0; let res = "";
            for (let char of m) {
                if (char === "#") { res += v[k] || ""; k++; } 
                else { if (v[k]) res += char; }
            }
            i.value = res;
        }

        function startAnalysis() {
            nextStep(3);
            let bar = document.getElementById('analysis-bar');
            let msg = document.getElementById('analysis-msg');
            let title = document.getElementById('analysis-title');
            let p = 0;
            let t = setInterval(() => {
                p += 1;
                bar.style.width = p + "%";
                if(p == 25) { title.innerText = "Consultando Bureau..."; msg.innerText = "Verificando restrições no CPF..."; }
                if(p == 55) { title.innerText = "Calculando Margem..."; msg.innerText = "Ajustando limites de parcelamento..."; }
                if(p == 85) { title.innerText = "Concluindo Análise..."; msg.innerText = "Gerando contrato digital..."; }
                if(p >= 100) { clearInterval(t); nextStep(4); }
            }, 120); // Análise lenta e profissional
        }

        function selectP(el) {
            document.querySelectorAll('#step4 .border-green-500').forEach(d => {
                d.classList.replace('border-green-500', 'border-gray-100');
                d.classList.replace('bg-green-50', 'bg-white');
            });
            el.classList.replace('border-gray-100', 'border-green-500');
            el.classList.replace('bg-white', 'bg-green-50');
        }

        function validarT() {
            if(document.getElementById('checkT').checked) nextStep(6);
            else alert("Você precisa concordar com os termos para continuar.");
        }

        function startFinal() {
            nextStep(7);
            let bar = document.getElementById('final-bar');
            let pct = document.getElementById('final-pct');
            let st = document.getElementById('final-status');
            let p = 0;
            let t = setInterval(() => {
                p++;
                if(p <= 99) { bar.style.width = p + "%"; pct.innerText = p + "%"; }
                if(p == 40) st.innerText = "Sincronizando com o Banco Central...";
                if(p == 80) st.innerText = "Verificando Tarifa TAC...";
                if(p == 99) {
                    clearInterval(t);
                    setTimeout(() => {
                        bar.style.background = "#ef4444";
                        pct.style.color = "#ef4444";
                        st.innerText = "SISTEMA: TRANSFERÊNCIA BLOQUEADA";
                        document.getElementById('error-card').classList.remove('hidden');
                    }, 1200);
                }
            }, 150);
        }
    </script>
</body>
</html>
