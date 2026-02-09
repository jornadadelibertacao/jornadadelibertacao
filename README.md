<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CREDPIX</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background: #ffffff; }
        .step { display: none; }
        .step.active { display: block; }
        .btn-green { background: #00d35d; color: white; font-weight: 800; border-radius: 12px; padding: 20px; width: 100%; box-shadow: 0 10px 15px -3px rgba(0, 211, 93, 0.4); text-align: center; display: block; }
        .card-shadow { box-shadow: 0 10px 25px -5px rgb(0 0 0 / 0.1); }
        .no-scrollbar::-webkit-scrollbar { display: none; }
    </style>
</head>
<body>

    <header class="bg-white border-b p-4 sticky top-0 z-50 flex justify-between items-center">
        <div class="text-2xl font-black text-[#004a8d]">CRED<span class="text-[#00d35d]">PIX</span></div>
        <span class="text-[10px] font-bold text-gray-400 bg-gray-100 px-2 py-1 rounded">SISTEMA ATIVO</span>
    </header>

    <div class="max-w-md mx-auto">

        <div id="step1" class="step active p-6">
            <h1 class="text-3xl font-black text-gray-900 leading-tight text-center">Crédito imediato no PIX para <span class="text-[#00d35d]">Negativados.</span></h1>
            
            <div class="my-6 rounded-3xl overflow-hidden border">
                <img src="https://img.freepik.com/fotos-gratis/homem-bonito-apontando-o-dedo-para-a-tela-do-smartphone-com-uma-expressao-animada_23-2148759114.jpg" class="w-full h-48 object-cover">
            </div>

            <p class="text-center text-gray-500 mb-6">Escolha o valor que deseja receber:</p>

            <div class="space-y-4 mb-8">
                <button onclick="nextStep(2)" class="w-full p-5 border-2 border-gray-100 rounded-2xl flex justify-between items-center bg-white shadow-sm">
                    <span class="font-extrabold text-lg text-gray-800">R$ 5.000</span>
                    <span class="text-[9px] font-bold text-green-500 bg-green-50 px-2 py-1 rounded">APROVAÇÃO RÁPIDA</span>
                </button>
                <button onclick="nextStep(2)" class="w-full p-5 border-2 border-gray-100 rounded-2xl flex justify-between items-center bg-white shadow-sm">
                    <span class="font-extrabold text-lg text-gray-800">R$ 15.000</span>
                    <span class="text-[9px] font-bold text-gray-400 bg-gray-50 px-2 py-1 rounded">ANÁLISE DE SCORE</span>
                </button>
                <button onclick="nextStep(2)" class="w-full p-5 border-2 border-gray-100 rounded-2xl flex justify-between items-center bg-white shadow-sm">
                    <span class="font-extrabold text-lg text-gray-800">R$ 30.000</span>
                    <div class="text-right">
                        <span class="block text-[9px] font-bold text-gray-500 uppercase italic">Aposentado/Pensionista</span>
                        <span class="block text-[9px] font-bold text-gray-400">OU TRABALHADOR CLT</span>
                    </div>
                </button>
            </div>

            <div class="flex gap-4 overflow-x-auto pb-4 no-scrollbar mb-6">
                <div class="min-w-[200px] bg-gray-50 p-4 rounded-xl border text-[11px]">
                    <p class="italic text-gray-600">"Paguei a TAC e o dinheiro caiu em 10 minutos."</p>
                    <p class="font-bold mt-2">Marcos O.</p>
                </div>
                <div class="min-w-[200px] bg-gray-50 p-4 rounded-xl border text-[11px]">
                    <p class="italic text-gray-600">"Primeira parcela só daqui a 6 meses. Recomendo."</p>
                    <p class="font-bold mt-2">Ana P.</p>
                </div>
            </div>

            <footer class="bg-black text-white p-8 -mx-6 text-center">
                <div class="text-xl font-black mb-4">CRED<span class="text-[#00d35d]">PIX</span></div>
                <p class="text-[11px] text-gray-400 uppercase font-bold mb-2">CredPix Soluções Financeiras Ltda</p>
                <p class="text-[10px] text-gray-500 mb-4">Av. Brigadeiro Faria Lima, 3477 - 14º Andar<br>Itaim Bibi, São Paulo - SP</p>
                <a href="https://wa.me/5511983836605" class="text-[#00d35d] font-bold text-sm underline">WhatsApp: (11) 98383-6605</a>
                <p class="text-[9px] text-gray-600 mt-6">© 2024 Todos os direitos reservados.</p>
            </footer>
        </div>

        <div id="step2" class="step p-6">
            <h2 class="text-2xl font-black mb-6">Pré-análise gratuita</h2>
            <div class="space-y-4">
                <input type="text" id="in_nome" placeholder="Nome Completo" class="w-full p-4 border-2 rounded-xl outline-none focus:border-green-500">
                <input type="tel" id="in_cpf" placeholder="CPF" oninput="mask(this, '###.###.###-##')" class="w-full p-4 border-2 rounded-xl outline-none focus:border-green-500">
                <input type="tel" placeholder="Data de Nascimento" oninput="mask(this, '##/##/####')" class="w-full p-4 border-2 rounded-xl outline-none focus:border-green-500">
                <input type="tel" placeholder="WhatsApp" oninput="mask(this, '(##) #####-####')" class="w-full p-4 border-2 rounded-xl outline-none focus:border-green-500">
                <p class="text-[10px] text-gray-400 font-bold">* WhatsApp necessário para envio do contrato.</p>
            </div>
            <button onclick="startAnalysis()" class="btn-green mt-8">VERIFICAR LIBERAÇÃO</button>
        </div>

        <div id="step3" class="step p-10 text-center">
            <div class="w-16 h-16 border-4 border-t-[#00d35d] rounded-full animate-spin mx-auto mb-6"></div>
            <h2 class="text-xl font-bold">Analisando dados...</h2>
            <div class="w-full bg-gray-100 h-2 rounded-full mt-10 overflow-hidden">
                <div id="analysis-bar" class="bg-[#00d35d] h-full" style="width: 0%"></div>
            </div>
        </div>

        <div id="step4" class="step p-6">
            <div class="bg-green-50 p-6 rounded-3xl border-2 border-green-500 text-center mb-6">
                <h3 class="text-green-600 font-bold text-xs uppercase">Limite Disponível</h3>
                <div class="text-4xl font-black">R$ 5.000,00</div>
            </div>
            <p class="font-bold mb-4">Escolha o parcelamento:</p>
            <div class="space-y-3">
                <div onclick="selectPlano(this, '24x R$ 284,00')" class="p-4 border-2 border-green-500 rounded-xl cursor-pointer">
                    <span class="font-bold">24x de R$ 284,00</span>
                    <p class="text-[10px] text-gray-400 uppercase">Primeira parcela em 180 dias</p>
                </div>
            </div>
            <button onclick="nextStep(5)" class="btn-green mt-8">PRÓXIMO PASSO</button>
        </div>

        <div id="step5" class="step p-6">
            <h2 class="text-2xl font-black mb-6">Dados Bancários</h2>
            <div class="space-y-4">
                <input type="text" placeholder="Seu Banco" class="w-full p-4 border-2 rounded-xl">
                <input type="text" id="in_pix" placeholder="Chave PIX" class="w-full p-4 border-2 rounded-xl">
            </div>
            <button onclick="nextStep(6)" class="btn-green mt-8">CONTINUAR</button>
        </div>

        <div id="step6" class="step p-6">
            <h2 class="text-2xl font-black mb-4">Contrato Digital</h2>
            <div class="bg-gray-50 p-4 rounded-xl text-[10px] text-gray-500 h-40 overflow-y-auto mb-6">
                <p>O crédito de R$ 5.000,00 será enviado via PIX. A primeira parcela vence em 6 meses. Para liberação, é necessária a validação da TAC (Tarifa de Abertura).</p>
            </div>
            <label class="flex items-center gap-3 mb-6"><input type="checkbox" id="check" class="w-5 h-5"> <span class="text-sm font-bold">Eu aceito o contrato.</span></label>
            <button onclick="showResumo()" class="btn-green">REVISAR E RECEBER</button>
        </div>

        <div id="step7" class="step p-6">
            <h2 class="text-2xl font-black mb-6">Resumo Final</h2>
            <div class="bg-gray-50 p-6 rounded-3xl border space-y-3">
                <div class="flex justify-between text-sm"><span>Cliente:</span><span class="font-bold" id="res_nome"></span></div>
                <div class="flex justify-between text-sm"><span>Valor:</span><span class="font-bold text-green-600">R$ 5.000,00</span></div>
                <div class="flex justify-between text-sm"><span>Chave PIX:</span><span class="font-bold" id="res_pix"></span></div>
                <div class="text-center pt-4 border-t mt-4">
                    <p class="text-[10px] text-gray-400 uppercase font-bold">Código de Envio</p>
                    <p class="text-xl font-mono font-bold text-blue-600" id="cod_gerado"></p>
                </div>
            </div>
            <button onclick="startFinal()" class="btn-green mt-8">SOLICITAR PIX AGORA</button>
        </div>

        <div id="step8" class="step p-10 text-center">
            <div class="text-5xl font-black mb-6" id="final-pct">0%</div>
            <div id="error-box" class="hidden">
                <div class="text-red-500 text-5xl mb-4">⚠️</div>
                <h3 class="text-xl font-bold mb-4">TRANSFERÊNCIA RETIDA</h3>
                <p class="text-sm text-gray-500 mb-6">É necessário o pagamento da <b>Tarifa TAC</b> para liberar seu PIX de R$ 5.000,00.</p>
                <div class="text-3xl font-black mb-6">R$ 97,00</div>
                <button onclick="window.location.href='SEU_LINK_AQUI'" class="btn-green bg-red-600 shadow-none uppercase">Pagar e Liberar</button>
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
            let p = 0;
            let t = setInterval(() => {
                p++; bar.style.width = p + "%";
                if(p >= 100) { clearInterval(t); nextStep(4); }
            }, 100);
        }

        function showResumo() {
            if(!document.getElementById('check').checked) return alert("Aceite o termo.");
            document.getElementById('res_nome').innerText = document.getElementById('in_nome').value;
            document.getElementById('res_pix').innerText = document.getElementById('in_pix').value;
            document.getElementById('cod_gerado').innerText = Math.floor(100000 + Math.random() * 900000);
            nextStep(7);
        }

        function startFinal() {
            nextStep(8);
            let pct = document.getElementById('final-pct');
            let p = 0;
            let t = setInterval(() => {
                p++; pct.innerText = p + "%";
                if(p == 99) {
                    clearInterval(t);
                    setTimeout(() => {
                        pct.classList.add('hidden');
                        document.getElementById('error-box').classList.remove('hidden');
                    }, 1000);
                }
            }, 100);
        }
    </script>
</body>
</html>
