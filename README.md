<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vakinha Online - Ajuda da Luana</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"/>
    <style>
        body { font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; background-color: #f4f7f6; }
        .progress-fill { transition: width 2s ease-in-out; }
        .notif-float { display: none; position: fixed; bottom: 110px; left: 20px; z-index: 999; }
        .sticky-footer { position: fixed; bottom: 0; left: 0; width: 100%; background: white; padding: 15px; box-shadow: 0 -5px 15px rgba(0,0,0,0.05); z-index: 100; }
        .modal { display: none; position: fixed; inset: 0; background: rgba(0,0,0,0.9); align-items: center; justify-content: center; z-index: 1000; backdrop-filter: blur(5px); }
        .modal.active { display: flex; }
    </style>
</head>
<body class="pb-28">

    <div id="notif-box" class="notif-float animate__animated animate__fadeInUp">
        <div class="bg-white/95 shadow-2xl rounded-full px-5 py-2.5 border border-gray-100 flex items-center space-x-3">
            <div class="bg-green-500 w-2 h-2 rounded-full animate-ping"></div>
            <div class="text-[11px]">
                <p class="font-bold text-gray-800"><span id="notif-nome">Mariana</span> acabou de doar</p>
                <p class="text-green-600 font-black">R$ <span id="notif-valor">27,50</span></p>
            </div>
        </div>
    </div>

    <header class="bg-white p-4 flex justify-between items-center border-b sticky top-0 z-50">
        <img src="https://logodownload.org/wp-content/uploads/2018/10/vakinha-logo.png" class="h-7">
        <div class="flex space-x-1.5 items-center">
            <span class="text-[10px] font-black text-red-500 uppercase tracking-tighter">Ao vivo: 842 ajudando</span>
            <div class="w-2 h-2 bg-red-500 rounded-full animate-pulse"></div>
        </div>
    </header>

    <main class="max-w-md mx-auto bg-white min-h-screen shadow-sm">
        
        <div class="p-6">
            <div class="flex items-center space-x-2 mb-2">
                <span class="bg-green-100 text-green-700 text-[9px] font-black px-2 py-0.5 rounded uppercase">Campanha Verificada</span>
                <span class="text-[9px] text-gray-400 font-bold uppercase">ID: 928374</span>
            </div>
            <h1 class="text-2xl font-black text-gray-800 leading-tight">Escolher entre minha faculdade ou o prato deles foi a dor mais forte que senti...</h1>
        </div>

        <div class="relative px-4">
            <img src="https://images.unsplash.com/photo-1534361960057-19889db9621e?q=80&w=600" class="w-full rounded-2xl h-72 object-cover shadow-lg border-2 border-white">
            <div class="absolute bottom-6 left-8 bg-black/50 backdrop-blur-sm text-white px-3 py-1 rounded-full text-[10px] font-bold">
                📸 Ver 12 fotos da garagem
            </div>
        </div>

        <div class="p-6 flex items-center space-x-4 border-b border-gray-50">
            <div class="w-14 h-14 rounded-full border-2 border-green-500 p-0.5">
                <img src="https://randomuser.me/api/portraits/women/44.jpg" class="w-full h-full rounded-full object-cover">
            </div>
            <div>
                <h3 class="font-black text-gray-800 text-sm">Luana Oliveira</h3>
                <p class="text-[10px] text-gray-500 font-bold uppercase tracking-widest">Vila Velha / ES</p>
                <div class="flex space-x-3 mt-1 text-[10px] font-bold text-green-600">
                    <span>14 resgatados hoje</span>
                    <span>9 vaquinhas concluídas</span>
                </div>
            </div>
        </div>

        <div class="p-6">
            <div class="flex justify-between items-end mb-1">
                <span class="text-2xl font-black text-green-500">R$ <span id="money">2.418,92</span></span>
                <span class="text-[10px] text-gray-400 font-bold mb-1 uppercase">Meta: R$ 5.000,00</span>
            </div>
            <div class="w-full bg-gray-100 h-3 rounded-full overflow-hidden border border-gray-50">
                <div id="prog-bar" class="bg-green-500 h-full progress-fill" style="width: 48%"></div>
            </div>
            <p class="text-[11px] text-gray-400 font-medium mt-3 italic underline decoration-green-300 underline-offset-4 tracking-tighter uppercase">536 pessoas já contribuíram para essa missão</p>
        </div>

        <div class="px-6 py-4 space-y-5 text-[15px] text-gray-700 leading-relaxed font-medium">
            <p>Oi, eu sou a Luana. Tudo começou com o <b>Bolinha</b>. Ele dormia exatamente na frente do meu portão todo santo dia. Comecei dando um resto de comida, depois comprei um saquinho de ração... e meu coração não me deixou parar ali.</p>
            
            <p>Em poucos meses, minha garagem virou o abrigo de 14 anjos. Eu já doei 3 filhotes para amigos próximos, mas sou muito rigorosa, pois eles merecem o melhor. Em breve vou abrir um formulário de adoção oficial.</p>
            
            <div class="bg-green-50 p-5 rounded-2xl border-l-4 border-green-500 italic text-green-900 font-bold shadow-sm">
                "Paguei minha faculdade e meu orçamento zerou. Tive que escolher entre os livros do semestre e a ração dos meus anjos. Eu escolhi eles, mas hoje não tenho mais nada para amanhã."
            </div>

            <p>Tive um imprevisto familiar pesado, onde tive que ajudar com remédios e cirurgia em casa, o que quebrou meu orçamento. Não peço por mim, peço por eles. Salve uma vida agora.</p>
        </div>

        <div class="p-6 bg-gray-50 mt-10">
            <h4 class="font-black text-gray-700 text-sm mb-6 flex items-center">
                <span class="bg-green-500 w-1 h-4 mr-2"></span> Comentários (14)
            </h4>
            <div class="space-y-6">
                <div class="flex space-x-3">
                    <img src="https://randomuser.me/api/portraits/women/67.jpg" class="w-9 h-9 rounded-full border">
                    <div class="text-xs">
                        <p class="font-black text-blue-700">Beatriz Helena</p>
                        <p class="text-gray-600 mt-1 font-medium">Lu, você é um anjo! Acabei de doar R$ 50 para ajudar na ração. Parabéns pela coragem!</p>
                        <p class="text-[10px] font-bold text-gray-400 mt-2 uppercase">Curtir • Responder • 2 min</p>
                    </div>
                </div>
            </div>
        </div>

    </main>

    <div id="modal-pix" class="modal">
        <div class="bg-white rounded-[40px] p-8 max-w-xs w-full text-center relative animate__animated animate__fadeInUp shadow-2xl">
            <button onclick="closePix()" class="absolute top-6 right-6 text-gray-300 text-2xl font-bold">&times;</button>
            <p class="text-green-500 font-black text-[10px] uppercase tracking-widest mb-2">Pague com PIX Copia e Cola</p>
            <h2 class="text-3xl font-black text-gray-900 mb-6">R$ <span id="modal-vlr">0,00</span></h2>
            
            <img id="modal-qr" src="" class="w-48 h-48 mx-auto mb-6 p-2 border-2 border-dashed border-green-200 rounded-3xl shadow-inner">
            
            <button id="btn-copy" onclick="copy()" class="w-full bg-green-500 text-white font-black py-4 rounded-2xl shadow-lg active:scale-95 transition mb-3 uppercase text-sm tracking-wider">Copiar Código PIX</button>
            <p id="msg-copy" class="text-blue-600 text-[10px] font-black hidden">CÓDIGO COPIADO! AGORA COLE NO SEU BANCO.</p>
        </div>
    </div>

    <div class="sticky-footer max-w-md mx-auto">
        <button onclick="scrollToTop()" class="w-full bg-green-500 hover:bg-green-600 text-white font-black py-4 rounded-2xl text-lg shadow-xl shadow-green-200 transition-transform active:scale-95 uppercase">
            Quero Ajudar Agora
        </button>
    </div>

    <script>
        let pixCode = "";
        let currentAmt = 2418.92;

        // Efeito de valor subindo
        setInterval(() => {
            currentAmt += Math.random() * 3.50;
            document.getElementById('money').innerText = currentAmt.toLocaleString('pt-BR', { minimumFractionDigits: 2 });
            document.getElementById('prog-bar').style.width = (currentAmt / 5000 * 100) + "%";
        }, 12000);

        // Notificações flutuantes
        const nomes = ["Camila", "Fernanda", "Rodrigo", "Sérgio", "Márcia", "Talita"];
        const valores = ["12,00", "27,50", "50,00", "15,00"];
        function showNotif() {
            document.getElementById('notif-nome').innerText = nomes[Math.floor(Math.random()*nomes.length)];
            document.getElementById('notif-valor').innerText = valores[Math.floor(Math.random()*valores.length)];
            const n = document.getElementById('notif-box');
            n.style.display = 'block';
            setTimeout(() => { n.style.display = 'none'; }, 4500);
        }
        setInterval(showNotif, 15000);

        function scrollToTop() {
            // No mobile, abriremos as opções direto para facilitar
            openPix('27,50', 'COLE_SEU_PIX_AQUI', 'LINK_QR_27');
        }

        function openPix(v, p, i) {
            document.getElementById('modal-vlr').innerText = v;
            document.getElementById('modal-qr').src = i;
            document.getElementById('modal-pix').classList.add('active');
            pixCode = p;
        }
        function closePix() { document.getElementById('modal-pix').classList.remove('active'); }
        function copy() {
            navigator.clipboard.writeText(pixCode);
            document.getElementById('btn-copy').innerText = "CÓDIGO COPIADO!";
        }
    </script>
</body>
</html>
