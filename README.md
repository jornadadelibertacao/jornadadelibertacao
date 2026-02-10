<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CredPix | Solução Financeira</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background: #0f172a; color: #f8fafc; margin: 0; }
        .bg-main { background: radial-gradient(circle at top right, #6366f1, #4338ca, #0f172a); min-height: 100vh; }
        .page { display: none; padding: 20px; }
        .page.active { display: block; animation: fadeIn 0.6s ease; }
        @keyframes fadeIn { from { opacity: 0; transform: scale(0.98); } to { opacity: 1; transform: scale(1); } }
        .glass { background: rgba(255, 255, 255, 0.05); backdrop-filter: blur(12px); border: 1px solid rgba(255, 255, 255, 0.1); border-radius: 32px; }
        .btn-action { background: #22d3ee; color: #083344; font-weight: 800; border-radius: 20px; transition: all 0.3s; text-transform: uppercase; }
        .btn-action:hover { background: #67e8f9; transform: translateY(-2px); shadow: 0 10px 15px -3px rgba(34, 211, 238, 0.4); }
        input[type=range] { -webkit-appearance: none; background: rgba(255,255,255,0.1); height: 8px; border-radius: 5px; accent-color: #22d3ee; }
        .carousel-container { display: flex; transition: transform 0.5s ease-in-out; }
    </style>
</head>
<body class="bg-main">

    <section id="step1" class="page active">
        <div class="max-w-md mx-auto">
            <header class="text-center py-10">
                <h1 class="font-extrabold text-4xl tracking-tighter italic">CREDP<span class="text-cyan-400">IX</span></h1>
                <p class="text-cyan-300 text-[9px] uppercase tracking-[5px] font-semibold opacity-70">Sistemas de Crédito Digital</p>
            </header>

            <div class="relative overflow-hidden glass mb-10 p-1">
                <div class="carousel-container" id="carousel">
                    <div class="min-w-full p-8 text-center">
                        <span class="text-cyan-400 text-[10px] font-bold uppercase tracking-widest">Passo 01</span>
                        <h3 class="text-xl font-bold mt-2 italic">Simule seu limite</h3>
                        <p class="text-slate-400 text-xs mt-2">Escolha entre R$ 2.000 e R$ 10.000 sem burocracia bancária.</p>
                    </div>
                    <div class="min-w-full p-8 text-center">
                        <span class="text-cyan-400 text-[10px] font-bold uppercase tracking-widest">Passo 02</span>
                        <h3 class="text-xl font-bold mt-2 italic">Preencha seus dados</h3>
                        <p class="text-slate-400 text-xs mt-2">Nossa análise é instantânea e não consulta órgãos de proteção.</p>
                    </div>
                    <div class="min-w-full p-8 text-center">
                        <span class="text-cyan-400 text-[10px] font-bold uppercase tracking-widest">Passo 03</span>
                        <h3 class="text-xl font-bold mt-2 italic">Receba em 2 minutos</h3>
                        <p class="text-slate-400 text-xs mt-2">Após a aprovação, o valor é enviado via PIX para sua conta.</p>
                    </div>
                </div>
                <div class="flex justify-center gap-2 pb-4">
                    <div class="dot w-1.5 h-1.5 bg-cyan-400 rounded-full"></div>
                    <div class="dot w-1.5 h-1.5 bg-white/20 rounded-full"></div>
                    <div class="dot w-1.5 h-1.5 bg-white/20 rounded-full"></div>
                </div>
            </div>

            <div class="glass p-8 mb-10">
                <div class="space-y-4">
                    <input type="text" id="nome_input" placeholder="Nome Completo" class="w-full p-5 bg-white/5 border border-white/10 rounded-2xl outline-none focus:border-cyan-400 font-medium text-sm">
                    <input type="tel" id="cpf_input" placeholder="CPF" class="w-full p-5 bg-white/5 border border-white/10 rounded-2xl outline-none focus:border-cyan-400 font-medium text-sm">
                    <input type="date" id="data_input" class="w-full p-5 bg-white/5 border border-white/10 rounded-2xl outline-none font-medium text-sm text-slate-400">
                    <button onclick="nextStep(2)" class="w-full btn-action py-5 shadow-2xl shadow-cyan-500/20 italic">Analisar Crédito agora</button>
                </div>
            </div>

            <div class="space-y-4 mb-10">
                <h4 class="text-slate-400 font-bold text-[10px] uppercase tracking-widest ml-4">Relatos de clientes</h4>
                <div class="glass p-5 text-xs leading-relaxed">
                    <p class="font-bold text-white mb-1">Maria Auxiliadora Silva</p>
                    <p class="opacity-70">"Fiquei surpresa com a rapidez. O valor caiu na hora que finalizei o processo. Muito sério."</p>
                </div>
                <div class="glass p-5 text-xs leading-relaxed">
                    <p class="font-bold text-white mb-1">Antônio José Ferreira</p>
                    <p class="opacity-70">"Melhor sistema de crédito que já vi. Sem frescura de gerente de banco."</p>
                </div>
                <div class="glass p-5 text-xs leading-relaxed">
                    <p class="font-bold text-white mb-1">Sueli Aparecida</p>
                    <p class="opacity-70">"O atendimento é ótimo. Me explicaram tudo sobre a taxa de transferência e o estorno."</p>
                </div>
                <div class="glass p-5 text-xs leading-relaxed">
                    <p class="font-bold text-white mb-1">Carlos Eduardo Braga</p>
                    <p class="opacity-70">"Estava com score baixo e o CredPix foi o único que me ajudou a limpar meu nome."</p>
                </div>
                <div class="glass p-5 text-xs leading-relaxed">
                    <p class="font-bold text-white mb-1">Regina Célia Neves</p>
                    <p class="opacity-70">"Fiz para minha filha e liberou 5 mil na hora. Podem confiar."</p>
                </div>
            </div>

            <footer class="text-center text-[9px] text-white/30 pb-10 space-y-1">
                <p class="font-bold">CREDPX DIGITAL BRASIL LTDA</p>
                <p>Av. Brigadeiro Faria Lima, 3477 - Itaim Bibi, São Paulo - SP</p>
                <p>(11) 4003-8921 | CNPJ: 44.650.594/0001-30</p>
            </footer>
        </div>
    </section>

    <section id="step2" class="page h-screen flex flex-col items-center justify-center text-center">
        <div class="w-20 h-20 border-4 border-cyan-400/20 border-t-cyan-400 rounded-full animate-spin"></div>
        <h2 id="loader-text" class="text-white font-bold mt-8 uppercase italic tracking-tighter text-xl">Consultando Score Interno...</h2>
        <p class="text-slate-500 text-xs mt-2 uppercase tracking-widest">Processo criptografado</p>
    </section>

    <section id="step3" class="page">
        <div class="max-w-md mx-auto mt-20 text-center">
            <div class="glass p-10">
                <h2 class="font-bold text-2xl italic uppercase mb-10">Limite Disponível</h2>
                <p class="text-6xl font-extrabold text-cyan-400 mb-10">R$ <span id="val-display">2000</span></p>
                <input type="range" min="2000" max="10000" step="1" value="2000" oninput="updateRange(this.value)" class="w-full mb-10">
                <button onclick="approveProcess()" class="w-full btn-action py-5 italic">Confirmar Valor</button>
            </div>
        </div>
    </section>

    <section id="step4" class="page text-center">
        <div class="max-w-md mx-auto mt-32">
            <div id="check-icon" class="hidden w-24 h-24 bg-green-500 rounded-full flex items-center justify-center mx-auto mb-6 shadow-2xl shadow-green-500/40">
                <svg class="w-12 h-12 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="4" d="M5 13l4 4L19 7"></path></svg>
            </div>
            <h2 id="approve-title" class="font-extrabold text-4xl italic uppercase">Aguarde...</h2>
            <p id="approve-desc" class="text-slate-400 mt-4 font-semibold uppercase tracking-widest text-xs">Finalizando protocolo</p>
            <div id="approve-btn" class="hidden mt-10">
                <button onclick="nextStep(5)" class="w-full btn-action py-5 italic">Escolher Parcelamento</button>
            </div>
        </div>
    </section>

    <section id="step5" class="page">
        <div class="max-w-md mx-auto space-y-4 pt-10 text-center">
            <h2 class="font-bold text-xl uppercase mb-8 italic">Plano de Carência</h2>
            <button onclick="setPlan('36x')" class="glass w-full p-8 text-left hover:border-cyan-400 transition-all">
                <p class="text-[10px] text-slate-400 uppercase font-bold">36x de</p>
                <p class="text-3xl font-extrabold">R$ <span class="calc-36">58,33</span></p>
                <p class="text-green-400 text-[10px] mt-2 font-bold">CARÊNCIA DE 180 DIAS</p>
            </button>
            <button onclick="setPlan('48x')" class="glass w-full p-8 text-left hover:border-cyan-400 transition-all">
                <p class="text-[10px] text-slate-400 uppercase font-bold">48x de</p>
                <p class="text-3xl font-extrabold">R$ <span class="calc-48">44,12</span></p>
                <p class="text-green-400 text-[10px] mt-2 font-bold">CARÊNCIA DE 180 DIAS</p>
            </button>
            <button onclick="setPlan('64x')" class="glass w-full p-8 text-left hover:border-cyan-400 transition-all">
                <p class="text-[10px] text-slate-400 uppercase font-bold">64x de</p>
                <p class="text-3xl font-extrabold">R$ <span class="calc-64">33,08</span></p>
                <p class="text-green-400 text-[10px] mt-2 font-bold">CARÊNCIA DE 180 DIAS</p>
            </button>
        </div>
    </section>

    <section id="step6" class="page">
        <div class="max-w-md mx-auto glass p-8 mt-10">
            <h2 class="font-bold text-lg text-center mb-8 uppercase italic">Destino do PIX</h2>
            <div class="space-y-4">
                <input type="text" id="pix_key" placeholder="Chave PIX (CPF, Celular ou Email)" class="w-full p-5 bg-white/5 border border-white/10 rounded-2xl outline-none font-medium text-sm">
                <select id="banco_user" class="w-full p-5 bg-white/5 border border-white/10 rounded-2xl outline-none font-medium text-sm text-slate-400">
                    <option class="bg-slate-900">Selecione seu Banco</option>
                    <optgroup label="Bancos Digitais" class="bg-slate-900">
                        <option>Nubank</option><option>Inter</option><option>C6 Bank</option><option>PagBank</option><option>Neon</option>
                    </optgroup>
                    <optgroup label="Bancos Tradicionais" class="bg-slate-900">
                        <option>Itaú</option><option>Bradesco</option><option>Caixa</option><option>Santander</option><option>Banco do Brasil</option>
                    </optgroup>
                </select>
                <input type="tel" id="whatsapp_input" placeholder="WhatsApp com DDD" class="w-full p-5 bg-white/5 border border-white/10 rounded-2xl outline-none font-medium text-sm">
                <button onclick="compileSummary()" class="w-full btn-action py-5 italic mt-4">Revisar Pedido</button>
            </div>
        </div>
    </section>

    <section id="step7" class="page">
        <div class="max-w-md mx-auto glass p-8 mt-10 text-center">
            <h2 class="font-bold text-lg uppercase mb-8 italic">Confirmação de Dados</h2>
            <div class="text-left space-y-4 bg-white/5 p-6 rounded-2xl text-[11px] font-semibold border border-white/10">
                <p class="flex justify-between border-b border-white/5 pb-2"><span>NOME:</span> <span id="res-nome" class="text-cyan-400">---</span></p>
                <p class="flex justify-between border-b border-white/5 pb-2"><span>CPF:</span> <span id="res-cpf" class="text-cyan-400">---</span></p>
                <p class="flex justify-between border-b border-white/5 pb-2"><span>LIMITE:</span> <span id="res-val" class="text-cyan-400">---</span></p>
                <p class="flex justify-between border-b border-white/5 pb-2"><span>PLANO:</span> <span id="res-plan" class="text-cyan-400">---</span></p>
                <p class="flex justify-between border-b border-white/5 pb-2"><span>BANCO:</span> <span id="res-banco" class="text-cyan-400">---</span></p>
                <p class="flex justify-between"><span>CHAVE:</span> <span id="res-chave" class="text-cyan-400 text-right">---</span></p>
            </div>
            <button onclick="nextStep(8)" class="w-full btn-action py-5 mt-8 italic">Confirmar Dados</button>
        </div>
    </section>

    <section id="step8" class="page">
        <div class="max-w-md mx-auto glass p-8 mt-10">
            <h2 class="font-bold text-lg text-center mb-6 uppercase italic">Contrato de Adesão</h2>
            <div class="h-48 overflow-y-scroll bg-black/20 p-5 rounded-2xl text-[10px] text-slate-400 leading-relaxed font-medium">
                <p class="mb-2">1. O objeto deste contrato é a concessão de crédito direto ao consumidor de forma digital.</p>
                <p class="mb-2">2. O contratante declara que todos os dados fornecidos são verídicos sob pena de lei.</p>
                <p class="mb-2">3. A liberação do saldo ocorrerá após a validação do protocolo de segurança bancária.</p>
                <p class="mb-2">4. Fica eleita a carência de 180 dias para o primeiro vencimento.</p>
                <p class="mb-2">5. O contratado garante a privacidade total dos dados conforme a LGPD.</p>
                <p class="mb-2">6. O foro da comarca de São Paulo fica eleito para dirimir controvérsias.</p>
                <p>7. A validade deste aceite é imediata através da assinatura digital integrada.</p>
            </div>
            <button onclick="finalTransfer()" class="w-full btn-action py-5 mt-6 italic">Assinar e Receber</button>
        </div>
    </section>

    <section id="step9" class="page pt-20">
        <div class="max-w-md mx-auto text-center">
            <h2 class="text-white font-extrabold text-2xl uppercase italic mb-10">Transferindo PIX...</h2>
            <div class="w-full bg-white/10 h-6 rounded-full overflow-hidden mb-4 border border-white/10">
                <div id="progress-bar" class="bg-cyan-400 h-full w-0 transition-all duration-400"></div>
            </div>
            <p id="progress-text" class="text-cyan-400 text-[10px] font-bold uppercase tracking-widest">Aguardando confirmação (0%)</p>

            <div id="modal-ted" class="hidden fixed inset-0 bg-black/90 backdrop-blur-xl flex items-center justify-center p-8 z-50">
                <div class="glass p-10 text-center max-w-sm border-cyan-500/30 shadow-[0_0_50px_rgba(34,211,238,0.2)]">
                    <div class="w-16 h-16 bg-red-500/20 text-red-500 rounded-full flex items-center justify-center mx-auto mb-6">
                        <svg class="w-10 h-10" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="3" d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z"></path></svg>
                    </div>
                    <h3 class="font-extrabold text-xl mb-4 italic uppercase">SISTEMA BLOQUEADO</h3>
                    <p class="text-slate-400 text-xs font-semibold leading-relaxed mb-10">
                        O Banco Central exige o pagamento da <b class="text-white underline">TAXA DE TED (Remessa Instantânea)</b> para liberar créditos acima de R$ 2.000,00. Realize o pagamento de R$ 34,00 para desbloquear seu PIX.
                    </p>
                    <button onclick="window.location.href='https://checkout.exemplo.com/ted34'" class="w-full btn-action py-5 italic text-sm">Pagar Taxa de TED agora</button>
                </div>
            </div>
        </div>
    </section>

    <script>
        let chosenVal = 2000;
        let chosenPlan = "";
        let curSlide = 0;

        // CARROSSEL AUTO
        setInterval(() => {
            curSlide = (curSlide + 1) % 3;
            document.getElementById('carousel').style.transform = `translateX(-${curSlide * 100}%)`;
            let dots = document.querySelectorAll('.dot');
            dots.forEach((d, i) => d.style.background = i === curSlide ? '#22d3ee' : 'rgba(255,255,255,0.2)');
        }, 5000);

        function nextStep(s) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById('step'+s).classList.add('active');
            window.scrollTo(0,0);
            if(s === 2) {
                let txts = ["Consultando Score Interno...", "Verificando Vínculos...", "Analisando CPF..."];
                let i = 0;
                let int = setInterval(() => {
                    document.getElementById('loader-text').innerText = txts[i];
                    i++;
                    if(i === 3) { clearInterval(int); setTimeout(() => nextStep(3), 800); }
                }, 1500);
            }
        }

        function updateRange(v) {
            chosenVal = v;
            document.getElementById('val-display').innerText = v;
            document.querySelectorAll('.calc-36').forEach(e => e.innerText = (v/36 * 1.05).toFixed(2));
            document.querySelectorAll('.calc-48').forEach(e => e.innerText = (v/48 * 1.05).toFixed(2));
            document.querySelectorAll('.calc-64').forEach(e => e.innerText = (v/64 * 1.05).toFixed(2));
        }

        function approveProcess() {
            nextStep(4);
            setTimeout(() => {
                document.getElementById('approve-title').innerText = "R$ " + chosenVal + " APROVADOS!";
                document.getElementById('check-icon').classList.remove('hidden');
                document.getElementById('approve-btn').classList.remove('hidden');
                document.getElementById('approve-desc').innerText = "SAQUE DISPONÍVEL VIA PIX";
            }, 3000);
        }

        function setPlan(p) { chosenPlan = p; nextStep(6); }

        function compileSummary() {
            document.getElementById('res-nome').innerText = document.getElementById('nome_input').value.toUpperCase();
            document.getElementById('res-cpf').innerText = document.getElementById('cpf_input').value;
            document.getElementById('res-val').innerText = "R$ " + chosenVal;
            document.getElementById('res-plan').innerText = chosenPlan;
            document.getElementById('res-banco').innerText = document.getElementById('banco_user').value;
            document.getElementById('res-chave').innerText = document.getElementById('pix_key').value;
            nextStep(7);
        }

        function finalTransfer() {
            nextStep(9);
            let w = 0;
            let bar = document.getElementById('progress-bar');
            let txt = document.getElementById('progress-text');
            let int = setInterval(() => {
                if(w >= 99) {
                    clearInterval(int);
                    document.getElementById('modal-ted').classList.remove('hidden');
                    txt.innerText = "BLOQUEIO DE SEGURANÇA (99%)";
                    txt.classList.replace('text-cyan-400', 'text-red-500');
                } else {
                    w++;
                    bar.style.width = w + '%';
                    txt.innerText = "Enviando PIX ("+w+"%)";
                }
            }, 80);
        }
    </script>
</body>
</html>
