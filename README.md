<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ajuda da Luana - Missão Patinhas</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"/>
    <style>
        .font-poppins { font-family: 'Poppins', sans-serif; }
        #modal-pix { display: none; position: fixed; inset: 0; background: rgba(0,0,0,0.85); align-items: center; justify-content: center; z-index: 1000; backdrop-filter: blur(8px); }
        #modal-pix.active { display: flex; }
        .notification { position: fixed; bottom: 20px; left: 50%; transform: translateX(-50%); z-index: 500; display: none; }
    </style>
</head>
<body class="bg-gray-50 font-poppins">

    <div id="notif" class="notification animate__animated animate__fadeInUp bg-white shadow-2xl rounded-2xl p-4 border-l-4 border-purple-500 w-[90%] max-w-sm">
        <div class="flex items-center space-x-3">
            <div class="bg-purple-100 p-2 rounded-full text-purple-600">❤️</div>
            <div>
                <p class="text-[10px] font-bold text-gray-400 uppercase">Doação Confirmada</p>
                <p class="text-xs text-gray-700 font-semibold" id="notif-user">Alguém acabou de doar R$ 24,90</p>
            </div>
        </div>
    </div>

    <main class="max-w-md mx-auto bg-white min-h-screen shadow-2xl relative">
        
        <div class="p-4 flex justify-between items-center border-b">
            <div class="flex items-center space-x-2">
                <div class="w-8 h-8 bg-purple-600 rounded-full flex items-center justify-center text-white font-bold text-xs">L</div>
                <span class="text-sm font-bold text-gray-700 tracking-tight">Diário de Resgate da Lu</span>
            </div>
            <span class="text-[10px] bg-purple-100 text-purple-700 px-2 py-1 rounded-full font-bold uppercase">Estudante de Veterinária 🎓</span>
        </div>

        <div class="relative overflow-hidden">
            <img src="https://images.unsplash.com/photo-1534361960057-19889db9621e?q=80&w=500" class="w-full h-72 object-cover grayscale-[20%]">
            <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent"></div>
            <div class="absolute bottom-6 left-6 right-6">
                <h1 class="text-white text-2xl font-black leading-tight">Escolher entre minha faculdade ou o prato deles foi a dor mais forte que senti...</h1>
            </div>
        </div>

        <div class="p-6">
            <div class="mb-8">
                <div class="flex justify-between items-end mb-2">
                    <div>
                        <p class="text-[10px] font-bold text-purple-500 uppercase tracking-widest">Arrecadado com amor</p>
                        <p class="text-3xl font-black text-gray-900">R$ <span id="arrecadado">2.145,00</span></p>
                    </div>
                    <div class="text-right">
                        <p class="text-[10px] font-bold text-gray-400 uppercase">Meta Semanal</p>
                        <p class="text-sm font-bold text-gray-600">R$ 3.500</p>
                    </div>
                </div>
                <div class="w-full bg-gray-100 rounded-full h-4 overflow-hidden border">
                    <div id="progress-bar" class="bg-purple-600 h-full transition-all duration-1000 shadow-[0_0_15px_rgba(147,51,234,0.5)]" style="width: 61%"></div>
                </div>
            </div>

            <div class="space-y-4 text-gray-600 text-sm leading-relaxed mb-8">
                <p>Tudo começou com o <b>"Bolinha"</b>. Ele dormia na frente do meu portão todo santo dia. Comecei dando um resto de comida, depois comprei um saquinho de ração... e meu coração não me deixou parar ali.</p>
                <p>Em poucos meses, minha garagem virou o abrigo de 14 anjos. Eu já consegui doar 3 para amigos de confiança da faculdade, mas sou muito rigorosa: não entrego para qualquer um. Em breve vou abrir um formulário oficial, pois eles merecem o melhor.</p>
                <p class="bg-yellow-50 p-4 border-l-4 border-yellow-400 text-gray-800 font-medium italic rounded-r-lg">
                    "Paguei minha mensalidade da faculdade ontem e meu saldo zerou. O estoque de ração e os remédios de verme acabam hoje. Eu nunca imaginei ter que pedir ajuda, mas não posso deixar eles passarem fome."
                </p>
            </div>

            <h3 class="font-black text-gray-900 text-lg mb-4">Como você pode me ajudar:</h3>
            <div class="grid grid-cols-1 gap-4">
                
                <button onclick="openPix('12,00', 'SEU_PIX_AQUI', 'LINK_QR_12')" class="flex items-center justify-between p-4 bg-white border-2 border-gray-100 rounded-2xl hover:border-purple-500 transition shadow-sm group">
                    <div class="text-left">
                        <p class="font-black text-gray-800">Ração do Dia</p>
                        <p class="text-[10px] text-gray-400">Garante a barriguinha cheia hoje</p>
                    </div>
                    <span class="bg-purple-50 text-purple-600 font-black px-4 py-2 rounded-xl">R$ 12,00</span>
                </button>

                <button onclick="openPix('27,50', 'SEU_PIX_AQUI', 'LINK_QR_27')" class="flex items-center justify-between p-5 bg-purple-600 rounded-2xl shadow-xl shadow-purple-200 scale-105 transition-transform">
                    <div class="text-left">
                        <p class="font-black text-white">Ração + Vermífugo</p>
                        <p class="text-[10px] text-purple-200 uppercase font-bold tracking-tighter">🚨 Urgência da semana</p>
                    </div>
                    <span class="bg-white text-purple-600 font-black px-4 py-2 rounded-xl">R$ 27,50</span>
                </button>

                <button onclick="openPix('55,00', 'SEU_PIX_AQUI', 'LINK_QR_55')" class="flex items-center justify-between p-4 bg-white border-2 border-gray-100 rounded-2xl hover:border-purple-500 transition shadow-sm">
                    <div class="text-left">
                        <p class="font-black text-gray-800">Banho e Cuidado</p>
                        <p class="text-[10px] text-gray-400">Higiene para 2 cachorros</p>
                    </div>
                    <span class="bg-purple-50 text-purple-600 font-black px-4 py-2 rounded-xl">R$ 55,00</span>
                </button>

            </div>

            <p class="text-center text-[10px] text-gray-400 mt-8 uppercase font-bold tracking-widest">Agradeço de todo meu coração em nome dos pequenos.</p>
        </div>
    </main>

    <div id="modal-pix" class="p-4">
        <div class="bg-white rounded-3xl p-8 max-w-xs w-full text-center relative animate__animated animate__zoomIn">
            <button onclick="closePix()" class="absolute top-4 right-4 text-gray-300 text-2xl font-bold">&times;</button>
            <p class="text-purple-600 font-black text-xs uppercase mb-1">Finalizar Doação</p>
            <h2 class="text-3xl font-black text-gray-900 mb-6">R$ <span id="vlr">0,00</span></h2>
            
            <img id="qr" src="" class="w-48 h-48 mx-auto mb-6 p-2 border-2 border-dashed border-purple-200 rounded-2xl">
            
            <button id="btn-copy" onclick="copy()" class="w-full bg-purple-600 text-white font-black py-4 rounded-2xl shadow-lg active:scale-95 transition mb-4 uppercase text-sm tracking-wider">Copiar Código PIX</button>
            <p id="msg-copy" class="text-green-600 text-[10px] font-black hidden">CÓDIGO COPIADO! AGORA COLE NO SEU BANCO.</p>
        </div>
    </div>

    <script>
        let pixCode = "";
        let currentAmount = 2145.00;
        let targetAmount = 3500;

        // Faz o valor aumentar sozinho simulando doações
        function updateArrecadado() {
            const increment = Math.random() * (2.50 - 0.10) + 0.10;
            currentAmount += increment;
            document.getElementById('arrecadado').innerText = currentAmount.toLocaleString('pt-BR', { minimumFractionDigits: 2 });
            const percent = (currentAmount / targetAmount) * 100;
            document.getElementById('progress-bar').style.width = percent + "%";
        }
        setInterval(updateArrecadado, 12000);

        // Notificações Fakes
        const names = ["Beatriz", "Marcos", "Cláudia", "Vinícius", "Elena", "Gustavo", "Renata"];
        function showNotif() {
            const name = names[Math.floor(Math.random() * names.length)];
            const val = [12.00, 27.50, 10.00, 55.00, 5.00][Math.floor(Math.random() * 5)];
            document.getElementById('notif-user').innerText = `${name} doou R$ ${val.toFixed(2)} agora`;
            const n = document.getElementById('notif');
            n.style.display = 'block';
            setTimeout(() => { n.style.display = 'none'; }, 4000);
        }
        setInterval(showNotif, 15000);

        function openPix(v, p, i) {
            document.getElementById('vlr').innerText = v;
            document.getElementById('qr').src = i;
            document.getElementById('modal-pix').classList.add('active');
            pixCode = p;
        }
        function closePix() { document.getElementById('modal-pix').classList.remove('active'); }
        function copy() {
            navigator.clipboard.writeText(pixCode);
            document.getElementById('msg-copy').classList.remove('hidden');
            document.getElementById('btn-copy').innerText = "COPIADO COM SUCESSO!";
        }
    </script>
</body>
</html>
