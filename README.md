<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>A Fonte da Juventude - Método Europeu</title>
    <style>
        /* RESET E CORES */
        body { font-family: 'Segoe UI', Arial, sans-serif; margin: 0; padding: 0; background-color: #f0f2f5; color: #1c1e21; line-height: 1.6; }
        .container { max-width: 600px; margin: 0 auto; background: #fff; box-shadow: 0 4px 12px rgba(0,0,0,0.1); }
        
        /* HEADER */
        header { background: #003366; color: white; padding: 15px; text-align: center; font-size: 13px; font-weight: bold; border-bottom: 4px solid #f39c12; }
        
        /* SEÇÃO PRINCIPAL */
        .headline-container { padding: 25px 15px; text-align: center; }
        h1 { font-size: 26px; color: #d63031; line-height: 1.2; margin-bottom: 15px; }
        h2 { font-size: 19px; color: #2d3436; font-weight: normal; margin-bottom: 20px; }
        
        /* VÍDEO / IMAGEM */
        .video-placeholder { width: 100%; aspect-ratio: 16/9; background: #000; display: flex; align-items: center; justify-content: center; color: white; position: relative; cursor: pointer; }
        .play-button { font-size: 60px; opacity: 0.8; }

        /* BOTÃO DE COMPRA */
        .btn-container { padding: 30px 20px; text-align: center; }
        .btn-pix { background: #27ae60; color: white; text-decoration: none; padding: 20px 30px; font-size: 22px; font-weight: bold; border-radius: 10px; display: block; animation: pulse 1.5s infinite; box-shadow: 0 5px 15px rgba(39, 174, 96, 0.4); }
        @keyframes pulse { 0% { transform: scale(1); } 50% { transform: scale(1.05); } 100% { transform: scale(1); } }
        
        /* PREÇO E ESCASSEZ */
        .price { margin-bottom: 10px; }
        .old-price { text-decoration: line-through; color: #636e72; font-size: 18px; }
        .new-price { color: #27ae60; font-size: 32px; font-weight: bold; }
        .vagas { color: #d63031; font-weight: bold; font-size: 14px; margin-top: 10px; }

        /* TEXTO DE CONTEÚDO */
        .content { padding: 20px; font-size: 18px; text-align: justify; }
        .content b { color: #003366; }

        /* DEPOIMENTOS FACEBOOK */
        .fb-comments { border-top: 1px solid #ddd; padding: 20px; background: #fff; }
        .fb-title { font-size: 14px; color: #4b4f56; font-weight: bold; margin-bottom: 15px; border-bottom: 1px solid #ddd; padding-bottom: 10px; }
        .comment { display: flex; margin-bottom: 15px; }
        .avatar { width: 48px; height: 48px; border-radius: 50%; margin-right: 10px; background: #eee; }
        .comment-box { background: #f0f2f5; padding: 10px; border-radius: 18px; flex: 1; }
        .comment-name { color: #385898; font-weight: bold; font-size: 13px; cursor: pointer; }
        .comment-text { font-size: 14px; color: #1c1e21; display: block; margin-top: 3px; }
        .comment-actions { font-size: 12px; color: #90949c; margin-top: 5px; margin-left: 10px; }

        /* POPUP */
        #popup { position: fixed; bottom: 20px; left: 20px; background: #333; color: white; padding: 15px; border-radius: 10px; display: none; font-size: 14px; z-index: 9999; box-shadow: 0 10px 30px rgba(0,0,0,0.5); border-left: 5px solid #27ae60; }

        /* FOOTER */
        footer { padding: 30px; text-align: center; font-size: 12px; color: #636e72; background: #f0f2f5; }
    </style>
</head>
<body>

<div class="container">
    <header>ESTUDO REVELA MÉTODO DA EUROPA PARA ALÍVIO DE DORES</header>

    <div class="headline-container">
        <h1>O "Interruptor da Juventude": Destrave seu corpo em apenas 7 minutos por dia</h1>
        <h2>O segredo para viver sem dores e sem depender de remédios de farmácia.</h2>
    </div>

    <div class="video-placeholder">
        <div class="play-button">▶</div>
        <p style="position:absolute; bottom:10px; font-size:12px;">Clique para iniciar o áudio</p>
    </div>

    <div class="content">
        <p>Você já sentiu que seu corpo está <b>"enferrujado"</b>? De acordo com pesquisadores da <b>Universidade de Heidelberg</b>, na Alemanha, isso ocorre pela inflamação das articulações.</p>
        <p>Desenvolvemos o guia <b>"A Fonte da Juventude"</b>, focado em movimentos simples para fazer sentado, que lubrificam suas juntas e devolvem sua disposição.</p>
        <p><b>O QUE VOCÊ VAI RECEBER HOJE:</b></p>
        <ul>
            <li>Guia "A Fonte da Juventude" (Vídeos e PDF)</li>
            <li>Bônus: O Chá Anti-inflamatório Europeu</li>
            <li>Bônus: Protocolo Adeus Remédios</li>
        </ul>
    </div>

    <div class="btn-container">
        <div class="price">
            <span class="old-price">De R$ 197,00 por</span><br>
            <span class="new-price">R$ 47,00</span>
        </div>
        <a href="SEU_LINK_DA_KIRVANO_AQUI" class="btn-pix">QUERO MEU ACESSO AGORA</a>
        <p class="vagas">⚠️ ATENÇÃO: Restam apenas 7 unidades com desconto.</p>
    </div>

    <div class="fb-comments">
        <div class="fb-title">12 comentários</div>
        
        <div class="comment">
            <img class="avatar" src="https://i.pravatar.cc/150?u=98">
            <div class="comment-box">
                <span class="comment-name">Maria das Graças</span>
                <span class="comment-text">Gente, eu estava quase marcando cirurgia. Com 4 dias fazendo o método sentado já me sinto outra pessoa!</span>
            </div>
        </div>
        <div class="comment-actions">Curtir · Responder · 12 min</div>

        <div class="comment" style="margin-top:15px;">
            <img class="avatar" src="https://i.pravatar.cc/150?u=12">
            <div class="comment-box">
                <span class="comment-name">Roberto Silva</span>
                <span class="comment-text">O chá que o Emmanuel ensina no bônus é tiro e queda. Recomendo muito o guia.</span>
            </div>
        </div>
        <div class="comment-actions">Curtir · Responder · 25 min</div>

        <div class="comment" style="margin-top:15px;">
            <img class="avatar" src="https://i.pravatar.cc/150?u=5">
            <div class="comment-box">
                <span class="comment-name">Zuleide Pereira</span>
                <span class="comment-text">Consegui comprar! Só tinham 7 vagas quando entrei. Ansiosa pra começar.</span>
            </div>
        </div>
        <div class="comment-actions">Curtir · Responder · 43 min</div>
    </div>

    <footer>
        A Fonte da Juventude © 2026<br>
        Este site não é afiliado ao Facebook. Todo o conteúdo é meramente informativo.
    </footer>
</div>

<div id="popup">✅ <b>Joana G.</b> acabou de garantir o acesso!</div>

<script>
    // Script do Popup a cada 7 segundos
    const nomes = ["Ricardo S.", "Maria L.", "Antônio P.", "Dona Cida", "Geraldo M.", "Terezinha F."];
    const popup = document.getElementById('popup');
    
    setInterval(() => {
        const nomeAleatorio = nomes[Math.floor(Math.random() * nomes.length)];
        popup.innerHTML = `✅ <b>${nomeAleatorio}</b> acabou de garantir o acesso!`;
        popup.style.display = 'block';
        
        setTimeout(() => {
            popup.style.display = 'none';
        }, 4000); // Fica visível por 4 segundos
    }, 7000); // Repete a cada 7 segundos
</script>

</body>
</html>
