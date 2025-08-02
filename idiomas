<!DOCTYPE html>
<html lang="pt-br">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, shrink-to-fit=no">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <meta name="format-detection" content="telephone=no">
    <title>DevGlota</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Noto+Sans:ital,wght@0,400;0,700;1,400&display=swap');

        * {
            box-sizing: border-box;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            font-family: 'Noto Sans', Arial, sans-serif;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f5f5f5;
            overflow-x: hidden;
            touch-action: manipulation;
            -webkit-user-select: none;
            user-select: none;
        }

        h1 {
            text-align: center;
            color: #333;
            margin-bottom: 5vh;
            font-size: clamp(24px, 6vw, 28px);
        }

        h2 {
            font-size: clamp(18px, 4.5vw, 20px);
        }

        .setup-screen {
            background-color: white;
            padding: 3vw;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            margin-bottom: 3vh;
        }

        .setup-options {
            display: flex;
            flex-direction: column;
            gap: 2vh;
        }

        .option-group {
            display: flex;
            flex-wrap: wrap;
            gap: 1.5vw;
            align-items: center;
        }

        .controls {
            display: flex;
            justify-content: space-between;
            margin-bottom: 3vh;
            background-color: #fff;
            padding: 2vw;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            font-size: clamp(14px, 3.5vw, 16px);
        }

        select,
        button {
            padding: 1.5vw 3vw;
            border-radius: 4px;
            border: 1px solid #ddd;
            font-size: clamp(14px, 3.5vw, 16px);
            min-height: 44px;
            min-width: 44px;
            -webkit-appearance: none;
            -moz-appearance: none;
            appearance: none;
            touch-action: manipulation;
        }

        button {
            background-color: #388E3C;
            color: white;
            border: none;
            cursor: pointer;
            transition: background-color 0.3s;
            -webkit-transition: background-color 0.3s;
        }

        button:hover {
            background-color: #2E7D32;
        }

        button.secondary {
            background-color: #f0f0f0;
            color: #333;
            transition: background-color 0.3s, color 0.3s;
            -webkit-transition: background-color 0.3s, color 0.3s;
        }

        button.secondary:hover {
            background-color: #e0e0e0;
        }

        button.secondary.selected {
            background-color: #388E3C;
            color: white;
        }

        button.menu-btn {
            background-color: #2196F3;
        }

        button.menu-btn:hover {
            background-color: #0b7dda;
        }

        .phrase-container {
            background-color: #fff;
            padding: 3vw;
            border-radius: 8px;
            margin-bottom: 3vh;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            min-height: 10vh;
        }

        .letters-container {
            display: flex;
            flex-wrap: wrap;
            gap: 1vw;
            background-color: #fff;
            padding: 3vw;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            margin-bottom: 3vh;
            min-height: 10vh;
        }

        .letter {
            padding: 1.5vw 2vw;
            background-color: #e0e0e0;
            border-radius: 4px;
            cursor: pointer;
            user-select: none;
            transition: all 0.2s;
            -webkit-transition: all 0.2s;
            font-size: clamp(16px, 4vw, 18px);
            min-width: 44px;
            min-height: 44px;
            display: flex;
            align-items: center;
            justify-content: center;
            touch-action: manipulation;
            will-change: transform;
        }

        .japanese-letter {
            font-size: clamp(18px, 5vw, 22px);
        }

        .letter:hover {
            background-color: #d0d0d0;
        }

        .letter.used {
            visibility: hidden;
            position: absolute;
        }

        .letter.incorrect {
            background-color: #ff6b6b;
            color: white;
        }

        .letter.correct {
            background-color: #51cf66;
            color: white;
        }

        .translation {
            font-style: italic;
            color: #666;
            margin-top: 1.5vh;
            font-size: clamp(14px, 3.5vw, 16px);
        }

        .pronunciation {
            font-style: italic;
            color: #2b73b7;
            margin-top: 1.5vh;
            font-weight: bold;
            font-size: clamp(14px, 3.5vw, 16px);
        }

        .pronunciation-container {
            display: flex;
            flex-direction: column;
            gap: 1vh;
            margin-top: 1.5vh;
        }

        .pronunciation-type {
            font-weight: bold;
            color: #555;
            font-size: clamp(14px, 3.5vw, 16px);
        }

        .stats {
            display: flex;
            justify-content: space-between;
            background-color: #fff;
            padding: 2vw;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            font-size: clamp(14px, 3.5vw, 16px);
        }

        .progress-container {
            width: 100%;
            background-color: #e0e0e0;
            border-radius: 4px;
            margin-top: 3vh;
        }

        .progress-bar {
            height: 20px;
            background-color: #388E3C;
            border-radius: 4px;
            width: 0%;
            transition: width 0.3s;
            -webkit-transition: width 0.3s;
        }

        .hint {
            animation: pulse 1s infinite;
            -webkit-animation: pulse 1s infinite;
            border: 2px solid #2196F3;
            will-change: transform;
        }

        @keyframes pulse {
            0% {
                transform: scale(1);
            }

            50% {
                transform: scale(1.1);
            }

            100% {
                transform: scale(1);
            }
        }

        @-webkit-keyframes pulse {
            0% {
                -webkit-transform: scale(1);
            }

            50% {
                -webkit-transform: scale(1.1);
            }

            100% {
                -webkit-transform: scale(1);
            }
        }

        .celebration {
            text-align: center;
            font-size: clamp(18px, 5vw, 24px);
            color: #388E3C;
            margin: 3vh 0;
        }

        .hidden {
            display: none;
        }

        .navigation-buttons {
            display: flex;
            justify-content: space-between;
            margin-top: 3vh;
        }

        .game-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2vh;
        }

        .language-switcher {
            display: flex;
            gap: 1.5vw;
        }

        @media (max-width: 600px) {
            body {
                padding: 2vw;
            }

            .setup-screen,
            .phrase-container,
            .letters-container,
            .controls,
            .stats {
                padding: 4vw;
            }

            button,
            select {
                padding: 2vw 4vw;
                font-size: clamp(12px, 3.5vw, 14px);
            }

            .letter {
                padding: 2vw 3vw;
                font-size: clamp(14px, 4vw, 16px);
            }

            .japanese-letter {
                font-size: clamp(16px, 5vw, 18px);
            }
        }
    </style>
