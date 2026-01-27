<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>RotaFixa App</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Kanit:wght@600;900&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Kanit', sans-serif; -webkit-tap-highlight-color: transparent; }
        .nav-bottom { box-shadow: 0 -2px 10px rgba(0,0,0,0.1); }
    </style>
</head>
<body class="bg-gray-50 select-none">

    <header class="bg-yellow-400 p-5 pt-10 rounded-b-[30px] shadow-lg text-center">
        <h1 class="text-3xl font-black italic tracking-tighter">ROTA<span class="text-white">FIXA</span></h1>
    </header>

    <main class="p-4 pb-24">
        <div class="flex gap-2 overflow-x-auto pb-4 no-scrollbar text-[10px] font-bold">
            <button class="bg-black text-white px-4 py-2 rounded-full whitespace-nowrap">MÓVEIS</button>
            <button class="bg-white text-black border border-gray-200 px-4 py-2 rounded-full whitespace-nowrap">MERCADO</button>
            <button class="bg-white text-black border border-gray-200 px-4 py-2 rounded-full whitespace-nowrap">ALIMENTOS</button>
        </div>

        <h2 class="text-gray-400 text-[10px] font-black uppercase mb-4">Ajudantes disponíveis para amanhã</h2>

        <div class="space-y-4">
            <div class="bg-white p-4 rounded-3xl shadow-sm border border-gray-100 flex items-center gap-4">
                <div class="w-16 h-16 bg-gray-200 rounded-2xl overflow-hidden">
                    <img src="https://randomuser.me/api/portraits/men/1.jpg" class="w-full h-full object-cover">
                </div>
                <div class="flex-1">
                    <h3 class="font-black text-gray-800">RICARDO SILVA</h3>
                    <p class="text-[10px] text-gray-500">⭐ 4.9 | Especialista em Mudanças</p>
                    <button onclick="window.location.href='https://wa.me/55...'" class="mt-2 bg-yellow-400 text-black text-[10px] font-black px-3 py-1 rounded-lg">RESERVAR</button>
                </div>
            </div>
            <div class="bg-white p-4 rounded-3xl shadow-sm border border-gray-100 flex items-center gap-4">
                <div class="w-16 h-16 bg-gray-200 rounded-2xl overflow-hidden">
                    <img src="https://randomuser.me/api/portraits/men/2.jpg" class="w-full h-full object-cover">
                </div>
                <div class="flex-1">
                    <h3 class="font-black text-gray-800">MARCOS PAULO</h3>
                    <p class="text-[10px] text-gray-500">⭐ 5.0 | Ajudante de Entrega</p>
                    <button class="mt-2 bg-yellow-400 text-black text-[10px] font-black px-3 py-1 rounded-lg">RESERVAR</button>
                </div>
            </div>
        </div>
    </main>

    <nav class="fixed bottom-0 left-0 right-0 bg-white p-4 flex justify-around nav-bottom rounded-t-[25px]">
        <button class="text-yellow-500 font-black text-[10px]">INÍCIO</button>
        <button class="text-gray-400 font-black text-[10px]">MINHAS ROTAS</button>
        <button class="text-gray-400 font-black text-[10px]">PERFIL</button>
    </nav>

</body>
</html>
