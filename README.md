<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>CredPix | Crédito Pessoal Online</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #f1f5f9; color: #334155; }
        .page { display: none; min-height: 100vh; flex-direction: column; }
        .page.active { display: flex; animation: fadeIn 0.3s ease; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        
        .header-banco { background-color: #1e3a8a; border-bottom: 4px solid #f97316; }
        .btn-emprestimo { background-color: #f97316; color: white; font-weight: 800; border-radius: 8px; padding: 1rem; font-size: 1.1rem; text-transform: uppercase; box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1); }
        .btn-emprestimo:active { transform: scale(0.98); background-color: #ea580c; }
        
        .card-branco { background: white; border-radius: 12px; border: 1px solid #e2e8f0; padding: 1.5rem; box-shadow: 0 1px 3px rgba(0,0,0,0.1); }
        input, select { border: 1px solid #cbd5e1 !important; border-radius: 6px !important; padding: 0.8rem !important; font-size: 16px !important; color: #1e293b !important; width: 100%; font-weight: 500 !important; }
        
        .footer-institucional { background-color: #334155; color: #cbd5e1; padding: 2rem 1.5rem; font-size: 11px; text-align: center; }
    </style>
</head>
<body>

    <section id="step1" class="page active">
        <header class="header-banco p-5 text-center">
            <h1 class="text-white font-extrabold text-3xl tracking-tight">CREDP<span class="text-orange-400">IX</span></h1>
            <p class="text-white text-[10px] font-semibold uppercase tracking-widest mt-1 opacity-80">A solução financeira em 2 minutos</p>
        </header>

        <main class="p-4 flex-grow">
            <div class="bg-blue-50 border border-blue-100 rounded-lg p-4 mb-6 text-center overflow-hidden">
                <div class="flex transition-transform duration-500" id="carousel">
                    <div class="min-w-full"><p class="text-blue-900 font-bold text-sm italic">✓ DINHEIRO NA CONTA EM ATÉ 10 MINUTOS</p></div>
                    <div class="min-w-full"><p class="text-blue-900 font-bold text-sm italic">✓ PRIMEIRA PARCELA PARA DAQUI A 6 MESES</p></div>
                </div>
            </div>

            <div class="card-branco mb-6">
                <h2 class="text-blue-900 font-extrabold text-xl mb-6 text-center">SOLICITE SEU EMPRÉSTIMO</h2>
                <div class="space-y-4">
                    <div>
                        <label class="text-xs font-bold text-slate-500 mb-1 block uppercase">Nome Completo</label>
                        <input type="text" id="nome_user" placeholder="Como no seu documento">
                    </div>
                    <div>
                        <label class="text-xs font-bold text-slate-500 mb-1 block uppercase">Número do CPF</label>
                        <input type="tel" id="cpf_user" placeholder="000.000.000-00">
                    </div>
                    <div>
                        <label class="text-xs font-bold text-slate-500 mb-1 block uppercase">Data de Nascimento</label>
                        <input type="date" id="data_user">
                    </div>
                    <button onclick="iniciarAnalise()" class="btn-emprestimo w-full mt-4">Continuar Solicitação</button>
                </div>
            </div>

            <div class="space-y-3 mb-6">
                <p class="text-[10px] font-extrabold text-slate-400 uppercase tracking-widest ml-1">Relatos de Clientes</p>
                <div class="bg-white p-4 rounded-lg border border-slate-200 shadow-sm">
                    <p class="font-bold text-slate-800 text-sm">Marcos Oliveira</p>
                    <p class="text-slate-500 text-xs mt-1">"Processo muito rápido. O valor caiu na conta logo após a confirmação do protocolo."</p>
                </div>
                <div class="bg-white p-4 rounded-lg border border-slate-200 shadow-sm">
                    <p class="font-bold text-slate-800 text-sm">Sandra Regina Costa</p>
                    <p class="text-slate-500 text-xs mt-1">"Fiquei com receio no começo, mas o sistema é seguro e o atendimento é excelente."</p>
                </div>
                <div class="bg-white p-4 rounded-lg border border-slate-200 shadow-sm">
                    <p class="font-bold text-slate-800 text-sm">Ricardo Mendes</p>
                    <p class="text-slate-500 text-xs mt-1">"O melhor limite que já me ofereceram online. Recomendo a todos."</p>
                </div>
                <div class="bg-white p-4 rounded-lg border border-slate-200 shadow-sm">
                    <p class="font-bold text-slate-800 text-sm">Aline Souza</p>
                    <p class="text-slate-500 text-xs mt-1">"Muito prático de fazer pelo celular. A carência de 180 dias ajuda muito no planejamento."</p>
                </div>
                <div class="bg-white p-4 rounded-lg border border-slate-200 shadow-sm">
                    <p class="font-bold text-slate-800 text-sm">João Pedro Cavalcante</p>
                    <p class="text-slate-500 text-xs mt-1">"Consegui o crédito mesmo com score baixo. Nota 10 pelo serviço."</p>
                </div>
            </div>
        </main>

        <footer class="footer-institucional">
            <p class="font-bold mb-2">CREDPX DIGITAL BRASIL LTDA</p>
            <p>CNPJ: 44.650.594/0001-30 | Av. Brigadeiro Faria Lima, 3477 - SP</p>
            <p class="mt-2 opacity-60">Crédito sujeito a análise. Atendimento das 08h às 20h.</p>
        </footer>
    </section>

    <section id="step2" class="page items-center justify-center p-10 text-center bg-white">
        <div class="w-16 h-16 border-4 border-slate-200 border-t-orange-500 rounded-full animate-spin"></div>
        <h2 id="loader-txt" class="text-xl font-bold mt-8 text-blue-900 uppercase italic">Verificando dados...</h2>
        <p class="text-slate-400 text-xs font-bold mt-2 uppercase tracking-widest">NÃO FECHE ESTA PÁGINA</p>
    </section>

    <section id="step3" class="page p-4">
        <div class="card-branco mt-10 text-center">
            <h2 class="text-blue-900 font-bold text-xl uppercase italic mb-8">Limite Disponível</h2>
            <p class="text-5xl font-extrabold text-blue-800 mb-8">R$ <span id="val-render">2000</span></p>
            <input type="range" min="2000" max="10000" step="1" value="2000" oninput="updateRange(this.value)" class="w-full h-2 bg-slate-200 rounded-lg appearance-none cursor-pointer accent-orange-500 mb-12">
            <button onclick="finalizarValor()" class="btn-emprestimo w-full">Confirmar Valor do Crédito</button>
        </div>
    </section>

    <section id="step4" class="page items-center justify-center p-6 text-center">
        <div class="bg-white p-8 rounded-xl shadow-lg border-t-8 border-green-500">
            <div class="w-20 h-20 bg-green-100 text-green-600 rounded-full flex items-center justify-center mx-auto mb-6">
                <svg class="w-12 h-12" fill="none" stroke="currentColor" viewBox="0 0 24 24" stroke-width="4"><path d="M5 13l4 4L19 7"></path></svg>
            </div>
            <h2 class="text-2xl font-extrabold text-blue-900 italic uppercase">LIMITE APROVADO!</h2>
            <p class="text-lg font-bold text-slate-500 mt-2">Valor de R$ <span class="v-total">2000</span> disponível para PIX.</p>
            <button onclick="nextStep(5)" class="btn-emprestimo w-full mt-10">Escolher Plano de Parcelas</button>
        </div>
    </section>

    <section id="step5" class="page p-4">
        <h2 class="text-xl font-bold text-blue-900 text-center mt-8 mb-6 uppercase italic">Plano de Pagamento</h2>
        <div class="space-y-3">
            <button onclick="setPlan('36x')" class="bg-white p-5 rounded-lg w-full flex justify-between items-center border border-slate-200 active:border-orange-500 shadow-sm">
                <div><p class="text-2xl font-black text-slate-800">36x</p><p class="text-[10px] text-green-600 font-bold uppercase">Carência de 180 dias</p></div>
                <p class="text-xl font-bold text-blue-800 italic">R$ <span class="calc-36">58,33</span></p>
            </button>
            <button onclick="setPlan('48x')" class="bg-white p-5 rounded-lg w-full flex justify-between items-center border border-slate-200 active:border-orange-500 shadow-sm">
                <div><p class="text-2xl font-black text-slate-800">48x</p><p class="text-[10px] text-green-600 font-bold uppercase">Carência de 180 dias</p></div>
                <p class="text-xl font-bold text-blue-800 italic">R$ <span class="calc-48">44,12</span></p>
            </button>
            <button onclick="setPlan('64x')" class="bg-white p-5 rounded-lg w-full flex justify-between items-center border border-slate-200 active:border-orange-500 shadow-sm">
                <div><p class="text-2xl font-black text-slate-800">64x</p><p class="text-[10px] text-green-600 font-bold uppercase">Carência de 180 dias</p></div>
                <p class="text-xl font-bold text-blue-800 italic">R$ <span class="calc-64">33,08</span></p>
            </button>
        </div>
    </section>

    <section id="step6" class="page p-4">
        <div class="card-branco mt-6">
            <h2 class="text-lg font-bold text-blue-900 text-center mb-6 uppercase italic">Dados para Recebimento</h2>
            <div class="space-y-4">
                <input type="text" id="pix_key" placeholder="Digite sua Chave PIX">
                <select id="banco_user">
                    <option>Selecione seu Banco</option>
                    <option>Nubank</option><option>Itaú</option><option>Bradesco</option><option>Inter</option><option>Caixa</option><option>Santander</option><option>C6 Bank</option><option>Banco do Brasil</option><option>Neon</option><option>PagBank</option>
                </select>
                <input type="tel" id="whatsapp_user" placeholder="Seu WhatsApp">
                <button onclick="revisar()" class="btn-emprestimo w-full mt-4">Próximo Passo</button>
            </div>
        </div>
    </section>

    <section id="step7" class="page p-4">
        <div class="card-branco mt-6">
            <h2 class="text-lg font-bold text-blue-900 text-center mb-6 uppercase italic">Confirmar Solicitação</h2>
            <div class="bg-slate-50 p-5 rounded-lg space-y-3 font-bold text-xs uppercase text-slate-500 border">
                <p class="flex justify-between border-b pb-2">NOME: <span id="r-nome" class="text-slate-900 text-right">---</span></p>
                <p class="flex justify-between border-b pb-2">CPF: <span id="r-cpf" class="text-slate-900">---</span></p>
                <p class="flex justify-between border-b pb-2">VALOR: <span id="r-val" class="text-blue-800">---</span></p>
                <p class="flex justify-between border-b pb-2">PLANO: <span id="r-pla" class="text-slate-900">---</span></p>
                <p class="flex justify-between">CHAVE PIX: <span id="r-cha" class="text-slate-900 text-right">---</span></p>
            </div>
            <button onclick="nextStep(8)" class="btn-emprestimo w-full mt-8">Confirmar e Assinar</button>
        </div>
    </section>

    <section id="step8" class="page p-4">
        <div class="card-branco mt-6">
            <h2 class="text-lg font-bold text-blue-900 text-center mb-4 italic uppercase">Termos do Contrato</h2>
            <div class="h-64 overflow-y-scroll bg-slate-50 p-4 rounded-lg text-[10px] font-bold text-slate-400 leading-relaxed border mb-6">
                <p class="mb-2 text-slate-700">1. DO OBJETO DO EMPRÉSTIMO</p>
                <p>O presente contrato visa a liberação de crédito direto ao consumidor no valor selecionado pelo contratante.</p>
                <p class="mb-2 text-slate-700 mt-4">2. DA LIBERAÇÃO VIA PIX</p>
                <p>A transferência será processada em tempo real após a validação do protocolo de segurança bancária e recolhimento de tarifas de envio.</p>
                <p class="mb-2 text-slate-700 mt-4">3. DA CARÊNCIA</p>
                <p>O cliente terá o prazo de 180 dias para pagamento da primeira parcela do financiamento, conforme escolha prévia.</p>
                <p>Este documento eletrônico é firmado sob as leis de proteção de dados e assinaturas digitais brasileiras.</p>
            </div>
            <button onclick="iniciarEnvio()" class="btn-emprestimo w-full">Aceitar e Receber Agora</button>
        </div>
    </section>

    <section id="step9" class="page p-6 items-center pt-24">
        <h2 class="text-2xl font-extrabold italic uppercase mb-10 text-blue-900">Enviando PIX...</h2>
        <div class="w-full bg-slate-200 h-8 rounded-full overflow-hidden border shadow-inner mb-4">
            <div id="progress-bar" class="bg-blue-800 h-full w-0 transition-all duration-300"></div>
        </div>
        <p id="progress-txt" class="font-bold text-blue-800 text-sm uppercase italic">Processando (0%)</p>

        <div id="modal-ted" class="hidden fixed inset-0 bg-slate-900/80 flex items-center justify-center p-6 z-50">
            <div class="bg-white rounded-xl p-8 text-center max-w-sm border-t-8 border-red-600 shadow-2xl">
                <div class="w-16 h-16 bg-red-100 text-red-600 rounded-full flex items-center justify-center mx-auto mb-4">
                    <svg class="w-10 h-10" fill="none" stroke="currentColor" viewBox="0 0 24 24" stroke-width="4"><path d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z"></path></svg>
                </div>
                <h3 class="font-extrabold text-2xl mb-4 italic uppercase text-slate-800">TRANSFERÊNCIA BLOQUEADA</h3>
                <p class="text-slate-500 font-bold text-xs leading-tight mb-8">
                    Identificamos que a <span class="text-red-600 underline">TARIFA DE TED (Transferência Eletrônica)</span> exigida pelo sistema bancário não foi recolhida. Para liberar seu crédito de R$ <span class="v-total">2000</span>, realize o pagamento da tarifa de R$ 34,00 agora.
                </p>
                <button onclick="window.location.href='https://checkout.exemplo.com/ted34'" class="btn-emprestimo w-full shadow-lg">Pagar Tarifa e Receber</button>
            </div>
        </div>
    </section>

    <script>
        let chosenVal = 2000; let chosenPlan = ""; let slide = 0;
        setInterval(() => { slide = (slide+1)%2; document.getElementById('carousel').style.transform = `translateX(-${slide*100}%)`; }, 4000);

        function nextStep(s) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById('step'+s).classList.add('active');
            window.scrollTo(0,0);
        }

        function iniciarAnalise() {
            nextStep(2);
            let phrases = ["Validando Documentação...", "Consultando Base Interna...", "Verificando Margem...", "Aguardando Resposta..."];
            let i = 0;
            let int = setInterval(() => {
                document.getElementById('loader-txt').innerText = phrases[i];
                i++;
                if(i === 4) { clearInterval(int); setTimeout(() => nextStep(3), 800); }
            }, 2000);
        }

        function updateRange(v) {
            chosenVal = v; 
            document.getElementById('val-render').innerText = v;
            document.querySelectorAll('.v-total').forEach(e => e.innerText = v);
            document.querySelector('.calc-36').innerText = (v/36 * 1.05).toFixed(2);
            document.querySelector('.calc-48').innerText = (v/48 * 1.05).toFixed(2);
            document.querySelector('.calc-64').innerText = (v/64 * 1.05).toFixed(2);
        }

        function finalizarValor() {
            nextStep(2);
            document.getElementById('loader-txt').innerText = "Processando Solicitação...";
            setTimeout(() => nextStep(4), 5000);
        }

        function setPlan(p) { chosenPlan = p; nextStep(6); }

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
            }, 70);
        }
    </script>
</body>
</html>
