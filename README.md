<html><head><base href="https://cristianbiblico.com/"><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no"><style>
html, body {
    height: 100%;
    margin: 0;
    padding: 0;
    overflow-x: hidden;
    overflow-y: auto;
}

body {
    font-family: 'Arial', sans-serif;
    font-size: 16px;
    background-color: #e8f4f8; /* Light blue background */
    color: #333;
    line-height: 1.6;
    padding: 10px;
    margin: 0;
    box-sizing: border-box;
    margin-bottom: 30px; /* Add this to create space for the footer */
    min-height: 100vh;
    display: flex;
    flex-direction: column;
}

.game-container, .login-container {
    flex: 1;
    overflow-y: auto;
    padding-bottom: 60px; /* Add space for footer */
}

.footer {
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
}

h1, h2 {
    color: #2c3e50;
    text-align: center;
}

.category-selector, .question-container, .result, .score, .timer, .team-info {
    width: 100%;
    max-width: 600px;
    margin: 10px auto;
}

.team-display {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
}

.team {
    width: 100%;
    max-width: 300px;
    margin: 10px;
}

.answer-btn, .next-btn, .summary-btn, .footer-settings-btn {
    width: 100%;
    max-width: 400px;
    margin: 5px auto;
    display: block;
}

.watermark {
    position: absolute;
    top: 10px;
    right: 10px;
    font-size: 14px;
    color: rgba(0, 0, 0, 0.3);
    pointer-events: none;
}

#category-dropdown {
    width: 100%;
    max-width: none;
    padding: 12px 20px;
    border: none;
    border-radius: 25px;
    background-color: #3498db;
    color: white;
    font-size: 16px;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 1px;
    cursor: pointer;
    transition: all 0.3s ease;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    appearance: none;
    -webkit-appearance: none;
    -moz-appearance: none;
    background-image: url('data:image/svg+xml;charset=US-ASCII,<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="6 9 12 15 18 9"></polyline></svg>');
    background-repeat: no-repeat;
    background-position: right 10px center;
    margin-bottom: 10px;
}

#category-dropdown:hover {
    background-color: #2980b9;
    transform: translateY(-2px);
    box-shadow: 0 4px 8px rgba(0,0,0,0.2);
}

#category-dropdown:focus {
    outline: none;
    box-shadow: 0 0 0 3px rgba(52, 152, 219, 0.5);
}

.question-container {
    background-color: #f0f8ff; /* Light blue background */
    padding: 20px;
    border-radius: 5px;
    margin-bottom: 20px;
}

.answer-btn {
    display: block;
    width: 100%;
    padding: 10px;
    margin-bottom: 10px;
    background-color: #ecf0f1; /* Light gray background */
    color: #2c3e50;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: all 0.3s ease;
    font-size: 16px;
}

.answer-btn.selected {
    background-color: #ffd700; /* Gold color for selected answers */
}

.answer-btn.correct-answer {
    background-color: #3498db; /* Blue color for correct answers */
    color: white;
}

.answer-btn:hover {
    background-color: #bdc3c7;
}

.result {
    text-align: center;
    font-weight: bold;
    margin-top: 20px;
    padding: 10px;
    background-color: #f0f8ff; /* Light blue background */
    border-radius: 5px;
}

.daily-verse {
    background-color: #f9e79f;
    padding: 15px;
    border-radius: 5px;
    margin-top: 30px;
    text-align: center;
    font-style: italic;
    margin-bottom: 40px; /* Increase bottom margin to prevent overlap with footer */
}

.score {
    text-align: center;
    font-size: 1.2em;
    margin-top: 20px;
    background-color: #f0f8ff; /* Light blue background */
    padding: 10px;
    border-radius: 5px;
}

.timer {
    font-size: 1.5em;
    font-weight: bold;
    color: #e74c3c;
    text-align: center;
    margin-bottom: 20px;
    background-color: #f0f8ff; /* Light blue background */
    padding: 10px;
    border-radius: 5px;
}

