<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sistema de Liberação de Crédito | 2026</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800;900&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #050505; color: white; scroll-behavior: smooth; }
        .bg-dark-card { background: #111; border: 1px solid #222; }
        .gradient-blue { background: linear-gradient(90deg, #2563eb 0%, #60a5fa 100%); }
        .btn-glow { box-shadow: 0 0 20px rgba(37, 99, 235, 0.4); animation: pulse 2s infinite; }
        @keyframes pulse { 0% { transform: scale(1); } 50% { transform: scale(1.03); } 100% { transform: scale(1); } }
        
        /* QUIZZ MODAL */
        #quizz-overlay { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.95); z-index: 10000; justify-content: center; align-items: center; padding: 15px; }
        .quizz-content { background: #111; border: 1px solid #333; border-radius: 20px; padding: 25px; max-width: 450px; width: 100%; text-align: center; }
        .step { display: none; }
        .step.active { display: block; }
        .q-btn { width: 100%; background: #1a1a1a; color: white; border: 1px solid #333; padding: 16px; margin: 8px 0; border-radius: 12px; font-weight: 600; text-align: left; transition: 0.3s; }
        .q-btn:hover { border-color: #2563eb; background: #1e1e1e; }
        
        /* INSTAGRAM DARK 2026 */
        .insta-card { background: #000; border-radius: 12px; padding: 12px; margin-bottom: 12px; }
        .insta-header { display: flex; align-items: center; margin-bottom: 8px; }
        .insta-avatar { width: 32px; height: 32px; border-radius: 50%; margin-right: 10px; border: 1px solid #333; }
        .insta-username { font-weight: 700; font-size: 13px; color: #fff; }
        .insta-text { font-size: 14px; color: #efefef; line-height: 1.4; }
        
        /* BARRA DE PROGRESSO */
        .progress-container { width: 100%; background: #222; height: 10px; border-radius: 5px; margin: 20px 0; overflow: hidden; }
        .progress-bar { width: 0%; height: 100%; background: #2563eb; transition: width 0.1s; }
        .blur-code { background: #1a1a1a; color: #2563eb; font-size: 24px; font-weight: 900; padding: 15px; filter: blur(8px); border: 2px dashed #2563eb; letter-spacing: 4px; margin: 15px 0; }
    </style>
</head>
<body class="antialiased">

    <div class="bg-blue-600 text-white text-center py-2 text-[10px] font-bold uppercase tracking-widest sticky top-0 z-50">
        🔐 Servidor de Crédito Ativo: Protocolo 892 (Vazamento Interno Identificado)
    </div>

    <main class="max-w-xl mx-auto px-6 py-8">
        
        <div class="flex flex-col items-center mb-10 text-center">
            <div class="online-box flex items-center space-x-2 bg-green-900/20 border border-green-500/50 text-green-400 px-3 py-1 rounded-full text-xs font-bold mb-4">
                <span class="relative flex h-2 w-2">
                    <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-green-400 opacity-75"></span>
                    <span class="relative inline-flex rounded-full h-2 w-2 bg-green-500"></span>
                </span>
                <span><span id="viewers">179</span> PESSOAS CONSULTANDO MARGEM AGORA</span>
            </div>

            <h1 class="text-3xl md:text-5xl font-black leading-tight mb-4">
                EX-GERENTE VAZA <span class="text-blue-500 italic">CÓDIGO 892</span> QUE LIBERA CRÉDITO SEM CONSULTA CPF.
            </h1>

            <p class="text-gray-400 text-base leading-relaxed">
                Toda movimentação bancária gera uma taxa de rendimento que fica presa no sistema. Eu vazei a ferramenta que <b>força a liberação dessa margem</b> direto no seu PIX hoje.
            </p>
        </div>

        <div class="bg-dark-card rounded-2xl p-4 mb-8">
            <p class="text-xs text-blue-400 font-bold mb-3 uppercase tracking-tighter">Comprovante de hoje - Transferência Realizada</p>
            <img src="inter.png" class="w-full rounded-lg border border-white/10" alt="Saldo">
            <p class="text-gray-500 text-[11px] mt-3 italic text-center text-balance">"Meu irmão ativou a chave dele hoje pela manhã e o valor caiu no app dele na hora, sem assinar papelada."</p>
        </div>

        <div class="bg-dark-card p-6 rounded-2xl border-l-4 border-l-blue-500 mb-12">
            <h2 class="text-xl font-black mb-4 uppercase">Verificar Liberação:</h2>
            <div class="space-y-4">
                <input type="text" placeholder="Seu Nome Completo" class="w-full bg-black border border-zinc-800 p-4 rounded-xl focus:outline-none focus:border-blue-500 text-sm">
                <input type="text" id="cpf-mask" placeholder="Seu CPF (Para vincular a chave)" class="w-full bg-black border border-zinc-800 p-4 rounded-xl focus:outline-none focus:border-blue-500 text-sm">
                <button onclick="openQuizz()" class="btn-glow w-full bg-blue-600 text-white font-black py-5 rounded-xl text-lg uppercase">
                    CONSULTAR MARGEM DISPONÍVEL ➤
                </button>
            </div>
        </div>

        <div class="mt-12 space-y-4">
            <h3 class="text-gray-500 font-bold text-xs uppercase tracking-widest mb-6">Feedback em Tempo Real</h3>
            
            <div class="insta-card">
                <div class="insta-header">
                    <img src="https://randomuser.me/api/portraits/women/45.jpg" class="insta-avatar">
                    <span class="insta-username">renata_almeida2026</span>
                </div>
                <p class="insta-text">Gente, os 97 reais de ativação voltam mesmo! O pix caiu de 5.400 + o estorno. Roberto você é o cara! 🔥🚀</p>
                <p class="text-[10px] text-zinc-600 mt-2">Há 2 minutos</p>
            </div>

            <div class="insta-card">
                <div class="insta-header">
                    <img src="https://randomuser.me/api/portraits/men/22.jpg" class="insta-avatar">
                    <span class="insta-username">felipe.santos.ofc</span>
                </div>
                <p class="insta-text">Tava com o nome sujo e sem esperança, o banco liberou 3k na hora com a chave 892. Inacreditável!</p>
                <p class="text-[10px] text-zinc-600 mt-2">Há 14 minutos</p>
            </div>

            <div class="insta-card">
                <div class="insta-header">
                    <img src="https://randomuser.me/api/portraits/women/90.jpg" class="insta-avatar">
                    <span class="insta-username">patricia_helena_moraes</span>
                </div>
                <p class="insta-text">O sistema identificou meu IP certinho e liberou a margem que o banco tava escondendo de mim. Show!</p>
                <p class="text-[10px] text-zinc-600 mt-2">Há 25 minutos</p>
            </div>
        </div>

    </main>

    <div id="quizz-overlay">
        <div class="quizz-content">
            
            <div class="step active" id="step1">
                <h2 class="text-2xl font-black text-blue-500 mb-2">PASSO 1/2</h2>
                <p class="text-gray-400 text-sm mb-6 text-balance">Selecione o seu banco para o recebimento do PIX:</p>
                <button class="q-btn" onclick="startLoading(1)">🏦 Banco Itaú</button>
                <button class="q-btn" onclick="startLoading(1)">🏦 Caixa Econômica</button>
                <button class="q-btn" onclick="startLoading(1)">📱 Nubank / Bancos Digitais</button>
                <button class="q-btn" onclick="startLoading(1)">🔑 Outros Bancos</button>
            </div>

            <div class="step" id="loading1">
                <h2 class="text-xl font-bold mb-4">CONSULTANDO PERFIL BANCÁRIO</h2>
                <div class="progress-container"><div class="progress-bar" id="bar1"></div></div>
                <p class="text-xs text-gray-500" id="status1">Rastreando Protocolo 892 via IP...</p>
            </div>

            <div class="step" id="step2">
                <h2 class="text-green-500 font-black text-2xl uppercase">Margem Localizada!</h2>
                <p class="text-gray-400 text-xs mt-2">O sistema encontrou um crédito disponível para sua conexão:</p>
                <div class="text-4xl font-black my-6" id="valor-sorteado">R$ 4.820,00</div>
                <button class="w-full bg-blue-600 p-5 rounded-xl font-black text-lg btn-glow" onclick="startLoading(2)">
                    GERAR MINHA CHAVE DE LIBERAÇÃO
                </button>
            </div>

            <div class="step" id="loading2">
                <h2 class="text-xl font-bold mb-4">GERANDO CHAVE 892</h2>
                <div class="progress-container"><div class="progress-bar" id="bar2"></div></div>
                <p class="text-xs text-gray-500" id="status2">Criptografando Chave de Custódia...</p>
            </div>

            <div class="step" id="stepFinal">
                <h2 class="text-blue-500 font-black text-2xl">CHAVE RESERVADA!</h2>
                <div class="blur-code">S892-BR2026</div>
                <div class="bg-blue-900/10 border border-blue-500/30 p-4 rounded-xl text-left text-xs mb-6 text-blue-100 leading-relaxed">
                    <strong>⚠️ INSTRUÇÃO DE SAQUE:</strong><br>
                    Para liberar o código oculto e o guia de resgate, você deve ativar sua chave. A taxa de ativação é de <b>R$ 97</b>. <br><br>
                    Este valor será <b>100% ESTORNADO</b> para sua conta junto com o seu crédito aprovado em até 2 minutos após a conclusão.
                </div>
                <a href="https://go.perfectpay.com.br/PPU38CQ79SG" class="block w-full bg-green-600 p-5 rounded-xl font-black text-lg uppercase text-center">
                    CONCLUIR ATIVAÇÃO HOJE ➤
                </a>
            </div>

        </div>
    </div>

    <script>
        function openQuizz() { document.getElementById('quizz-overlay').style.display = 'flex'; }

        function startLoading(n) {
            document.querySelectorAll('.step').forEach(s => s.classList.remove('active'));
            document.getElementById('loading' + n).classList.add('active');
            
            let width = 0;
            let bar = document.getElementById('bar' + n);
            let status = document.getElementById('status' + n);
            
            let interval = setInterval(() => {
                if (width >= 100) {
                    clearInterval(interval);
                    if(n == 1) {
                        const valor = (Math.random() * (2940 - 1200) + 1200).toLocaleString('pt-br', {style: 'currency', currency: 'BRL'});
                        document.getElementById('valor-sorteado').innerText = valor;
                        showStep('step2');
                    } else {
                        showStep('stepFinal');
                    }
                } else {
                    width += 2;
                    bar.style.width = width + '%';
                    if(n == 1 && width == 40) status.innerText = "Destravando margem via servidor...";
                    if(n == 1 && width == 80) status.innerText = "Conectando ao perfil bancário...";
                    if(n == 2 && width == 50) status.innerText = "Vinculando CPF à chave de custódia...";
                }
            }, 60);
        }

        function showStep(id) {
            document.querySelectorAll('.step').forEach(s => s.classList.remove('active'));
            document.getElementById(id).classList.add('active');
        }

        // Contador de visualização
        let viewers = 179;
        setInterval(() => {
            viewers += Math.floor(Math.random() * 7) - 3;
            if(viewers < 160) viewers = 165;
            document.getElementById('viewers').innerText = viewers;
        }, 3000);
    </script>
</body>
</html>
