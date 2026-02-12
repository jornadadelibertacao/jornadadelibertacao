<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>A Fonte da Juventude - Método Europeu</title>
    <link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;800;900&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #0066FF;
            --secondary: #22C55E;
            --accent: #F59E0B;
            --danger: #EF4444;
            --bg: #F8FAFC;
        }

        body { 
            font-family: 'Nunito', sans-serif; 
            margin: 0; 
            padding: 0; 
            background-color: var(--bg); 
            color: #1E293B; 
            overflow-x: hidden;
        }

        .top-banner {
            background: linear-gradient(90deg, #1E40AF, #3B82F6);
            color: white;
            text-align: center;
            padding: 12px;
            font-weight: 800;
            font-size: 14px;
            text-transform: uppercase;
        }

        .container {
            max-width: 550px;
            margin: 0 auto;
            background: white;
            box-shadow: 0 20px 50px rgba(0,0,0,0.05);
        }

        .hero {
            padding: 40px 20px;
            text-align: center;
        }

        h1 {
            font-size: 32px;
            line-height: 1.1;
            margin-bottom: 20px;
            color: #0F172A;
            font-weight: 900;
        }

        .highlight {
            color: var(--primary);
            position: relative;
            display: inline-block;
        }

        .video-box {
            margin: 0 15px;
            background: #000;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 15px 30px rgba(0,0,0,0.2);
            position: relative;
            padding-bottom: 56.25%;
            height: 0;
            border: 4px solid white;
        }

        .vsl-placeholder {
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            color: white;
            background: linear-gradient(rgba(0,0,0,0.3), rgba(0,0,0,0.7));
            cursor: pointer;
        }

        .play-btn {
            width: 70px;
            height: 70px;
            background: var(--danger);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 10px;
            font-size: 30px;
            animation: pulse-shadow 2s infinite;
        }

        @keyframes pulse-shadow {
            0% { box-shadow: 0 0 0 0 rgba(239, 68, 68, 0.7); }
            70% { box-shadow: 0 0 0 20px rgba(239, 68, 68, 0); }
            100% { box-shadow: 0 0 0 0 rgba(239, 68, 68, 0); }
        }

        .bonus-card {
            margin: 20px;
            padding: 25px;
            background: #EFF6FF;
            border-radius: 24px;
            border: 2px solid #DBEAFE;
        }

        .bonus-item {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 15px;
            background: white;
            padding: 12px;
            border-radius: 16px;
        }

        .bonus-icon { font-size: 32px; }

        .price-tag {
            text-align: center;
            padding: 30px 20px;
        }

        .old-price { text-decoration: line-through; color: #94A3B8; font-size: 18px; }
        .new-price { font-size: 56px; font-weight: 900; color: var(--secondary); display: block; }

        .btn-buy {
            background: var(--secondary);
            color: white;
            text-decoration: none;
            display: block;
            padding: 22px;
            border-radius: 50px;
            font-size: 24px;
            font-weight: 900;
            box-shadow: 0 10px 25px rgba(34, 197, 94, 0.3);
            margin: 20px 0;
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-5px); }
        }

        .fb-section {
            padding: 20px;
            border-top: 8px solid #F1F5F9;
        }

        .comment {
            display: flex;
            gap: 12px;
            margin-bottom: 20px;
        }

        .avatar {
            width: 48px;
            height: 48px;
            border-radius: 50%;
            border: 2px solid var(--primary);
        }

        .comment-bubble {
            background: #F1F5F9;
            padding: 12px 16px;
            border-radius: 18px;
            flex: 1;
        }

        .comment-name {
            font-weight: 800;
            color: #2563EB;
            font-size: 14px;
            display: block;
            margin-bottom: 4px;
        }

        .visitor-counter {
            position: fixed;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            background: rgba(15, 23, 42, 0.9);
            color: white;
            padding: 10px 20px;
            border-radius: 30px;
            font-size: 14px;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 8px;
            z-index: 100;
            backdrop-filter: blur(5px);
        }

        .live-dot {
            height: 8px;
            width: 8px;
            background: var(--secondary);
            border-radius: 50%;
            animation: blink 1s infinite;
        }

        @keyframes blink { 50% { opacity: 0; } }

    </style>