.team-info {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
    background-color: #f0f8ff;
    padding: 15px;
    border-radius: 10px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

.current-team {
    font-size: 1.2em;
    font-weight: bold;
    color: #2c3e50;
}

.next-btn {
    padding: 10px 20px;
    background-color: #2ecc71;
    color: white;
    border: none;
    border-radius: 25px;
    cursor: pointer;
    font-size: 1em;
    transition: all 0.3s ease;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

.next-btn:hover {
    background-color: #27ae60;
    transform: translateY(-2px);
    box-shadow: 0 4px 8px rgba(0,0,0,0.2);
}

.next-btn:active {
    transform: translateY(0);
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}

.fade-in {
    animation: fadeIn 0.5s;
}

.login-container {
    max-width: 400px;
    width: 100%;
    margin: 50px auto;
    padding: 20px;
    background-color: #fff;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0,0,0,0.1);
    box-sizing: border-box;
}

.login-container h2 {
    text-align: center;
    color: #2c3e50;
}

.login-container input {
    width: 100%;
    padding: 10px;
    margin-bottom: 10px;
    border: 1px solid #ddd;
    border-radius: 5px;
}

.login-container button {
    width: 100%;
    padding: 10px;
    background-color: #3498db;
    color: white;
    border: none;
    border-radius: 5px;
}

.login-container button:hover {
    background-color: #2980b9;
}

.team-display {
    margin-top: 20px;
    text-align: center;
}

.team {
    display: inline-block;
    width: 45%;
    padding: 10px;
    margin: 10px;
    background-color: #ecf0f1;
    border-radius: 5px;
}

.final-results {
    background-color: #f0f8ff;
    padding: 20px;
    border-radius: 10px;
    margin-top: 20px;
    text-align: center;
}

.team-result {
    background-color: #ffffff;
    border-radius: 5px;
    padding: 10px;
    margin-bottom: 10px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

.team-result h3 {
    color: #3498db;
    margin-bottom: 10px;
}

.player-list {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
}

.player {
    background-color: #ecf0f1;
    padding: 5px 10px;
    border-radius: 15px;
    font-size: 0.9em;
}

.footer {
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: rgba(44, 62, 80, 0.7);
    color: #ecf0f1;
    padding: 5px 0;
    font-size: 0.8em;
    overflow: hidden;
    white-space: nowrap;
    z-index: 100;
}

.footer-content {
    display: inline-block;
    padding-left: 100%;
    animation: scroll-left 30s linear infinite;
}

@keyframes scroll-left {
    0% { transform: translateX(100%); }
    100% { transform: translateX(-100%); }
}

#summary-page {
    display: none;
    max-width: 600px;
    width: 100%;
    margin: 50px auto;
    padding: 20px;
    background-color: #ffffff;
    border-radius: 10px;
    box-shadow: 0 0 20px rgba(0,0,0,0.1);
    box-sizing: border-box;
}

#summary-page h2 {
    text-align: center;
    color: #2c3e50;
    margin-bottom: 20px;
}

.summary-content {
    display: flex;
    justify-content: space-between;
}

.team-summary {
    width: 48%;
    background-color: #f0f8ff;
    padding: 15px;
    border-radius: 10px;
}

.team-summary h3 {
    color: #3498db;
    margin-bottom: 10px;
}

.player-list {
    margin-top: 10px;
}

.player {
    background-color: #ecf0f1;
    padding: 5px 10px;
    border-radius: 15px;
    font-size: 0.9em;
    display: inline-block;
    margin: 2px;
}

.close-summary {
    display: block;
    width: 100%;
    padding: 10px;
    background-color: #3498db;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    margin-top: 20px;
    transition: background-color 0.3s;
}

.close-summary:hover {
    background-color: #2980b9;
}

.summary {
    background-color: #f0f8ff;
    padding: 15px;
    border-radius: 10px;
    margin-top: 20px;
    text-align: center;
    display: none;
}

.summary h3 {
    color: #3498db;
    margin-bottom: 10px;
}

.team-summary {
    display: flex;
    justify-content: space-around;
    margin-top: 10px;
}

.team-summary div {
    background-color: #ecf0f1;
    padding: 10px;
    border-radius: 5px;
    width: 45%;
}

.summary-btn {
    display: inline-block;
    padding: 12px 20px;
    background-color: #3498db;
    color: white;
    border: none;
    border-radius: 25px;
    cursor: pointer;
    font-size: 16px;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 1px;
    transition: all 0.3s ease;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    width: 100%;
    margin-bottom: 10px;
}

.summary-btn:hover {
    background-color: #2980b9;
    transform: translateY(-2px);
    box-shadow: 0 4px 8px rgba(0,0,0,0.2);
}

.button-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 20px;
}

.footer-settings-btn {
    padding: 12px 20px;
    background-color: #3498db;
    color: white;
    border: none;
    border-radius: 25px;
    cursor: pointer;
    font-size: 16px;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 1px;
    transition: all 0.3s ease;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    width: 100%;
    margin-bottom: 10px;
}

.footer-settings-btn:hover {
    background-color: #2980b9;
    transform: translateY(-2px);
    box-shadow: 0 4px 8px rgba(0,0,0,0.2);
}

.modal {
    display: none;
    position: fixed;
    z-index: 1000;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0,0,0,0.4);
}

.modal-content {
    background-color: #fefefe;
    margin: 15% auto;
    padding: 20px;
    border: 1px solid #888;
    width: 80%;
    max-width: 600px;
}

#footer-message-list {
    margin-bottom: 10px;
}

.footer-message-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 5px;
}

.footer-message-item button {
    margin-left: 5px;
}

.footer {
    background-color: rgba(44, 62, 80, 0.7);
}

.footer-content {
    animation: scroll-left 30s linear infinite;
}

@keyframes scroll-left {
    0% { transform: translateX(100%); }
    100% { transform: translateX(-100%); }
}

@media (max-width: 768px) {
    body {
        font-size: 14px;
    }

    h1 {
        font-size: 24px;
    }

    h2 {
        font-size: 20px;
    }

    .answer-btn, .next-btn, .summary-btn, .footer-settings-btn {
        font-size: 14px;
        padding: 10px;
    }

    .timer {
        font-size: 1.2em;
    }

    .team-info {
        flex-direction: column;
        align-items: center;
    }

    .current-team, .timer {
        margin-bottom: 10px;
    }

    .footer {
        font-size: 0.7em;
    }
}

@media (max-width: 480px) {
    body {
        font-size: 12px;
        padding: 5px;
    }

    h1 {
        font-size: 20px;
    }

    h2 {
        font-size: 18px;
    }

    .answer-btn, .next-btn, .summary-btn, .footer-settings-btn {
        font-size: 12px;
        padding: 8px;
    }

    .timer {
        font-size: 1em;
    }

    .category-selector, .question-container, .result, .score, .timer, .team-info {
        margin: 5px auto;
    }

    .fullscreen-btn {
        padding: 5px 10px;
        font-size: 12px;
    }
}