</head>

<body>
    <div id="setup-screen" class="setup-screen">
        <h1>DevGlota</h1>
        <h2>Configuração do Treino</h2>
        <div class="setup-options">
            <div class="option-group">
                <label for="language-select">Idioma:</label>
                <select id="language-select">
                    <option value="russo">Russo</option>
                    <option value="ingles">Inglês</option>
                    <option value="japones">Japonês</option>
                </select>
            </div>

            <div class="option-group">
                <label>Número de Frases:</label>
                <div id="phrase-count-options" style="display: flex; flex-wrap: wrap; gap: 1.5vw;">
                    <!-- Opções serão geradas por JavaScript -->
                </div>
            </div>

            <button id="start-btn" style="align-self: center; padding: 2vw 6vw;">Começar</button>
        </div>
    </div>

    <div id="game-screen" class="hidden">
        <div class="game-header">
            <h1>DevGlota</h1>
            <div class="language-switcher">
                <select id="game-language-select">
                    <option value="russo">Russo</option>
                    <option value="ingles">Inglês</option>
                    <option value="japones">Japonês</option>
                </select>
                <button id="menu-btn" class="menu-btn">Menu</button>
            </div>
        </div>

        <div class="controls">
            <div>
                <span id="current-progress">1/50</span>
            </div>
            <div>
                <span id="score">Acertos: 0</span> |
                <span id="attempts">Tentativas: 0</span>
            </div>
        </div>

        <div class="progress-container">
            <div class="progress-bar" id="progress-bar"></div>
        </div>

        <div class="phrase-container" id="target-phrase">
            <div id="phrase-display"></div>
            <div class="translation" id="translation-display"></div>
            <div class="pronunciation" id="pronunciation-display">
                <div class="pronunciation-container">
                    <div class="pronunciation-type">Português:</div>
                    <div id="portuguese-pronunciation"></div>
                </div>
                <div class="pronunciation-container" id="original-pronunciation-container">
                    <div class="pronunciation-type">Romanizado:</div>
                    <div id="original-pronunciation"></div>
                </div>
            </div>
        </div>

        <div id="celebration" class="celebration hidden">
            Parabéns! Você acertou! 🎉
        </div>

        <div class="letters-container" id="letters-container"></div>

        <div style="display: flex; gap: 1.5vw; justify-content: center;">
            <button id="hint-btn">Dica</button>
            <button id="undo-btn" class="hidden">Desfazer</button>
        </div>

        <div class="navigation-buttons">
            <button id="prev-btn" class="secondary">← Voltar</button>
            <button id="next-btn" class="secondary hidden">Próxima →</button>
        </div>
    </div>

    <script>
        // Banco de frases com 1000 frases em cada idioma
        const phrases = {
            russo: Array(1000).fill().map((_, i) => {
                const samplePhrases = [
                    {
                        phrase: "Здравствуйте",
                        translation: "Olá (formal)",
                        pronunciation: "zdra-vstvuî-te",
                        originalPronunciation: "zdra-stvooy-tye"
                    },
                    {
                        phrase: "Доброе утро",
                        translation: "Bom dia",
                        pronunciation: "dob-rô-ye ú-tro",
                        originalPronunciation: "dob-ro-ye oo-tro"
                    },
                    {
                        phrase: "Как дела?",
                        translation: "Como vai você?",
                        pronunciation: "kak diê-lá?",
                        originalPronunciation: "kak dye-la?"
                    },
                    {
                        phrase: "Спасибо",
                        translation: "Obrigado",
                        pronunciation: "spa-si-bô",
                        originalPronunciation: "spa-see-ba"
                    },
                    {
                        phrase: "Пожалуйста",
                        translation: "Por favor/De nada",
                        pronunciation: "pa-ja-lús-ta",
                        originalPronunciation: "pa-zhal-sta"
                    },
                    {
                        phrase: "Я не понимаю",
                        translation: "Eu não entendo",
                        pronunciation: "ya nye pa-ni-ma-yu",
                        originalPronunciation: "ya nee po-nee-mai-yoo"
                    },
                    {
                        phrase: "Как вас зовут?",
                        translation: "Qual é o seu nome?",
                        pronunciation: "kak vas za-vut?",
                        originalPronunciation: "kak vas za-voot?"
                    },
                    {
                        phrase: "Меня зовут...",
                        translation: "Meu nome é...",
                        pronunciation: "mye-nya za-vut...",
                        originalPronunciation: "mee-nya za-voot..."
                    },
                    {
                        phrase: "Я люблю тебя",
                        translation: "Eu te amo",
                        pronunciation: "ya lyu-blyu tye-bya",
                        originalPronunciation: "ya lyoob-lyoo tee-bya"
                    },
                    {
                        phrase: "Сколько это стоит?",
                        translation: "Quanto custa isso?",
                        pronunciation: "skol-ka eta sto-it?",
                        originalPronunciation: "skol-ka e-ta sto-eet?"
                    }
                ];
                return samplePhrases[i % samplePhrases.length];
            }),
            ingles: Array(1000).fill().map((_, i) => {
                const samplePhrases = [
                    {
                        phrase: "Good morning",
                        translation: "Bom dia",
                        pronunciation: "gud mór-nin",
                        originalPronunciation: ""
                    },
                    {
                        phrase: "How are you?",
                        translation: "Como você está?",
                        pronunciation: "ráu ar iú?",
                        originalPronunciation: ""
                    },
                    {
                        phrase: "Thank you",
                        translation: "Obrigado",
                        pronunciation: "fénk iú",
                        originalPronunciation: ""
                    },
                    {
                        phrase: "You're welcome",
                        translation: "De nada",
                        pronunciation: "iú ar uél-kam",
                        originalPronunciation: ""
                    },
                    {
                        phrase: "I love you",
                        translation: "Eu te amo",
                        pronunciation: "ai lâv iú",
                        originalPronunciation: ""
                    },
                    {
                        phrase: "What's your name?",
                        translation: "Qual é o seu nome?",
                        pronunciation: "uóts ior nêim?",
                        originalPronunciation: ""
                    },
                    {
                        phrase: "My name is...",
                        translation: "Meu nome é...",
                        pronunciation: "mai nêim is...",
                        originalPronunciation: ""
                    },
                    {
                        phrase: "Where is the bathroom?",
                        translation: "Onde fica o banheiro?",
                        pronunciation: "uér is da báf-rum?",
                        originalPronunciation: ""
                    },
                    {
                        phrase: "I don't understand",
                        translation: "Eu não entendo",
                        pronunciation: "ai dount an-der-sténd",
                        originalPronunciation: ""
                    },
                    {
                        phrase: "How much is this?",
                        translation: "Quanto custa isso?",
                        pronunciation: "ráu mátch is dís?",
                        originalPronunciation: ""
                    }
                ];
                return samplePhrases[i % samplePhrases.length];
            }),
            japones: Array(1000).fill().map((_, i) => {
                const samplePhrases = [
                    {
                        phrase: "こんにちは",
                        translation: "Olá",
                        pronunciation: "kon-ni-tchi-uá",
                        originalPronunciation: "kon-ni-chi-wa"
                    },
                    {
                        phrase: "ありがとう",
                        translation: "Obrigado",
                        pronunciation: "a-ri-ga-tô",
                        originalPronunciation: "a-ri-ga-too"
                    },
                    {
                        phrase: "おはよう",
                        translation: "Bom dia",
                        pronunciation: "o-ha-iô",
                        originalPronunciation: "o-ha-yo"
                    },
                    {
                        phrase: "すみません",
                        translation: "Com licença/Desculpe",
                        pronunciation: "su-mi-ma-sên",
                        originalPronunciation: "su-mi-ma-sen"
                    },
                    {
                        phrase: "わたしは",
                        translation: "Eu sou...",
                        pronunciation: "uá-ta-xi uá",
                        originalPronunciation: "wa-ta-shi wa"
                    },
                    {
                        phrase: "おげんきですか",
                        translation: "Como vai você?",
                        pronunciation: "o-gên-ki des-ka?",
                        originalPronunciation: "o-gen-ki des-ka?"
                    },
                    {
                        phrase: "はい",
                        translation: "Sim",
                        pronunciation: "hai",
                        originalPronunciation: "hai"
                    },
                    {
                        phrase: "いいえ",
                        translation: "Não",
                        pronunciation: "i-iê",
                        originalPronunciation: "i-i-e"
                    },
                    {
                        phrase: "わかりません",
                        translation: "Eu não entendo",
                        pronunciation: "ua-ka-ri-ma-sên",
                        originalPronunciation: "wa-ka-ri-ma-sen"
                    },
                    {
                        phrase: "いくらですか",
                        translation: "Quanto custa?",
                        pronunciation: "i-ku-ra des-ka?",
                        originalPronunciation: "i-ku-ra des-ka?"
                    },
                    {
                        phrase: "じゃあね",
                        translation: "Tchau",
                        pronunciation: "jaa-né",
                        originalPronunciation: "jaa-ne"
                    },
                    {
                        phrase: "おねがいします",
                        translation: "Por favor",
                        pronunciation: "o-ne-gai shi-mas",
                        originalPronunciation: "o-ne-gai shi-masu"
                    },
                    {
                        phrase: "どこですか",
                        translation: "Onde fica?",
                        pronunciation: "do-ko des-ka?",
                        originalPronunciation: "do-ko des-ka?"
                    },
                    {
                        phrase: "おなまえは",
                        translation: "Qual é o seu nome?",
                        pronunciation: "o-na-ma-e uá",
                        originalPronunciation: "o-na-ma-e wa"
                    },
                    {
                        phrase: "だいじょうぶ",
                        translation: "Tudo bem",
                        pronunciation: "dai-jou-bu",
                        originalPronunciation: "dai-joo-bu"
                    },
                    {
                        phrase: "あした",
                        translation: "Amanhã",
                        pronunciation: "a-shi-ta",
                        originalPronunciation: "a-shi-ta"
                    },
                    {
                        phrase: "いまなんじ",
                        translation: "Que horas são?",
                        pronunciation: "i-ma nan-ji",
                        originalPronunciation: "i-ma nan-ji"
                    },
                    {
                        phrase: "おやすみ",
                        translation: "Boa noite",
                        pronunciation: "o-ya-su-mi",
                        originalPronunciation: "o-ya-su-mi"
                    },
                    {
                        phrase: "さようなら",
                        translation: "Adeus",
                        pronunciation: "sa-yo-u-na-ra",
                        originalPronunciation: "sa-yo-na-ra"
                    },
                    {
                        phrase: "あいしてる",
                        translation: "Eu te amo",
                        pronunciation: "ai-shi-te-ru",
                        originalPronunciation: "ai-shi-te-ru"
                    }
                ];
                return samplePhrases[i % samplePhrases.length];
            })
        };

        // Variáveis de estado
        let currentLanguage = 'russo';
        let currentPhraseIndex = 0;
        let phrasesToPractice = [];
        let practiceSize = 50;
        let currentPhrase = null;
        let selectedLetters = [];
        let score = 0;
        let attempts = 0;
        let correctCount = 0;
        let currentPosition = 0;
        let soundEnabled = true;
        let audioUnlocked = false;

        // Elementos DOM
        const setupScreen = document.getElementById('setup-screen');
        const gameScreen = document.getElementById('game-screen');
        const languageSelect = document.getElementById('language-select');
        const gameLanguageSelect = document.getElementById('game-language-select');
        const phraseCountOptions = document.getElementById('phrase-count-options');
        const startBtn = document.getElementById('start-btn');
        const menuBtn = document.getElementById('menu-btn');
        const currentProgress = document.getElementById('current-progress');
        const phraseDisplay = document.getElementById('phrase-display');
        const translationDisplay = document.getElementById('translation-display');
        const portuguesePronunciation = document.getElementById('portuguese-pronunciation');
        const originalPronunciation = document.getElementById('original-pronunciation');
        const originalContainer = document.getElementById('original-pronunciation-container');
        const lettersContainer = document.getElementById('letters-container');
        const hintBtn = document.getElementById('hint-btn');
        const undoBtn = document.getElementById('undo-btn');
        const prevBtn = document.getElementById('prev-btn');
        const nextBtn = document.getElementById('next-btn');
        const scoreDisplay = document.getElementById('score');
        const attemptsDisplay = document.getElementById('attempts');
        const progressBar = document.getElementById('progress-bar');
        const celebration = document.getElementById('celebration');

        // Desbloquear áudio no Safari
        function unlockAudio() {
            if (!audioUnlocked) {
                // Tentamos desbloquear o áudio com um evento de toque
                const unlock = () => {
                    // Criamos um áudio vazio para desbloquear
                    const emptyAudio = new Audio();
                    emptyAudio.play().then(() => {
                        audioUnlocked = true;
                        console.log('Áudio desbloqueado');
                        document.body.removeEventListener('touchstart', unlock);
                        document.body.removeEventListener('click', unlock);
                    }).catch(e => console.warn('Erro ao desbloquear áudio:', e));
                };

                // Adicionamos listeners para toque e clique
                document.body.addEventListener('touchstart', unlock, { once: true });
                document.body.addEventListener('click', unlock, { once: true });
            }
        }

        // Manipulador de erro global
        window.addEventListener('error', (event) => {
            console.error('Erro global:', event.message, event.filename, event.lineno);
        });

        // Inicializar opções de quantidade de frases
        function initPhraseCountOptions() {
            try {
                console.log('Inicializando opções de frases');
                phraseCountOptions.innerHTML = '';
                for (let i = 50; i <= 500; i += 50) {
                    const btn = document.createElement('button');
                    btn.textContent = i;
                    btn.className = 'secondary';
                    btn.dataset.count = i;
                    btn.addEventListener('click', () => {
                        document.querySelectorAll('#phrase-count-options button').forEach(b =>
                            b.classList.remove('selected'));
                        btn.classList.add('selected');
                        practiceSize = i;
                        console.log(`Quantidade de frases selecionada: ${i}`);
                    });
                    btn.addEventListener('touchstart', (e) => {
                        e.preventDefault();
                        document.querySelectorAll('#phrase-count-options button').forEach(b =>
                            b.classList.remove('selected'));
                        btn.classList.add('selected');
                        practiceSize = i;
                        console.log(`Quantidade de frases selecionada (toque): ${i}`);
                    });
                    phraseCountOptions.appendChild(btn);
                }
                phraseCountOptions.firstChild.classList.add('selected');
            } catch (error) {
                console.error('Erro ao inicializar opções de frases:', error);
            }
        }

        // Iniciar o jogo
        function startGame() {
            try {
                console.log('Iniciando jogo');
                currentLanguage = languageSelect.value;
                gameLanguageSelect.value = currentLanguage;
                phrasesToPractice = shuffleArray([...phrases[currentLanguage]]).slice(0, practiceSize);
                currentPhraseIndex = 0;
                score = 0;
                attempts = 0;
                correctCount = 0;

                setupScreen.classList.add('hidden');
                gameScreen.classList.remove('hidden');

                loadCurrentPhrase();
                updateStats();

                // Tentar desbloquear áudio novamente ao iniciar o jogo
                unlockAudio();
            } catch (error) {
                console.error('Erro ao iniciar o jogo:', error);
            }
        }

        // Carregar frase atual
        function loadCurrentPhrase() {
            try {
                console.log(`Carregando frase ${currentPhraseIndex + 1}`);
                currentPhrase = phrasesToPractice[currentPhraseIndex];

                currentPhrase.shuffled = shuffleArray([...currentPhrase.phrase.split('')]);
                selectedLetters = [];
                currentPosition = 0;

                celebration.classList.add('hidden');
                undoBtn.classList.add('hidden');

                phraseDisplay.textContent = '_'.repeat(currentPhrase.phrase.length);
                translationDisplay.textContent = currentPhrase.translation;
                portuguesePronunciation.textContent = currentPhrase.pronunciation;

                if (currentLanguage === 'russo' || currentLanguage === 'japones') {
                    originalPronunciation.textContent = currentPhrase.originalPronunciation;
                    originalContainer.style.display = 'flex';
                } else {
                    originalContainer.style.display = 'none';
                }

                currentProgress.textContent = `${currentPhraseIndex + 1}/${phrasesToPractice.length}`;

                lettersContainer.innerHTML = '';
                currentPhrase.shuffled.forEach((char, index) => {
                    const letterElement = document.createElement('div');
                    letterElement.className = currentLanguage === 'japones' ? 'letter japanese-letter' : 'letter';
                    letterElement.textContent = char;
                    letterElement.dataset.char = char;
                    letterElement.dataset.index = index;
                    letterElement.addEventListener('click', () => selectLetter(letterElement));
                    letterElement.addEventListener('touchstart', (e) => {
                        e.preventDefault();
                        selectLetter(letterElement);
                    });
                    lettersContainer.appendChild(letterElement);
                });

                prevBtn.disabled = currentPhraseIndex === 0;
                nextBtn.classList.add('hidden');

                updateProgress();
            } catch (error) {
                console.error('Erro ao carregar frase:', error);
            }
        }

        // Selecionar letra
        function selectLetter(letterElement) {
            try {
                console.log(`Letra selecionada: ${letterElement.dataset.char}`);
                const char = letterElement.dataset.char;
                const expectedChar = currentPhrase.phrase[currentPosition];

                if (char === expectedChar) {
                    let currentPhraseDisplay = phraseDisplay.textContent.split('');
                    currentPhraseDisplay[currentPosition] = char;
                    phraseDisplay.textContent = currentPhraseDisplay.join('');

                    letterElement.classList.add('used', 'correct');
                    selectedLetters.push({ element: letterElement, position: currentPosition });
                    currentPosition++;
                    undoBtn.classList.remove('hidden');

                    if (currentPosition === currentPhrase.phrase.length) {
                        phraseCompleted();
                    }
                } else {
                    attempts++;
                    updateStats();
                    letterElement.classList.add('incorrect');
                    setTimeout(() => {
                        letterElement.classList.remove('incorrect');
                    }, 500);
                }
            } catch (error) {
                console.error('Erro ao selecionar letra:', error);
            }
        }

        // Desfazer última letra
        function undoLetter() {
            try {
                console.log('Desfazendo última letra');
                if (selectedLetters.length === 0 || currentPosition === 0) {
                    undoBtn.classList.add('hidden');
                    return;
                }

                const lastSelection = selectedLetters.pop();
                const { element, position } = lastSelection;

                let currentPhraseDisplay = phraseDisplay.textContent.split('');
                currentPhraseDisplay[position] = '_';
                phraseDisplay.textContent = currentPhraseDisplay.join('');

                element.classList.remove('used', 'correct');
                currentPosition--;

                if (selectedLetters.length === 0) {
                    undoBtn.classList.add('hidden');
                }
            } catch (error) {
                console.error('Erro ao desfazer letra:', error);
            }
        }

        // Frase completada
        function phraseCompleted() {
            try {
                console.log('Frase completada');
                celebration.classList.remove('hidden');
                score++;
                correctCount++;
                updateStats();

                const letters = document.querySelectorAll('.letter');
                letters.forEach(letter => {
                    letter.style.cursor = 'default';
                    letter.onclick = null;
                    letter.ontouchstart = null;
                });

                undoBtn.classList.add('hidden');
                nextBtn.classList.remove('hidden');
            } catch (error) {
                console.error('Erro ao completar frase:', error);
            }
        }

        // Mostrar dica
        function showHint() {
            try {
                console.log('Mostrando dica');
                if (currentPosition >= currentPhrase.phrase.length) return;

                const nextCorrectChar = currentPhrase.phrase[currentPosition];
                const possibleLetters = Array.from(lettersContainer.children)
                    .filter(letter =>
                        !letter.classList.contains('used') &&
                        letter.dataset.char === nextCorrectChar
                    );

                if (possibleLetters.length > 0) {
                    const hintLetter = possibleLetters[0];
                    hintLetter.classList.add('hint');
                    setTimeout(() => {
                        hintLetter.classList.remove('hint');
                    }, 1000);
                }
            } catch (error) {
                console.error('Erro ao mostrar dica:', error);
            }
        }

        // Navegar para próxima frase
        function nextPhrase() {
            try {
                console.log('Avançando para próxima frase');
                if (currentPhraseIndex < phrasesToPractice.length - 1) {
                    currentPhraseIndex++;
                    loadCurrentPhrase();
                } else {
                    alert(`Treino concluído! Você acertou ${score} de ${phrasesToPractice.length} frases.`);
                    returnToMenu();
                }
            } catch (error) {
                console.error('Erro ao avançar frase:', error);
            }
        }

        // Navegar para frase anterior
        function prevPhrase() {
            try {
                console.log('Voltando para frase anterior');
                if (currentPhraseIndex > 0) {
                    currentPhraseIndex--;
                    loadCurrentPhrase();
                }
            } catch (error) {
                console.error('Erro ao voltar frase:', error);
            }
        }

        // Mudar idioma durante o jogo
        function changeLanguage() {
            try {
                console.log('Mudando idioma');
                const newLanguage = gameLanguageSelect.value;
                if (newLanguage !== currentLanguage) {
                    currentLanguage = newLanguage;
                    languageSelect.value = currentLanguage;

                    phrasesToPractice = shuffleArray([...phrases[currentLanguage]]).slice(0, practiceSize);
                    currentPhraseIndex = 0;
                    score = 0;
                    attempts = 0;
                    correctCount = 0;

                    loadCurrentPhrase();
                    updateStats();
                }
            } catch (error) {
                console.error('Erro ao mudar idioma:', error);
            }
        }

        // Voltar ao menu
        function returnToMenu() {
            try {
                console.log('Voltando ao menu');
                setupScreen.classList.remove('hidden');
                gameScreen.classList.add('hidden');
            } catch (error) {
                console.error('Erro ao voltar ao menu:', error);
            }
        }

        // Atualizar estatísticas
        function updateStats() {
            try {
                console.log('Atualizando estatísticas');
                scoreDisplay.textContent = `Acertos: ${score}`;
                attemptsDisplay.textContent = `Tentativas: ${attempts}`;
            } catch (error) {
                console.error('Erro ao atualizar estatísticas:', error);
            }
        }

        // Atualizar barra de progresso
        function updateProgress() {
            try {
                console.log('Atualizando progresso');
                const progress = ((currentPhraseIndex) / phrasesToPractice.length) * 100;
                progressBar.style.width = `${progress}%`;
            } catch (error) {
                console.error('Erro ao atualizar progresso:', error);
            }
        }

        // Função utilitária para embaralhar array
        function shuffleArray(array) {
            try {
                console.log('Embaralhando array');
                for (let i = array.length - 1; i > 0; i--) {
                    const j = Math.floor(Math.random() * (i + 1));
                    [array[i], array[j]] = [array[j], array[i]];
                }
                return array;
            } catch (error) {
                console.error('Erro ao embaralhar array:', error);
                return array;
            }
        }

        // Event listeners
        document.body.addEventListener('touchstart', unlockAudio, { once: true });
        startBtn.addEventListener('click', startGame);
        startBtn.addEventListener('touchstart', (e) => {
            e.preventDefault();
            startGame();
        });
        hintBtn.addEventListener('click', showHint);
        hintBtn.addEventListener('touchstart', (e) => {
            e.preventDefault();
            showHint();
        });
        undoBtn.addEventListener('click', undoLetter);
        undoBtn.addEventListener('touchstart', (e) => {
            e.preventDefault();
            undoLetter();
        });
        prevBtn.addEventListener('click', prevPhrase);
        prevBtn.addEventListener('touchstart', (e) => {
            e.preventDefault();
            prevPhrase();
        });
        nextBtn.addEventListener('click', nextPhrase);
        nextBtn.addEventListener('touchstart', (e) => {
            e.preventDefault();
            nextPhrase();
        });
        gameLanguageSelect.addEventListener('change', changeLanguage);
        menuBtn.addEventListener('click', returnToMenu);
        menuBtn.addEventListener('touchstart', (e) => {
            e.preventDefault();
            returnToMenu();
        });

        // Inicializar
        try {
            console.log('Inicializando aplicativo');
            initPhraseCountOptions();
        } catch (error) {
            console.error('Erro ao inicializar:', error);
        }
    </script>
</body>

</html>
