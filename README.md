<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ajuda Urgente - Orfanato Esperança</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        .progress-bar { transition: width 2s ease-in-out; }
        .modal { display: none; position: fixed; inset: 0; background: rgba(0,0,0,0.8); align-items: center; justify-content: center; z-index: 50; }
        .modal.active { display: flex; }
    </style>
</head>
<body class="bg-gray-100 font-sans">

    <div class="bg-red-600 text-white text-center py-2 text-sm font-bold uppercase tracking-widest">
        ⚠️ Campanha Emergencial: Alimentos acabando em 24h
    </div>

    <main class="max-w-md mx-auto bg-white min-h-screen shadow-lg pb-10">
        <img src="https://images.unsplash.com/photo-1488521787991-ed7bbaae773c?q=80&w=500" alt="Orfanato" class="w-full h-64 object-cover">

        <div class="p-6">
            <h1 class="text-2xl font-bold text-gray-800 leading-tight">Ajude a garantir o leite das 42 crianças do Abrigo Esperança</h1>
            
            <div class="mt-6">
                <div class="flex justify-between text-sm mb-1 font-bold">
                    <span>Meta: R$ 5.000,00</span>
                    <span class="text-red-600">Faltam R$ 642,00</span>
                </div>
                <div class="w-full bg-gray-200 rounded-full h-4">
                    <div class="bg-green-500 h-4 rounded-full progress-bar" style="width: 87%"></div>
                </div>
                <p class="text-xs text-gray-500 mt-2 italic font-semibold">142 doadores contribuíram hoje</p>
            </div>

            <p class="mt-6 text-gray-600 leading-relaxed">
                Cada doação é um prato de comida. Não temos apoio do governo e o estoque acaba amanhã. <b>Sua ajuda é a única esperança desses pequenos hoje.</b>
            </p>

            <div class="mt-8 space-y-4">
                <button onclick="abrirModal('15,00', 'COLE_AQUI_CODIGO_PIX_15', 'https://via.placeholder.com/200?text=QR+15')" class="w-full bg-white border-2 border-green-500 text-green-600 font-bold py-4 rounded-xl hover:bg-green-50 shadow-sm transition">
                    DOAR R$ 15,00 (Café da Manhã)
                </button>
                
                <button onclick="abrirModal('27,90', 'COLE_AQUI_CODIGO_PIX_27', 'https://via.placeholder.com/200?text=QR+27')" class="w-full bg-green-600 text-white font-bold py-5 rounded-xl hover:bg-green-700 shadow-md transition scale-105 border-2 border-green-400">
                    DOAR R$ 27,90 (1 Semana de Leite) ⭐
                </button>

                <button onclick="abrirModal('50,00', 'COLE_AQUI_CODIGO_PIX_50', 'https://via.placeholder.com/200?text=QR+50')" class="w-full bg-white border-2 border-green-500 text-green-600 font-bold py-4 rounded-xl hover:bg-green-50 shadow-sm transition">
                    DOAR R$ 50,00 (Kit Higiene)
                </button>
            </div>
        </div>
    </main>

    <div id="pixModal" class="modal p-4">
        <div class="bg-white rounded-2xl p-6 max-w-xs w-full text-center relative">
            <button onclick="fecharModal()" class="absolute top-2 right-4 text-gray-400 text-2xl font-bold">&times;</button>
            <h2 class="text-xl font-bold text-gray-800">Sua Doação: R$ <span id="vlrTexto">0,00</span></h2>
            <p class="text-sm text-gray-500 mb-4">Escaneie o QR Code ou copie o código abaixo</p>
            
            <img id="qrImg" src="" alt="QR Code" class="mx-auto w-48 h-48 mb-4 border p-2">
            
            <button id="btnCopiar" onclick="copiarPix()" class="w-full bg-blue-600 text-white font-bold py-3 rounded-lg mb-2">
                COPIAR CÓDIGO PIX
            </button>
            <p id="feedback" class="text-green-600 text-xs font-bold hidden">Copiado com sucesso! Cole no seu Banco.</p>
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
        }

        function fecharModal() {
            document.getElementById('pixModal').classList.remove('active');
        }

        function copiarPix() {
            navigator.clipboard.writeText(pixAtual).then(() => {
                const f = document.getElementById('feedback');
                f.classList.remove('hidden');
                const b = document.getElementById('btnCopiar');
                b.innerText = "CÓDIGO COPIADO!";
                setTimeout(() => { b.innerText = "COPIAR CÓDIGO PIX"; }, 3000);
            });
        }
    </script>
</body>
</html>