/* Adjustments for larger screens */
@media (min-width: 1200px) {
    body {
        font-size: 18px;
    }

    .game-container, .login-container {
        max-width: 1400px;
    }

    .category-selector, .question-container, .result, .score, .timer, .team-info {
        max-width: 800px;
    }
}
</style></head><body>
    <div id="login-page" class="login-container">
        <h2>Cadastro de Jogadores</h2>
        <input type="text" id="player-name" placeholder="Nome do jogador">
        <button onclick="addPlayer()">Adicionar Jogador</button>
        <div id="player-list"></div>
        <button onclick="createTeams()">Criar Equipes</button>
        <div id="team-display" class="team-display"></div>
    </div>

    <div id="footer-settings-modal" class="modal">
        <div class="modal-content">
            <h2>Ajustes de Mensagens do Rodapé</h2>
            <div>
                <label for="footer-speed">Velocidade:</label>
                <input type="range" id="footer-speed" min="5" max="50" value="30">
            </div>
            <div id="footer-message-list"></div>
            <input type="text" id="new-footer-message" placeholder="Nova mensagem">
            <button onclick="addFooterMessage()">Adicionar Mensagem</button>
            <button onclick="closeFooterSettings()">Fechar</button>
        </div>
    </div>

    <div id="game-container" class="game-container">
        <div class="watermark">@CWD2024</div>
        <h1>Desafio Bíblico: Fé e Sabedoria</h1>
        
        <button id="fullscreen-toggle" class="fullscreen-btn">Tela Cheia</button>

        <div class="team-info">
            <div id="current-team" class="current-team"></div>
            <div id="timer" class="timer">30</div>
            <button id="next-question" class="next-btn" style="display: none;">Próxima Pergunta</button>
        </div>
        
        <div class="category-selector fade-in">
            <select id="category-dropdown" onchange="selectCategory(this.value)">
                <option value="">Selecione uma categoria</option>
                <option value="historias">Histórias Bíblicas</option>
                <option value="versiculos">Versículos e Doutrina</option>
                <option value="parabolas">Parábolas de Jesus</option>
                <option value="personagens">Personagens Bíblicos</option>
                <option value="frutos">Frutos do Espírito</option>
            </select>
            <button id="show-summary" class="summary-btn" onclick="toggleSummary()">Mostrar Resumo</button>
            <button id="footer-settings-btn" class="footer-settings-btn">Ajustar Mensagens do Rodapé</button>
        </div>
        
        <div id="question-container" class="question-container fade-in">
            <h2 id="question">Selecione uma categoria para começar!</h2>
            <div id="answers"></div>
        </div>
        
        <div id="result" class="result fade-in"></div>
        <div id="score" class="score fade-in" style="display: none;">Pontuação: 0</div>
        <div id="daily-verse" class="daily-verse"></div>

        <div id="summary" class="summary"></div>

        <div id="final-results" class="final-results" style="display: none;">
            <h2>Resultado Final</h2>
            <div id="team-results"></div>
        </div>
    </div>

    <div id="summary-page">
        <h2>Resumo Atual</h2>
        <div class="summary-content">
            <div class="team-summary" id="team1-summary">
                <h3>Semeadores da Sabedoria: <span id="team1-score"></span> pontos</h3>
                <div class="player-list" id="team1-players"></div>
            </div>
            <div class="team-summary" id="team2-summary">
                <h3>Embaixadores do Conhecimento: <span id="team2-score"></span> pontos</h3>
                <div class="player-list" id="team2-players"></div>
            </div>
        </div>
        <button class="close-summary" onclick="closeSummary()">Fechar Resumo</button>
    </div>

    <footer class="footer">
        <div class="footer-content">
            <span id="footer-messages"></span>
        </div>
    </footer>

    <script>
