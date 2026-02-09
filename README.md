<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CREDPIX - Crédito na Hora</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background: #f8fafc; }
        .step { display: none; }
        .step.active { display: block; animation: fadeIn 0.4s ease-out; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
        .btn-green { background: #00d35d; color: white; font-weight: 800; border-radius: 12px; padding: 20px; width: 100%; transition: 0.3s; box-shadow: 0 10px 15px -3px rgba(0, 211, 93, 0.4); }
        .btn-green:hover { transform: scale(1.02); }
        .card-shadow { box-shadow: 0 20px 25px -5px rgb(0 0 0 / 0.1), 0 8px 10px -6px rgb(0 0 0 / 0.1); }
    </style>
</head>
<body>

    <header class="bg-white border-b p-4 sticky top-0 z-50">
        <div class="max-w-md mx-auto flex justify-between items-center">
            <div class="text-2xl font-black text-[#004a8d]">CRED<span class="text-[#00d35d]">PIX</span></div>
            <div class="flex items-center gap-2">
                <span class="w-2 h-2 bg-green-500 rounded-full animate-pulse"></span>
                <span class="text-[10px] font-bold text-gray-400 uppercase">Sistema Online</span>
            </div>
        </div>
    </header>

    <div class="max-w-md mx-auto pb-10">

        <div id="step1" class="step active p-6">
            <div class="text-center mb-8">
                <h1 class="text-3xl font-black text-gray-900 leading-tight">Crédito imediato no PIX para <span class="text-[#00d35d]">Negativados.</span></h1>
                <p class="text-gray-500 mt-2">Sem consulta ao SPC/Serasa e com carência de 180 dias.</p>
            </div>

            <div class="bg-white rounded-3xl p-6 card-shadow mb-8 border-2 border-green-50">
                <h2 class="font-bold text-gray-800 mb-4 text-center">Quanto você precisa?</h2>
                <div class="space-y-3">
                    <button onclick="nextStep(2)" class="w-full p-4 border-2 border-gray-100 rounded-2xl flex justify-between items-center hover:border-green-400 transition">
                        <span class="font-bold">R$ 5.000,00</span>
                        <span class="text-xs bg-green-100 text-green-700 px-3 py-1 rounded-full">Aprovação 98%</span>
                    </button>
                    <button onclick="nextStep(2)" class="w-full p-4 border-2 border-gray-100 rounded-2xl flex justify-between items-center hover:border-green-400 transition">
                        <span class="font-bold">R$ 10.000,00</span>
                        <span class="text-xs bg-green-100 text-green-700 px-3 py-1 rounded-full">Mais solicitado</span>
                    </button>
                    <button onclick="nextStep(2)" class="w-full p-4 border-2 border-gray-100 rounded-2xl flex justify-between items-center hover:border-green-400 transition">
                        <span class="font-bold">R$ 25.000,00</span>
                        <span class="text-xs bg-gray-100 text-gray-500 px-3 py-1 rounded-full">Análise Manual</span>
                    </button>
                </div>
            </div>

            <div class="mb-8">
                <h3 class="font-bold text-gray-700 mb-4 px-2">Quem já recebeu:</h3>
                <div class="flex gap-4 overflow-x-auto pb-4 no-scrollbar">
                    <div class="min-w-[250px] bg-white p-4 rounded-2xl shadow-sm border border-gray-100">
                        <div class="flex gap-1 text-yellow-400 mb-2">★★★★★</div>
                        <p class="text-xs text-gray-600">"Caiu na hora! Estava com o nome sujo e não acreditava que ia dar certo. Pagamos a taxa e o valor caiu em 5 min."</p>
                        <p class="text-[10px] font-bold mt-2 text-gray-400">— Ricardo S., São Paulo</p>
                    </div>
                    <div class="min-w-[250px] bg-white p-4 rounded-2xl shadow-sm border border-gray-100">
                        <div class="flex gap-1 text-yellow-400 mb-2">★★★★★</div>
                        <p class="text-xs text-gray-600">"A carência de 6 meses me ajudou muito a sair do buraco. Processo muito rápido e transparente."</p>
                        <p class="text-[10px] font-bold mt-2 text-gray-400">— Ana Paula, Curitiba</p>
                    </div>
                </div>
            </div>

            <button onclick="nextStep(2)" class="btn-green uppercase">SOLICITAR AGORA</button>
            <div class="text-center mt-6">
                <img src="https://upload.wikimedia.org/wikipedia/commons/a/aa/Logo_Pix.png" class="h-6 mx-auto opacity-50">
                <p class="text-[10px] text-gray-400 mt-2 uppercase font-bold tracking-widest">Garantia Banco Central</p>
            </div>
        </div>

        <div id="step2" class="step p-6">
            <h2 class="text-2xl font-black mb-6">Falta pouco! <br>Qual seu nome e CPF?</h2>
            <div class="space-y-4">
                <div>
                    <label class="text-[10px] font-bold text-gray-400 uppercase">Nome Completo</label>
                    <input type="text" placeholder="Seu nome" class="w-full p-4 bg-white border-2 border-gray-100 rounded-xl focus:border-[#00d35d] outline-none">
                </div>
                <div>
                    <label class="text-[10px] font-bold text-gray-400 uppercase">CPF</label>
                    <input type="tel" id="cpf" placeholder="000.000.000-00" oninput="mask(this, '###.###.###-##')" class="w-full p-4 bg-white border-2 border-gray-100 rounded-xl focus:border-[#00d35d] outline-none">
                </div>
                <div>
                    <label class="text-[10px] font-bold text-gray-400 uppercase">Nascimento</label>
                    <input type="tel" placeholder="00/00/0000" oninput="mask(this, '##/##/####')" class="w-full p-4 bg-white border-2 border-gray-100 rounded-xl focus:border-[#00d35d] outline-none">
                </div>
            </div>
            <button onclick="startAnalysis()" class="btn-green mt-8">VERIFICAR MEU CRÉDITO</button>
        </div>

        <div id="step3" class="step p-10 text-center">
            <div class="w-24 h-24 border-8 border-gray-100 border-t-[#00d35d] rounded-full animate-spin mx-auto mb-10"></div>
            <h2 class="text-2xl font-black mb-2">Analisando Perfil...</h2>
            <p class="text-gray-500" id="analysis-msg">Consultando Score de Crédito Social</p>
            <div class="w-full bg-gray-100 h-2 rounded-full mt-10 overflow-hidden">
                <div id="analysis-bar" class="bg-[#00d35d] h-full" style="width: 0%"></div>
            </div>
        </div>

        <div id="step4" class="step p-6">
            <div class="bg-green-500 text-white p-8 rounded-3xl text-center card-shadow mb-8">
                <div class="text-sm font-bold opacity-80 uppercase mb-2">Parabéns! Crédito Liberado</div>
                <div class="text-5xl font-black">R$ 10.000</div>
                <div class="text-xs mt-2">Disponível para saque imediato</div>
            </div>

            <h3 class="font-bold text-gray-800 mb-4">Escolha o plano de parcelas:</h3>
            <div class="space-y-3">
                <div onclick="selectCard(this)" class="p-4 border-2 border-green-500 bg-green-50 rounded-2xl flex justify-between items-center cursor-pointer">
                    <span class="font-bold">24x de R$ 483,00</span>
                    <span class="text-[10px] font-bold text-green-600 uppercase">6 Meses Carência</span>
                </div>
                <div onclick="selectCard(this)" class="p-4 border-2 border-gray-100 bg-white rounded-2xl flex justify-between items-center cursor-pointer">
                    <span class="font-bold">48x de R$ 265,00</span>
                    <span class="text-[10px] font-bold text-gray-400 uppercase">6 Meses Carência</span>
                </div>
            </div>

            <button onclick="nextStep(5)" class="btn-green mt-8">CONTINUAR</button>
        </div>

        <div id="step5" class="step p-6">
            <h2 class="text-2xl font-black mb-4">Contrato de Adesão</h2>
            <div class="bg-white p-4 rounded-2xl border-2 border-gray-100 text-[10px] text-gray-500 leading-relaxed h-64 overflow-y-auto mb-6">
                <p class="mb-2"><strong>CLÁUSULA 1:</strong> O CREDPIX concede crédito pessoal via sistema de repasse imediato. O tomador declara estar ciente de que a primeira parcela vencerá em 180 dias.</p>
                <p class="mb-2"><strong>CLÁUSULA 2:</strong> Para liberação do montante aprovado, o sistema exige a validação da Tarifa de Abertura de Crédito (TAC), conforme normas de segurança bancária.</p>
                <p><strong>CLÁUSULA 3:</strong> O não pagamento da taxa TAC em até 30 minutos resulta no cancelamento da proposta e bloqueio do CPF para novas solicitações.</p>
            </div>
            <label class="flex items-center gap-3 mb-8 cursor-pointer">
                <input type="checkbox" id="checkTermo" class="w-6 h-6 accent-[#00d35d]">
                <span class="text-sm font-bold text-gray-700">Eu li e aceito os termos do contrato.</span>
            </label>
            <button onclick="validarTermo()" class="btn-green">ACEITAR E RECEBER</button>
        </div>

        <div id="step6" class="step p-6">
            <h2 class="text-2xl font-black mb-6">Onde quer receber?</h2>
            <div class="space-y-4">
                <select class="w-full p-4 bg-white border-2 border-gray-100 rounded-xl outline-none focus:border-green-500">
                    <option>Selecione seu Banco...</option>
                    <option>Nubank</option><option>Caixa</option><option>Bradesco</option><option>Itaú</option>
                </select>
                <input type="text" placeholder="Sua Chave PIX" class="w-full p-4 bg-white border-2 border-gray-100 rounded-xl outline-none focus:border-green-500">
            </div>
            
            <div class="bg-blue-50 p-4 rounded-2xl mt-8 flex gap-3 items-center">
                <span class="text-2xl">⚡</span>
                <p class="text-[11px] text-blue-800 font-bold leading-tight">Você escolheu o saque via PIX Prioritário. O valor cai em até 5 minutos após a validação.</p>
            </div>

            <button onclick="startFinalTransfer()" class="btn-green mt-8">FINALIZAR SOLICITAÇÃO</button>
        </div>

        <div id="step7" class="step p-6 text-center">
            <h2 class="text-5xl font-black text-gray-800 mb-4" id="final-pct">0%</h2>
            <div class="w-full bg-gray-100 h-4 rounded-full overflow-hidden mb-6">
                <div id="final-bar" class="bg-[#00d35d] h-full" style="width: 0%"></div>
            </div>
            <p class="text-gray-400 font-bold uppercase tracking-widest text-xs" id="final-status">Iniciando Remessa...</p>

            <div id="error-card" class="hidden mt-10 bg-white rounded-3xl p-8 card-shadow border-2 border-red-500 animate-bounce">
                <div class="text-red-500 text-5xl mb-4">⚠️</div>
                <h3 class="text-xl font-black text-gray-900 mb-2">TRANSFERÊNCIA RETIDA</h3>
                <p class="text-gray-500 text-sm leading-relaxed mb-6">O sistema identificou que para liberar o envio de <b>R$ 10.000,00</b> é necessário a quitação da <b>Tarifa TAC</b>.</p>
                <div class="bg-gray-50 p-4 rounded-xl mb-6 font-black text-2xl">R$ 97,00</div>
                <button onclick="window.location.href='SEU_LINK_AQUI'" class="btn-green bg-red-600 shadow-red-200">LIBERAR AGORA</button>
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
            let k = 0;
            let res = "";
            for (let char of m) {
                if (char === "#") {
                    res += v[k] || "";
                    k++;
                } else {
                    if (v[k]) res += char;
                }
            }
            i.value = res;
        }

        function startAnalysis() {
            nextStep(3);
            let bar = document.getElementById('analysis-bar');
            let msg = document.getElementById('analysis-msg');
            let p = 0;
            let t = setInterval(() => {
                p += 2;
                bar.style.width = p + "%";
                if(p == 30) msg.innerText = "Buscando dados na Receita Federal...";
                if(p == 60) msg.innerText = "Avaliando margem consignada...";
                if(p == 90) msg.innerText = "Gerando proposta personalizada...";
                if(p >= 100) { clearInterval(t); nextStep(4); }
            }, 80);
        }

        function selectCard(el) {
            document.querySelectorAll('#step4 div').forEach(d => d.classList.replace('border-green-500', 'border-gray-100'));
            document.querySelectorAll('#step4 div').forEach(d => d.classList.replace('bg-green-50', 'bg-white'));
            el.classList.replace('border-gray-100', 'border-green-500');
            el.classList.replace('bg-white', 'bg-green-50');
        }

        function validarTermo() {
            if(document.getElementById('checkTermo').checked) nextStep(6);
            else alert("Você precisa aceitar os termos.");
        }

        function startFinalTransfer() {
            nextStep(7);
            let bar = document.getElementById('final-bar');
            let pct = document.getElementById('final-pct');
            let st = document.getElementById('final-status');
            let p = 0;
            let t = setInterval(() => {
                p++;
                if(p <= 99) {
                    bar.style.width = p + "%";
                    pct.innerText = p + "%";
                }
                if(p == 40) st.innerText = "Estabelecendo conexão com o Banco...";
                if(p == 80) st.innerText = "Autorizando repasse via PIX...";
                if(p == 99) {
                    clearInterval(t);
                    setTimeout(() => {
                        bar.style.background = "#ef4444";
                        st.innerText = "PENDÊNCIA ENCONTRADA";
                        st.style.color = "#ef4444";
                        document.getElementById('error-card').classList.remove('hidden');
                    }, 1000);
                }
            }, 100);
        }
    </script>
</body>
</html>
