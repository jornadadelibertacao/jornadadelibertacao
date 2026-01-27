<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vakinha Online - Ajuda Urgente</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"/>
    <style>
        @keyframes progressAnimation { 0% { width: 72%; } 100% { width: 89%; } }
        .progress-fill { animation: progressAnimation 30s infinite alternate; }
        #notification { display: none; position: fixed; top: 20px; right: 20px; z-index: 100; }
        .modal { display: none; position: fixed; inset: 0; background: rgba(0,0,0,0.85); align-items: center; justify-content: center; z-index: 200; backdrop-filter: blur(5px); }
        .modal.active { display: flex; }
    </style>
</head>
<body class="bg-[#f4f7f6] font-sans">

    <div id="notification" class="animate__animated animate__fadeInRight bg-white shadow-xl rounded-lg p-4 flex items-center space-x-3 border-l-4 border-green-500 max-w-[280px]">
        <div class="bg-green-100 p-2 rounded-full">
            <svg class="w-6 h-6 text-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path></svg>
        </div>
        <div>
            <p class="text-xs font-bold text-gray-800" id="notif-text">Alguém acabou de doar!</p>
            <p class="text-[10px] text-gray-500">R$ 27,90 via PIX</p>
        </div>
    </div>

    <header class="bg-white p-4 shadow-sm border-b sticky top-0 z-50">
        <div class="max-w-md mx-auto flex justify-between items-center">
            <img src="https://logodownload.org/wp-content/uploads/2018/10/vakinha-logo.png" class="h-6" alt="Vakinha">
            <div class="flex items-center space-x-1">
                <div class="w-2 h-2 bg-red-500 rounded-full animate-pulse"></div>
                <span class="text-[10px] font-bold text-red-500 uppercase">1.242 pessoas ajudando agora</span>
            </div>
        </div>
    </header>

    <main class="max-w-md mx-auto">
        <div class="relative w-full h-80 bg-gray-200">
            <img src="SUA_FOTO_DA_GARAGEM_AQUI.jpg" class="w-full h-full object-cover shadow-inner" alt="Causa">
            <div class="absolute bottom-4 left-4 bg-black/60 backdrop-blur-md text-white px-3 py-1 rounded-full text-xs font-bold">
                📸 Ver todas as 12 fotos
            </div>
        </div>

        <div class="bg-white p-6 rounded-b-3xl shadow-lg relative -mt-5 z-10">
            <h1 class="text-2xl font-black text-gray-900 leading-tight mb-4">
                Urgente: Minha garagem lotou e não tenho mais ração para os 14 cachorros.
            </h1>

            <div class="bg-gray-100 p-4 rounded-2xl mb-6 border border-gray-200">
                <div class="flex justify-between items-end mb-2">
                    <div>
                        <p class="text-[10px] uppercase text-gray-500 font-bold tracking-wider">Arrecadado</p>
                        <p class="text-2xl font-black text-green-600">R$ 4.418,92</p>
                    </div>
                    <p class="text-[11px] font-bold text-gray-400 text-right">Meta: R$ 5.000,00</p>
                </div>
                <div class="w-full bg-gray-300 rounded-full h-3">
                    <div class="bg-green-500 h-3 rounded-full progress-fill" style="width: 88%"></div>
                </div>
            </div>

            <div class="space-y-4 text-gray-700 text-sm leading-relaxed">
                <p>Oii, eu sou a [Seu Nome], e o que você vê é o meu dia a dia. Comecei sozinha cuidando de um cachorro de rua e hoje minha garagem é o único teto de 14 animais.</p>
                <p class="font-bold border-l-4 border-yellow-500 pl-3">A ração acabou hoje cedo. Estou desesperada porque não tenho como comprar mais. Qualquer valor salva uma vida agora.</p>
            </div>

            <div class="mt-8 space-y-3">
                <button onclick="abrirModal('15,00', 'SEU_PIX_AQUI', 'QR_IMG_15')" class="w-full bg-white border-2 border-gray-100 flex items-center justify-between p-4 rounded-2xl shadow-sm hover:border-green-500 transition">
                    <span class="font-black text-gray-800">Doar R$ 15,00</span>
                    <span class="bg-green-100 text-green-700 px-3 py-1 rounded-lg text-xs font-bold">AJUDAR AGORA</span>
                </button>

                <button onclick="abrirModal('27,90', 'SEU_PIX_AQUI', 'QR_IMG_27')" class="w-full bg-[#00b259] flex items-center justify-between p-5 rounded-2xl shadow-xl shadow-green-200 scale-105 border-2 border-green-400">
                    <span class="font-black text-white text-lg">Doar R$ 27,90</span>
                    <span class="bg-white text-green-600 px-3 py-1 rounded-lg text-xs font-bold animate-bounce">MAIS ESCOLHIDO</span>
                </button>

                <button onclick="abrirModal('50,00', 'SEU_PIX_AQUI', 'QR_IMG_50')" class="w-full bg-white border-2 border-gray-100 flex items-center justify-between p-4 rounded-2xl shadow-sm hover:border-green-500 transition">
                    <span class="font-black text-gray-800">Doar R$ 50,00</span>
                    <span class="bg-green-100 text-green-700 px-3 py-1 rounded-lg text-xs font-bold">DOAR KIT</span>
                </button>
            </div>

            <div class="mt-8 p-4 bg-yellow-50 rounded-xl border border-yellow-100 flex items-center space-x-3 text-[11px] text-yellow-800 font-medium">
                <svg class="w-8 h-8 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20"><path d="M10 18a8 8 0 100-16 8 8 0 000 16zm1-12a1 1 0 10-2 0v4a1 1 0 00.293.707l2.828 2.829a1 1 0 101.415-1.415L11 9.586V6z"></path></svg>
                <p>Doação Segura: O valor é repassado instantaneamente para o cuidado dos animais via PIX oficial.</p>
            </div>
        </div>
    </main>

    <div id="pixModal" class="modal">
        <div class="bg-white rounded-3xl p-6 max-w-[320px] w-full text-center shadow-2xl animate__animated animate__zoomIn">
            <h2 class="text-xl font-black text-gray-800 mb-2">Pague com PIX</h2>
            <p class="text-3xl font-black text-green-600 mb-4">R$ <span id="vlrTexto">0,00</span></p>
            <img id="qrImg" src="" class="mx-auto w-48 h-48 border-4 border-gray-100 rounded-2xl mb-4 p-2">
            <button id="btnCopiar" onclick="copiarPix()" class="w-full bg-[#00b259] text-white font-black py-4 rounded-2xl mb-3 shadow-lg">COPIAR CÓDIGO PIX</button>
            <button onclick="fecharModal()" class="text-gray-400 font-bold text-xs uppercase underline">Fechar</button>
            <p id="feedback" class="text-blue-600 text-[10px] font-bold mt-2 hidden">COPIADO! COLE NO SEU APP DO BANCO</p>
        </div>
    </div>

    <script>
        let pixAtual = "";
        const nomes = ["Marcos", "Ana", "Carla", "Ricardo", "Fabiana", "Lucas", "Julia", "Matheus"];
        
        function showNotification() {
            const name = nomes[Math.floor(Math.random() * nomes.length)];
            document.getElementById('notif-text').innerText = `${name} acabou de doar!`;
            const notif = document.getElementById('notification');
            notif.style.display = 'flex';
            setTimeout(() => { notif.classList.replace('animate__fadeInRight', 'animate__fadeOutRight'); }, 4000);
            setTimeout(() => { 
                notif.style.display = 'none'; 
                notif.classList.replace('animate__fadeOutRight', 'animate__fadeInRight');
            }, 5000);
        }
        setInterval(showNotification, 8000);

        function abrirModal(valor, pix, img) {
            document.getElementById('vlrTexto').innerText = valor;
            document.getElementById('qrImg').src = img;
            document.getElementById('pixModal').classList.add('active');
            pixAtual = pix;
        }
        function fecharModal() { document.getElementById('pixModal').classList.remove('active'); }
        function copiarPix() {
            navigator.clipboard.writeText(pixAtual);
            document.getElementById('feedback').classList.remove('hidden');
            document.getElementById('btnCopiar').innerText = "CÓDIGO COPIADO!";
        }
    </script>
</body>
</html>