const questions = {
    historias: [
        {
            question: "Quem construiu a arca?",
            answers: ["Noé", "Moisés", "Abraão", "Davi"],
            correct: 0
        },
        {
            question: "Quantos dias e noites choveu durante o dilúvio?",
            answers: ["30", "40", "50", "60"],
            correct: 1
        },
        {
            question: "Quem foi lançado na cova dos leões?",
            answers: ["Davi", "Daniel", "Jonas", "Elias"],
            correct: 1
        },
        {
            question: "Qual profeta foi engolido por um grande peixe?",
            answers: ["Jonas", "Jeremias", "Isaías", "Ezequiel"],
            correct: 0
        },
        {
            question: "Quem liderou os israelitas na saída do Egito?",
            answers: ["Josué", "Moisés", "Arão", "Abraão"],
            correct: 1
        },
        {
            question: "Quantas pragas Deus enviou sobre o Egito?",
            answers: ["7", "10", "12", "14"],
            correct: 1
        },
        {
            question: "Quem matou o gigante Golias?",
            answers: ["Saul", "Davi", "Salomão", "Samuel"],
            correct: 1
        },
        {
            question: "Qual era o nome do jardim onde Adão e Eva viviam?",
            answers: ["Éden", "Getsêmani", "Babilônia", "Jerusalém"],
            correct: 0
        },
        {
            question: "Quem recebeu as tábuas dos Dez Mandamentos?",
            answers: ["Abraão", "Josué", "Moisés", "Elias"],
            correct: 2
        },
        {
            question: "Qual foi o primeiro milagre de Jesus?",
            answers: ["Multiplicação dos pães", "Cura de um cego", "Transformar água em vinho", "Ressuscitar Lázaro"],
            correct: 2
        },
        {
            question: "Quem traiu Jesus por 30 moedas de prata?",
            answers: ["Pedro", "João", "Judas Iscariotes", "Tomé"],
            correct: 2
        },
        {
            question: "Quantos anos os israelitas vagaram no deserto?",
            answers: ["20", "30", "40", "50"],
            correct: 2
        },
        {
            question: "Quem foi o primeiro rei de Israel?",
            answers: ["Davi", "Saul", "Salomão", "Samuel"],
            correct: 1
        },
        {
            question: "Qual profeta foi arrebatado ao céu em um redemoinho?",
            answers: ["Elias", "Eliseu", "Ezequiel", "Enoque"],
            correct: 0
        },
        {
            question: "Quem construiu o Templo em Jerusalém?",
            answers: ["Davi", "Salomão", "Ezequias", "Josias"],
            correct: 1
        },
        {
            question: "Qual era o nome do irmão de Moisés?",
            answers: ["Josué", "Calebe", "Arão", "Jetro"],
            correct: 2
        },
        {
            question: "Quem foi vendido como escravo por seus irmãos?",
            answers: ["José", "Benjamim", "Judá", "Rúben"],
            correct: 0
        },
        {
            question: "Qual profeta desafiou os profetas de Baal no Monte Carmelo?",
            answers: ["Isaías", "Jeremias", "Elias", "Ezequiel"],
            correct: 2
        },
        {
            question: "Quem negou Jesus três vezes antes do galo cantar?",
            answers: ["João", "Tiago", "Pedro", "André"],
            correct: 2
        },
        {
            question: "Qual era o nome da esposa de Abraão?",
            answers: ["Rebeca", "Raquel", "Sara", "Lia"],
            correct: 2
        },
        {
            question: "Quem foi a mãe de Samuel?",
            answers: ["Ana", "Penina", "Raquel", "Lia"],
            correct: 0
        }
    ],
    versiculos: [
        {
            question: "Complete o versículo: 'Porque Deus amou o mundo de tal maneira que...'",
            answers: [
                "deu o seu Filho unigênito",
                "criou o homem e a mulher",
                "enviou os profetas",
                "estabeleceu os dez mandamentos"
            ],
            correct: 0
        },
        {
            question: "Qual é o 'fruto do Espírito' mencionado em Gálatas 5:22-23?",
            answers: [
                "Fé, esperança e caridade",
                "Amor, alegria, paz, paciência, bondade, fidelidade, mansidão e domínio próprio",
                "Sabedoria, entendimento e conhecimento",
                "Misericórdia, graça e perdão"
            ],
            correct: 1
        },
        { 
            question: "Complete: 'No princípio era o Verbo, e o Verbo estava com Deus, e o Verbo...'", 
            answers: ["era a luz", "era Deus", "se fez carne", "estava no mundo"], 
            correct: 1 
        },
        {
            question: "Qual versículo diz 'O Senhor é o meu pastor; nada me faltará'?",
            answers: ["Salmos 23:1", "Provérbios 3:5", "João 3:16", "Isaías 40:31"],
            correct: 0
        },
        {
            question: "Complete: 'Eu sou o caminho, a verdade e...'",
            answers: ["a vida", "a luz", "o amor", "a salvação"],
            correct: 0
        },
        {
            question: "Qual livro da Bíblia começa com 'No princípio, criou Deus os céus e a terra'?",
            answers: ["Êxodo", "Gênesis", "João", "Apocalipse"],
            correct: 1
        },
        {
            question: "Qual é o versículo que diz 'Ora, a fé é o firme fundamento das coisas que se esperam, e a prova das coisas que não se veem'?",
            answers: ["Romanos 10:17", "Hebreus 11:1", "Tiago 2:14", "1 Coríntios 13:13"],
            correct: 1
        },
        {
            question: "Complete: 'Porque o salário do pecado é a morte, mas o dom gratuito de Deus é...'",
            answers: ["a vida eterna", "a salvação", "o perdão", "a graça"],
            correct: 0
        },
        {
            question: "Qual é o menor versículo da Bíblia?",
            answers: ["Jesus chorou", "Alegrai-vos sempre", "Orai sem cessar", "Deus é amor"],
            correct: 0
        },
        {
            question: "Complete o versículo: 'Tudo posso naquela que...'",
            answers: ["me fortalece", "me guia", "me salva", "me ama"],
            correct: 0
        },
        {
            question: "Qual é o 'maior mandamento' segundo Jesus?",
            answers: ["Amar a Deus", "Amar ao próximo", "Não matar", "Honrar pai e mãe"],
            correct: 0
        },
        {
            question: "Complete: 'Bem-aventurados os pobres de espírito, porque...'",
            answers: ["deles é o reino dos céus", "serão consolados", "herdarão a terra", "verão a Deus"],
            correct: 0
        },
        {
            question: "Qual versículo diz 'Porque onde estiver o vosso tesouro, aí estará também o vosso coração'?",
            answers: ["Mateus 6:21", "Lucas 12:34", "Marcos 10:21", "João 14:6"],
            correct: 0
        },
        {
            question: "Complete: 'E conhecereis a verdade, e a verdade...'",
            answers: ["vos libertará", "vos guiará", "vos fortalecerá", "vos salvará"],
            correct: 0
        },
        {
            question: "Qual é o versículo que diz 'No mundo tereis aflições, mas tende bom ânimo; eu venci o mundo'?",
            answers: ["João 16:33", "Romanos 8:28", "Filipenses 4:13", "2 Coríntios 12:9"],
            correct: 0
        },
        {
            question: "Complete: 'Não to mandei eu? Sê forte e corajoso; não temas, nem te espantes, porque o Senhor, teu Deus, é...'",
            answers: ["contigo", "fiel", "poderoso", "misericordioso"],
            correct: 0
        },
        {
            question: "Qual versículo diz 'Entrega o teu caminho ao Senhor; confia nele, e ele tudo fará'?",
            answers: ["Salmos 37:5", "Provérbios 3:5-6", "Jeremias 29:11", "Isaías 41:10"],
            correct: 0
        },
        {
            question: "Complete: 'Porque eu bem sei os pensamentos que penso de vós, diz o Senhor; pensamentos de...'",
            answers: ["paz, e não de mal", "amor e misericórdia", "graça e verdade", "justiça e retidão"],
            correct: 0
        },
        {
            question: "Qual é o versículo que diz 'Mas buscai primeiro o reino de Deus, e a sua justiça, e todas estas coisas vos serão acrescentadas'?",
            answers: ["Mateus 6:33", "Lucas 12:31", "Marcos 10:29-30", "João 3:3"],
            correct: 0
        },
        {
            question: "Complete: 'Porque Deus não nos deu o espírito de temor, mas de...'",
            answers: ["fortaleza, e de amor, e de moderação", "paz e de alegria", "fé e de esperança", "sabedoria e de entendimento"],
            correct: 0
        }
    ],
    parabolas: [
        {
            question: "Na parábola do Bom Samaritano, quem ajudou o homem ferido?",
            answers: ["Um sacerdote", "Um levita", "Um samaritano", "Um fariseu"],
            correct: 2
        },
        {
            question: "O que representa o 'fermento' na parábola do fermento?",
            answers: ["O pecado", "O Reino de Deus", "A igreja", "A fé"],
            correct: 1
        },
        {
            question: "Na parábola do Filho Pródigo, o que o pai fez quando o filho retornou?",
            answers: ["O repreendeu", "O ignorou", "O recebeu com festa", "O expulsou"],
            correct: 2
        },
        {
            question: "Qual é a moral da parábola dos Talentos?",
            answers: ["Acumular riquezas", "Usar bem os dons dados por Deus", "Enterrar tesouros", "Não confiar em ninguém"],
            correct: 1
        },
        {
            question: "Na parábola do Semeador, o que representa a semente?",
            answers: ["Dinheiro", "Palavra de Deus", "Boas obras", "Fé"],
            correct: 1
        },
        {
            question: "O que Jesus compara ao Reino dos Céus na parábola da Pérola de Grande Valor?",
            answers: ["Um tesouro escondido", "Uma rede lançada ao mar", "Uma pérola valiosa", "Um grão de mostarda"],
            correct: 2
        },
        {
            question: "Na parábola das Dez Virgens, o que as virgens prudentes tinham que as insensatas não tinham?",
            answers: ["Vestidos bonitos", "Azeite extra", "Convites para a festa", "Lamparinas maiores"],
            correct: 1
        },
        {
            question: "Qual é a lição principal da parábola do Fariseu e do Publicano?",
            answers: ["A importância da oração", "A humildade", "O perdão dos pecados", "A obediência à lei"],
            correct: 1
        },
        {
            question: "Na parábola da Ovelha Perdida, quantas ovelhas o pastor deixa para buscar a perdida?",
            answers: ["50", "99", "100", "1000"],
            correct: 1
        },
        {
            question: "O que representa a 'casa construída sobre a rocha' na parábola dos Dois Alicerces?",
            answers: ["Riqueza material", "Fé em Jesus", "Conhecimento bíblico", "Tradições religiosas"],
            correct: 1
        },
        {
            question: "Na parábola do Rico e Lázaro, o que separa o rico de Lázaro no além?",
            answers: ["Um muro", "Um abismo", "Um rio", "Uma porta"],
            correct: 1
        },
        {
            question: "Qual é a moral da parábola dos Trabalhadores da Vinha?",
            answers: ["Trabalhar duro", "A generosidade de Deus", "Chegar cedo ao trabalho", "Negociar salários"],
            correct: 1
        },
        {
            question: "Na parábola do Banquete de Casamento, por que os convidados originais não compareceram?",
            answers: ["Estavam doentes", "Tinham outros compromissos", "Não gostavam do noivo", "Não foram avisados"],
            correct: 1
        },
        {
            question: "O que Jesus compara ao Reino dos Céus na parábola do Grão de Mostarda?",
            answers: ["Uma semente pequena que cresce", "Um tesouro escondido", "Uma rede de pesca", "Um banquete"],
            correct: 0
        },
        {
            question: "Na parábola do Credor Incompassivo, o que o rei fez quando o servo não pôde pagar sua dívida?",
            answers: ["O prendeu", "Perdoou a dívida", "Vendeu-o como escravo", "Exigiu trabalho forçado"],
            correct: 1
        },
        {
            question: "Qual é a lição principal da parábola do Rico Insensato?",
            answers: ["Acumular riquezas", "Planejar o futuro", "A vida não consiste na abundância dos bens", "Construir celeiros maiores"],
            correct: 2
        },
        {
            question: "Na parábola da Figueira Estéril, quanto tempo o dono esperou por frutos?",
            answers: ["1 ano", "2 anos", "3 anos", "5 anos"],
            correct: 2
        },
        {
            question: "O que representa o 'joio' na parábola do Joio e do Trigo?",
            answers: ["Pessoas boas", "Os filhos do maligno", "Anjos", "Apóstolos"],
            correct: 1
        },
        {
            question: "Na parábola do Bom Pastor, como o pastor protege suas ovelhas?",
            answers: ["Com uma cerca", "Com cães de guarda", "Dando sua vida por elas", "Contratando ajudantes"],
            correct: 2
        },
        {
            question: "Qual é a moral da parábola dos Dois Devedores?",
            answers: ["Pagar dívidas rapidamente", "Quem é mais perdoado, ama mais", "Não emprestar dinheiro", "A importância de manter registros"],
            correct: 1
        }
    ],
    personagens: [
        {
            question: "Quem foi o primeiro rei de Israel?",
            answers: ["Davi", "Saul", "Salomão", "Samuel"],
            correct: 1
        },
        {
            question: "Quem escreveu a maior parte das cartas do Novo Testamento?",
            answers: ["Pedro", "João", "Tiago", "Paulo"],
            correct: 3
        },
        {
            question: "Quem foi chamado de 'amigo de Deus'?",
            answers: ["Moisés", "Davi", "Abraão", "José"],
            correct: 2
        },
        {
            question: "Qual profeta foi alimentado por corvos?",
            answers: ["Isaías", "Jeremias", "Elias", "Eliseu"],
            correct: 2
        },
        {
            question: "Quem era a esposa de Isaque?",
            answers: ["Sara", "Rebeca", "Raquel", "Lia"],
            correct: 1
        },
        {
            question: "Qual discípulo de Jesus era cobrador de impostos?",
            answers: ["Pedro", "Mateus", "João", "Tiago"],
            correct: 1
        },
        {
            question: "Quem foi o sucessor de Moisés na liderança de Israel?",
            answers: ["Josué", "Calebe", "Arão", "Samuel"],
            correct: 0
        },
        {
            question: "Qual rei construiu o primeiro templo em Jerusalém?",
            answers: ["Davi", "Salomão", "Roboão", "Ezequias"],
            correct: 1
        },
        {
            question: "Quem era o pai de João Batista?",
            answers: ["José", "Zacarias", "Joaquim", "Zebedeu"],
            correct: 1
        },
        {
            question: "Qual profeta foi engolido por um grande peixe?",
            answers: ["Jonas", "Oséias", "Amós", "Miquéias"],
            correct: 0
        },
        {
            question: "Quem era a sogra de Rute?",
            answers: ["Noemi", "Orfa", "Raabe", "Débora"],
            correct: 0
        },
        {
            question: "Qual apóstolo é conhecido como 'o discípulo amado'?",
            answers: ["Pedro", "Tiago", "João", "André"],
            correct: 2
        },
        {
            question: "Quem foi o primeiro mártir cristão?",
            answers: ["Pedro", "Paulo", "Estêvão", "Tiago"],
            correct: 2
        },
        {
            question: "Qual mulher escondeu os espias israelitas em Jericó?",
            answers: ["Raabe", "Débora", "Rute", "Ester"],
            correct: 0
        },
        {
            question: "Quem era o pai de Salomão?",
            answers: ["Saul", "Davi", "Josias", "Ezequias"],
            correct: 1
        },
        {
            question: "Qual profeta viu uma visão de ossos secos?",
            answers: ["Isaías", "Jeremias", "Ezequiel", "Daniel"],
            correct: 2
        },
        {
            question: "Quem era a mãe de Samuel?",
            answers: ["Ana", "Penina", "Raquel", "Lia"],
            correct: 0
        },
        {
            question: "Qual rei babilônico teve um sonho interpretado por Daniel?",
            answers: ["Ciro", "Dario", "Nabucodonosor", "Belsazar"],
            correct: 2
        },
        {
            question: "Quem era o irmão de Moisés?",
            answers: ["Josué", "Calebe", "Arão", "Jetro"],
            correct: 2
        },
        {
            question: "Qual juíza liderou Israel contra Sísera?",
            answers: ["Débora", "Jael", "Rute", "Ester"],
            correct: 0
        }
    ],
    frutos: [
        {
            question: "Qual destes NÃO é um fruto do Espírito mencionado em Gálatas 5?",
            answers: ["Amor", "Paciência", "Bondade", "Coragem"],
            correct: 3
        },
        {
            question: "Como podemos cultivar os frutos do Espírito em nossas vidas?",
            answers: [
                "Através de esforço próprio",
                "Pedindo a Deus em oração",
                "Permitindo que o Espírito Santo trabalhe em nós",
                "Estudando a Bíblia diariamente"
            ],
            correct: 2
        },
        {
            question: "Qual é o primeiro fruto do Espírito mencionado em Gálatas 5:22?",
            answers: ["Alegria", "Paz", "Amor", "Paciência"],
            correct: 2
        },
        {
            question: "Qual fruto do Espírito está relacionado com a capacidade de esperar?",
            answers: ["Mansidão", "Longanimidade", "Domínio próprio", "Fidelidade"],
            correct: 1
        },
        {
            question: "Qual fruto do Espírito se opõe diretamente à ira?",
            answers: ["Paz", "Mansidão", "Paciência", "Bondade"],
            correct: 1
        },
        {
            question: "Qual fruto do Espírito está associado à lealdade e constância?",
            answers: ["Fidelidade", "Bondade", "Benignidade", "Temperança"],
            correct: 0
        },
        {
            question: "Qual fruto do Espírito se relaciona com a habilidade de controlar impulsos?",
            answers: ["Mansidão", "Temperança", "Paciência", "Bondade"],
            correct: 1
        },
        {
            question: "Qual fruto do Espírito é frequentemente associado com felicidade?",
            answers: ["Paz", "Alegria", "Bondade", "Amor"],
            correct: 1
        },
        {
            question: "Qual fruto do Espírito está ligado à gentileza e compaixão?",
            answers: ["Bondade", "Benignidade", "Mansidão", "Amor"],
            correct: 1
        },
        {
            question: "Qual fruto do Espírito é considerado o oposto da ansiedade?",
            answers: ["Alegria", "Paz", "Paciência", "Fé"],
            correct: 1
        },
        {
            question: "Qual fruto do Espírito está relacionado com a humildade?",
            answers: ["Mansidão", "Bondade", "Fidelidade", "Temperança"],
            correct: 0
        },
        {
            question: "Qual é o último fruto do Espírito mencionado em Gálatas 5:23?",
            answers: ["Mansidão", "Fidelidade", "Domínio próprio", "Bondade"],
            correct: 2
        },
        {
            question: "Qual fruto do Espírito é frequentemente descrito como 'amor em ação'?",
            answers: ["Bondade", "Benignidade", "Fidelidade", "Mansidão"],
            correct: 1
        },
        {
            question: "Qual fruto do Espírito está associado à tranquilidade interior?",
            answers: ["Alegria", "Paz", "Paciência", "Mansidão"],
            correct: 1
        },
        {
            question: "Qual fruto do Espírito se opõe ao egoísmo?",
            answers: ["Amor", "Bondade", "Mansidão", "Fidelidade"],
            correct: 0
        },
        {
            question: "Qual fruto do Espírito está relacionado com a perseverança?",
            answers: ["Paciência", "Fidelidade", "Domínio próprio", "Longanimidade"],
            correct: 3
        },
        {
            question: "Qual fruto do Espírito é muitas vezes associado à integridade?",
            answers: ["Fidelidade", "Bondade", "Mansidão", "Temperança"],
            correct: 0
        },
        {
            question: "Qual fruto do Espírito se opõe à amargura?",
            answers: ["Alegria", "Paz", "Bondade", "Amor"],
            correct: 2
        },
        {
            question: "Qual fruto do Espírito está ligado à capacidade de perdoar?",
            answers: ["Mansidão", "Amor", "Paciência", "Bondade"],
            correct: 1
        },
        {
            question: "Qual fruto do Espírito é frequentemente descrito como 'a cola' que mantém os outros juntos?",
            answers: ["Paz", "Fidelidade", "Amor", "Bondade"],
            correct: 2
        }
    ]
};

