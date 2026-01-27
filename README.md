<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RotaFixa | Ajudantes para sua Rota</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        .yellow-gradient { background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 100%); }
    </style>
</head>
<body class="bg-gray-100 font-sans">

    <header class="yellow-gradient p-6 text-center shadow-lg">
        <h1 class="text-3xl font-black italic tracking-tighter text-black">ROTA<span class="text-white">FIXA</span></h1>
        <p class="text-black font-bold text-xs uppercase tracking-widest mt-1">O braço direito do motorista de entrega</p>
    </header>

    <main class="max-w-md mx-auto p-6">
        
        <div class="bg-white rounded-3xl p-8 shadow-xl mb-8 border-t-8 border-black">
            <h2 class="text-2xl font-black text-gray-800 mb-4 leading-tight">PRECISA DE AJUDANTE PARA A ROTA DE AMANHÃ?</h2>
            <p class="text-gray-600 text-sm mb-6">Não perca tempo em postos. Contrate um ajudante verificado para te acompanhar na rota de <b>Móveis, Mercado ou Alimentos</b>.</p>
            
            <div class="space-y-3">
                <div class="flex items-center gap-3 text-sm font-bold text-gray-700">
                    <span class="bg-green-100 text-green-600 p-1 rounded-full text-[10px]">✔</span> Ajudante sobe na cabine e faz a rua
                </div>
                <div class="flex items-center gap-3 text-sm font-bold text-gray-700">
                    <span class="bg-green-100 text-green-600 p-1 rounded-full text-[10px]">✔</span> Feche o contrato 24h antes
                </div>
                <div class="flex items-center gap-3 text-sm font-bold text-gray-700">
                    <span class="bg-green-100 text-green-600 p-1 rounded-full text-[10px]">✔</span> Selecionados por tipo de carga
                </div>
            </div>
        </div>

        <div class="grid grid-cols-1 gap-4">
            <button onclick="window.location.href='SEU_LINK_WHATSAPP_MOTORISTA'" class="bg-black text-white p-6 rounded-2xl flex justify-between items-center group active:scale-95 transition">
                <div class="text-left">
                    <p class="font-black text-lg">SOU MOTORISTA</p>
                    <p class="text-[10px] text-gray-400">Quero contratar para amanhã</p>
                </div>
                <span class="text-yellow-400 text-2xl font-bold">→</span>
            </button>

            <button onclick="window.location.href='SEU_LINK_WHATSAPP_AJUDANTE'" class="bg-white border-2 border-black p-6 rounded-2xl flex justify-between items-center active:scale-95 transition">
                <div class="text-left">
                    <p class="font-black text-lg text-black">SOU AJUDANTE</p>
                    <p class="text-[10px] text-gray-500">Quero trabalhar nas rotas</p>
                </div>
                <span class="text-black text-2xl font-bold">→</span>
            </button>
        </div>

        <div class="mt-12">
            <p class="text-center text-[10px] font-black text-gray-400 uppercase tracking-widest mb-6">Especialidades disponíveis</p>
            <div class="grid grid-cols-2 gap-3">
                <div class="bg-white p-4 rounded-xl text-center shadow-sm">
                    <span class="block text-2xl mb-1">📦</span>
                    <p class="text-[10px] font-bold">MÓVEIS</p>
                </div>
                <div class="bg-white p-4 rounded-xl text-center shadow-sm">
                    <span class="block text-2xl mb-1">🛒</span>
                    <p class="text-[10px] font-bold">MERCADO</p>
                </div>
                <div class="bg-white p-4 rounded-xl text-center shadow-sm">
                    <span class="block text-2xl mb-1">🍎</span>
                    <p class="text-[10px] font-bold">ALIMENTOS</p>
                </div>
                <div class="bg-white p-4 rounded-xl text-center shadow-sm">
                    <span class="block text-2xl mb-1">🚛</span>
                    <p class="text-[10px] font-bold">CARRETAS</p>
                </div>
            </div>
        </div>

    </main>

    <footer class="p-8 text-center text-[10px] text-gray-400 font-bold uppercase">
        © 2026 RotaFixa Tecnologia - Logística Inteligente
    </footer>

</body>
</html>
