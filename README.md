<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>A Fonte da Juventude - Método Europeu</title>
    <style>
        body { font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; margin: 0; padding: 0; background-color: #f5f7f8; color: #333; }
        .container { max-width: 600px; margin: 0 auto; background: #fff; border: 1px solid #e1e4e8; }
        
        /* HEADER ALERTA */
        .top-bar { background: #cc0000; color: white; padding: 10px; text-align: center; font-size: 14px; font-weight: bold; text-transform: uppercase; }
        
        /* HEADLINE */
        .headline-section { padding: 30px 20px; text-align: center; background: #fff; }
        h1 { font-size: 28px; color: #1a202c; line-height: 1.2; margin: 0 0 15px 0; font-weight: 800; }
        .highlight { background-color: #ffeb3b; padding: 2px 5px; }
        h2 { font-size: 18px; color: #4a5568; font-weight: 400; margin: 0; line-height: 1.5; }

        /* VÍDEO VSL */
        .vsl-container { background: #000; width: 100%; position: relative; padding-bottom: 56.25%; height: 0; }
        .vsl-container iframe, .vsl-container div { position: absolute; top: 0; left: 0; width: 100%; height: 100%; display: flex; align-items: center; justify-content: center; color: white; }

        /* SEÇÃO DE BÔNUS (ESTILIZADA) */
        .bonus-section { padding: 25px; background: #f9f9f9; border: 2px dashed #003366; margin: 20px; border-radius: 15px; }
        .bonus-title { text-align: center; font-weight: bold; color: #003366; font-size: 20px; margin-bottom: 20px; text-transform: uppercase; }
        .bonus-item { display: flex; align-items: center; margin-bottom: 15px; background: #fff; padding: 10px; border-radius: 8px; box-shadow: 0 2px 5px rgba(0,0,0,0.05); }
        .bonus-icon { font-size: 30px; margin-right: 15px; }
        .bonus-text b { color: #d63031; display: block; font-size: 16px; }
        .bonus-text span { font-size: 14px; color: #555; }

        /* PREÇO E BOTÃO */
        .cta-section { text-align: center; padding: 30px 20px; background: #fff; }
        .old-price { font-size: 18px; color: #999; text-decoration: line-through; }
        .new-price { font-size: 48px; color: #27ae60; font-weight: 900; display: block; margin: 5px 0; }
        .btn-cta { background: #28a745; color: white; text-decoration: none; padding: 20px; font-size: 24px; font-weight: bold; border-radius: 12px; display: block; box-shadow: 0 6px 0 #1e7e34; transition: 0.2s; animation: pulse 1.5s infinite; }
        @keyframes pulse { 0% { transform: scale(1); } 50% { transform: scale(1.03); } 100% { transform: scale(1); } }
        .urgency { color: #cc0000; font-weight: bold; margin-top: 15px; font-size: 15px; }

        /* FACEBOOK COMMENTS */
        .fb-comments { padding: 20px; background: #fff; border-top: 10px solid #f0f2f5; }
        .comment { display: flex; margin-bottom: 20px; font-size: 14px; }
        .avatar { width: 48px; height: 48px; border-radius: 50%; margin-right: 10px; object-fit: cover; }
        .comment-content { background: #f0f2f5; padding: 12px; border-radius: 18px; flex: 1; }
        .name { color: #385898; font-weight: bold; font-size: 13px; margin-bottom: 3px; display: block; }
        .footer-comment { font-size: 12px; color: #90949c; margin-top: 5px; margin-left: 10px; }

        /* POPUP VISUALIZAÇÃO */
        #visitor-popup { position: fixed; bottom: 20px; left: 20px; background: rgba(0,0,0,0.8); color: white; padding: 12px 20px; border-radius: 30px; font-size: 14px; font-weight: bold; display: flex; align-items: center; gap: 10px; z-index: 1000; transition: 0.5s; }
        .dot { height: 10px; width: 10px; background-color: #27ae60; border-radius: 50%; display: inline-block; animation: blink 1s infinite; }
        @keyframes blink { 0% { opacity: 1; } 50% { opacity: 0.3; } 100% { opacity: 1; } }
    </style>
</head>
<body>

<div class="top-bar">⚠️ PROMOÇÃO EXCLUSIVA: RESTAM APENAS 7 VAGAS COM DESCONTO</div>

<div class="container">
    <div class="headline-section">
        <h1>O Método Europeu para <span class="highlight">Destravar o Corpo</span> sem Remédios</h1>
        <h2>Apenas 7 minutos por dia sentado no seu sofá para recuperar a agilidade dos seus 40 anos.</h2>
    </div>

    <div class="vsl-container">
        <div>
            <p>▶ [VÍDEO DE APRESENTAÇÃO]</p>
        </div>
    </div>

    <div class="cta-section">
        <span class="old-price">De R$ 197,00</span>
        <span class="new-price">R$ 47,00</span>
        <a href="SEU_LINK_KIRVANO" class="btn-cta">QUERO MEU ACESSO AGORA</a>
        <p class="urgency">⚠️ ATENÇÃO: Restam apenas 7 vagas com este preço!</p>
    </div>

    <div class="bonus-section">
        <div class="bonus-title">🎁 PRESENTES EXCLUSIVOS (SÓ HOJE)</div>
        
        <div class="bonus-item">
            <span class="bonus-icon">☕</span>
            <div class="bonus-text">
                <b>BÔNUS 1: O Chá Secreto Europeu</b>
                <span>A receita milenar para desinflamar as juntas em 24h.</span>
            </div>
        </div>

        <div class="bonus-item">
            <span class="bonus-icon">💊</span>
            <div class="bonus-text">
                <b>BÔNUS 2: Protocolo Adeus Remédios</b>
                <span>Como diminuir a dependência de químicos usando a natureza.</span>
            </div>
        </div>

        <div class="bonus-item">
            <span class="bonus-icon">🥗</span>
            <div class="bonus-text">
                <b>BÔNUS 3: Guia Alimentar da Juventude</b>
                <span>Os 5 alimentos que você deve evitar para não envelhecer rápido.</span>
            </div>
        </div>
    </div>

    <div class="fb-comments">
        <p style="font-weight: bold; border-bottom: 1px solid #ddd; padding-bottom: 10px;">12 comentários</p>
        
        <div class="comment">
            <img class="avatar" src="https://randomuser.me/api/portraits/women/44.jpg">
            <div>
                <div class="comment-content">
                    <span class="name">Tereza Neves</span>
                    <span>Gente, eu não conseguia nem levantar da cadeira sem gemer de dor. Fiz os exercícios hoje e pareço outra! Deus abençoe vcs!</span>
                </div>
                <div class="footer-comment">Curtir · Responder · 4 min</div>
            </div>
        </div>

        <div class="comment">
            <img class="avatar" src="https://randomuser.me/api/portraits/men/32.jpg">
            <div>
                <div class="comment-content">
                    <span class="name">João Ferreira</span>
                    <span>O chá que eles ensinam no bônus 1 é fantástico. Já economizei muito em pomada pra dor. Vale cada centavo!</span>
                </div>
                <div class="footer-comment">Curtir · Responder · 15 min</div>
            </div>
        </div>

        <div class="comment">
            <img class="avatar" src="https://randomuser.me/api/portraits/women/65.jpg">
            <div>
                <div class="comment-content">
                    <span class="name">Maria Auxiliadora</span>
                    <span>Consegui pegar o meu por 47 reais agora, faltavam só 2 quando finalizei. Ansiosa!</span>
                </div>
                <div class="footer-comment">Curtir · Responder · 22 min</div>
            </div>
        </div>

        <div class="comment">
            <img class="avatar" src="https://randomuser.me/api/portraits/men/85.jpg">
            <div>
                <div class="comment-content">
                    <span class="name">Luiz Carlos</span>
                    <span>Minha coluna travada era um pesadelo. Esses alongamentos de cadeira salvaram meu dia. Recomendo.</span>
                </div>
                <div class="footer-comment">Curtir · Responder · 34 min</div>
            </div>
        </div>

        <div class="comment">
            <img class="avatar" src="https://randomuser.me/api/portraits/women/22.jpg">
            <div>
                <div class="comment-content">
                    <span class="name">Fátima Souza</span>
                    <span>Comprei para o meu marido e estamos fazendo juntos. Ele parou de reclamar da dor no joelho logo no segundo dia.</span>
                </div>
                <div class="footer-comment">Curtir · Responder · 1h</div>
            </div>
        </div>
    </div>

    <footer style="text-align: center; padding: 30px; font-size: 12px; color: #999;">
        A Fonte da Juventude &copy; 2026<br>
        Termos de Uso | Políticas de Privacidade
    </footer>
</div>

<div id="visitor-popup">
    <span class="dot"></span>
    <span id="visitor-count">54</span> pessoas vendo esta página agora
</div>

<script>
    // Atualiza o contador de pessoas vendo agora para parecer real
    const countElement = document.getElementById('visitor-count');
    setInterval(() => {
        let current = parseInt(countElement.innerText);
        let change = Math.floor(Math.random() * 5) - 2; // Varia entre -2 e +2
        let newValue = current + change;
        if (newValue < 40) newValue = 40;
        if (newValue > 62) newValue = 62;
        countElement.innerText = newValue;
    }, 4000);
</script>

</body>
</html>