const categoryVerses = {
    historias: [
        "No princípio, criou Deus os céus e a terra. - Gênesis 1:1",
        "Disse Deus: Haja luz; e houve luz. - Gênesis 1:3",
        "E viu Deus tudo quanto fizera, e eis que era muito bom. - Gênesis 1:31"
    ],
    versiculos: [
        "Porque Deus amou o mundo de tal maneira que deu o seu Filho unigênito... - João 3:16",
        "O Senhor é o meu pastor; nada me faltará. - Salmos 23:1",
        "Tudo posso naquele que me fortalece. - Filipenses 4:13"
    ],
    parabolas: [
        "O reino dos céus é semelhante a um grão de mostarda... - Mateus 13:31",
        "O reino dos céus é semelhante ao fermento... - Mateus 13:33",
        "O reino dos céus é semelhante a um tesouro escondido no campo... - Mateus 13:44"
    ],
    personagens: [
        "Disse Davi: O Senhor, que me livrou das garras do leão e das garras do urso... - 1 Samuel 17:37",
        "Respondeu-lhe Jesus: Eu sou o caminho, e a verdade, e a vida... - João 14:6",
        "E disse Moisés a Deus: Quem sou eu para ir a Faraó e tirar do Egito os filhos de Israel? - Êxodo 3:11"
    ],
    frutos: [
        "Mas o fruto do Espírito é: amor, alegria, paz, longanimidade... - Gálatas 5:22",
        "Toda árvore boa produz bons frutos... - Mateus 7:17",
        "Eu sou a videira, vós, os ramos. Quem permanece em mim, e eu, nele, esse dá muito fruto... - João 15:5"
    ]
};