</head>
<body>

    <div class="top-banner">⚠️ ÚLTIMAS 7 VAGAS COM DESCONTO DISPONÍVEIS</div>

    <div class="container">
        <section class="hero">
            <h1>Recupere sua <span class="highlight">Agilidade</span> de 20 Anos atrás</h1>
            <h2>Destrave seu corpo em 7 minutos com o segredo Europeu. Sem remédios e sem sair de casa.</h2>
        </section>

        <div class="video-box">
            <div class="vsl-placeholder">
                <div class="play-btn">▶</div>
                <p>Clique para assistir o método</p>
            </div>
        </div>

        <section class="price-tag">
            <span class="old-price">De R$ 197,00 por</span>
            <span class="new-price">R$ 47,00</span>
            <a href="SEU_LINK_KIRVANO" class="btn-buy">QUERO ACESSO AGORA</a>
            <p style="color:var(--danger); font-weight: 800; font-size: 14px;">PROMOÇÃO VÁLIDA SOMENTE HOJE!</p>
        </section>

        <section class="bonus-card">
            <p style="text-align:center; font-weight:900; color:var(--primary); margin-top:0;">VOCÊ TAMBÉM LEVA GRÁTIS:</p>
            
            <div class="bonus-item">
                <span class="bonus-icon">🍵</span>
                <div class="bonus-text">
                    <b style="display:block">O Chá Mágico Europeu</b>
                    <small>Desinflamação profunda enquanto dorme.</small>
                </div>
            </div>

            <div class="bonus-item">
                <span class="bonus-icon">🧘</span>
                <div class="bonus-text">
                    <b style="display:block">Guia Articulações Blindadas</b>
                    <small>Como nunca mais travar a coluna ou joelho.</small>
                </div>
            </div>
        </section>

        <section class="fb-section">
            <p style="font-weight:900; margin-bottom:20px;">Comentários (12)</p>

            <div class="comment">
                <img src="https://randomuser.me/api/portraits/women/45.jpg" class="avatar">
                <div class="comment-bubble">
                    <span class="comment-name">Maria Helena</span>
                    <span>Emmanuel, meu filho, Deus te abençoe! Fiz os movimentos hoje cedo e já consegui caminhar sem dor.</span>
                </div>
            </div>

            <div class="comment">
                <img src="https://randomuser.me/api/portraits/men/33.jpg" class="avatar">
                <div class="comment-bubble">
                    <span class="comment-name">Antônio Silva</span>
                    <span>Tava cético, mas o bônus do chá valeu o investimento. Me sinto mais leve. Recomendo!</span>
                </div>
            </div>

            <div class="comment">
                <img src="https://randomuser.me/api/portraits/women/68.jpg" class="avatar">
                <div class="comment-bubble">
                    <span class="comment-name">Sônia Regina</span>
                    <span>Consegui pegar a penúltima vaga! Ansiosa pra ver os resultados.</span>
                </div>
            </div>
        </section>

        <footer style="text-align:center; padding: 40px; font-size: 12px; color: #94A3B8;">
            A Fonte da Juventude &copy; 2026<br>
            CNPJ: 00.000.000/0001-00
        </footer>
    </div>

    <div class="visitor-counter">
        <span class="live-dot"></span>
        <span id="v-count">47</span> pessoas vendo agora
    </div>

    <script>
        const count = document.getElementById('v-count');
        setInterval(() => {
            let n = parseInt(count.innerText);
            let diff = Math.floor(Math.random() * 5) - 2;
            let final = n + diff;
            if(final < 40) final = 40;
            if(final > 62) final = 62;
            count.innerText = final;
        }, 3000);
    </script>

</body>
</html>
