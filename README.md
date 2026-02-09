<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CREDPIX - Crédito na Hora</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background: #f8fafc; overflow-x: hidden; }
        .step { display: none; }
        .step.active { display: block; animation: fadeIn 0.4s ease-out; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
        .btn-green { background: #00d35d; color: white; font-weight: 800; border-radius: 12px; padding: 20px; width: 100%; transition: 0.3s; box-shadow: 0 10px 15px -3px rgba(0, 211, 93, 0.4); text-align: center; display: block; }
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
            <div class="text-center mb-6">
                <h1 class="text-3xl font-black text-gray-900 leading-tight">Crédito imediato no PIX para <span class="text-[#00d35d]">Negativados.</span></h1>
                
                <div class="my-6 bg-gray-200 rounded-3xl h-52 flex items-center justify-center overflow-hidden border-2 border-dashed border-gray-300">
                    <img src="https://img.freepik.com/fotos-gratis/homem-bonito-apontando-o-dedo-para-a-tela-do-smartphone-com-uma-expressao-animada_23-2148759114.jpg" alt="CredPix Celular" class="w-full h-full object-cover">
                </div>

                <p class="text-gray-500 mt-2">Sem consulta ao SPC/Serasa e com liberação em 5 minutos.</p>
            </div>

            <div class="bg-white rounded-3xl p-5 card-shadow mb-8 border-2 border-green-50">
                <h2 class="font-bold text-gray-800 mb-5 text-center italic">Pré-análise gratuita:</h2>
                <div class="space-y-4">
                    <input type="text" id="res_nome" placeholder="Nome Completo" class="w-full p-4 bg-gray-50 border-2 border-gray-100 rounded-xl outline-none focus:border-green-500">
                    <input type="tel" id="res_cpf" placeholder="CPF" oninput="mask(this, '###.###.###-##')" class="w-full p-4 bg-gray-50 border-2 border-gray-100 rounded-xl outline-none focus:border-green-500">
                    <input type="tel" placeholder="Data de Nascimento" oninput="mask(this, '##/##/####')" class="w-full p-4 bg-gray-50 border-2 border-gray-100 rounded-xl outline-none focus:border-green-500">
                    <input type="tel" placeholder="WhatsApp" oninput="mask(this, '(##) #####-####')" class="w-full p-4 bg-gray-50 border-2 border-gray-100 rounded-xl outline-none focus:border-green-500">
                    <p class="text-[10px] text-gray-400 px-1 font-bold">* É necessário o WhatsApp para envio da cópia do contrato após aprovação.</p>
                </div>
            </div>

            <button onclick="startAnalysis()" class="btn-green uppercase">CONSULTAR MEU LIMITE</button>

            <div class="mt-10 overflow-hidden">
                <div class="flex gap-4 overflow-x-auto pb-4 no-scrollbar">
                    <div class="min-w-[250px] bg-white p-4 rounded-2xl shadow-sm border">
                        <p class="text-[12px] text-gray-600 italic">"Caiu na hora! Paguei a taxa TAC e liberaram o PIX em 5 min."</p>
                        <p class="text-[10px] font-bold mt-2 text-gray-400">Ricardo S., SP</p>
                    </div>
                    <div class="min-w-[250px] bg-white p-4 rounded-2xl shadow-sm border">
                        <p class="text-[12px] text-gray-600 italic">"A carência de 6 meses me ajudou a sair do buraco. Top!"</p>
                        <p class="text-[10px] font-bold mt-2 text-gray-400">Ana Paula, RJ</p>
                    </div>
                </div>
            </div>

            <footer class="mt-10 pt-6 border-t border-gray-200 text-center text-gray-400">
                <p class="text-[11px] font-bold uppercase">CredPix Soluções Financeiras Ltda</p>
                <p class="text-[10px]">Av. Brg. Faria Lima, 3477 - Itaim Bibi, São Paulo - SP, 04538-133</p>
                <p class="text-[10px] mt-2 italic">WhatsApp Suporte: (11) 98383-6605</p>
                <p class="text-[9px] mt-4">© 2024 Todos os direitos reservados.</p>
            </footer>
        </div>

        <div id="step2" class="step p-10 text-center">
            <div class="w-20 h-20 border-4 border-gray-100 border-t-[#00d35d] rounded-full animate-spin mx-auto mb-8"></div>
            <h2 class="text-xl font-black mb-2">Analisando Perfil...</h2>
            <div class="w-full bg-gray-100 h-2 rounded-full mt-10 overflow-hidden">
                <div id="analysis-bar" class="bg-[#00d35d] h-full transition-all duration-500" style="width: 0%"></div>
            </div>
        </div>

        <div id="step3" class="step py-6">
            <div class="text-center mb-8">
                <h2 class="text-2xl font-black">Limite Liberado!</h2>
                <p class="text-gray-500">Escolha o valor e o prazo de pagamento:</p>
            </div>
            
            <div class="space-y-4">
                <div onclick="selectVal(this, 'R$ 5.000', '24x R$ 284,00')" class="p-5 border-2 border-green-500 bg-green-50 rounded-2xl flex justify-between items-center cursor-pointer">
                    <span class="font-black text-lg">R$ 5.000,00</span>
                    <span class="text-[10px] font-bold text-green-600">24x R$ 284,00</span>
                </div>
                <div onclick="selectVal(this, 'R$ 10.000', '48x R$ 265,00')" class="p-5 border-2 border-gray-100 bg-white rounded-2xl flex justify-between items-center cursor-pointer">
                    <span class="font-black text-lg">R$ 10.000,00</span>
                    <span class="text-[10px] font-bold text-gray-400">48x R$ 265,00</span>
                </div>
            </div>
            <button onclick="nextStep(4)" class="btn-green mt-8">CONTINUAR</button>
        </div>

        <div id="step4" class="step py-6">
            <h2 class="text-2xl font-black mb-6">Onde quer receber?</h2>
            <div class="space-y-4">
                <select id="res_banco" class="w-full p-4 bg-white border-2 border-gray-100 rounded-xl outline-none focus:border-green-500">
                    <option>Selecione seu Banco...</option>
                    <option>Nubank</option><option>Caixa</option><option>Inter</option><option>Itaú</option>
                </select>
                <input type="text" id="res_pix" placeholder="Sua Chave PIX" class="w-full p-4 bg-white border-2 border-gray-100 rounded-xl outline-none focus:border-green-500">
            </div>
            <button onclick="nextStep(5)" class="btn-green mt-8 uppercase">PRÓXIMO PASSO</button>
        </div>

        <div id="step5" class="step py-6">
            <h2 class="text-2xl font-black mb-4">Contrato Digital</h2>
            <div class="bg-gray-100 p-4 rounded-2xl text-[10px] text-gray-500 h-52 overflow-y-auto mb-6">
                <p class="mb-2"><strong>CLÁUSULA 1:</strong> A primeira parcela vencerá em 180 dias após o recebimento.</p>
                <p class="mb-2"><strong>CLÁUSULA 2:</strong> A liberação do crédito depende da validação da Tarifa de Abertura (TAC).</p>
                <p><strong>CLÁUSULA 3:</strong> Valor da TAC será reembolsado junto com o empréstimo.</p>
            </div>
            <label class="flex items-center gap-3 mb-8 cursor-pointer">
                <input type="checkbox" id="checkT" class="w-6 h-6 accent-[#00d35d]">
                <span class="text-sm font-bold">Aceito os termos e prazos.</span>
            </label>
            <button onclick="resumo()" class="btn-green uppercase">REVISAR PROPOSTA</button>
        </div>

        <div id="step6" class="step py-6">
            <h2 class="text-2xl font-black mb-6">Resumo da Solicitação</h2>
            <div class="bg-white p-6 rounded-[32px] border-2 border-gray-100 space-y-4 card-shadow">
                <div class="flex justify-between border-b pb-2"><span class="text-gray-400 text-sm">Cliente:</span><span class="font-bold" id="out_nome">-</span></div>
                <div class="flex justify-between border-b pb-2"><span class="text-gray-400 text-sm">Valor:</span><span class="font-bold text-green-600" id="out_valor">R$ 5.000</span></div>
                <div class="flex justify-between border-b pb-2"><span class="text-gray-400 text-sm">Plano:</span><span class="font-bold" id="out_plano">-</span></div>
                <div class="flex justify-between border-b pb-2"><span class="text-gray-400 text-sm">Chave PIX:</span><span class="font-bold" id="out_pix">-</span></div>
                <div class="flex justify-between pt-2"><span class="text-gray-400 text-sm">Status:</span><span class="text-blue-500 font-bold uppercase text-[10px]">Aguardando Envio</span></div>
            </div>
            <div class="mt-6 text-center text-gray-400 text-[10px] uppercase font-bold tracking-widest">Código de Envio: <span id="cod_envio"></span></div>
            <button onclick="startFinal()" class="btn-green mt-8 uppercase">RECEBER MEU PIX AGORA</button>
        </div>

        <div id="step7" class="step py-10 text-center">
            <div class="text-6xl font-black mb-6" id="final-pct">0%</div>
            <div class="w-full bg-gray-100 h-3 rounded-full overflow-hidden mb-6">
                <div id="final-bar" class="bg-[#00d35d] h-full" style="width: 0%"></div>
            </div>
            <p class="text-gray-400 font-bold uppercase text-xs">Validando Chave PIX no Banco Central...</p>

            <div id="error-card" class="hidden mt-10 bg-white rounded-[32px] p-8 border-2 border-red-500 card-shadow animate-bounce">
                <div class="text-red-500 text-6xl mb-4">⚠️</div>
                <h3 class="text-xl font-black mb-2 uppercase italic">Atenção: Envio Retido</h3>
                <p class="text-gray-500 text-sm leading-relaxed mb-6">É necessário a quitação imediata da <b>Tarifa TAC</b> para liberar o depósito de R$ 5.000,00 na sua conta.</p>
                <div class="bg-red-50 text-red-600 p-5 rounded-2xl mb-8 font-black text-3xl">R$ 97,00</div>
                <button onclick="window.location.href='SEU_LINK_AQUI'" class="btn-green bg-red-600 shadow-none uppercase">Pagar Tarifa e Receber</button>
            </div>
        </div>

    </div>

    <script>
        let v_escolhido = "R$ 5.000,00";
        let p_escolhido = "24x R$ 284,00";

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

        function selectVal(el, v, p) {
            document.querySelectorAll('#step3 .border-green-500').forEach(d => {
                d.classList.replace('border-green-500', 'border-gray-100');
                d.classList.replace('bg-green-50', 'bg-white');
            });
            el.classList.replace('border-gray-100', 'border-green-500');
            el.classList.replace('bg-white', 'bg-green-50');
            v_escolhido = v; p_escolhido = p;
        }

        function startAnalysis() {
            nextStep(2);
            let bar = document.getElementById('analysis-bar');
            let p = 0;
            let t = setInterval(() => {
                p += 1; bar.style.width = p + "%";
                if(p >= 100) { clearInterval(t); nextStep(3); }
            }, 120);
        }

        function resumo() {
            if(!document.getElementById('checkT').checked) return alert("Aceite os termos.");
            document.getElementById('out_nome').innerText = document.getElementById('res_nome').value || "Não informado";
            document.getElementById('out_valor').innerText = v_escolhido;
            document.getElementById('out_plano').innerText = p_escolhido;
            document.getElementById('out_pix').innerText = document.getElementById('res_pix').value || "Não informado";
            document.getElementById('cod_envio').innerText = Math.floor(100000 + Math.random() * 900000);
            nextStep(6);
        }

        function startFinal() {
            nextStep(7);
            let bar = document.getElementById('final-bar');
            let pct = document.getElementById('final-pct');
            let p = 0;
            let t = setInterval(() => {
                p++;
                if(p <= 99) { bar.style.width = p + "%"; pct.innerText = p + "%"; }
                if(p == 99) {
                    clearInterval(t);
                    setTimeout(() => {
                        bar.style.background = "#ef4444";
                        document.getElementById('error-card').classList.remove('hidden');
                    }, 1200);
                }
            }, 150);
        }
    </script>
</body>
</html>