let currentCategory = '';
let currentQuestionIndex = 0;
let usedQuestions = [];
let score = 0;
let timeLeft = 30; // 30 segundos
let timerInterval;
let currentTeam = 0; // 0 para Semeadores da Sabedoria, 1 para Embaixadores do Conhecimento
let teamNames = ["Semeadores da Sabedoria", "Embaixadores do Conhecimento"];
let teamScores = [0, 0];
let team1Players = [];
let team2Players = [];
let players = [];
let footerMessages = [];
let footerSpeed = 30;

function requestFullscreen() {
    const elem = document.documentElement;
    if (elem.requestFullscreen) {
        elem.requestFullscreen();
    } else if (elem.webkitRequestFullscreen) { /* Safari */
        elem.webkitRequestFullscreen();
    } else if (elem.msRequestFullscreen) { /* IE11 */
        elem.msRequestFullscreen();
    }
}

function addPlayer() {
    const playerName = document.getElementById('player-name').value.trim();
    if (playerName) {
        players.push(playerName);
        document.getElementById('player-name').value = '';
        updatePlayerList();
    }
}

function updatePlayerList() {
    const playerList = document.getElementById('player-list');
    playerList.innerHTML = players.map(player => `<div>${player}</div>`).join('');
}

function startTimer() {
    clearInterval(timerInterval);
    timeLeft = 30;
    document.getElementById('timer').textContent = timeLeft;
    timerInterval = setInterval(updateTimer, 1000);
}

