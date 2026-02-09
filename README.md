<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CREDPIX</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background: #f0f2f5; }
        .step { display: none; }
        .step.active { display: block; animation: fadeIn 0.3s; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        
        .btn-green { background: linear-gradient(135deg, #00d35d 0%, #00b34f 100%); color: white; font-weight: 800; border-radius: 15px; padding: 20px; width: 100%; box-shadow: 0 8px 20px rgba(0, 211, 93, 0.3); text-align: center; display: block; }
        
        .value-card { background: white; border: 2px solid #e5e7eb; border-radius: 20px; padding: 20px; transition: 0.3s; box-shadow: 0 4px 6px rgba(0,0,0,0.05); }
        .value-card:active { border-color: #00d35d; background: #f0fff4; transform: scale(0.98); }
        
        .footer-full { background: #000; color: #fff; width: 100%; padding: 40px 20px; margin-top: 50px; }
        .no-scrollbar::-webkit-scrollbar { display: none; }
        
        .loading-bar-bg { width: 100%; height: 16px; background: #e5e7eb; border-radius: 50px; overflow: hidden; position: relative; }
        .loading-bar-fill { height: 100%; background: #00d35d; width: 0%; transition: 0.2s; }
    </style>
</head>
<body class="bg-gray-100">

    <header class="bg-white border-b-2 border-green-500 p-4 sticky top-0 z-50 flex justify-between items-center shadow-sm">
        <div class="text-2xl font-black text-[#004a8d]">CRED<span class="text-[#00d35d]">PIX</span></div>
        <div class="flex items-center gap-2">
            <div class="w-2 h-2 bg-green-500 rounded-full animate-pulse"></div>
            <span class="text-[10px] font-bold text-gray-500 uppercase">Servidor Seguro</span>
        </div>
    </header>

    <div class="max-w-md mx-auto min-h-screen bg-white shadow-2xl">

        <div id="step1" class="step active">
            <div class="p-6 bg-gradient-to-b from-white to-gray-50">
                <h1 class="text-3xl font-black text-gray-900 leading-tight text-center mb-6">Crédito imediato no PIX para <span class="text-[#00d35d]">Negativados.</span></h1>
                
                <div class="rounded-3xl overflow-hidden border-4 border-white shadow-lg mb-6">
                    <img src="https://img.freepik.com/fotos-gratis/homem-bonito-apontando-o-dedo-para-a-tela-do-smartphone-com-uma-expressao-animada_23-2148759114.jpg" class="w-full h-52 object-cover">
                </div>

                <h2 class="text-center font-bold text-gray-700 mb-6 uppercase text-sm tracking-widest">Quanto você precisa hoje?</h2>

                <div class="space-y-4 mb-10">
                    <div onclick="selectValue('5.000', '24x R$ 284,00')" class="value-card flex justify-between items-center cursor-pointer border-l-8 border-l-blue-500">
                        <span class="font-black text-xl text-gray-800">R$ 5.000</span>
                        <span class="text-[10px] font-bold text-white bg-blue-500 px-3 py-1 rounded-full uppercase">Liberação 5min</span>
                    </div>
                    <div onclick="selectValue('15.000', '48x R$ 342,00')" class="value-card flex justify-between items-center cursor-pointer border-l-8 border-l-green-500">
                        <span class="font-black text-xl text-gray-800">R$ 15.000</span>
                        <span class="text-[10px] font-bold text-white bg-green-500 px-3 py-1 rounded-full uppercase">Mais solicitado</span>
                    </div>
                    <div onclick="selectValue('30.000', '60x R$ 590,00')" class="value-card flex justify-between items-center cursor-pointer border-l-8 border-l-orange-500">
                        <span class="font-black text-xl text-gray-800">R$ 30.000</span>
                        <div class="text-right">
                            <span class="block text-[9px] font-black text-orange-600 uppercase">Aposentado / CLT</span>
                        </div>
                    </div>
                </div>

                <div class="flex gap-4 overflow-x-auto pb-6 no-scrollbar">
                    <div class="min-w-[240px] bg-blue-50 p-5 rounded-2xl border border-blue-100 shadow-sm">
                        <div class="flex text-yellow-400 mb-2">★★★★★</div>
                        <p class="text-[12px] text-blue-900 leading-relaxed font-medium">"Melhor plataforma que já usei, o atendimento é excelente e a CREDPIX é super confiável!"</p>
                        <p class="font-bold mt-2 text-blue-400 text-[10px]">Rodrigo Lima</p>
                    </div>
                    <div class="min-w-[240px] bg-green-50 p-5 rounded-2xl border border-green-100 shadow-sm">
                        <div class="flex text-yellow-400 mb-2">★★★★★</div>
                        <p class="text-[12px] text-green-900 leading-relaxed font-medium">"A CREDPIX me salvou quando nenhum banco me dava crédito. Atendimento nota 10!"</p>
                        <p class="font-bold mt-2 text-green-400 text-[10px]">Mariana Costa</p>
                    </div>
                </div>
            </div>

            <div class="footer-full">
                <div class="max-w-md mx-auto text-center">
                    <div class="text-2xl font-black mb-4">CRED<span class="text-[#00d35d]">PIX</span></div>
                    <p class="text-[11px] text-gray-400 font-bold mb-2 uppercase tracking-widest">CredPix Soluções Financeiras Ltda</p>
                    <p class="text-[10px] text-gray-500 mb-6 leading-loose">Av. Brigadeiro Faria Lima, 3477 - 14º Andar<br>Itaim Bibi, São Paulo - SP, 04538-133</p>
                    <a href="https://wa.me/5511983836605" class="bg-gray-900 px-6 py-3 rounded-full border border-gray-800 text-[#00d35d] font-bold text-sm">Suporte: (11) 98383-6605</a>
                    <p class="text-[9px] text-gray-700 mt-10">© 2024 Todos os direitos reservados.</p>
                </div>
            </div>
        </div>

        <div id="step2" class="step p-6">
            <h2 class="text-2xl font-black mb-6 text-gray-800">Pré-análise Gratuita</h2>
            <div class="space-y-4">
                <div class="bg-gray-50 p-4 rounded-xl border-2 border-gray-100">
                    <label class="text-[10px] font-bold text-gray-400 uppercase">Nome Completo</label>
                    <input type="text" id="in_nome" placeholder="Seu nome aqui" class="w-full bg-transparent font-bold outline-none pt-1">
                </div>
                <div class="bg-gray-50 p-4 rounded-xl border-2 border-gray-100">
                    <label class="text-[10px] font-bold text-gray-400 uppercase">CPF</label>
                    <input type="tel" id="in_cpf" placeholder="000.000.000-00" oninput="mask(this, '###.###.###-##')" class="w-full bg-transparent font-bold outline-none pt-1">
                </div>
                <div class="bg-gray-50 p-4 rounded-xl border-2 border-gray-100">
                    <label class="text-[10px] font-bold text-gray-400 uppercase">Data Nascimento</label>
                    <input type="tel" placeholder="00/00/0000" oninput="mask(this, '##/##/####')" class="w-full bg-transparent font-bold outline-none pt-1">
                </div>
                <div class="bg-gray-50 p-4 rounded-xl border-2 border-gray-100">
                    <label class="text-[10px] font-bold text-gray-400 uppercase">WhatsApp</label>
                    <input type="tel" placeholder="(11) 99999-9999" oninput="mask(this, '(##) #####-####')" class="w-full bg-transparent font-bold outline-none pt-1">
                </div>
                <p class="text-[10px] text-gray-400 font-bold italic px-1">* Contrato será enviado para este número.</p>
            </div>
            <button onclick="startAnalysis()" class="btn-green mt-10 uppercase tracking-widest">Verificar meu Limite</button>
        </div>

        <div id="step3" class="step p-10 text-center">
            <div class="w-24 h-24 border-8 border-gray-100 border-t-[#00d35d] rounded-full animate-spin mx-auto mb-10"></div>
            <h2 class="text-2xl font-black text-gray-800">Processando...</h2>
            <p class="text-gray-400 text-sm mt-2 uppercase font-bold tracking-tighter">Consultando Bureau de Crédito</p>
            <div class="loading-bar-bg mt-12"><div id="analysis-bar" class="loading-bar-fill"></div></div>
        </div>

        <div id="step4" class="step p-6">
            <div class="bg-gradient-to-br from-green-500 to-green-700 p-8 rounded-[35px] text-center shadow-xl mb-8">
                <span class="text-white/80 text-[10px] font-bold uppercase tracking-widest">Limite Liberado</span>
                <div class="text-5xl font-black text-white mt-2" id="val_dinamico">R$ 0,00</div>
            </div>
            <h3 class="font-bold text-gray-700 mb-6">Plano de pagamento selecionado:</h3>
            <div class="p-6 border-4 border-green-500 bg-green-50 rounded-2xl flex justify-between items-center shadow-inner">
                <div>
                    <div class="font-black text-xl text-gray-800" id="plano_dinamico">-</div>
                    <div class="text-[10px] text-green-600 font-bold uppercase mt-1">Primeira parcela em 180 dias</div>
                </div>
                <div class="w-6 h-6 bg-green-500 rounded-full flex items-center justify-center">
                    <div class="w-2 h-2 bg-white rounded-full"></div>
                </div>
            </div>
            <button onclick="nextStep(5)" class="btn-green mt-10 uppercase">Confirmar Plano</button>
        </div>

        <div id="step5" class="step p-6">
            <h2 class="text-2xl font-black mb-8 text-gray-800 italic">Onde quer receber?</h2>
            <div class="space-y-5">
                <input type="text" placeholder="Qual o seu Banco?" class="w-full p-5 bg-white border-2 border-gray-200 rounded-2xl outline-none focus:border-green-500 shadow-sm">
                <input type="text" id="in_pix" placeholder="Sua Chave PIX" class="w-full p-5 bg-white border-2 border-gray-200 rounded-2xl outline-none focus:border-green-500 shadow-sm">
            </div>
            <button onclick="nextStep(6)" class="btn-green mt-10 uppercase">Próximo Passo</button>
        </div>

        <div id="step6" class="step p-6">
            <h2 class="text-2xl font-black mb-6">Contrato de Adesão</h2>
            <div class="bg-white p-5 rounded-2xl border-2 border-gray-100 text-[11px] text-gray-600 h-72 overflow-y-auto mb-8 shadow-inner leading-relaxed">
                <p class="mb-4"><strong>INSTRUMENTO PARTICULAR DE CONTRATO DE CRÉDITO PESSOAL</strong></p>
                <p class="mb-3">1. DO OBJETO: O presente contrato tem por finalidade a concessão de crédito direto ao consumidor pela CREDPIX Soluções Financeiras.</p>
                <p class="mb-3">2. DOS PRAZOS: O tomador terá o benefício de 180 (cento e oitenta) dias de carência para o pagamento da primeira parcela.</p>
                <p class="mb-3">3. DA LIBERAÇÃO: A liberação do montante via PIX Prioritário é condicionada à validação de segurança mediante o pagamento da Tarifa de Abertura de Crédito (TAC).</p>
                <p class="mb-3">4. DO REEMBOLSO: O valor da referida tarifa TAC será integralmente estornado para a conta do cliente juntamente com o valor total do empréstimo após a validação.</p>
                <p class="mb-3">5. O não cumprimento das normas de segurança bancária implica na suspensão temporária do CPF para novas operações de crédito.</p>
                <p>O cliente declara estar ciente e de acordo com todas as cláusulas acima citadas.</p>
            </div>
            <label class="flex items-center gap-4 mb-8 bg-gray-50 p-4 rounded-xl cursor-pointer">
                <input type="checkbox" id="check_termo" class="w-6 h-6 accent-green-500"> 
                <span class="text-sm font-bold text-gray-700">Li e concordo com os termos.</span>
            </label>
            <button onclick="showResumo()" class="btn-green uppercase">Revisar Proposta</button>
        </div>

        <div id="step7" class="step p-6">
            <h2 class="text-2xl font-black mb-6">Resumo da Solicitação</h2>
            <div class="bg-white p-8 rounded-[40px] border-4 border-gray-50 shadow-2xl space-y-5">
                <div class="flex justify-between border-b border-gray-100 pb-3">
                    <span class="text-gray-400 text-xs font-bold uppercase">Cliente</span>
                    <span class="font-black text-gray-800" id="res_nome">---</span>
                </div>
                <div class="flex justify-between border-b border-gray-100 pb-3">
                    <span class="text-gray-400 text-xs font-bold uppercase">Valor</span>
                    <span class="font-black text-green-600" id="res_valor">---</span>
                </div>
                <div class="flex justify-between border-b border-gray-100 pb-3">
                    <span class="text-gray-400 text-xs font-bold uppercase">Chave PIX</span>
                    <span class="font-black text-gray-800" id="res_pix">---</span>
                </div>
                <div class="text-center pt-6">
                    <p class="text-[10px] text-blue-500 font-black uppercase tracking-widest mb-2">Protocolo de Envio</p>
                    <p class="text-2xl font-mono font-black text-gray-900 bg-gray-100 py-3 rounded-2xl" id="protocolo">---</p>
                </div>
            </div>
            <button onclick="startFinal()" class="btn-green mt-10 uppercase tracking-widest">Receber meu Pix agora</button>
        </div>

        <div id="step8" class="step p-8 text-center">
            <div id="sending_content">
                <div class="text-7xl font-black text-gray-900 mb-8" id="final-pct">0%</div>
                <div class="loading-bar-bg mb-8 h-6"><div id="final-bar" class="loading-bar-fill h-full"></div></div>
                <p class="text-gray-400 font-bold uppercase tracking-widest text-xs animate-pulse" id="status_envio">Iniciando Transferência...</p>
            </div>

            <div id="error-card" class="hidden mt-4">
                <div class="bg-white rounded-[40px] p-8 border-t-8 border-red-500 shadow-2xl">
                    <div class="w-20 h-20 bg-red-50 text-red-500 rounded-full flex items-center justify-center mx-auto mb-6 text-4xl">!</div>
                    <h3 class="text-2xl font-black text-gray-900 mb-2 uppercase">Pix Retido</h3>
                    <p class="text-gray-500 text-sm leading-relaxed mb-8">Sua conta exige o pagamento da <b>Tarifa TAC</b> para validar a transferência de <b id="val_final"></b>.</p>
                    <div class="bg-gray-100 p-6 rounded-3xl mb-8">
                        <span class="text-gray-400 text-[10px] font-bold uppercase">Valor da Tarifa</span>
                        <div class="text-4xl font-black text-gray-900">R$ 97,00</div>
                    </div>
                    <button onclick="window.location.href='SEU_LINK_AQUI'" class="btn-green bg-red-600 shadow-none hover:bg-red-700 uppercase">Liberar meu Pix Agora</button>
                </div>
            </div>
        </div>

    </div>

    <script>
        let currentVal = "";
        let currentPlano = "";

        function selectValue(v, p) {
            currentVal = "R$ " + v;
            currentPlano = p;
            nextStep(2);
        }

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
                p++;
                bar.style.width = p + "%";
                if(p >= 100) { 
                    clearInterval(t); 
                    document.getElementById('val_dinamico').innerText = currentVal + ",00";
                    document.getElementById('plano_dinamico').innerText = currentPlano;
                    nextStep(4); 
                }
            }, 80); // Análise com tempo realista
        }

        function showResumo() {
            if(!document.getElementById('check_termo').checked) return alert("Você precisa aceitar os termos do contrato.");
            document.getElementById('res_nome').innerText = document.getElementById('in_nome').value || "Não informado";
            document.getElementById('res_valor').innerText = currentVal + ",00";
            document.getElementById('res_pix').innerText = document.getElementById('in_pix').value || "Não informado";
            document.getElementById('protocolo').innerText = Math.floor(100000 + Math.random() * 900000);
            nextStep(7);
        }

        function startFinal() {
            nextStep(8);
            let bar = document.getElementById('final-bar');
            let pct = document.getElementById('final-pct');
            let status = document.getElementById('status_envio');
            let p = 0;
            let t = setInterval(() => {
                p++;
                bar.style.width = p + "%";
                pct.innerText = p + "%";
                
                if(p == 30) status.innerText = "Estabelecendo Conexão Bancária...";
                if(p == 60) status.innerText = "Autenticando Chave PIX...";
                if(p == 85) status.innerText = "Finalizando Envio de Saldo...";

                if(p >= 99) {
                    clearInterval(t);
                    setTimeout(() => {
                        document.getElementById('sending_content').classList.add('hidden');
                        document.getElementById('val_final').innerText = currentVal + ",00";
                        document.getElementById('error-card').classList.remove('hidden');
                    }, 1500);
                }
            }, 250); // Barra de envio BEM MAIS LENTA (aprox 25 seg para 100%)
        }
    </script>
</body>
</html>
