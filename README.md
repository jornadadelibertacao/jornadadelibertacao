<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Diário da Lu | Minha Jornada</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Lora:italic,wght@400;700&family=Inter:wght@300;400;600;800&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; }
        .serif { font-family: 'Lora', serif; }
        .progress-bar { transition: width 3s ease-in-out; }
        #pix-modal { display: none; position: fixed; inset: 0; background: rgba(0,0,0,0.9); z-index: 999; align-items: center; justify-content: center; backdrop-filter: blur(10px); }
        #pix-modal.active { display: flex; }
        .carrossel { display: flex; overflow-x: auto; scroll-snap-type: x mandatory; gap: 10px; }
        .carrossel img { flex: 0 0 80%; scroll-snap-align: center; border-radius: 15px; height: 250px; object-cover: cover; }
    </style>
</head>
<body class="bg-[#FCFCFC] text-[#333]">

    <div class="bg-purple-600 text-white text-[11px] py-2 text-center font-bold tracking-widest uppercase px-4">
        Atualizado: Terça-feira, 27 de Janeiro de 2026 - Por Luana Oliveira
    </div>

    <article class="max-w-2xl mx-auto bg-white shadow-sm pb-20">
        
        <header class="p-8 text-center border-b border-gray-100">
            <h1 class="serif italic text-4xl text-gray-800 mb-2 font-bold leading-tight">O que eu não contei para ninguém até agora...</h1>
            <p class="text-gray-400 text-sm italic">Como minha vida mudou depois do Bolinha e o desafio de manter 14 anjos sozinha.</p>
        </header>

        <div class="px-4 py-6">
            <img src="https://images.unsplash.com/photo-1541123437800-1bb1317badc2?q=80&w=800" class="w-full h-96 object-cover rounded-2xl shadow-lg mb-8">
            
            <div class="prose prose-purple mx-auto text-gray-700 leading-relaxed space-y-6">
                <p class="text-lg serif italic">
                    "Oi, se você chegou até aqui, provavelmente viu algum vídeo meu ou alguém que me conhece te mandou esse link. Meu nome é Luana, moro em [Sua Cidade] e hoje minha vida se resume a duas coisas: meus estudos na faculdade e o abrigo improvisado na minha garagem."
                </p>

                <h2 class="text-2xl font-bold text-gray-900 mt-10">Tudo começou com uma marmita...</h2>
                <p>
                    Eu estava no segundo semestre da faculdade quando o <b>Bolinha</b> apareceu. Ele dormia exatamente na frente do meu portão. No começo, eu dava só o que sobrava da janta, mas ele me olhava de um jeito que eu não conseguia ignorar. Comecei a comprar um saquinho de ração pequeno e, em menos de um mês, ele já era o dono da calçada.
                </p>

                <p>
                    O tempo passou e as pessoas começaram a notar. Infelizmente, no nosso bairro, quando veem alguém cuidando, acham que podem abandonar mais. De repente, eram 3, depois 7... hoje estou com 14. Eu já doei 3 filhotes para amigos muito próximos da faculdade, porque sou super rigorosa, não entrego para qualquer um. Inclusive, em breve quero abrir um formulário oficial para adoção responsável, mas por enquanto, eles são minha responsabilidade.
                </p>

                <div class="bg-gray-50 p-4 rounded-3xl my-10">
                    <p class="text-xs font-bold text-gray-400 mb-3 uppercase tracking-tighter text-center">Conheça alguns dos meus pequenos:</p>
                    <div class="carrossel pb-4">
                        <img src="https://images.unsplash.com/photo-1583511655857-d19b40a7a54e?w=400" alt="Dog 1">
                        <img src="https://images.unsplash.com/photo-1537151608828-ea2b11777ee8?w=400" alt="Dog 2">
                        <img src="https://images.unsplash.com/photo-1598133894008-61f7fdb8cc3a?w=400" alt="Dog 3">
                        <img src="https://images.unsplash.com/photo-1517423440428-a5a00ad1e3e8?w=400" alt="Dog 4">
                    </div>
                </div>

                <h2 class="text-2xl font-bold text-gray-900">O momento em que tudo apertou...</h2>
                <p>
                    Eu vinha conseguindo manter tudo com ajuda de alguns amigos e fazendo bicos. Mas esse mês foi o meu "limite". Tive gastos altíssimos com livros técnicos para o curso e, para piorar, uma pessoa da minha família que mora comigo adoeceu e quebrou a perna. Tive que ajudar com remédios e o orçamento que já era curto, simplesmente evaporou.
                </p>
                <p class="font-bold text-red-600 italic border-l-4 border-red-500 pl-4">
                    Eu tive que escolher: ou eu pagava os materiais e a ajuda em casa, ou eu comprava a ração do mês. Eu optei pelos meus anjos, mas agora não tenho como comprar os remédios de verme e as vacinas atrasadas.
                </p>

                <div class="bg-purple-50 p-6 rounded-2xl border border-purple-100 my-8">
                    <p class="text-sm text-purple-800 mb-4 font-semibold">Em breve vou organizar um sorteio para tentar estabilizar tudo, mas hoje a urgência é o prato de comida deles.</p>
                    
                    <div class="flex justify-between text-xs mb-1 font-bold text-purple-900">
                        <span>Arrecadado: R$ <span id="val">2.842,00</span></span>
                        <span>Meta: R$ 5.000</span>
                    </div>
                    <div class="w-full bg-gray-200 h-3 rounded-full overflow-hidden">
                        <div id="bar" class="bg-purple-600 h-full progress-bar" style="width: 56%"></div>
                    </div>
                </div>

                <div class="space-y-6 pt-6 border-t border-gray-100">
                    <h3 class="text-xl font-bold text-center">Se você puder me ajudar com qualquer valor...</h3>
                    
                    <div class="grid gap-4">
                        <button onclick="openPix('15,00', 'SEU_PIX_AQUI', 'QR_LINK')" class="w-full bg-white border-2 border-gray-200 p-6 rounded-2xl flex justify-between items-center hover:border-purple-500 transition shadow-sm">
                            <div class="text-left">
                                <span class="block font-bold text-gray-800">Doar R$ 15,00</span>
                                <span class="text-xs text-gray-400 italic">"Ajuda com a ração do dia"</span>
                            </div>
                            <span class="text-purple-600 font-bold">DOAR PIX</span>
                        </button>

                        <button onclick="openPix('37,00', 'SEU_PIX_AQUI', 'QR_LINK')" class="w-full bg-purple-600 p-6 rounded-2xl flex justify-between items-center shadow-xl shadow-purple-100 scale-105 border-4 border-white">
                            <div class="text-left">
                                <span class="block font-bold text-white">Doar R$ 37,00</span>
                                <span class="text-xs text-purple-200 italic">"Ração + Vacina de 1 dog"</span>
                            </div>
                            <span class="text-white font-black">MAIS ESCOLHIDO</span>
                        </button>

                        <button onclick="openPix('60,00', 'SEU_PIX_AQUI', 'QR_LINK')" class="w-full bg-white border-2 border-gray-200 p-6 rounded-2xl flex justify-between items-center hover:border-purple-500 transition shadow-sm">
                            <div class="text-left">
                                <span class="block font-bold text-gray-800">Doar R$ 60,00</span>
                                <span class="text-xs text-gray-400 italic">"Kit cuidado completo"</span>
                            </div>
                            <span class="text-purple-600 font-bold">DOAR PIX</span>
                        </button>
                    </div>
                </div>

                <p class="text-center text-xs text-gray-400 pt-10">
                    Obrigada por ler minha história. Cada vida salva é uma vitória nossa. <br> Com carinho, Luana.
                </p>
            </div>
        </div>
    </article>

    <div id="pix-modal">
        <div class="bg-white rounded-[40px] p-10 max-w-sm w-full text-center animate__animated animate__fadeInUp">
            <p class="text-purple-600 font-bold text-xs mb-2">VOCÊ ESTÁ SALVANDO UMA VIDA!</p>
            <h2 class="text-4xl font-black text-gray-900 mb-6">R$ <span id="vlr">0,00</span></h2>
            <img id="qr" src="" class="w-48 h-48 mx-auto mb-6 p-2 border-2 border-dashed border-purple-200 rounded-3xl">
            <button onclick="copyPix()" id="copy-btn" class="w-full bg-purple-600 text-white font-bold py-5 rounded-2xl shadow-lg active:scale-95 transition mb-4">COPIAR CÓDIGO PIX</button>
            <button onclick="closePix()" class="text-gray-400 text-xs font-bold uppercase tracking-widest">Agora não</button>
        </div>
    </div>

    <script>
        let pixCode = "";
        let valAtual = 2842.00;

        // Aumenta o valor conforme a pessoa fica no site
        setInterval(() => {
            valAtual += Math.random() * 2;
            document.getElementById('val').innerText = valAtual.toLocaleString('pt-BR', { minimumFractionDigits: 2 });
            document.getElementById('bar').style.width = (valAtual / 5000 * 100) + "%";
        }, 5000);

        function openPix(v, p, i) {
            document.getElementById('vlr').innerText = v;
            document.getElementById('qr').src = i;
            document.getElementById('pix-modal').classList.add('active');
            pixCode = p;
        }
        function closePix() { document.getElementById('pix-modal').classList.remove('active'); }
        function copyPix() {
            navigator.clipboard.writeText(pixCode);
            document.getElementById('copy-btn').innerText = "COPIADO!";
            setTimeout(() => { document.getElementById('copy-btn').innerText = "COPIAR CÓDIGO PIX"; }, 3000);
        }
    </script>
</body>
</html>
