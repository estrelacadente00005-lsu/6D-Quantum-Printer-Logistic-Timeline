
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Impressora Quântica 6D - Cronograma Logístico da Transformação</title>
    <style>
        :root {
            --bg-dark: #030611;
            --panel-bg: rgba(7, 14, 31, 0.88);
            --border-cyan: rgba(0, 243, 255, 0.3);
            --neon-cyan: #00f3ff;
            --neon-purple: #b700ff;
            --neon-gold: #ffc400;
            --neon-green: #00ff73;
            --text-main: #d0f2ff;
            --font-code: 'Courier New', Courier, monospace;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: var(--font-code);
            user-select: none;
        }

        body {
            background-color: var(--bg-dark);
            color: var(--text-main);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 15px;
            overflow-x: hidden;
            background-image: 
                radial-gradient(circle at 15% 15%, rgba(183, 0, 255, 0.12) 0%, transparent 40%),
                radial-gradient(circle at 85% 85%, rgba(0, 243, 255, 0.1) 0%, transparent 45%);
        }

        header {
            text-align: center;
            width: 100%;
            max-width: 1400px;
            margin-bottom: 15px;
            border-bottom: 1px solid var(--border-cyan);
            padding-bottom: 12px;
        }

        header h1 {
            font-size: 1.5rem;
            color: var(--neon-cyan);
            text-shadow: 0 0 12px rgba(0, 243, 255, 0.6);
            letter-spacing: 2px;
        }

        header p {
            font-size: 0.82rem;
            color: #8da9cb;
            margin-top: 4px;
        }

        .logistic-tag {
            display: inline-block;
            background: linear-gradient(90deg, var(--neon-purple), var(--neon-cyan));
            color: #fff;
            padding: 3px 12px;
            font-size: 0.72rem;
            border-radius: 12px;
            font-weight: bold;
            margin-top: 6px;
            box-shadow: 0 0 10px rgba(183, 0, 255, 0.4);
        }

        .app-container {
            display: grid;
            grid-template-columns: 360px 1fr 340px;
            gap: 15px;
            width: 100%;
            max-width: 1400px;
            height: calc(100vh - 120px);
            min-height: 680px;
        }

        @media (max-width: 1100px) {
            .app-container {
                grid-template-columns: 1fr;
                height: auto;
            }
        }

        .panel {
            background: var(--panel-bg);
            border: 1px solid var(--border-cyan);
            border-radius: 8px;
            padding: 15px;
            display: flex;
            flex-direction: column;
            gap: 12px;
            backdrop-filter: blur(8px);
            box-shadow: 0 0 15px rgba(0, 243, 255, 0.05);
            overflow-y: auto;
        }

        .panel-title {
            font-size: 0.88rem;
            color: var(--neon-cyan);
            border-bottom: 1px solid var(--border-cyan);
            padding-bottom: 6px;
            text-transform: uppercase;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-weight: bold;
        }

        .mode-selector {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 8px;
        }

        .mode-btn {
            background: rgba(4, 12, 28, 0.8);
            border: 1px solid var(--border-cyan);
            color: #a0c2e6;
            padding: 10px;
            border-radius: 6px;
            cursor: pointer;
            font-size: 0.72rem;
            font-weight: bold;
            text-align: center;
            transition: all 0.3s;
        }

        .mode-btn:hover {
            border-color: var(--neon-cyan);
            color: var(--neon-cyan);
        }

        .mode-btn.active-bio {
            background: rgba(0, 243, 255, 0.15);
            border-color: var(--neon-cyan);
            color: #fff;
            box-shadow: 0 0 12px rgba(0, 243, 255, 0.3);
        }

        .mode-btn.active-cosmic {
            background: rgba(183, 0, 255, 0.18);
            border-color: var(--neon-purple);
            color: #fff;
            box-shadow: 0 0 12px rgba(183, 0, 255, 0.4);
        }

        .info-card {
            background: rgba(2, 6, 16, 0.85);
            border: 1px solid rgba(0, 243, 255, 0.15);
            border-radius: 6px;
            padding: 10px;
            display: flex;
            flex-direction: column;
            gap: 4px;
        }

        .info-card h4 {
            font-size: 0.76rem;
            color: var(--neon-gold);
            text-transform: uppercase;
        }

        .info-card p {
            font-size: 0.7rem;
            color: #8da9cb;
            line-height: 1.35;
        }

        .control-group {
            display: flex;
            flex-direction: column;
            gap: 3px;
        }

        .control-label {
            font-size: 0.7rem;
            color: #8da9cb;
            display: flex;
            justify-content: space-between;
        }

        .control-value {
            color: var(--neon-cyan);
            font-weight: bold;
        }

        input[type="range"] {
            appearance: none;
            -webkit-appearance: none;
            width: 100%;
            height: 5px;
            background: #0b1a30;
            border-radius: 3px;
            outline: none;
        }

        input[type="range"]::-webkit-slider-thumb {
            -webkit-appearance: none;
            width: 14px;
            height: 14px;
            border-radius: 50%;
            background: var(--neon-cyan);
            cursor: pointer;
            box-shadow: 0 0 8px var(--neon-cyan);
        }

        .canvas-container {
            display: flex;
            flex-direction: column;
            gap: 10px;
            position: relative;
        }

        .canvas-card {
            position: relative;
            background: #010309;
            border: 1px solid var(--border-cyan);
            border-radius: 8px;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        canvas {
            display: block;
            width: 100%;
            height: 100%;
        }

        .canvas-tag {
            position: absolute;
            top: 8px;
            left: 10px;
            background: rgba(0, 0, 0, 0.8);
            border: 1px solid var(--border-cyan);
            padding: 3px 8px;
            font-size: 0.65rem;
            color: var(--neon-cyan);
            border-radius: 4px;
            pointer-events: none;
            letter-spacing: 1px;
        }

        .canvas-hud {
            position: absolute;
            bottom: 8px;
            right: 10px;
            background: rgba(0, 0, 0, 0.85);
            border: 1px solid rgba(183, 0, 255, 0.4);
            padding: 5px 10px;
            font-size: 0.65rem;
            color: #aaccff;
            border-radius: 4px;
            pointer-events: none;
            text-align: right;
        }

        .btn-action {
            background: transparent;
            border: 1px solid var(--neon-cyan);
            color: var(--neon-cyan);
            padding: 10px;
            border-radius: 5px;
            font-weight: bold;
            font-size: 0.75rem;
            cursor: pointer;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: all 0.3s ease;
            box-shadow: 0 0 8px rgba(0, 243, 255, 0.15);
        }

        .btn-action:hover {
            background: var(--neon-cyan);
            color: #000;
            box-shadow: 0 0 15px var(--neon-cyan);
        }

        .btn-action.purple {
            border-color: var(--neon-purple);
            color: var(--neon-purple);
        }

        .btn-action.purple:hover {
            background: var(--neon-purple);
            color: #fff;
            box-shadow: 0 0 15px var(--neon-purple);
        }

        .dest-grid {
            display: flex;
            flex-direction: column;
            gap: 6px;
        }

        .dest-card {
            background: rgba(2, 6, 16, 0.8);
            border: 1px solid rgba(0, 243, 255, 0.15);
            border-radius: 5px;
            padding: 8px;
            cursor: pointer;
            transition: all 0.2s;
        }

        .dest-card:hover {
            border-color: var(--neon-cyan);
            background: rgba(0, 243, 255, 0.08);
        }

        .dest-card.selected {
            border-color: var(--neon-green);
            background: rgba(0, 255, 115, 0.1);
            box-shadow: 0 0 10px rgba(0, 255, 115, 0.2);
        }

        .dest-title {
            font-size: 0.73rem;
            font-weight: bold;
            color: var(--neon-green);
            display: flex;
            justify-content: space-between;
        }

        .dest-desc {
            font-size: 0.66rem;
            color: #8da9cb;
            margin-top: 3px;
        }

        .terminal {
            background: #01040a;
            border: 1px solid rgba(0, 243, 255, 0.2);
            border-radius: 5px;
            padding: 8px;
            height: 120px;
            overflow-y: auto;
            font-size: 0.66rem;
            color: #88c5ff;
            display: flex;
            flex-direction: column;
            gap: 4px;
        }

        .log-line { line-height: 1.25; }
        .log-line.warn { color: var(--neon-gold); }
        .log-line.alert { color: var(--neon-purple); }
        .log-line.success { color: var(--neon-green); }
    </style>
</head>
<body>

    <header>
        <h1>IMPRESSORA QUÂNTICA 6D — CRONOGRAMA LOGÍSTICO</h1>
        <p>Mapeamento de Transmutação: Quando, Onde e Para Onde? (Operações Terrestres, Colonização Extrema & Multiverso)</p>
        <span class="logistic-tag" id="mainStatusTag">TIPO: TRANSFORMAÇÃO BIOLÓGICA / CIBERNÉTICA IMEDIATA</span>
    </header>

    <div class="app-container">
        <!-- PAINEL ESQUERDO: SELEÇÃO DE CRONOGRAMA & QUANDO / ONDE -->
        <div class="panel">
            <div class="panel-title">
                <span>1. PERFIL DE TRANSFORMAÇÃO</span>
            </div>

            <div class="mode-selector">
                <div class="mode-btn active-bio" id="btnBioMode" onclick="setMode('bio')">
                    BIOLÓGICA / CIBERNÉTICA<br>
                    <span style="font-size:0.6rem; opacity:0.8;">(Iron Man / Wolverine)</span>
                </div>
                <div class="mode-btn" id="btnCosmicMode" onclick="setMode('cosmic')">
                    TRANSCENDÊNCIA CÓSMICA<br>
                    <span style="font-size:0.6rem; opacity:0.8;">(Doutor Manhattan)</span>
                </div>
            </div>

            <!-- CARTÃO QUANDO -->
            <div class="info-card">
                <h4 id="whenTitle">QUANDO? (TEMPO DE EXECUÇÃO)</h4>
                <p id="whenText">
                    <strong>IMEDIATO:</strong> Realizado instantaneamente logo após a calibração da Impressora 6D de laboratório. Não exige excitação de vácuo profundo.
                </p>
            </div>

            <!-- CARTÃO ONDE -->
            <div class="info-card">
                <h4>ONDE? (AMBIENTE DE PROCESSAMENTO)</h4>
                <p>
                    <strong>BERÇO DE IMPRESSÃO ISOLADO SAMS:</strong> Laboratório Orbital no Espaço Profundo com Ruído Quântico Zero Absoluto para evitar decoerência e interferências gravitacionais.
                </p>
            </div>

            <div class="panel-title" style="margin-top: 5px;">
                <span>MODULADORES DE ISOLAMENTO</span>
            </div>

            <div class="control-group">
                <div class="control-label">
                    <span>Amiudamento de Ruído Quântico:</span>
                    <span class="control-value" id="valNoise">0.0001 dB</span>
                </div>
                <input type="range" id="sliderNoise" min="1" max="100" value="1">
            </div>

            <div class="control-group">
                <div class="control-label">
                    <span>Estabilizador Gravitacional SAMS:</span>
                    <span class="control-value" id="valGrav">100.0%</span>
                </div>
                <input type="range" id="sliderGrav" min="0" max="100" value="100">
            </div>

            <div class="control-group">
                <div class="control-label">
                    <span>Frequência HD-MHD (Ressonância):</span>
                    <span class="control-value" id="valFreq">440.0 GHz</span>
                </div>
                <input type="range" id="sliderFreq" min="10" max="100" value="44">
            </div>

            <button class="btn-action" id="btnProcess" onclick="triggerTransformation()" style="margin-top: auto;">INICIAR PROCESSAMENTO QUÂNTICO</button>
        </div>

        <!-- PAINEL CENTRAL: CANVASES DE VISUALIZAÇÃO -->
        <div class="canvas-container">
            <!-- CANVAS TOP: BERÇO DE IMPRESSÃO SAMS (ONDE) -->
            <div class="canvas-card" style="flex: 1.2;">
                <div class="canvas-tag">CÂMARA ORBITAL DE IMPRESSÃO SAMS — ZERO RUÍDO QUÂNTICO</div>
                <canvas id="cradleCanvas"></canvas>
                <div class="canvas-hud" id="hudCradle">
                    RUÍDO AMBIENTE: 0.0001 dB<br>
                    DESVIO GRAVITACIONAL: 0.00%<br>
                    CAMPO SAMS: ATIVO
                </div>
            </div>

            <!-- CANVAS BOTTOM: MAPA LOGÍSTICO DE DESLOCAMENTO (PARA ONDE) -->
            <div class="canvas-card" style="flex: 1;">
                <div class="canvas-tag">ROTAS DE DESLOCAMENTO PÓS-MUTAÇÃO (VETORES DE DEPLOY)</div>
                <canvas id="mapCanvas"></canvas>
                <div class="canvas-hud" id="hudMap">
                    DESTINO ATIVO: TERRA (INFRAESTRUTURA PESADA)<br>
                    STATUS DE EJEÇÃO: PRONTO
                </div>
            </div>
        </div>

        <!-- PAINEL DIREITO: DESTINOS (PARA ONDE?) & LOGS -->
        <div class="panel">
            <div class="panel-title">
                <span>2. PARA ONDE? (DESTINOS)</span>
            </div>

            <div class="dest-grid" id="destGrid">
                <!-- DESTINO 1: TERRA -->
                <div class="dest-card selected" id="destEarth" onclick="selectDestination('earth')">
                    <div class="dest-title">
                        <span>1. TERRA (INFRAESTRUTURA)</span>
                        <span style="font-size: 0.65rem; color: var(--neon-cyan);">1.0 AU</span>
                    </div>
                    <div class="dest-desc">
                        Operação em cidades e bases industriais. Atuação em infraestrutura hiper-pesada e defesa planetária.
                    </div>
                </div>

                <!-- DESTINO 2: SUPER-TERRAS -->
                <div class="dest-card" id="destSuperEarth" onclick="selectDestination('superEarth')">
                    <div class="dest-title">
                        <span>2. SUPER-TERRA (GLIESE-667C)</span>
                        <span style="font-size: 0.65rem; color: var(--neon-cyan);">23.6 Anos-Luz</span>
                    </div>
                    <div class="dest-desc">
                        Exploração de ambientes de gravidade extrema, radiação severa e mineração interestelar.
                    </div>
                </div>

                <!-- DESTINO 3: MULTIVERSO -->
                <div class="dest-card" id="destMultiverse" onclick="selectDestination('multiverse')">
                    <div class="dest-title">
                        <span>3. FENDA DE BRANAS (MULTIVERSO)</span>
                        <span style="font-size: 0.65rem; color: var(--neon-purple);">FORA DO 4D</span>
                    </div>
                    <div class="dest-desc">
                        Exclusivo do Módulo Cósmico (Doutor Manhattan). Ejeção para além do espaço-tempo para mapear novas realidades.
                    </div>
                </div>
            </div>

            <button class="btn-action purple" id="btnEject" onclick="triggerEjection()" style="margin-top: 5px;">DISPARAR VETOR DE EJEÇÃO</button>

            <div class="panel-title" style="margin-top: 10px;">
                <span>TELEMETRIA LOGÍSTICA</span>
            </div>

            <div class="terminal" id="terminalLog">
                <div class="log-line success">> Sistema logístico pronto no laboratório orbital.</div>
                <div class="log-line">> Aguardando definição de perfil e comando do operador.</div>
            </div>
        </div>
    </div>

    <script>
        const cradleCanvas = document.getElementById('cradleCanvas');
        const cradleCtx = cradleCanvas.getContext('2d');
        const mapCanvas = document.getElementById('mapCanvas');
        const mapCtx = mapCanvas.getContext('2d');

        const sliderNoise = document.getElementById('sliderNoise');
        const sliderGrav = document.getElementById('sliderGrav');
        const sliderFreq = document.getElementById('sliderFreq');

        const valNoise = document.getElementById('valNoise');
        const valGrav = document.getElementById('valGrav');
        const valFreq = document.getElementById('valFreq');

        const mainStatusTag = document.getElementById('mainStatusTag');
        const whenTitle = document.getElementById('whenTitle');
        const whenText = document.getElementById('whenText');
        const terminalLog = document.getElementById('terminalLog');

        let currentMode = 'bio'; 
        let currentDest = 'earth'; 
        let isProcessing = false;
        let isEjecting = false;
        let processProgress = 0;
        let ejectionProgress = 0;

        function resizeCanvases() {
            cradleCanvas.width = cradleCanvas.parentElement.clientWidth;
            cradleCanvas.height = cradleCanvas.parentElement.clientHeight;
            mapCanvas.width = mapCanvas.parentElement.clientWidth;
            mapCanvas.height = mapCanvas.parentElement.clientHeight;
        }
        window.addEventListener('resize', resizeCanvases);

        function logMsg(msg, type = 'info') {
            const entry = document.createElement('div');
            entry.className = `log-line ${type}`;
            const time = new Date().toLocaleTimeString();
            entry.textContent = `[${time}] ${msg}`;
            terminalLog.appendChild(entry);
            terminalLog.scrollTop = terminalLog.scrollHeight;
        }

        sliderNoise.addEventListener('input', (e) => {
            valNoise.textContent = (e.target.value * 0.0001).toFixed(4) + ' dB';
        });
        sliderGrav.addEventListener('input', (e) => {
            valGrav.textContent = e.target.value + '.0%';
        });
        sliderFreq.addEventListener('input', (e) => {
            valFreq.textContent = (e.target.value * 10).toFixed(1) + ' GHz';
        });

        function setMode(mode) {
            currentMode = mode;
            const btnBio = document.getElementById('btnBioMode');
            const btnCosmic = document.getElementById('btnCosmicMode');

            if (mode === 'bio') {
                btnBio.className = 'mode-btn active-bio';
                btnCosmic.className = 'mode-btn';
                mainStatusTag.textContent = 'TIPO: TRANSFORMAÇÃO BIOLÓGICA / CIBERNÉTICA IMEDIATA';
                whenTitle.textContent = 'QUANDO? (EXECUÇÃO IMEDIATA)';
                whenText.innerHTML = '<strong>IMEDIATO:</strong> Executado logo após a calibração da Impressora 6D. Fusão nanometrológica direta nos ossos e músculos sem necessidade de Fase 2/3.';
                selectDestination('earth');
                logMsg('Modo ajustado: Mutações Cibernéticas/Biológicas (Terra / Super-Terras).', 'info');
            } else {
                btnBio.className = 'mode-btn';
                btnCosmic.className = 'mode-btn active-cosmic';
                mainStatusTag.textContent = 'TIPO: TRANSCENDÊNCIA CÓSMICA (FASE 2 & 3)';
                whenTitle.textContent = 'QUANDO? (FASE 2 E 3 REQUERIDAS)';
                whenText.innerHTML = '<strong>FASES 2 E 3:</strong> Exige desmonte atômico por HD-MHD, transferência neural SROS para o vácuo e re-ancoragem no Espaço de Hilbert 6D.';
                selectDestination('multiverse');
                logMsg('Modo ajustado: Transcendência Cósmica (Doutor Manhattan - Multiverso).', 'alert');
            }
        }

        function selectDestination(dest) {
            if (currentMode === 'bio' && dest === 'multiverse') {
                logMsg('AVISO: Mutações Biológicas/Cibernéticas não possuem ancoragem dimensional para navegar no Multiverso sem um chassi 6D. Selecionado Super-Terra.', 'warn');
                dest = 'superEarth';
            }

            currentDest = dest;
            document.getElementById('destEarth').className = 'dest-card' + (dest === 'earth' ? ' selected' : '');
            document.getElementById('destSuperEarth').className = 'dest-card' + (dest === 'superEarth' ? ' selected' : '');
            document.getElementById('destMultiverse').className = 'dest-card' + (dest === 'multiverse' ? ' selected' : '');

            const labelMap = {
                earth: 'TERRA (INFRAESTRUTURA PESADA)',
                superEarth: 'SUPER-TERRA GLIESE-667C (GRAVIDADE EXTREMA)',
                multiverse: 'FENDA DE BRANAS MULTIVERSAL (FORA DO 4D)'
            };
            document.getElementById('hudMap').innerHTML = `
                DESTINO ATIVO: ${labelMap[dest]}<br>
                STATUS DE EJEÇÃO: PRONTO
            `;
            logMsg(`Destino configurado: ${labelMap[dest]}`, 'success');
        }

        function triggerTransformation() {
            if (isProcessing) return;
            isProcessing = true;
            processProgress = 0;
            logMsg('Iniciando alinhamento do Berço SAMS em Espaço Profundo...', 'warn');
        }

        function triggerEjection() {
            if (isEjecting) return;
            isEjecting = true;
            ejectionProgress = 0;
            logMsg(`Iniciando lançamento e ejeção de vetor para [${currentDest.toUpperCase()}]...`, 'alert');
        }

        function drawCradle() {
            const w = cradleCanvas.width;
            const h = cradleCanvas.height;
            const cx = w / 2;
            const cy = h / 2;

            cradleCtx.clearRect(0, 0, w, h);

            cradleCtx.strokeStyle = 'rgba(0, 243, 255, 0.05)';
            cradleCtx.lineWidth = 1;
            for (let x = 0; x < w; x += 30) {
                cradleCtx.beginPath(); cradleCtx.moveTo(x, 0); cradleCtx.lineTo(x, h); cradleCtx.stroke();
            }
            for (let y = 0; y < h; y += 30) {
                cradleCtx.beginPath(); cradleCtx.moveTo(0, y); cradleCtx.lineTo(w, y); cradleCtx.stroke();
            }

            const time = Date.now() * 0.002;
            cradleCtx.lineWidth = 2;
            for (let i = 1; i <= 3; i++) {
                cradleCtx.strokeStyle = currentMode === 'bio' ? `rgba(0, 243, 255, ${0.2 * i})` : `rgba(183, 0, 255, ${0.25 * i})`;
                cradleCtx.beginPath();
                cradleCtx.ellipse(cx, cy, 120 + i * 25, 50 + i * 12, time * (i % 2 === 0 ? 1 : -1), 0, Math.PI * 2);
                cradleCtx.stroke();
            }

            cradleCtx.save();
            cradleCtx.translate(cx, cy);

            if (currentMode === 'bio') {
                cradleCtx.fillStyle = '#00f3ff';
                cradleCtx.shadowColor = '#00f3ff';
                cradleCtx.shadowBlur = 15;
                cradleCtx.beginPath(); cradleCtx.arc(0, -35, 12, 0, Math.PI * 2); cradleCtx.fill();
                cradleCtx.fillRect(-12, -20, 24, 45);
                cradleCtx.fillRect(-22, -20, 8, 40); cradleCtx.fillRect(14, -20, 8, 40);
                cradleCtx.fillRect(-10, 28, 8, 45); cradleCtx.fillRect(2, 28, 8, 45);
            } else {
                cradleCtx.fillStyle = 'rgba(183, 0, 255, 0.8)';
                cradleCtx.shadowColor = '#b700ff';
                cradleCtx.shadowBlur = 25;
                cradleCtx.beginPath(); cradleCtx.arc(0, -35, 14, 0, Math.PI * 2); cradleCtx.fill();
                cradleCtx.fillRect(-14, -20, 28, 50);
                
                cradleCtx.strokeStyle = '#ffffff';
                cradleCtx.lineWidth = 1.5;
                cradleCtx.beginPath();
                cradleCtx.ellipse(0, 0, 45, 15, time * 2, 0, Math.PI * 2);
                cradleCtx.stroke();
            }
            cradleCtx.restore();

            if (isProcessing) {
                processProgress += 0.5;
                cradleCtx.strokeStyle = '#00ff73';
                cradleCtx.lineWidth = 3;
                cradleCtx.beginPath();
                cradleCtx.arc(cx, cy, 180, -Math.PI / 2, (-Math.PI / 2) + (Math.PI * 2 * (processProgress / 100)));
                cradleCtx.stroke();

                if (processProgress >= 100) {
                    isProcessing = false;
                    logMsg('Processamento Quântico e Estabilização SAMS Concluídos com Sucesso!', 'success');
                }
            }

            document.getElementById('hudCradle').innerHTML = `
                RUÍDO AMBIENTE: ${(sliderNoise.value * 0.0001).toFixed(4)} dB<br>
                ESTABILIZAÇÃO GRAVITACIONAL: ${sliderGrav.value}.0%<br>
                SISTEMA SAMS: ${isProcessing ? 'TRANSFORMANDO (' + Math.floor(processProgress) + '%)' : 'PRONTO'}
            `;
        }

        function drawMap() {
            const w = mapCanvas.width;
            const h = mapCanvas.height;

            mapCtx.clearRect(0, 0, w, h);
            mapCtx.fillStyle = '#010309';
            mapCtx.fillRect(0, 0, w, h);

            const nodeStation = { x: 80, y: h / 2, label: 'LAB ORBITAL (SAMS)' };
            const nodeEarth = { x: w * 0.45, y: h * 0.3, label: 'TERRA 4D' };
            const nodeSuperEarth = { x: w * 0.55, y: h * 0.75, label: 'GLIESE-667C' };
            const nodeMultiverse = { x: w * 0.85, y: h / 2, label: 'MULTIVERSO (BRANAS)' };

            mapCtx.lineWidth = 1.5;
            
            mapCtx.strokeStyle = currentDest === 'earth' ? '#00f3ff' : 'rgba(0, 243, 255, 0.2)';
            mapCtx.beginPath(); mapCtx.moveTo(nodeStation.x, nodeStation.y); mapCtx.lineTo(nodeEarth.x, nodeEarth.y); mapCtx.stroke();

            mapCtx.strokeStyle = currentDest === 'superEarth' ? '#00ff73' : 'rgba(0, 255, 115, 0.2)';
            mapCtx.beginPath(); mapCtx.moveTo(nodeStation.x, nodeStation.y); mapCtx.lineTo(nodeSuperEarth.x, nodeSuperEarth.y); mapCtx.stroke();

            mapCtx.strokeStyle = currentDest === 'multiverse' ? '#b700ff' : 'rgba(183, 0, 255, 0.2)';
            mapCtx.beginPath(); mapCtx.moveTo(nodeStation.x, nodeStation.y); mapCtx.lineTo(nodeMultiverse.x, nodeMultiverse.y); mapCtx.stroke();

            [nodeStation, nodeEarth, nodeSuperEarth, nodeMultiverse].forEach(node => {
                mapCtx.beginPath();
                mapCtx.arc(node.x, node.y, 8, 0, Math.PI * 2);
                
                if (node.label.includes('MULTIVERSO')) mapCtx.fillStyle = '#b700ff';
                else if (node.label.includes('TERRA 4D')) mapCtx.fillStyle = '#00f3ff';
                else if (node.label.includes('GLIESE')) mapCtx.fillStyle = '#00ff73';
                else mapCtx.fillStyle = '#ffc400';

                mapCtx.fill();
                mapCtx.fillStyle = '#ffffff';
                mapCtx.font = '10px Courier New';
                mapCtx.fillText(node.label, node.x - 30, node.y + 20);
            });

            if (isEjecting) {
                ejectionProgress += 1.2;
                let targetNode = nodeEarth;
                if (currentDest === 'superEarth') targetNode = nodeSuperEarth;
                if (currentDest === 'multiverse') targetNode = nodeMultiverse;

                const curX = nodeStation.x + (targetNode.x - nodeStation.x) * (ejectionProgress / 100);
                const curY = nodeStation.y + (targetNode.y - nodeStation.y) * (ejectionProgress / 100);

                mapCtx.fillStyle = currentMode === 'bio' ? '#00f3ff' : '#b700ff';
                mapCtx.shadowColor = mapCtx.fillStyle;
                mapCtx.shadowBlur = 15;
                mapCtx.beginPath();
                mapCtx.arc(curX, curY, 6, 0, Math.PI * 2);
                mapCtx.fill();
                mapCtx.shadowBlur = 0;

                if (ejectionProgress >= 100) {
                    isEjecting = false;
                    logMsg(`VETOR DE EJEÇÃO CONCLUÍDO: Indivíduo chegou com sucesso em [${targetNode.label}]!`, 'success');
                }
            }
        }

        function render() {
            drawCradle();
            drawMap();
            requestAnimationFrame(render);
        }

        resizeCanvases();
        render();
    </script>
</body>
</html>