function updateTimer() {
    document.getElementById('timer').textContent = timeLeft;
    if (timeLeft === 0) {
        clearInterval(timerInterval);
        document.getElementById('result').textContent = "Tempo esgotado!";
        disableAnswerButtons();
        document.getElementById('next-question').style.display = 'inline-block';
    } else {
        timeLeft--;
    }
}

function endGame() {
    document.getElementById('question-container').innerHTML = '<h2>Tempo esgotado!</h2>';
    document.getElementById('result').textContent = `Pontuação final: ${score}`;
}

function updateDailyVerse(category) {
    const verseContainer = document.getElementById('daily-verse');
    if (categoryVerses[category] && categoryVerses[category].length > 0) {
        const randomIndex = Math.floor(Math.random() * categoryVerses[category].length);
        verseContainer.textContent = categoryVerses[category][randomIndex];
    } else {
        verseContainer.textContent = "Versículo não disponível para esta categoria.";
    }
}

function selectCategory(category) {
    if (!category) return; // Não faz nada se nenhuma categoria for selecionada
    currentCategory = category;
    currentQuestionIndex = 0;
    usedQuestions = [];
    score = 0;
    updateScore();
    showQuestion();
    startTimer();
    updateDailyVerse(category);
}

function resetCategoryDropdown() {
    document.getElementById('category-dropdown').value = "";
}

function showQuestion() {
    if (usedQuestions.length === questions[currentCategory].length) {
        document.getElementById('question').textContent = "Parabéns! Você completou todas as perguntas desta categoria.";
        document.getElementById('answers').innerHTML = '';
        document.getElementById('timer').textContent = '';
        document.getElementById('next-question').style.display = 'none';
        showFinalResults(); 
        usedQuestions = [];
        resetCategoryDropdown();
        return;
    }

    let questionIndex;
    do {
        questionIndex = Math.floor(Math.random() * questions[currentCategory].length);
    } while (usedQuestions.includes(questionIndex));

    usedQuestions.push(questionIndex);
    currentQuestionIndex = questionIndex;

    const questionData = questions[currentCategory][questionIndex];
    document.getElementById('question').textContent = questionData.question;
    
    const answersHtml = questionData.answers.map((answer, index) => 
        `<button class="answer-btn" onclick="checkAnswer(${index}, ${questionIndex})">${answer}</button>`
    ).join('');
    
    document.getElementById('answers').innerHTML = answersHtml;
    document.getElementById('result').textContent = '';
    document.getElementById('next-question').style.display = 'none';
    
    updateTeamDisplay();
    startTimer();
}

function checkAnswer(answerIndex, questionIndex) {
    clearInterval(timerInterval);
    const questionData = questions[currentCategory][questionIndex];
    const buttons = document.querySelectorAll('.answer-btn');
    
    buttons.forEach((button, index) => {
        if (index === answerIndex) {
            button.classList.add('selected');
        }
        if (index === questionData.correct) {
            button.classList.add('correct-answer');
        }
        button.disabled = true; // Desabilita todos os botões após responder
    });

    if (answerIndex === questionData.correct) {
        teamScores[currentTeam]++;
        document.getElementById('result').textContent = "Correto!";
    } else if (answerIndex !== -1) {
        document.getElementById('result').textContent = "Incorreto!";
    }
    
    updateScore();
    document.getElementById('next-question').style.display = 'inline-block';
}

function disableAnswerButtons() {
    const buttons = document.querySelectorAll('.answer-btn');
    buttons.forEach(button => {
        button.disabled = true;
    });
}

function nextQuestion() {
    currentTeam = 1 - currentTeam; // Alterna para a outra equipe
    showQuestion();
    document.getElementById('next-question').style.display = 'none';
}

document.getElementById('next-question').addEventListener('click', nextQuestion);

function updateScore() {
    document.getElementById('score').textContent = `Pontuação: Semeadores da Sabedoria ${teamScores[0]} - Embaixadores do Conhecimento ${teamScores[1]}`;
}

function updateTeamDisplay() {
    document.getElementById('current-team').textContent = `Equipe Atual: ${teamNames[currentTeam]}`;
}

function openFooterSettings() {
    document.getElementById('footer-settings-modal').style.display = 'block';
    updateFooterMessageList();
}

function closeFooterSettings() {
    document.getElementById('footer-settings-modal').style.display = 'none';
}

function updateFooterMessageList() {
    const messageList = document.getElementById('footer-message-list');
    messageList.innerHTML = footerMessages.map((message, index) => `
        <div class="footer-message-item">
            <span>${message}</span>
            <div>
                <button onclick="editFooterMessage(${index})">Editar</button>
                <button onclick="deleteFooterMessage(${index})">Apagar</button>
            </div>
        </div>
    `).join('');
}

function addFooterMessage() {
    const message = document.getElementById('new-footer-message').value.trim();
    if (message) {
        footerMessages.push(message);
        document.getElementById('new-footer-message').value = '';
        updateFooterMessageList();
        updateFooterMessages();
    }
}

