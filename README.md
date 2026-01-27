<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Minha Missão: Anjos de Garagem</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        .progress-bar { transition: width 2s ease-in-out; }
        .modal { display: none; position: fixed; inset: 0; background: rgba(0,0,0,0.9); align-items: center; justify-content: center; z-index: 50; }
        .modal.active { display: flex; }
    </style>
</head>
<body class="bg-gray-50 font-sans text-gray-800">

    <main class="max-w-md mx-auto bg-white min-h-screen shadow-2xl pb-12">
        
        <div class="relative">
            <img src="https://images.unsplash.com/photo-1548191265-cc70d3d45ba1?q=80&w=500" alt="Resgate" class="w-full h-72 object-cover">
            <div class="absolute bottom-0 left-0 bg-blue-600 text-white px-4 py-1 text-xs font-bold uppercase">
                Minha Rotina Diária
            </div>
        </div>

        <div class="p-6">
            <h1 class="text-2xl font-extrabold text-gray-900 leading-tight">Não sou ONG, sou apenas eu e eles na minha garagem...</h1>
            
            <div class="mt-4 flex items-center text-sm text-gray-500">
                <span class="bg-green-100 text-green-700 px-2 py-1 rounded-full text-xs font-bold">14 doguinhos hoje</span>
                <span class="ml-2 underline italic">São Paulo, SP</span>
            </div>

            <article class="mt-6 text-gray-700 leading-relaxed text-base space-y-4">
                <p>
                    Oi, eu sou a [Nome da Menina]! Algum tempo atrás, eu não imaginava que minha vida mudaria tanto. Tudo começou com um potinho de comida na calçada para um gatinho que apareceu com fome.
                </p>
                <p>
                    De repente, apareceram dois, três... e quando vi, minha garagem virou um refúgio. Comecei a recolher os cachorros abandonados aqui da região que estavam doentes. Eu mesma dou banho, cuido e tento encontrar donos responsáveis por aqui mesmo.
                </p>
                <p class="font-bold text-gray-900">
                    Mas a realidade é dura: a ração acaba rápido e os custos aumentaram muito. Eu não tenho luxo, moro de forma simples, mas não aguento ver eles sem comer.
                </p>
            </article>

            <div class="mt-8 bg-blue-50 p-4 rounded-2xl border border-blue-100">
                <div class="flex justify-between text-sm mb-2 font-bold text-blue-800">
                    <span>Meta de Ração (Semana)</span>
                    <span>82%</span>
                </div>
                <div class="w-full bg-gray-200 rounded-full h-3">
                    <div class="bg-blue-600 h-3 rounded-full progress-bar" style="width: 82%"></div>
                </div>
                <p class="text-[10px] text-gray-500 mt-2 text-center uppercase tracking-tighter">Faltam apenas R$ 185,00 para fechar o estoque de ração</p>
            </div>

            <div class="mt-8">
                <h3 class="text-center font-bold text-gray-500 uppercase text-xs mb-4">Escolha como você pode ajudar agora:</h3>
                
                <div class="space-y-3">
                    <button onclick="abrirModal('9,50', 'COLE_SEU_PIX_AQUI', 'LINK_DA_IMAGEM_QR')" class="w-full flex justify-between items-center bg-white border-2 border-gray-200 p-4 rounded-xl hover:border-blue-500 transition group">
                        <span class="font-bold text-gray-700 group-hover:text-blue-600">Um Saco de Ração 1kg</span>
                        <span class="bg-blue-100 text-blue-700 px-3 py-1 rounded-lg font-bold text-sm">R$ 9,50</span>
                    </button>

                    <button onclick="abrirModal('24,90', 'COLE_SEU_PIX_AQUI', 'LINK_DA_IMAGEM_QR')" class="w-full flex justify-between items-center bg-blue-600 p-4 rounded-xl shadow-lg shadow-blue-200 scale-105 transition">
                        <span class="font-bold text-white">Ração + Banho + Carinho</span>
                        <span class="bg-white text-blue-600 px-3 py-1 rounded-lg font-bold text-sm">R$ 24,90</span>
                    </button>

                    <button onclick="abrirModal('45,00', 'COLE_SEU_PIX_AQUI', 'LINK_DA_IMAGEM_QR')" class="w-full flex justify-between items-center bg-white border-2 border-gray-200 p-4 rounded-xl hover:border-blue-500 transition group">
                        <span class="font-bold text-gray-700 group-hover:text-blue-600">Ajuda com Remédios</span>
                        <span class="bg-blue-100 text-blue-700 px-3 py-1 rounded-lg font-bold text-sm">R$ 45,00</span>
                    </button>
                </div>
            </div>

            <p class="mt-8 text-center text-xs text-gray-400">
                Cada centavo vai direto para eles. Deus te abençoe! 🙏
            </p>
        </div>
    </main>

    <div id="pixModal" class="modal p-4">
        <div class="bg-white rounded-3xl p-8 max-w-xs w-full text-center relative shadow-2xl">
            <button onclick="fecharModal()" class="absolute top-4 right-4 text-gray-400 hover:text-gray-600 text-2xl">&times;</button>
            <p class="text-blue-600 font-bold text-xs uppercase tracking-widest mb-2">Quase lá!</p>
            <h2 class="text-2xl font-black text-gray-800 mb-4">R$ <span id="vlrTexto">0,00</span></h2>
            
            <img id="qrImg" src="" alt="QR Code" class="mx-auto w-44 h-44 mb-6 border-4 border-gray-50 rounded-xl p-2">
            
            <button id="btnCopiar" onclick="copiarPix()" class="w-full bg-blue-600 text-white font-bold py-4 rounded-2xl shadow-lg active:scale-95 transition">
                COPIAR CÓDIGO PIX
            </button>
            <p id="feedback" class="text-green-600 text-[10px] font-bold mt-2 hidden uppercase">Copiado! Agora é só colar no seu banco.</p>
        </div>
    </div>

    <script>
        let pixAtual = "";
        function abrirModal(valor, pix, img) {
            document.getElementById('vlrTexto').innerText = valor;
            document.getElementById('qrImg').src = img;
            document.getElementById('pixModal').classList.add('active');
            document.getElementById('feedback').classList.add('hidden');
            pixAtual = pix;
            document.getElementById('btnCopiar').innerText = "COPIAR CÓDIGO PIX";
        }
        function fecharModal() { document.getElementById('pixModal').classList.remove('active'); }
        function copiarPix() {
            navigator.clipboard.writeText(pixAtual).then(() => {
                document.getElementById('feedback').classList.remove('hidden');
                document.getElementById('btnCopiar').innerText = "CÓDIGO COPIADO!";
            });
        }
    </script>
</body>
</html>
