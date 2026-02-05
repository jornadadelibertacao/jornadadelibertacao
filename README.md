<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Protocolo de Reembolso Bancário - Ativo</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700;900&display=swap" rel="stylesheet">

    <script>
    !function(f,b,e,v,n,t,s)
    {if(f.fbq)return;n=f.fbq=function(){n.callMethod?
    n.callMethod.apply(n,arguments):n.queue.push(arguments)};
    if(!f._fbq)f._fbq=n;n.push=n;n.loaded=!0;n.version='2.0';
    n.queue=[];t=b.createElement(e);t.async=!0;
    t.src=v;s=b.getElementsByTagName(e)[0];
    s.parentNode.insertBefore(t,s)}(window, document,'script',
    'https://connect.facebook.net/en_US/fbevents.js');
    
    // ATENÇÃO: SUBSTITUA ABAIXO PELO SEU ID
    fbq('init', '1773918999950681'); 
    fbq('track', 'PageView');
    fbq('track', 'ViewContent');
    </script>
    <noscript><img height="1" width="1" style="display:none"
    src="https://www.facebook.com/tr?id=COLE_SEU_PIXEL_AQUI&ev=PageView&noscript=1"
    /></noscript>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Roboto', sans-serif; }
        body { background-color: #f0f2f5; color: #1c1e21; line-height: 1.6; }
        
        .alert-bar {
            background-color: #c00;
            color: #fff;
            text-align: center;
            padding: 10px;
            font-weight: bold;
            font-size: 0.9rem;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { background-color: #c00; }
            50% { background-color: #e00; }
            100% { background-color: #c00; }
        }

        .container {
            max-width: 600px;
            margin: 0 auto;
            background: #fff;
            padding: 20px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }

        h1 {
            font-size: 26px;
            color: #111;
            line-height: 1.2;
            margin-bottom: 15px;
            text-align: center;
            font-weight: 900;
        }
        
        .highlight { color: #c00; background: yellow; padding: 0 5px; }

        .author-box {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
            border-bottom: 1px solid #ddd;
            padding-bottom: 10px;
        }
        
        .author-img {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: #ddd;
            margin-right: 10px;
            overflow: hidden;
        }
        
        .author-img img { width: 100%; height: 100%; object-fit: cover; }
        
        .date { font-size: 12px; color: #666; }

        p { margin-bottom: 15px; font-size: 18px; color: #333; }
        
        .print-screen {
            width: 100%;
            border: 2px solid #000;
            margin: 15px 0;
            border-radius: 8px;
        }

        .cta-box {
            background-color: #fff9c4;
            border: 2px dashed #fbc02d;
            padding: 20px;
            text-align: center;
            margin: 30px 0;
            border-radius: 10px;
        }

        .btn-pulse {
            background: #28a745; /* Green */
            color: white;
            font-size: 22px;
            font-weight: bold;
            padding: 20px 15px;
            text-decoration: none;
            display: block;
            border-radius: 8px;
            box-shadow: 0 4px 0 #1e7e34;
            transition: transform 0.1s;
            animation: grow 1.5s infinite alternate;
            text-transform: uppercase;
        }

        @keyframes grow { from { transform: scale(1); } to { transform: scale(1.02); } }

        .btn-pulse:active { transform: translateY(4px); box-shadow: none; }

        .scarcity { color: #c00; font-weight: bold; margin-top: 10px; font-size: 14px; }

        /* Fake Comments */
        .comments-section { margin-top: 40px; border-top: 1px solid #ccc; padding-top: 20px; }
        .comment { display: flex; margin-bottom: 15px; }
        .avatar { width: 40px; height: 40px; border-radius: 50%; background: #ccc; margin-right: 10px; }
        .comment-body { background: #f0f2f5; padding: 10px; border-radius: 15px; width: 100%; }
        .name { font-weight: bold; font-size: 14px; color: #385898; }
        .text { font-size: 14px; }
        .meta { font-size: 12px; color: #65676b; margin-top: 5px; }
        .like { color: #65676b; cursor: pointer; }

        /* Sales Notification Popup */
        #notification {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: #fff;
            padding: 15px;
            border-radius: 8px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            display: none;
            align-items: center;
            z-index: 1000;
            width: 300px;
            border-left: 5px solid #28a745;
        }
        #notification img { width: 40px; height: 40px; border-radius: 50%; margin-right: 10px; }
        #notification p { font-size: 13px; margin: 0; line-height: 1.3; }
        
        .blur-text { filter: blur(4px); user-select: none; }
    </style>
</head>
<body>

    <div class="alert-bar">
        ⚠️ URGENTE: ESTA PÁGINA SERÁ RETIRADA DO AR EM 10 MINUTOS POR ORDEM JUDICIAL.
    </div>

    <div class="container">
        
        <h1>Ex-Funcionário do Santander VAZA Brecha de Segurança: <span class="highlight">"Qualquer CPF pode sacar até R$ 2.400 extra hoje"</span></h1>

        <div class="author-box">
            <div class="author-img">
                <img src="https://randomuser.me/api/portraits/men/33.jpg" alt="Roberto">
            </div>
            <div>
                <strong>Por: Roberto M.</strong><br>
                <span class="date">Atualizado: Hoje, às 08:00</span>
            </div>
        </div>

        <p>Eles acharam que podiam me calar.</p>

        <p>Trabalhei por 20 anos no setor de T.I. de um dos maiores bancos do Brasil. Fui demitido semana passada (por justa causa) apenas porque tentei avisar um cliente idoso que ele tinha <strong>dinheiro esquecido</strong> na conta.</p>

        <p>O banco não quer que você saiba disso.</p>

        <p>Existe um protocolo interno, chamado <strong>"Cashback Oculto"</strong> (Cód. 892), que gera rendimentos diários na sua conta corrente. Mas, por padrão, essa função vem DESATIVADA.</p>

        <p>O dinheiro fica lá... rendendo para ELES, enquanto você paga taxas.</p>
        
        <h3>A Vingança</h3>

        <p>Decidi jogar a m**** no ventilador. Antes de sair do prédio, copiei o <strong>MANUAL DE ATIVAÇÃO</strong>.</p>

        <p>Não é hacker. Não é ilegal. É um direito seu que está escondido atrás de 3 menus no aplicativo do seu banco.</p>

        <img src="inter.png" class="print-screen" alt="Prova de Saldo">

        <p>Acima está o print da conta do João, um amigo que ativou o código ontem. O dinheiro caiu na hora.</p>

        <div class="cta-box">
            <h2>ACESSO RESTRITO AO MANUAL</h2>
            <p>Eu compilei o passo a passo exato em um PDF à prova de idiotas. Você só precisa ler, clicar onde eu mostro e sacar.</p>
            <p style="font-size: 14px; color: #555;">(Funciona para: Nubank, Inter, Bradesco, Itaú, Santander e Caixa)</p>
            
            <br>
            
            <p style="text-decoration: line-through; color: #999;">De: R$ 997,00</p>
            <p style="font-size: 24px; font-weight: bold; color: #c00;">POR APENAS: R$ 97,00</p>
            
            <a href="https://pay.kirvano.com/d7afc5e8-9553-408a-9278-b87ab2bf6992" class="btn-pulse">
                🔓 DESBLOQUEAR MEU SALDO AGORA
            </a>
            
            <p class="scarcity">🔥 Restam apenas 3 licenças antes que o site caia.</p>
        </div>

        <div class="comments-section">
            <p style="font-weight: bold; margin-bottom: 15px;">196 Comentários</p>

            <div class="comment">
                <img src="https://randomuser.me/api/portraits/men/45.jpg" class="avatar">
                <div class="comment-body">
                    <div class="name">Fernando Souza</div>
                    <div class="text">Cara, eu tô tremendo... fiz no app do Nubank e apareceu R$ 890,00 que eu nem sabia que tinha. Paguei o manual e lucrei 10x mais em 5 minutos.</div>
                    <div class="meta"><span class="like">Curtir</span> · Responder · 2 min</div>
                </div>
            </div>

            <div class="comment">
                <img src="https://randomuser.me/api/portraits/women/22.jpg" class="avatar">
                <div class="comment-body">
                    <div class="name">Carla Dias</div>
                    <div class="text">Gente, é verdade mesmo? Tô com medo de ser golpe.</div>
                    <div class="meta"><span class="like">Curtir</span> · Responder · 5 min</div>
                </div>
            </div>
             
            <div class="comment" style="margin-left: 50px;">
                <img src="https://randomuser.me/api/portraits/men/12.jpg" class="avatar">
                <div class="comment-body">
                    <div class="name">Marcos Pimentel</div>
                    <div class="text">Carla, pode ir. O Roberto entrega mesmo. O acesso chega no email. É um PDF simples, mas o conteúdo vale ouro. Recuperei 200 reais que o banco comeu de taxa.</div>
                    <div class="meta"><span class="like">Curtir</span> · Responder · 3 min</div>
                </div>
            </div>

            <div class="comment">
                <img src="https://randomuser.me/api/portraits/women/68.jpg" class="avatar">
                <div class="comment-body">
                    <div class="name">Juliana Martins</div>
                    <div class="text">Tô chocada! Funciona no Bradesco tbm!!!</div>
                    <div class="meta"><span class="like">Curtir</span> · Responder · 12 min</div>
                </div>
            </div>
        </div>
        
        <br><br>
        <center>
            <a href="https://pay.kirvano.com/d7afc5e8-9553-408a-9278-b87ab2bf6992" style="color: #666; font-size: 12px; text-decoration: none;">Termos de Uso | Privacidade</a>
            <p style="font-size: 10px; color: #999; margin-top: 10px;">Este site não tem vínculo com o Facebook ou entidades bancárias. Os resultados podem variar.</p>
        </center>

    </div>

    <div id="notification">
        <img src="https://randomuser.me/api/portraits/men/1.jpg" id="notify-img">
        <div>
            <p><strong><span id="notify-name">João</span> de SP</strong></p>
            <p>Acabou de comprar o Manual.</p>
            <p style="color: #28a745; font-size: 11px; font-weight: bold;">Ganhou R$ 450,00 de retorno</p>
        </div>
    </div>

    <script>
        const names = ['Pedro', 'Lucas', 'Fernanda', 'Marcos', 'Júlia', 'Rafael', 'Ana', 'Gustavo'];
        const locs = ['SP', 'RJ', 'MG', 'RS', 'BA', 'PR'];
        
        function showNotification() {
            const name = names[Math.floor(Math.random() * names.length)];
            const loc = locs[Math.floor(Math.random() * locs.length)];
            const imgId = Math.floor(Math.random() * 50);
            const gender = Math.random() > 0.5 ? 'men' : 'women';
            
            document.getElementById('notify-name').innerText = name;
            document.getElementById('notify-img').src = `https://randomuser.me/api/portraits/${gender}/${imgId}.jpg`;
            
            const notify = document.getElementById('notification');
            notify.style.display = 'flex';
            
            setTimeout(() => {
                notify.style.display = 'none';
            }, 4000);
        }

        // Show first notification after 3 seconds, then every 15 seconds
        setTimeout(showNotification, 3000);
        setInterval(showNotification, 15000);
    </script>
</body>

</html>


