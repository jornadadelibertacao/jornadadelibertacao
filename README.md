<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>A Fonte da Juventude - Método Europeu</title>
    <link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Nunito', sans-serif; margin: 0; padding: 0; background-color: #f0f9ff; color: #2d3436; }
        .container { max-width: 600px; margin: 0 auto; background: #fff; border: none; box-shadow: 0 10px 30px rgba(0,0,0,0.1); }
        
        /* HEADER COLORIDO */
        .top-bar { background: linear-gradient(90deg, #ff4757, #ff6b81); color: white; padding: 12px; text-align: center; font-size: 14px; font-weight: 900; text-transform: uppercase; letter-spacing: 1px; }
        
        /* HEADLINE COLORIDA */
        .headline-section { padding: 40px 20px; text-align: center; background: #fff; }
        h1 { font-size: 30px; color: #0984e3; line-height: 1.2; margin: 0 0 15px 0; font-weight: 900; }
        .highlight { background: #fee08b; color: #d35400; padding: 2px 8px; border-radius: 5px; }
        h2 { font-size: 20px; color: #636e72; font-weight: 400; margin: 0; line-height: 1.5; }

        /* VSL CONTAINER */
        .vsl-outer { padding: 0 15px 30px 15px; }
        .vsl-container { background: #000; border: 4px solid #0984e3; border-radius: 15px; overflow: hidden; position: relative; padding-bottom: 56.25%; height: 0; box-shadow: 0 10px 20px rgba(9, 132, 227, 0.2); }
        .vsl-container div { position: absolute; top: 0; left: 0; width: 100%; height: 100%; display: flex; align-items: center; justify-content: center; color: white; font-weight: bold; }

        /* SEÇÃO DE BÔNUS ULTRA COLORIDA */
        .bonus-section { padding: 25px; background: #e3f2fd; border: 3px solid #0984e3; margin: 20px; border-radius: 20px; position: relative; }
        .bonus-badge { position: absolute; top: -15px; left: 50%; transform: translateX(-50%); background: #ff9f43; color: white; padding: 5px 20px; border-radius: 20px; font-weight: 900; font-size: 14px; }
        .bonus-title { text-align: center; font-weight: 900; color: #0984e3; font-size: 22px; margin: 10px 0 20px 0; }
        .bonus-item { display: flex; align-items: center; margin-bottom: 15px; background: #fff; padding: 15px; border-radius: 15px; border-left: 6px solid #ff9f43; }
        .bonus-icon { font-size: 35px; margin-right: 15px; }
        .bonus-text b { color: #2d3436; font-size: 17px; display: block; }
        .bonus-text span { font-size: 14px; color: #636e72; }

        /* PREÇO E BOTÃO COLORIDO */
        .cta-section { text-align: center; padding: 30px 20px; background: #fff; }
        .old-price { font-size: 20px; color: #b2bec3; text-decoration: line-through; }
        .new-price { font-size: 52px; color: #2ecc71; font-weight: 900; display: block; margin: 0; }
        .btn-cta { background: #2ecc71; color: white; text-decoration: none; padding: 22px; font-size: 26px; font-weight: 900; border-radius: 50px; display: block; box-shadow: 0 8px 0 #27ae60; transition: 0.2s; animation: pulse 1.5s infinite; }
        @keyframes pulse { 0% { transform: scale(1); } 50% { transform: scale(1.05); } 100% { transform: scale(1); } }
        .urgency { color: #ff4757; font-weight: 900; margin-top: 20px; font-size: 16px; }

        /* FACEBOOK COMMENTS - ESTILIZADO */
        .fb-comments { padding: 20px; background: #fff; border-top: 10px solid #f0f9ff; }
        .fb-header { font-weight: 900; color: #0984e3; border-bottom: 2px solid #f0f9ff; padding-bottom: 10px; margin-bottom: 20px; display: flex; justify-content: space-between; }
        .comment { display: flex; margin-bottom: 20px; }
        .avatar { width: 50px; height: 50px; border-radius: 50%; margin-right: 12px; border: 2px solid #0984e3; }
        .comment-content { background: #f1f2f6; padding: 15px; border-radius: 20px; flex: 1; }
        .name { color: #2f3542; font-weight: 900; font-size: 14px; margin-bottom: 5px; display: block; }
        .text { font-size: 15px; color: #2f3542; line-height: 1.4; }
        .footer-comment { font-size: 12px; color: #a4b0be; margin-top: 8px; margin-left: 10px; font-weight: bold; }

        /* POPUP VISUALIZAÇÃO */
        #visitor-popup { position: fixed; bottom: 20px; left: 20px; background: #2f3542; color: white; padding: 12px 20px; border-radius: 50px; font-size: 14px; font-weight: 700; display: flex; align-items: center; gap: 10px; z-index: 1000; box-shadow: 0 10px 20px rgba(0,0,0,0.2); }
        .dot { height: 12px; width: 12px; background-color: #2ecc71; border-radius: 50%; display: inline-block; animation: blink 1s infinite; }
        @keyframes blink { 0% { opacity: 1; } 50% { opacity: 0.3; } 100% { opacity: 1; } }
    </style>
</head>
<body>

<div class="top-bar">🚨 ATENÇÃO: ÚLTIMAS 7 VAGAS COM 75% DE DESCONTO</div>

<div class="container">
    <div class="headline-section">
        <h1>Recupere a <span class="highlight">Liberdade</span> do seu Corpo!</h1>
        <h2>O guia prático para eliminar dores sentado no sofá, sem remédios e sem esforço.</h2>
    </div>

    <div class="vsl-outer">
        <div class="vsl-container">
            <div>
                <p style="font-size:20px">▶ CLIQUE PARA ASSISTIR</p>
            </div>
        </div>
    </div>

    <div class="cta-section">
        <span class="old-price">De R$ 197,00 por apenas</span>
        <span class="new-price">R$ 47,00</span>
        <a href="SEU_LINK_KIRVANO" class="btn-cta">QUERO MINHA VAGA AGORA</a>
        <p class="urgency">⚠️ OPORTUNIDADE ÚNICA: Restam apenas 7 unidades!</p>
    </div>

    <div class="bonus-section">
        <div class="bonus-badge">GRÁTIS HOJE</div>
        <div class="bonus-title">VOCÊ TAMBÉM VAI RECEBER:</div>
        
        <div class="bonus-item">
            <span class="bonus-icon">☕</span>
            <div class="bonus-text">
                <b>BÔNUS 1: O Chá Mágico Europeu</b>
                <span>Desinflame suas juntas enquanto dorme.</span>
            </div>
        </div>

        <div class="bonus-item">
            <span class="bonus-icon">💧</span>
            <div class="bonus-text">
                <b>BÔNUS 2: Protocolo Adeus Remédios</b>
                <span>A limpeza natural para o seu estômago e fígado.</span>
            </div>
        </div>

        <div class="bonus-item">
            <span class="bonus-icon">🍎</span>
            <div class="bonus-text">
                <b>BÔNUS 3: Menu da Juventude</b>
                <span>O que comer para ter energia de um jovem de 30 anos.</span>
            </div>
        </div>
    </div>

    <div class="fb-comments">
        <div class="fb-header">
            <span>Comentários (12)</span>
            <span style="font-size: 12px; color: #a4b0be;">Mais recentes</span>
        </div>
        
        <div class="comment">
            <img class="avatar" src="https://randomuser.me/api/portraits/women/44.jpg">
            <div>
                <div class="comment-content">
                    <span class="name">Tereza Neves</span>
                    <span class="text">Gente do céu, eu não conseguia nem levantar pra ir ao banheiro. Com 3 dias de método já estou outra mulher! Gratidão Emmanuel! 🙏</span>
                </div>
                <div class="footer-comment">Curtir · Responder · 4 min</div>
            </div>
        </div>

        <div class="comment">
            <img class="avatar" src="https://randomuser.me/api/portraits/men/32.jpg">
            <div>
                <div class="comment-content">
                    <span class="name">João Ferreira</span>
                    <span class="text">Sou ex-atleta e o joelho tava acabado. Esse bônus do chá me surpreendeu, funcionou melhor que o remédio da farmácia.</span>
                </div>
                <div class="footer-comment">Curtir · Responder · 15 min</div>
            </div>
        </div>

        <div class="comment">
            <img class="avatar" src="https://randomuser.me/api/portraits/women/65.jpg">
            <div>
                <div class="comment-content">
                    <span class="name">Maria Auxiliadora</span>
                    <span class="text">Eu vi o anúncio e corri! Só tinha 7 vagas mesmo. O material é muito caprichado, vale muito a pena.</span>
                </div>
                <div class="footer-comment">Curtir · Responder · 22 min</div>
            </div>
        </div>

        <div class="comment">
            <img class="avatar" src="https://randomuser.me/api/portraits/men/85.jpg">
            <div>
                <div class="comment-content">
                    <span class="name">Luiz Carlos</span>
                    <span class="text">Finalmente algo honesto. Sem promessas milagrosas, mas com resultado real. Minha coluna agradece.</span>
                </div>
                <div class="footer-comment">Curtir · Responder · 34 min</div>
            </div>
        </div>

        <div class="comment">
            <img class="avatar" src="https://randomuser.me/api/portraits/women/22.jpg">
            <div>
                <div class="comment-content">
                    <span class="name">Fátima Souza</span>
                    <span class="text">Fiz a primeira vez ontem e hoje acordei sem aquela rigidez matinal. Estou impressionada!</span>
                </div>
                <div class="footer-comment">Curtir · Responder · 1h</div>
            </div>
        </div>
    </div>

    <footer style="text-align: center; padding: 40px; font-size: 12px; color: #a4b0be;">
        A Fonte da Juventude &copy; 2026<br>
        Todos os direitos reservados.
    </footer>
</div>

<div id="visitor-popup">
    <span class="dot"></span>
    <span id="visitor-count">48</span> pessoas vendo esta página agora
</div>

<script>
    const countElement = document.getElementById('visitor-count');
    setInterval(() => {
        let current = parseInt(countElement.innerText);
        let change = Math.floor(Math.random() * 5) - 2; 
        let newValue = current + change;
        if (newValue < 40) newValue = 40;
        if (newValue > 62) newValue = 62;
        countElement.innerText = newValue;
    }, 4000);
</script>

</body>
</html>
