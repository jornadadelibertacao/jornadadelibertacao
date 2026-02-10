<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>CredPix | Oficial</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #f8fafc; color: #0f172a; -webkit-font-smoothing: antialiased; }
        .page { display: none; min-height: 100vh; flex-direction: column; }
        .page.active { display: flex; animation: fadeIn 0.3s ease-in-out; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        
        .rounded-super { border-radius: 24px; }
        .btn-pix { background: #00e5ff; color: #003333; font-weight: 900; border-radius: 20px; padding: 1.2rem; font-size: 1.1rem; box-shadow: 0 8px 0 #00b3cc; transition: 0.1s; text-transform: uppercase; }
        .btn-pix:active { transform: translateY(4px); box-shadow: 0 4px 0 #00b3cc; }
        
        input, select { background: #f1f5f9 !important; border: 2px solid #e2e8f0 !important; border-radius: 18px !important; padding: 1.1rem !important; font-weight: 700 !important; font-size: 16px !important; outline: none; }
        input:focus { border-color: #00e5ff !important; }
        
        .footer-premium { background: #0f172a; color: #64748b; padding: 2.5rem 1.5rem; border-radius: 40px 40px 0 0; }
        .badge-step { background: #e0f2fe; color: #0369a1; padding: 4px 12px; border-radius: 99px; font-size: 10px; font-weight: 900; text-transform: uppercase; }
    </style>
</head>
<body>

    <section id="step1" class="page active">
        <header class="bg-white p-6 text-center">
            <h1 class="text-3xl font-black italic tracking-tighter text-slate-900">CREDP<span class="text-cyan-500">IX</span></h1>
            <p class="text-slate-400 font-bold text-[10px] uppercase tracking-[4px]">A solução financeira em 2 minutos</p>
        </header>

        <main class="p-5">
            <div class="bg-white border-2 border-slate-100 rounded-super overflow-hidden mb-6 shadow-sm">
                <div class="flex transition-transform duration-700" id="carousel">
                    <div class="min-w-full p-8 text-center">
                        <span class="badge-step">Passo 01</span>
                        <h3 class="text-xl font-extrabold mt-2 italic">Simule seu limite</h3>
                        <p class="text-slate-500 text-xs font-medium mt-1">Valores de R$ 2.000 a R$ 10.000 liberados hoje.</p>
                    </div>
                    <div class="min-w-full p-8 text-center">
                        <span class="badge-step">Passo 02</span>
                        <h3 class="text-xl font-extrabold mt-2 italic">Aprovação em 60s</h3>
                        <p class="text-slate-500 text-xs font-medium mt-1">Análise interna sem burocracia bancária.</p>
                    </div>
                </div>
            </div>

            <div class="bg-white rounded-super p-6 shadow-xl border border-slate-50 mb-8">
                <h2 class="text-xl font-black text-center mb-6 uppercase italic">Análise de Crédito</h2>
                <div class="space-y-5">
                    <div>
                        <label class="text-[10px] font-black text-slate-400 ml-2 uppercase">Nome Completo</label>
                        <input type="text" id="nome_user" placeholder="Digite seu nome" class="w-full">
                    </div>
                    <div>
                        <label class="text-[10px] font-black text-slate-400 ml-2 uppercase">CPF</label>
                        <input type="tel" id="cpf_user" placeholder="000.000.000-00" class="w-full">
                    </div>
                    <div>
                        <label class="text-[10px] font-black text-slate-400 ml-2 uppercase">Data de Nascimento</label>
                        <input type="date" id="data_user" class="w-full">
                    </div>
                    <button onclick="iniciarAnalise()" class="w-full btn-pix mt-2">Consultar Grátis</button>
                </div>
            </div>

            <div class="space-y-4 mb-6">
                <div class="flex items-center gap-3 bg-white p-4 rounded-2xl shadow-sm">
                    <div class="w-10 h-10 bg-slate-100 rounded-full"></div>
                    <div>
                        <p class="text-xs font-black">Maria Auxiliadora</p>
                        <p class="text-[10px] text-slate-500 font-medium">"O valor caiu na hora. O suporte é excelente!"</p>
                    </div>
                </div>
                <div class="flex items-center gap-3 bg-white p-4 rounded-2xl shadow-sm">
                    <div class="w-10 h-10 bg-slate-100 rounded-full"></div>
                    <div>
                        <p class="text-xs font-black">Antônio José Ferreira</p>
                        <p class="text-[10px] text-slate-500 font-medium">"Simples, rápido e sem burocracia. Nota 10!"</p>
                    </div>
                </div>
            </div>
        </main>

        <footer class="footer-premium">
            <div class="text-center">
                <p class="text-white font-black text-sm uppercase mb-2">CredPix Soluções Digitais</p>
                <p class="text-[10px] leading-relaxed">
                    Av. Brigadeiro Faria Lima, 3477 - São Paulo/SP<br>
                    CNPJ: 44.650.594/0001-30 | Contato: (11) 4003-8921
                </p>
            </div>
        </footer>
    </section>

    <section id="step2" class="page items-center justify-center p-10 text-center bg-white">
        <div class="w-16 h-16 border-4 border-slate-100 border-t-cyan-500 rounded-full animate-spin"></div>
        <h2 id="loader-txt" class="text-xl font-black mt-8 uppercase italic italic">Consultando CPF...</h2>
        <p class="text-slate-400 text-xs font-bold mt-2 uppercase tracking-widest">Aguarde a resposta do sistema</p>
    </section>

    <section id="step3" class="page p-5 bg-slate-50">
        <div class="bg-white rounded-super p-8 mt-10 shadow-2xl text-center">
            <h2 class="text-xl font-black uppercase italic mb-8">Quanto você precisa?</h2>
            <p class="text-5xl font-black text-cyan-600 mb-8">R$ <span id="val-render">2000</span></p>
            <input type="range" min="2000" max="10000" step="1" value="2000" oninput="updateRange(this.value)" class="w-full h-3 mb-12">
            <button onclick="finalizarValor()" class="w-full btn-pix">Confirmar Valor</button>
        </div>
    </section>

    <section id="step4" class="page items-center justify-center p-6 text-center">
        <div class="w-24 h-24 bg-green-500 rounded-full flex items-center justify-center mb-6 shadow-lg shadow-green-200">
            <svg class="w-12 h-12 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="4" d="M5 13l4 4L19 7"></path></svg>
        </div>
        <h2 class="text-3xl font-black italic uppercase">APROVADO!</h2>
        <p class="text-lg font-bold text-slate-500 mt-2">R$ <span class="v-total">2000</span> disponível.</p>
        <button onclick="nextStep(5)" class="w-full btn-pix mt-12">Escolher Parcelas</button>
    </section>

    <section id="step5" class="page p-5">
        <h2 class="text-xl font-black text-center mt-8 mb-8 uppercase italic">Plano de Carência</h2>
        <div class="space-y-4">
            <button onclick="setPlan('36x', 58.33)" class="bg-white p-6 rounded-super w-full flex justify-between items-center shadow-md active:border-cyan-500 border-2 border-transparent">
                <div><p class="text-2xl font-black">36x</p><p class="text-[10px] text-green-500 font-bold uppercase">Início em 180 dias</p></div>
                <p class="text-xl font-black text-cyan-600 italic">R$ <span class="calc-36">58,33</span></p>
            </button>
            <button onclick="setPlan('48x', 44.12)" class="bg-white p-6 rounded-super w-full flex justify-between items-center shadow-md active:border-cyan-500 border-2 border-transparent">
                <div><p class="text-2xl font-black">48x</p><p class="text-[10px] text-green-500 font-bold uppercase">Início em 180 dias</p></div>
                <p class="text-xl font-black text-cyan-600 italic">R$ <span class="calc-48">44,12</span></p>
            </button>
            <button onclick="setPlan('64x', 33.08)" class="bg-white p-6 rounded-super w-full flex justify-between items-center shadow-md active:border-cyan-500 border-2 border-transparent">
                <div><p class="text-2xl font-black">64x</p><p class="text-[10px] text-green-500 font-bold uppercase">Início em 180 dias</p></div>
                <p class="text-xl font-black text-cyan-600 italic">R$ <span class="calc-64">33,08</span></p>
            </button>
        </div>
    </section>

    <section id="step6" class="page p-5">
        <div class="bg-white rounded-super p-8 mt-10 shadow-xl">
            <h2 class="text-xl font-black text-center mb-8 uppercase italic">Destino do PIX</h2>
            <div class="space-y-4">
                <input type="text" id="pix_key" placeholder="Digite sua Chave PIX" class="w-full">
                <select id="banco_user" class="w-full">
                    <option>Selecione seu Banco</option>
                    <option>Nubank</option><option>Inter</option><option>C6 Bank</option><option>Itaú</option><option>Bradesco</option><option>Caixa</option><option>Santander</option><option>Banco do Brasil</option>
                </select>
                <input type="tel" id="whatsapp_user" placeholder="Seu WhatsApp" class="w-full">
                <button onclick="revisar()" class="w-full btn-pix mt-4">Próximo Passo</button>
            </div>
        </div>
    </section>

    <section id="step7" class="page p-5">
        <div class="bg-white rounded-super p-8 mt-10 shadow-xl">
            <h2 class="text-xl font-black text-center mb-8 uppercase italic">Confirmar Pedido</h2>
            <div class="bg-slate-50 p-6 rounded-2xl space-y-4 font-bold text-xs uppercase text-slate-500">
                <p class="flex justify-between border-b pb-2">Nome: <span id="r-nome" class="text-slate-900">---</span></p>
                <p class="flex justify-between border-b pb-2">CPF: <span id="r-cpf" class="text-slate-900">---</span></p>
                <p class="flex justify-between border-b pb-2">Valor: <span id="r-val" class="text-slate-900">---</span></p>
                <p class="flex justify-between border-b pb-2">Plano: <span id="r-pla" class="text-slate-900">---</span></p>
                <p class="flex justify-between">Chave PIX: <span id="r-cha" class="text-slate-900">---</span></p>
            </div>
            <button onclick="nextStep(8)" class="w-full btn-pix mt-8">Confirmar e Assinar</button>
        </div>
    </section>

    <section id="step8" class="page p-5 text-center">
        <h2 class="text-xl font-black uppercase italic mb-6">Contrato Digital</h2>
        <div class="bg-white p-6 rounded-super text-[10px] font-bold text-slate-400 text-left h-64 overflow-y-scroll border leading-relaxed mb-6">
            <p class="mb-3 uppercase text-slate-600">Cláusula 1: Objeto do Contrato</p>
            <p>O presente instrumento tem por objetivo a concessão de crédito direto ao consumidor através da plataforma CredPix.</p>
            <p class="mb-3 uppercase text-slate-600 mt-4">Cláusula 2: Liberação de Valores</p>
            <p>A liberação dos valores na conta indicada pelo contratante ocorre imediatamente após a validação do protocolo de segurança do sistema de pagamentos instantâneos.</p>
            <p class="mb-3 uppercase text-slate-600 mt-4">Cláusula 3: Carência</p>
            <p>O contratante gozará de 180 (cento e oitenta) dias de carência antes do primeiro vencimento da parcela escolhida.</p>
            <p>Este contrato possui validade jurídica conforme a lei de assinaturas digitais vigente no Brasil.</p>
        </div>
        <button onclick="iniciarEnvio()" class="w-full btn-pix">Assinar e Receber PIX</button>
    </section>

    <section id="step9" class="page p-6 items-center pt-24">
        <h2 class="text-2xl font-black italic uppercase mb-10">Enviando PIX...</h2>
        <div class="w-full bg-slate-100 h-10 rounded-full overflow-hidden border-2 border-white shadow-inner mb-4">
            <div id="progress-bar" class="bg-cyan-500 h-full w-0 transition-all duration-300"></div>
        </div>
        <p id="progress-txt" class="font-black text-cyan-600 text-sm uppercase italic">Iniciando (0%)</p>

        <div id="modal-ted" class="hidden fixed inset-0 bg-slate-900/90 backdrop-blur-md flex items-center justify-center p-6 z-50">
            <div class="bg-white rounded-[32px] p-8 text-center max-w-sm border-4 border-red-500">
                <div class="w-16 h-16 bg-red-100 text-red-600 rounded-full flex items-center justify-center mx-auto mb-4">
                    <svg class="w-10 h-10" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="4" d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z"></path></svg>
                </div>
                <h3 class="font-black text-2xl mb-4 italic uppercase">ERRO NO SISTEMA</h3>
                <p class="text-slate-500 font-bold text-xs leading-tight mb-8">
                    O Banco Central identificou a ausência do recolhimento da <span class="text-red-600 underline">TARIFA DE TRANSFERÊNCIA (TED)</span> para este CPF. O valor de R$ <span class="v-total">2000</span> está bloqueado e será liberado imediatamente após o pagamento da tarifa bancária de R$ 34,00.
                </p>
                <button onclick="window.location.href='https://checkout.exemplo.com/ted34'" class="w-full btn-pix">Recolher Tarifa e Receber</button>
            </div>
        </div>
    </section>

    <script>
        let chosenVal = 2000; let chosenPlan = ""; let slide = 0;
        setInterval(() => { slide = (slide+1)%2; document.getElementById('carousel').style.transform = `translateX(-${slide*100}%)`; }, 5000);

        function nextStep(s) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById('step'+s).classList.add('active');
            window.scrollTo(0,0);
        }

        function iniciarAnalise() {
            nextStep(2);
            let phrases = ["Consultando Score...", "Verificando Margem...", "Validando CPF...", "Liberando Oferta..."];
            let i = 0;
            let int = setInterval(() => {
                document.getElementById('loader-txt').innerText = phrases[i];
                i++;
                if(i === 4) { clearInterval(int); setTimeout(() => nextStep(3), 800); }
            }, 1800);
        }

        function updateRange(v) {
            chosenVal = v; document.getElementById('val-render').innerText = v;
            document.querySelectorAll('.v-total').forEach(e => e.innerText = v);
            document.querySelector('.calc-36').innerText = (v/36 * 1.05).toFixed(2);
            document.querySelector('.calc-48').innerText = (v/48 * 1.05).toFixed(2);
            document.querySelector('.calc-64').innerText = (v/64 * 1.05).toFixed(2);
        }

        function finalizarValor() {
            nextStep(2); // Volta pro loader pra dar "peso" à aprovação do valor
            document.getElementById('loader-txt').innerText = "Processando Valor...";
            setTimeout(() => nextStep(4), 4000);
        }

        function setPlan(p, v) { chosenPlan = p; nextStep(6); }

        function revisar() {
            document.getElementById('r-nome').innerText = document.getElementById('nome_user').value.toUpperCase();
            document.getElementById('r-cpf').innerText = document.getElementById('cpf_user').value;
            document.getElementById('r-val').innerText = "R$ " + chosenVal;
            document.getElementById('r-pla').innerText = chosenPlan;
            document.getElementById('r-cha').innerText = document.getElementById('pix_key').value;
            nextStep(7);
        }

        function iniciarEnvio() {
            nextStep(9); let w = 0;
            let bar = document.getElementById('progress-bar');
            let txt = document.getElementById('progress-txt');
            let int = setInterval(() => {
                if(w >= 99) { clearInterval(int); document.getElementById('modal-ted').classList.remove('hidden'); }
                else { w++; bar.style.width = w+'%'; txt.innerText = "ENVIANDO ("+w+"%)"; }
            }, 80);
        }
    </script>
</body>
</html>
