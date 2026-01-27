<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vakinha | Malu precisa de você</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"/>
    <style>
        body { font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; background-color: #f8f9fa; }
        .progress-bar { transition: width 2s ease-in-out; }
        .notification-toast { display: none; position: fixed; bottom: 100px; left: 20px; z-index: 1000; }
        .footer-sticky { position: fixed; bottom: 0; left: 0; right: 0; background: white; padding: 15px; box-shadow: 0 -2px 10px rgba(0,0,0,0.1); z-index: 500; }
    </style>
</head>
<body class="pb-24">

    <header class="bg-white p-4 flex justify-between items-center border-b">
        <img src="https://logodownload.org/wp-content/uploads/2018/10/vakinha-logo.png" class="h-8">
        <div class="space-y-1">
            <div class="w-6 h-0.5 bg-gray-600"></div>
            <div class="w-6 h-0.5 bg-gray-600"></div>
            <div class="w-6 h-0.5 bg-gray-600"></div>
        </div>
    </header>

    <main class="max-w-md mx-auto bg-white min-h-screen shadow-sm">
        
        <div class="p-6 text-center">
            <p class="text-[10px] uppercase font-bold text-gray-400 tracking-widest mb-2">Animais / Pets</p>
            <h1 class="text-2xl font-black text-[#444] leading-tight">Malu precisa de você 🙏</h1>
            <p class="text-xs text-gray-500 mt-1 uppercase font-bold tracking-tighter">ID: 4088889</p>
        </div>

        <div class="relative px-4">
            <img src="https://images.unsplash.com/photo-1541123437800-1bb1317badc2?q=80&w=600" class="w-full rounded-2xl shadow-md h-64 object-cover">
            <div class="absolute inset-y-0 left-6 flex items-center">
                <div class="bg-green-500 p-2 rounded-full text-white shadow-lg opacity-80 cursor-pointer">◀</div>
            </div>
            <div class="absolute inset-y-0 right-6 flex items-center">
                <div class="bg-green-500 p-2 rounded-full text-white shadow-lg opacity-80 cursor-pointer">▶</div>
            </div>
        </div>

        <div class="p-6 flex items-center space-x-3">
            <div class="flex -space-x-2">
                <div class="w-8 h-8 rounded-full bg-blue-500 border-2 border-white flex items-center justify-center text-[10px] text-white">❤️</div>
                <div class="w-8 h-8 rounded-full bg-red-500 border-2 border-white flex items-center justify-center text-[10px] text-white">❤️</div>
                <div class="w-8 h-8 rounded-full bg-green-500 border-2 border-white flex items-center justify-center text-[10px] text-white font-bold">+</div>
            </div>
            <p class="text-sm font-bold text-gray-700 underline decoration-green-500 decoration-2 underline-offset-4">536 corações recebidos 💚</p>
        </div>

        <div class="px-6 flex items-start space-x-4 mb-6">
            <div class="w-14 h-14 bg-pink-100 rounded-full flex items-center justify-center p-2 border border-pink-200">
                <img src="https://cdn-icons-png.flaticon.com/512/194/194279.png" class="opacity-70">
            </div>
            <div>
                <h3 class="font-black text-gray-800 text-sm">Anjos de 4 Patas</h3>
                <p class="text-[10px] text-gray-500">Vila Velha / Espirito Santo</p>
                <p class="text-[10px] text-gray-500 font-bold uppercase mt-0.5">Ativo(a) no Vakinha desde março/2021</p>
                <div class="flex space-x-4 mt-1">
                    <p class="text-[10px] font-bold text-gray-700">9 vaquinhas criadas</p>
                    <p class="text-[10px] font-bold text-gray-700">3 vaquinhas apoiadas</p>
                </div>
            </div>
        </div>

        <div class="px-6 mb-8">
            <div class="flex justify-between items-end mb-1">
                <span class="text-xl font-black text-green-500 italic">54%</span>
            </div>
            <div class="w-full bg-gray-200 h-2.5 rounded-full overflow-hidden">
                <div class="bg-green-500 h-full progress-bar" style="width: 54%"></div>
            </div>
            <div class="flex justify-between mt-2 font-black">
                <span class="text-xl text-green-600 font-black tracking-tighter">R$ 2.430,00</span>
                <span class="text-sm text-gray-400 mt-1">de R$ 4.500,00</span>
            </div>
        </div>

        <div class="px-6 border-t pt-6">
            <div class="flex space-x-4 mb-4">
                <span class="text-sm font-bold text-green-600 border-b-2 border-green-600 pb-1">Sobre</span>
            </div>
            
            <div class="bg-gray-50 p-6 rounded-2xl border border-gray-100 mb-8">
                <p class="text-xs font-bold text-gray-500 mb-2 uppercase">Vaquinha criada em: 09/01/2026</p>
                <p class="text-green-600 font-black mb-4 flex items-center">✅ História Verificada</p>
                
                <div class="space-y-4 text-sm text-gray-700 leading-relaxed font-medium">
                    <p>Uma cachorrinha indefesa sofreu uma violência brutal, marcada por abuso e ferimentos graves. Deus nos chama a agir com compaixão. Você vai virar as costas?</p>
                    <p>🚨 Malu sofreu uma crueldade inimaginável. Foi violentada, gravemente ferida e abandonada à própria dor. Ainda assim, Deus a sustentou quando tudo parecia perdido.</p>
                    <p>Agora ela espera pelo milagre do amor — e esse milagre pode chegar através da sua doação.</p>
                </div>
            </div>
        </div>

        <div class="px-6 pb-20">
            <h3 class="font-black text-gray-700 mb-6">Comentários recentes</h3>
            
            <div class="space-y-8">
                <div class="flex space-x-3">
                    <img src="https://randomuser.me/api/portraits/women/45.jpg" class="w-10 h-10 rounded-full border">
                    <div>
                        <p class="text-xs font-black text-blue-700">Nicole Silva</p>
                        <p class="text-xs text-gray-600 leading-snug mt-0.5 font-medium">Contribuí com 100 reais porque acompanho esse instituto há um tempo e confio no trabalho deles. Fiz o que pude, pois não suporto ver tanta dor nos olhinhos desses animais.</p>
                        <div class="flex space-x-3 text-[10px] font-bold text-blue-800 mt-2 uppercase">
                            <span>Responder</span> <span>•</span> <span>Curtir</span> <span>•</span> <span>Seguir</span> <span>•</span> <span class="text-gray-400">3 min</span>
                        </div>
                    </div>
                </div>

                <div class="flex space-x-3">
                    <img src="https://randomuser.me/api/portraits/women/12.jpg" class="w-10 h-10 rounded-full border">
                    <div>
                        <p class="text-xs font-black text-blue-700">Leandra Martins</p>
                        <p class="text-xs text-gray-600 leading-snug mt-0.5 font-medium">Contribuí aqui também, sempre apoio eles porque transformam vidas.</p>
                        <div class="flex space-x-3 text-[10px] font-bold text-blue-800 mt-2 uppercase">
                            <span>Responder</span> <span>•</span> <span>Curtir</span> <span>•</span> <span>Seguir</span> <span>•</span> <span class="text-gray-400">7 min</span>
                        </div>
                    </div>
                </div>
            </div>

            <button class="w-full bg-blue-500 text-white font-bold py-3 rounded-lg mt-10 text-sm">Ver todos os comentários</button>
        </div>

    </main>

    <div id="notif-toast" class="notification-toast animate__animated animate__fadeInUp">
        <div class="bg-white/95 shadow-2xl rounded-full px-6 py-3 border border-gray-100 flex items-center space-x-3">
            <img src="https://randomuser.me/api/portraits/women/65.jpg" class="w-8 h-8 rounded-full border">
            <div>
                <p class="text-xs font-bold text-green-600">Gabriela Duarte</p>
                <p class="text-[10px] font-black text-gray-500 uppercase tracking-tighter">Acabou de doar R$ 100,00</p>
            </div>
        </div>
    </div>

    <div class="footer-sticky">
        <div class="max-w-md mx-auto">
            <button onclick="window.location.href='TEU_LINK_DE_PAGAMENTO'" class="w-full bg-green-500 hover:bg-green-600 text-white font-black py-4 rounded-xl text-lg shadow-lg shadow-green-200 transition-all uppercase tracking-wider">
                Quero Ajudar
            </button>
        </div>
    </div>

    <script>
        // Lógica da Notificação Flutuante
        function showNotification() {
            const toast = document.getElementById('notif-toast');
            toast.style.display = 'block';
            setTimeout(() => {
                toast.classList.replace('animate__fadeInUp', 'animate__fadeOutDown');
                setTimeout(() => {
                    toast.style.display = 'none';
                    toast.classList.replace('animate__fadeOutDown', 'animate__fadeInUp');
                }, 1000);
            }, 4000);
        }

        // Mostra a notificação a cada 10 segundos
        setInterval(showNotification, 10000);
        setTimeout(showNotification, 3000);

        // Aumenta a barra de progresso suavemente ao carregar
        window.onload = () => {
            const bar = document.querySelector('.progress-bar');
            bar.style.width = '0%';
            setTimeout(() => bar.style.width = '54%', 500);
        };
    </script>
</body>
</html>