function editFooterMessage(index) {
    const newMessage = prompt("Editar mensagem:", footerMessages[index]);
    if (newMessage !== null) {
        footerMessages[index] = newMessage.trim();
        updateFooterMessageList();
        updateFooterMessages();
    }
}

function deleteFooterMessage(index) {
    if (confirm("Tem certeza que deseja apagar esta mensagem?")) {
        footerMessages.splice(index, 1);
        updateFooterMessageList();
        updateFooterMessages();
    }
}

function updateFooterMessages() {
    const footerContent = document.getElementById('footer-messages');
    const allMessages = footerMessages.join(' @CWD2024   ');
    footerContent.textContent = allMessages + ' @CWD2024   ';
    
    // Update animation duration based on content length and speed
    const contentWidth = footerContent.offsetWidth;
    const duration = (contentWidth / footerSpeed) * 0.5;
    document.querySelector('.footer-content').style.animationDuration = `${duration}s`;
}

document.getElementById('footer-speed').addEventListener('input', function() {
    footerSpeed = 55 - this.value; // Invert the scale so lower values mean slower speed
    updateFooterMessages();
});

document.getElementById('footer-settings-btn').addEventListener('click', openFooterSettings);

function createTeams() {
    if (players.length < 2) {
        alert('Adicione pelo menos 2 jogadores para criar equipes.');
        return;
    }

    // Shuffle the players array
    for (let i = players.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [players[i], players[j]] = [players[j], players[i]];
    }

    const midPoint = Math.ceil(players.length / 2);
    team1Players = players.slice(0, midPoint);
    team2Players = players.slice(midPoint);

    const teamDisplay = document.getElementById('team-display');
    teamDisplay.innerHTML = `
        <div class="team">
            <h3>Semeadores da Sabedoria</h3>
            ${team1Players.map(name => `<div>${name}</div>`).join('')}
        </div>
        <div class="team">
            <h3>Embaixadores do Conhecimento</h3>
            ${team2Players.map(name => `<div>${name}</div>`).join('')}
        </div>
        <button onclick="startGame()">Iniciar Jogo</button>
    `;
}

function startGame() {
    requestFullscreen(); // Add this line at the beginning of the function
    document.getElementById('login-page').style.display = 'none';
    document.getElementById('game-container').style.display = 'block';
    document.getElementById('summary-page').style.display = 'none';
    currentTeam = 0; // Começa com a primeira equipe
    teamScores = [0, 0]; // Redefine os pontos das equipes
    updateTeamDisplay();
    window.scrollTo(0, 0);
}

function showFinalResults() {
    const finalResults = document.getElementById('final-results');
    const teamResults = document.getElementById('team-results');
    
    teamResults.innerHTML = `
        <div class="team-result">
            <h3>Semeadores da Sabedoria: ${teamScores[0]} pontos</h3>
            <div class="player-list">
                ${team1Players.map(player => `<span class="player">${player}</span>`).join('')}
            </div>
        </div>
        <div class="team-result">
            <h3>Embaixadores do Conhecimento: ${teamScores[1]} pontos</h3>
            <div class="player-list">
                ${team2Players.map(player => `<span class="player">${player}</span>`).join('')}
            </div>
        </div>
    `;
    
    document.getElementById('score').style.display = 'block';
    document.getElementById('score').textContent = `Pontuação Final: Semeadores da Sabedoria ${teamScores[0]} - Embaixadores do Conhecimento ${teamScores[1]}`;
    finalResults.style.display = 'block';
}

function showSummary() {
    document.getElementById('game-container').style.display = 'none';
    document.getElementById('summary-page').style.display = 'block';
    
    document.getElementById('team1-score').textContent = teamScores[0];
    document.getElementById('team2-score').textContent = teamScores[1];
    
    document.getElementById('team1-players').innerHTML = team1Players.map(player => `<span class="player">${player}</span>`).join('');
    document.getElementById('team2-players').innerHTML = team2Players.map(player => `<span class="player">${player}</span>`).join('');
    
    window.scrollTo(0, 0);
}

function closeSummary() {
    document.getElementById('summary-page').style.display = 'none';
    document.getElementById('game-container').style.display = 'block';
    window.scrollTo(0, 0);
}

function toggleSummary() {
    const summaryPage = document.getElementById('summary-page');
    if (summaryPage.style.display === 'none') {
        showSummary();
    } else {
        closeSummary();
    }
}

document.getElementById('show-summary').addEventListener('click', toggleSummary);

document.getElementById('game-container').style.display = 'none';

function toggleFullscreen() {
    if (!document.fullscreenElement) {
        if (document.documentElement.requestFullscreen) {
            document.documentElement.requestFullscreen();
        } else if (document.documentElement.mozRequestFullScreen) { // Firefox
            document.documentElement.mozRequestFullScreen();
        } else if (document.documentElement.webkitRequestFullscreen) { // Chrome, Safari and Opera
            document.documentElement.webkitRequestFullscreen();
        } else if (document.documentElement.msRequestFullscreen) { // IE/Edge
            document.documentElement.msRequestFullscreen();
        }
    } else {
        if (document.exitFullscreen) {
            document.exitFullscreen();
        } else if (document.mozCancelFullScreen) { // Firefox
            document.mozCancelFullScreen();
        } else if (document.webkitExitFullscreen) { // Chrome, Safari and Opera
            document.webkitExitFullscreen();
        } else if (document.msExitFullscreen) { // IE/Edge
            document.msExitFullscreen();
        }
    }
}

function updateFullscreenButtonText() {
    const fullscreenButton = document.getElementById('fullscreen-toggle');
    if (document.fullscreenElement) {
        fullscreenButton.textContent = 'Sair da Tela Cheia';
    } else {
        fullscreenButton.textContent = 'Tela Cheia';
    }
}

// Add these event listeners at the end of your JavaScript code
document.getElementById('fullscreen-toggle').addEventListener('click', toggleFullscreen);
document.addEventListener('fullscreenchange', updateFullscreenButtonText);
document.addEventListener('webkitfullscreenchange', updateFullscreenButtonText);
document.addEventListener('mozfullscreenchange', updateFullscreenButtonText);
document.addEventListener('MSFullscreenChange', updateFullscreenButtonText);
</script>
</body></html>
