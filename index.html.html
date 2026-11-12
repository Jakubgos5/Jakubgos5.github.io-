<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Terminal Paint Pro // CAD & Graph System</title>
    <style>
        :root {
            --bg-color: #0f0f13; --panel-bg: #16161f; --panel-border: #2a2a3d;
            --accent: #00ffcc; --accent-glow: rgba(0, 255, 204, 0.2);
            --text-main: #ffffff; --text-muted: #8c8c9e;
            --danger: #ff4d4d; --success: #2ecc71; --warning: #f1c40f;
        }
        * { box-sizing: border-box; margin: 0; padding: 0; }
        body {
            background-color: var(--bg-color); color: var(--text-main);
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            display: flex; flex-direction: column; align-items: center;
            min-height: 100vh; padding: 15px;
        }
        .app-container { width: 100%; max-width: 1250px; display: flex; flex-direction: column; gap: 12px; }
        .header {
            display: flex; justify-content: space-between; align-items: center; gap: 10px; flex-wrap: wrap;
            background: var(--panel-bg); border: 1px solid var(--panel-border);
            padding: 10px 20px; border-radius: 12px; box-shadow: 0 4px 20px rgba(0,0,0,0.4);
        }
        .header h1 { font-size: 1.1rem; letter-spacing: 1.5px; color: var(--accent); font-weight: 600; }
        .header .status { font-size: 0.8rem; color: var(--text-muted); font-family: monospace; }
        .toolbar { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 10px; }
        .tool-card {
            background: var(--panel-bg); border: 1px solid var(--panel-border); border-radius: 10px;
            padding: 10px; display: flex; flex-direction: column; gap: 6px; box-shadow: 0 4px 12px rgba(0,0,0,0.2);
        }
        .tool-card > span {
            font-size: 0.7rem; text-transform: uppercase; letter-spacing: 1px;
            color: var(--text-muted); font-weight: bold;
        }
        .tool-buttons { display: flex; flex-wrap: wrap; gap: 5px; }
        button {
            background: #1f1f2e; color: var(--text-main); border: 1px solid var(--panel-border);
            padding: 5px 8px; border-radius: 6px; cursor: pointer; font-size: 0.75rem; transition: all 0.2s ease;
        }
        button:hover { border-color: var(--accent); background: #252538; }
        button.active {
            background: var(--accent); color: #000; border-color: var(--accent);
            font-weight: 600; box-shadow: 0 0 10px var(--accent-glow);
        }
        button.danger { background: rgba(255,77,77,0.1); color: var(--danger); border-color: rgba(255,77,77,0.3); }
        button.danger:hover { background: var(--danger); color: #fff; }
        button.success { background: rgba(46,204,113,0.1); color: var(--success); border-color: rgba(46,204,113,0.3); }
        button.success:hover { background: var(--success); color: #fff; }
        button.warning { background: rgba(241,196,15,0.1); color: var(--warning); border-color: rgba(241,196,15,0.3); }
        button.warning:hover { background: var(--warning); color: #000; }
        /* Naprawa: stan "active" przełączników był nadpisywany przez .warning */
        button.warning.active { background: var(--warning); color: #000; border-color: var(--warning); box-shadow: 0 0 10px rgba(241,196,15,0.4); }
        .controls-row { display: flex; align-items: center; justify-content: space-between; gap: 8px; }
        input[type="color"] { -webkit-appearance: none; border: none; width: 28px; height: 28px; border-radius: 6px; cursor: pointer; background: none; }
        input[type="color"]::-webkit-color-swatch-wrapper { padding: 0; }
        input[type="color"]::-webkit-color-swatch { border: 1px solid var(--panel-border); border-radius: 6px; }
        input[type="range"] { flex-grow: 1; accent-color: var(--accent); cursor: pointer; }
        select {
            background: #1f1f2e; color: var(--text-main); border: 1px solid var(--panel-border);
            padding: 4px 6px; border-radius: 6px; font-size: 0.75rem; cursor: pointer;
        }
        .function-panel {
            background: var(--panel-bg); border: 1px solid var(--panel-border); border-radius: 10px;
            padding: 10px 15px; display: flex; flex-wrap: wrap; gap: 15px; align-items: center;
        }
        .function-panel label { font-size: 0.75rem; color: var(--text-muted); }
        .function-panel input[type="number"] {
            background: #1f1f2e; color: var(--accent); border: 1px solid var(--panel-border);
            padding: 4px 6px; border-radius: 6px; width: 60px; font-family: monospace; text-align: center;
        }
        .canvas-container {
            background: var(--panel-bg); border: 1px solid var(--panel-border); border-radius: 12px;
            padding: 15px; display: flex; justify-content: center; align-items: center;
            box-shadow: 0 8px 30px rgba(0,0,0,0.5);
        }
        /* Dwie warstwy: rysunek (dół) + siatka/układ (góra, nie przechwytuje myszy) */
        .canvas-stack {
            position: relative; width: 100%; max-width: 1000px; aspect-ratio: 2 / 1;
            background: #ffffff; border-radius: 8px; overflow: hidden; container-type: inline-size; box-shadow: 0 4px 15px rgba(0,0,0,0.3);
        }
        .canvas-stack canvas { position: absolute; inset: 0; width: 100%; height: 100%; display: block; }
        #paintCanvas { cursor: crosshair; touch-action: none; }
        #overlayCanvas, #vecCanvas { pointer-events: none; }
        /* 1 px płótna = 0.1cqw, więc czcionka skaluje się razem z płótnem */
        .text-box {
            position: absolute; z-index: 5; padding: 0; margin: 0; border: 0;
            background: rgba(255,255,255,0.35); outline: 1px dashed #0077ff;
            resize: both; overflow: auto; min-width: 40px; min-height: 20px;
            line-height: 1.25; white-space: pre-wrap; word-break: break-word;
            font-size: calc(var(--fs) * 0.1cqw);
        }
        .drag-box { position: absolute; z-index: 5; outline: 1px dashed #0077ff; display: none; pointer-events: none; }
        .ring { position: absolute; z-index: 6; pointer-events: none; display: none; transform: translate(-50%, -50%);
            border: 1px solid #000; box-shadow: 0 0 0 1px #fff; width: calc(var(--d) * 0.1cqw); height: calc(var(--d) * 0.1cqw); border-radius: 50%; }
        .lbl { font-size: 0.7rem; color: var(--text-muted); min-width: 62px; }
        .val { font-size: 0.7rem; color: var(--accent); min-width: 36px; text-align: right; font-weight: normal; }
        .chk { font-size: 0.75rem; color: var(--text-muted); display: flex; gap: 6px; align-items: center; cursor: pointer; }
        #toast {
            position: fixed; bottom: 20px; left: 50%; transform: translateX(-50%);
            background: var(--panel-bg); border: 1px solid var(--accent); color: var(--accent);
            padding: 8px 16px; border-radius: 8px; font-size: 0.8rem; opacity: 0;
            transition: opacity 0.3s; pointer-events: none;
        }
        #toast.show { opacity: 1; }
    </style>
</head>
<body>

    <div class="app-container">
        <div class="header">
            <h1>// TERMINAL PAINT PRO (CAD & FUNCTIONS)</h1>
            <div class="status" id="toolStatus">Aktywne narzędzie: Ołówek</div>
        </div>

        <div class="toolbar">
            <div class="tool-card">
                <span>Rysowanie</span>
                <div class="tool-buttons">
                    <button data-tool="pencil" class="active">Ołówek</button>
                    <button data-tool="brush">Pędzel</button>
                    <button data-tool="spray">Spray</button>
                    <button data-tool="eraser">Gumka</button>
                    <button data-tool="fill">Kubełek</button>
                    <button data-tool="picker">Pipeta</button>
                </div>
            </div>

            <div class="tool-card">
                <span>Figury Geometryczne</span>
                <div class="tool-buttons">
                    <button data-tool="line">Linia</button>
                    <button data-tool="rect">Prostokąt</button>
                    <button data-tool="circle">Okrąg</button>
                    <button data-tool="triangle">Trójkąt</button>
                    <button data-tool="rombus">Romb</button>
                    <button data-tool="trapezoid">Trapez</button>
                    <button data-tool="text">Tekst</button>
                </div>
            </div>

            <div class="tool-card">
                <span>Konfiguracja</span>
                <div class="controls-row">
                    <div style="display:flex; align-items:center; gap:6px;">
                        <input type="color" id="colorPicker" value="#000000">
                        <span style="font-size: 0.75rem; color:var(--text-muted);">Kolor</span>
                    </div>
                    <span style="font-size: 0.75rem; color:var(--accent);" id="sizeVal">5px</span>
                </div>
                <div class="controls-row" data-p="size"><input type="range" id="brushSize" min="1" max="50" value="5"></div>
                <div class="controls-row"><div style="display:flex; align-items:center; gap:6px;"><input type="color" id="fillColor" value="#00aaff"><span style="font-size: 0.75rem; color:var(--text-muted);">Wypełnienie</span></div></div>
            </div>

            <div class="tool-card">
                <span id="optTitle">Ustawienia narzędzia</span>
                <div class="controls-row" data-p="opacity"><span class="lbl">Krycie</span><input type="range" id="opacity" min="1" max="100" value="100" data-out="opacityVal"><b class="val" id="opacityVal"></b></div>
                <div class="controls-row" data-p="hardness"><span class="lbl">Twardość</span><input type="range" id="hardness" min="0" max="100" value="60" data-out="hardnessVal"><b class="val" id="hardnessVal"></b></div>
                <div class="controls-row" data-p="smooth"><span class="lbl">Wygładzanie</span><input type="range" id="smooth" min="0" max="90" value="0" data-out="smoothVal"><b class="val" id="smoothVal"></b></div>
                <div class="controls-row" data-p="density"><span class="lbl">Gęstość</span><input type="range" id="density" min="5" max="100" value="50" data-out="densityVal"><b class="val" id="densityVal"></b></div>
                <div class="controls-row" data-p="tol"><span class="lbl">Tolerancja</span><input type="range" id="tol" min="0" max="128" value="40" data-out="tolVal" data-u=""><b class="val" id="tolVal"></b></div>
                <div class="controls-row" data-p="radius"><span class="lbl">Zaokrąglenie</span><input type="range" id="radius" min="0" max="100" value="0" data-out="radiusVal" data-u="px"><b class="val" id="radiusVal"></b></div>
                <div class="controls-row" data-p="sides"><span class="lbl">Boki/ramiona</span><input type="range" id="sides" min="3" max="12" value="5" data-out="sidesVal" data-u=""><b class="val" id="sidesVal"></b></div>
                <div class="controls-row" data-p="cap"><span class="lbl">Końce</span><select id="capSel"><option value="round">Okrągłe</option><option value="square">Kwadratowe</option><option value="butt">Płaskie</option></select></div>
                <div class="controls-row" data-p="dash"><span class="lbl">Linia</span><select id="dashSel"><option value="solid">Ciągła</option><option value="dashed">Kreskowana</option><option value="dotted">Kropkowana</option></select></div>
                <div class="controls-row" data-p="fillMode"><span class="lbl">Styl</span><select id="fillMode"><option value="stroke">Tylko kontur</option><option value="fill">Tylko wypełnienie</option><option value="both">Kontur + wypełnienie</option></select></div>
                <div class="controls-row" data-p="avg"><span class="lbl">Próbka</span><select id="avg"><option value="1">1 piksel</option><option value="3">Średnia 3×3</option><option value="5">Średnia 5×5</option><option value="9">Średnia 9×9</option></select></div>
                <div class="controls-row" data-p="eshape"><span class="lbl">Kształt</span><select id="eshape"><option value="round">Okrągła</option><option value="square">Kwadratowa</option></select></div>
                <div class="controls-row" data-p="emode"><span class="lbl">Tryb</span><select id="emode"><option value="pixel">Piksele (raster)</option><option value="object">Obiekty / zdjęcia</option></select></div>
            </div>

            <div class="tool-card">
                <span>Figury 2D / 3D</span>
                <div class="tool-buttons">
                    <button data-tool="ellipse">Elipsa</button>
                    <button data-tool="parallelogram">Równoległobok</button>
                    <button data-tool="polygon">Wielokąt</button>
                    <button data-tool="star">Gwiazda</button>
                    <button data-tool="arrow">Strzałka</button>
                    <button data-tool="heart">Serce</button>
                    <button data-tool="cross">Krzyż</button>
                </div>
                <div class="tool-buttons">
                    <button data-tool="cube">Sześcian 3D</button>
                    <button data-tool="cylinder">Walec 3D</button>
                    <button data-tool="cone">Stożek 3D</button>
                    <button data-tool="pyramid">Ostrosłup 3D</button>
                    <button data-tool="sphere">Kula 3D</button>
                </div>
            </div>

            <div class="tool-card">
                <span>Grafika wektorowa</span>
                <label class="chk"><input type="checkbox" id="vecMode"> Figury jako obiekty wektorowe</label>
                <label class="chk"><input type="checkbox" id="smoothPen"> Gładkie krzywe (Pióro)</label>
                <div class="tool-buttons">
                    <button data-tool="select">Zaznacz</button>
                    <button data-tool="pen">Pióro</button>
                    <button id="btn-dup">Duplikuj</button>
                    <button id="btn-del" class="danger">Usuń</button>
                    <button id="btn-up">Wyżej</button>
                    <button id="btn-down">Niżej</button>
                    <button id="btn-flat">Spłaszcz do rastra</button>
                    <button id="btn-svg" class="success">Eksport SVG</button>
                </div>
            </div>

            <div class="tool-card">
                <span>Raster i zdjęcia</span>
                <div class="controls-row">
                    <select id="filterSel">
                        <option value="grayscale(1)">Skala szarości</option><option value="sepia(1)">Sepia</option>
                        <option value="invert(1)">Negatyw</option><option value="blur(3px)">Rozmycie</option>
                        <option value="brightness(1.3)">Jaśniej</option><option value="brightness(0.7)">Ciemniej</option>
                        <option value="contrast(1.5)">Kontrast+</option><option value="saturate(2)">Nasycenie+</option>
                        <option value="hue-rotate(90deg)">Zmiana barw</option>
                    </select>
                    <button id="btn-filter">Zastosuj</button>
                </div>
                <div class="tool-buttons">
                    <button id="btn-fliph">Odbij ↔</button>
                    <button id="btn-flipv">Odbij ↕</button>
                    <button id="btn-photo" class="success">Wstaw zdjęcia</button>
                </div>
            </div>

            <div class="tool-card">
                <span>System & Pliki</span>
                <div class="tool-buttons">
                    <button id="btn-undo">Cofnij</button>
                    <button id="btn-redo">Ponów</button>
                    <button id="btn-grid" class="warning">Siatka</button>
                    <button id="btn-cartesian" class="warning">Kartezjusz</button>
                    <button id="btn-clear" class="danger">Wyczyść</button>
                    <button id="btn-save" class="success">Zapisz</button>
                    <button id="btn-open">Otwórz</button>
                </div>
            </div>
        </div>

        <div class="function-panel">
            <span style="color: var(--accent); font-weight: bold; font-size: 0.8rem;">WYKRES FUNKCJI:</span>
            <div style="display:flex; align-items:center; gap:6px;">
                <label>Typ:</label>
                <select id="funcType">
                    <option value="linear">Liniowa: a·x + b</option>
                    <option value="quadratic">Kwadratowa: a·x² + b·x + c</option>
                    <option value="sine">Trygonometryczna: a·sin(b·x) + c</option>
                    <option value="log">Logarytmiczna: a·log₁₀(x) + b</option>
                    <option value="ln">Naturalna: a·ln(x) + b</option>
                </select>
            </div>
            <div style="display:flex; align-items:center; gap:4px;"><label>a:</label><input type="number" id="paramA" value="1" step="0.5"></div>
            <div style="display:flex; align-items:center; gap:4px;"><label>b:</label><input type="number" id="paramB" value="0" step="0.5"></div>
            <div style="display:flex; align-items:center; gap:4px;"><label>c:</label><input type="number" id="paramC" value="0" step="0.5"></div>
            <button class="success" id="btn-func">Rysuj funkcję w układzie</button>
        </div>

        <div class="function-panel">
            <span style="color: var(--accent); font-weight: bold; font-size: 0.8rem;">TEKST:</span>
            <div style="display:flex; align-items:center; gap:6px;">
                <label>Czcionka:</label>
                <select id="textFont">
                    <option value="Arial, sans-serif">Arial</option>
                    <option value="Verdana, sans-serif">Verdana</option>
                    <option value="Georgia, serif">Georgia</option>
                    <option value="'Times New Roman', serif">Times New Roman</option>
                    <option value="'Courier New', monospace">Courier New</option>
                </select>
            </div>
            <div style="display:flex; align-items:center; gap:4px;">
                <label>Rozmiar:</label>
                <input type="number" id="textSize" value="32" min="8" max="200" step="2">
            </div>
            <button id="btn-bold" style="font-weight:bold">B</button>
            <button id="btn-italic" style="font-style:italic">I</button>
            <button class="success" id="btn-text-ok">Zatwierdź tekst</button>
            <span style="font-size:0.7rem; color:var(--text-muted);">Wybierz „Tekst”, kliknij lub przeciągnij na płótnie, wpisz lub wklej (Ctrl+V). Ctrl+Enter zatwierdza, Esc anuluje.</span>
        </div>

        <div class="canvas-container">
            <div class="canvas-stack">
                <canvas id="paintCanvas" width="1000" height="500"></canvas>
                <canvas id="vecCanvas" width="1000" height="500"></canvas>
                <canvas id="overlayCanvas" width="1000" height="500"></canvas>
                <div class="drag-box" id="dragBox"></div>
                <div class="ring" id="ring"></div>
            </div>
        </div>
    </div>

    <input type="file" id="fileInput" accept="image/*" hidden>
    <input type="file" id="photoInput" accept="image/*" multiple hidden>
    <div id="toast"></div>

    <script>
        const W = 1000, H = 500, SCALE = 25; // 25 px = 1 jednostka układu
        const canvas = document.getElementById('paintCanvas');
        const ctx = canvas.getContext('2d', { willReadFrequently: true });
        const overlay = document.getElementById('overlayCanvas');
        const octx = overlay.getContext('2d');

        let painting = false, currentTool = 'pencil';
        let startX = 0, startY = 0, lastX = 0, lastY = 0, curX = 0, curY = 0;
        let snapshot = null, sprayTimer = null;
        let undoStack = [], redoStack = [];
        let showGrid = false, showCartesian = false, fileHandle = null;
        let color = '#000000', size = 5;
        let activeBox = null, textDrag = false;
        const $ = id => document.getElementById(id);
        let objs = [], sel = null, drag = null, penPts = [], vecTemp = null, imgStore = [];
        let pts = [], sx = 0, sy = 0;
        const SHAPES = ['line', 'rect', 'circle', 'ellipse', 'triangle', 'rombus', 'trapezoid', 'parallelogram', 'polygon', 'star', 'arrow', 'heart', 'cross', 'cube', 'cylinder', 'cone', 'pyramid', 'sphere'];
        const vecCanvas = $('vecCanvas'), vctx = vecCanvas.getContext('2d');
        const opacity = () => $('opacity').value / 100;
        const vecMode = () => $('vecMode').checked;
        const dashFor = (d, w) => d === 'dashed' ? [w * 3, w * 2] : d === 'dotted' ? [1, w * 2] : [];
        let fontFamily = 'Arial, sans-serif', fontSize = 32, fontBold = false, fontItalic = false;
        const stack = document.querySelector('.canvas-stack');
        const dragBox = document.getElementById('dragBox');

        ctx.lineCap = 'round';
        ctx.lineJoin = 'round';

        const toolNames = {
            pencil: 'Ołówek', brush: 'Pędzel', spray: 'Spray', eraser: 'Gumka',
            fill: 'Kubełek z farbą', picker: 'Pipeta', line: 'Prosta linia',
            rect: 'Prostokąt', circle: 'Okrąg', triangle: 'Trójkąt',
            rombus: 'Romb', trapezoid: 'Trapez', text: 'Ramka tekstowa',
            select: 'Zaznaczanie (wektor)', pen: 'Pióro (wektor)', ellipse: 'Elipsa', parallelogram: 'Równoległobok',
            polygon: 'Wielokąt foremny', star: 'Gwiazda', arrow: 'Strzałka', heart: 'Serce', cross: 'Krzyż',
            cube: 'Sześcian 3D', cylinder: 'Walec 3D', cone: 'Stożek 3D', pyramid: 'Ostrosłup 3D', sphere: 'Kula 3D'
        };
        const FREEHAND = ['pencil', 'brush', 'eraser'];

        function toast(msg) {
            const t = document.getElementById('toast');
            t.textContent = msg;
            t.classList.add('show');
            clearTimeout(toast.timer);
            toast.timer = setTimeout(() => t.classList.remove('show'), 2000);
        }

        /* ---------- Cofnij / Ponów ---------- */
        function snap() { return { r: ctx.getImageData(0, 0, W, H), v: JSON.stringify(objs) }; }
        function restore(st) { ctx.putImageData(st.r, 0, 0); objs = JSON.parse(st.v); sel = null; renderVec(); }
        function saveState() {
            undoStack.push(snap());
            if (undoStack.length > 30) undoStack.shift();
            redoStack = [];
        }
        function undo() {
            if (activeBox) { cancelText(); return; }
            if (!undoStack.length) return;
            redoStack.push(snap());
            restore(undoStack.pop());
        }
        function redo() {
            if (activeBox || !redoStack.length) return;
            undoStack.push(snap());
            restore(redoStack.pop());
        }

        /* ---------- Narzędzia i ustawienia ---------- */
        function setTool(tool) {
            commitText();
            if (penPts.length) finishPen(false);
            if (tool !== 'select' && sel !== null) { sel = null; renderVec(); }
            currentTool = tool;
            canvas.style.cursor = tool === 'text' ? 'text' : tool === 'select' ? 'default' : 'crosshair';
            document.querySelectorAll('[data-tool]').forEach(b => b.classList.toggle('active', b.dataset.tool === tool));
            document.getElementById('toolStatus').textContent = 'Aktywne narzędzie: ' + toolNames[tool];
            loadProfile();
        }
        document.querySelectorAll('[data-tool]').forEach(b => b.addEventListener('click', () => setTool(b.dataset.tool)));

        const sizeVal = document.getElementById('sizeVal');
        document.getElementById('brushSize').addEventListener('input', e => {
            size = parseInt(e.target.value, 10);
            sizeVal.textContent = size + 'px';
        });
        const colorPicker = document.getElementById('colorPicker');
        colorPicker.addEventListener('input', e => { color = e.target.value; if (activeBox) styleTextBox(activeBox.el); });

        // Styl zależy od narzędzia; każde ma własny profil ustawień (patrz loadProfile)
        function applyStyle() {
            const er = currentTool === 'eraser', cap = er ? 'round' : $('capSel').value;
            ctx.lineWidth = size;
            ctx.strokeStyle = color;
            ctx.fillStyle = er ? '#000' : color;
            ctx.globalAlpha = opacity();
            ctx.lineCap = cap;
            ctx.lineJoin = cap === 'square' ? 'miter' : 'round';
            ctx.setLineDash(er ? [] : dashFor($('dashSel').value, size)); // gumka ignoruje styl linii
            ctx.globalCompositeOperation = er ? 'destination-out' : 'source-over';
            ctx.shadowBlur = (currentTool === 'brush' || er) ? size * (1 - $('hardness').value / 100) * 1.5 : 0;
            ctx.shadowColor = er ? '#000' : color;
        }
        function resetStyle() {
            ctx.globalCompositeOperation = 'source-over';
            ctx.globalAlpha = 1;
            ctx.shadowBlur = 0;
            ctx.setLineDash([]);
            ctx.lineCap = 'round';
            ctx.lineJoin = 'round';
        }

        // Ołówek/pędzel/gumka: cała ścieżka rysowana od zera → równe krycie bez "koralików"
        function strokePath() {
            ctx.putImageData(snapshot.r, 0, 0);
            if (currentTool === 'eraser' && $('eshape').value === 'square') { // gumka kwadratowa = stemplowanie
                ctx.globalAlpha = 1;
                const h = size / 2, st = Math.max(1, size / 4);
                const put = (x, y) => ctx.fillRect(x - h, y - h, size, size);
                put(pts[0][0], pts[0][1]);
                for (let i = 1; i < pts.length; i++) {
                    const [ax, ay] = pts[i - 1], [bx, by] = pts[i], n = Math.ceil(Math.hypot(bx - ax, by - ay) / st);
                    for (let k = 1; k <= n; k++) put(ax + (bx - ax) * k / n, ay + (by - ay) * k / n);
                }
                return;
            }
            ctx.save();
            // miękka krawędź: obiekt rysowany poza płótnem, widoczny tylko jego rozmyty cień
            if (ctx.shadowBlur > 0) { ctx.shadowOffsetX = 10000; ctx.translate(-10000, 0); }
            ctx.beginPath();
            ctx.moveTo(pts[0][0], pts[0][1]);
            if (pts.length === 1) ctx.lineTo(pts[0][0] + 0.01, pts[0][1]);
            else {
                for (let i = 1; i < pts.length - 1; i++)
                    ctx.quadraticCurveTo(pts[i][0], pts[i][1], (pts[i][0] + pts[i + 1][0]) / 2, (pts[i][1] + pts[i + 1][1]) / 2);
                const l = pts[pts.length - 1];
                ctx.lineTo(l[0], l[1]);
            }
            ctx.stroke();
            ctx.restore();
        }

        /* ---------- Rysowanie ---------- */
        function getPos(e) {
            const r = canvas.getBoundingClientRect();
            return { x: (e.clientX - r.left) * (W / r.width), y: (e.clientY - r.top) * (H / r.height) };
        }

        function segment(x1, y1, x2, y2) {
            ctx.beginPath();
            ctx.moveTo(x1, y1);
            ctx.lineTo(x2, y2);
            ctx.stroke();
        }

        function spray() {
            const r = size, n = Math.max(1, Math.ceil(r * r * 0.02 * $('density').value / 50));
            for (let i = 0; i < n; i++) {
                const a = Math.random() * Math.PI * 2, d = Math.sqrt(Math.random()) * r;
                ctx.fillRect(curX + Math.cos(a) * d, curY + Math.sin(a) * d, 1.3, 1.3);
            }
        }

        // Figury rastrowe używają tego samego modelu co wektorowe
        function drawShape() {
            ctx.putImageData(snapshot.r, 0, 0);
            drawObj(ctx, shapeObj(currentTool, startX, startY, curX, curY));
        }

        canvas.addEventListener('pointerdown', e => {
            if (e.button !== 0) return;
            const hadBox = !!activeBox;
            commitText();
            if (currentTool === 'text' && hadBox) return; // pierwsze kliknięcie tylko zatwierdza tekst
            const p = getPos(e);
            startX = lastX = curX = p.x;
            startY = lastY = curY = p.y;
            const ix = Math.min(W - 1, Math.max(0, Math.floor(p.x)));
            const iy = Math.min(H - 1, Math.max(0, Math.floor(p.y)));

            if (currentTool === 'pen') { penClick(); return; }
            if (currentTool === 'select') { selectDown(e, p); return; }
            if (vecMode() && SHAPES.includes(currentTool)) { canvas.setPointerCapture(e.pointerId); drag = { k: 'create' }; return; }

            if (currentTool === 'fill') { floodFill(ix, iy, hexToRgb(color)); return; }

            if (currentTool === 'picker') {
                const n = +$('avg').value, h0 = (n - 1) / 2;
                const px = ctx.getImageData(Math.max(0, Math.min(W - n, ix - h0)), Math.max(0, Math.min(H - n, iy - h0)), n, n).data;
                let rr = 0, gg = 0, bb = 0;
                for (let i = 0; i < px.length; i += 4) { // puste/półprzezroczyste piksele liczymy na białym tle
                    const a = px[i + 3] / 255;
                    rr += px[i] * a + 255 * (1 - a); gg += px[i + 1] * a + 255 * (1 - a); bb += px[i + 2] * a + 255 * (1 - a);
                }
                color = rgbToHex(Math.round(rr / (n * n)), Math.round(gg / (n * n)), Math.round(bb / (n * n)));
                colorPicker.value = color;
                setTool('pencil');
                return;
            }

            if (currentTool === 'text') {
                canvas.setPointerCapture(e.pointerId);
                textDrag = true;
                return;
            }

            canvas.setPointerCapture(e.pointerId);
            painting = true;
            saveState();
            snapshot = undoStack[undoStack.length - 1]; // stan sprzed rysowania = podgląd figur
            applyStyle();

            if (currentTool === 'eraser' && $('emode').value === 'object') {
                eraseObjects();
            } else if (FREEHAND.includes(currentTool)) {
                if (currentTool === 'eraser' && objs.length && !toast.hint) { toast.hint = 1; toast('Gumka pikselowa nie rusza obiektów i zdjęć — przełącz tryb na „Obiekty”'); }
                pts = [[startX, startY]]; sx = startX; sy = startY;
                strokePath();
            } else if (currentTool === 'spray') {
                spray();
                sprayTimer = setInterval(spray, 16); // spray działa też przy trzymaniu w miejscu
            }
        });

        canvas.addEventListener('pointermove', e => {
            if (drag || (currentTool === 'pen' && penPts.length)) {
                const p = getPos(e);
                curX = p.x; curY = p.y;
                vecMove();
                return;
            }
            if (textDrag) {
                const p = getPos(e);
                curX = p.x; curY = p.y;
                Object.assign(dragBox.style, {
                    display: 'block',
                    left: Math.min(startX, curX) / W * 100 + '%', top: Math.min(startY, curY) / H * 100 + '%',
                    width: Math.abs(curX - startX) / W * 100 + '%', height: Math.abs(curY - startY) / H * 100 + '%'
                });
                return;
            }
            if (!painting) return;
            const p = getPos(e);
            curX = p.x; curY = p.y;
            if (currentTool === 'eraser' && $('emode').value === 'object') eraseObjects();
            else if (FREEHAND.includes(currentTool)) {
                const sm = $('smooth').value / 100; // wygładzanie = opóźnione podążanie za kursorem
                sx += (curX - sx) * (1 - sm); sy += (curY - sy) * (1 - sm);
                pts.push([sx, sy]);
                strokePath();
            } else if (currentTool !== 'spray') {
                drawShape();
            }
        });

        function finish() {
            if (drag) { vecUp(); return; }
            if (textDrag) {
                textDrag = false;
                dragBox.style.display = 'none';
                let x = Math.min(startX, curX), y = Math.min(startY, curY);
                let w = Math.abs(curX - startX), h = Math.abs(curY - startY);
                if (w < 30 || h < 20) { // zwykłe kliknięcie → ramka domyślna
                    x = Math.min(startX, W - 60); y = startY;
                    w = Math.min(300, W - x);
                    h = Math.max(30, Math.min(fontSize * 1.25 * 3, H - y));
                }
                openTextBox(x, y, w, h);
                return;
            }
            if (!painting) return;
            painting = false;
            clearInterval(sprayTimer);
            resetStyle();
        }
        canvas.addEventListener('pointerup', finish);
        canvas.addEventListener('pointercancel', finish);

        /* ---------- Ramka tekstowa ---------- */
        function styleTextBox(ta) {
            ta.style.color = color;
            ta.style.fontFamily = fontFamily;
            ta.style.fontWeight = fontBold ? 'bold' : 'normal';
            ta.style.fontStyle = fontItalic ? 'italic' : 'normal';
            ta.style.setProperty('--fs', fontSize);
        }

        function openTextBox(x, y, w, h) {
            const ta = document.createElement('textarea');
            ta.className = 'text-box';
            ta.spellcheck = false;
            ta.style.left = x / W * 100 + '%';
            ta.style.top = y / H * 100 + '%';
            ta.style.width = w / W * 100 + '%';
            ta.style.height = h / H * 100 + '%';
            styleTextBox(ta);
            ta.addEventListener('keydown', e => {
                if (e.key === 'Escape') { e.preventDefault(); cancelText(); }
                else if (e.key === 'Enter' && (e.ctrlKey || e.metaKey)) { e.preventDefault(); commitText(); }
            });
            stack.appendChild(ta);
            activeBox = { el: ta };
            ta.focus();
        }

        function cancelText() {
            if (!activeBox) return;
            activeBox.el.remove();
            activeBox = null;
        }

        function wrapText(text, maxW) {
            const lines = [];
            text.split('\n').forEach(para => {
                let line = '';
                para.split(' ').forEach(word => {
                    const test = line ? line + ' ' + word : word;
                    if (ctx.measureText(test).width <= maxW) { line = test; return; }
                    if (line) lines.push(line);
                    line = '';
                    for (const ch of word) { // zbyt długie słowo łamiemy znak po znaku
                        if (line && ctx.measureText(line + ch).width > maxW) { lines.push(line); line = ch; }
                        else line += ch;
                    }
                });
                lines.push(line);
            });
            return lines;
        }

        function commitText() {
            if (!activeBox) return;
            const ta = activeBox.el;
            activeBox = null;
            const text = ta.value;
            const sr = stack.getBoundingClientRect(), r = ta.getBoundingClientRect();
            const k = W / sr.width;
            const x = (r.left - sr.left) * k, y = (r.top - sr.top) * k, w = r.width * k;
            ta.remove();
            if (!text.trim()) return;

            saveState();
            ctx.save();
            ctx.globalCompositeOperation = 'source-over';
            ctx.shadowBlur = 0;
            ctx.fillStyle = color;
            ctx.font = (fontItalic ? 'italic ' : '') + (fontBold ? 'bold ' : '') + fontSize + 'px ' + fontFamily;
            ctx.textBaseline = 'middle';
            ctx.textAlign = 'left';
            const lh = fontSize * 1.25;
            wrapText(text, w).forEach((line, i) => ctx.fillText(line, x, y + lh * (i + 0.5)));
            ctx.restore();
        }

        document.getElementById('textFont').addEventListener('change', e => {
            fontFamily = e.target.value;
            if (activeBox) { styleTextBox(activeBox.el); activeBox.el.focus(); }
        });
        document.getElementById('textSize').addEventListener('input', e => {
            const v = parseInt(e.target.value, 10);
            if (!v) return;
            fontSize = Math.min(200, Math.max(8, v));
            if (activeBox) styleTextBox(activeBox.el);
        });
        document.getElementById('btn-bold').addEventListener('click', e => {
            fontBold = !fontBold;
            e.currentTarget.classList.toggle('active', fontBold);
            if (activeBox) { styleTextBox(activeBox.el); activeBox.el.focus(); }
        });
        document.getElementById('btn-italic').addEventListener('click', e => {
            fontItalic = !fontItalic;
            e.currentTarget.classList.toggle('active', fontItalic);
            if (activeBox) { styleTextBox(activeBox.el); activeBox.el.focus(); }
        });
        document.getElementById('btn-text-ok').addEventListener('click', commitText);

        /* ---------- Siatka i układ kartezjański (osobna warstwa) ---------- */
        function drawOverlay() {
            octx.clearRect(0, 0, W, H);
            if (showGrid) {
                octx.strokeStyle = 'rgba(0, 0, 0, 0.1)';
                octx.lineWidth = 1;
                octx.beginPath();
                for (let x = 0; x <= W; x += SCALE) { octx.moveTo(x + 0.5, 0); octx.lineTo(x + 0.5, H); }
                for (let y = 0; y <= H; y += SCALE) { octx.moveTo(0, y + 0.5); octx.lineTo(W, y + 0.5); }
                octx.stroke();
            }
            if (showCartesian) {
                const cx = W / 2, cy = H / 2;
                octx.strokeStyle = 'rgba(231, 76, 60, 0.8)';
                octx.fillStyle = '#c0392b';
                octx.lineWidth = 2;
                octx.beginPath();
                octx.moveTo(0, cy); octx.lineTo(W, cy);
                octx.moveTo(cx, 0); octx.lineTo(cx, H);
                octx.stroke();
                for (let x = cx % SCALE; x < W; x += SCALE) octx.fillRect(x, cy - 3, 1, 6);
                for (let y = cy % SCALE; y < H; y += SCALE) octx.fillRect(cx - 3, y, 6, 1);
                octx.font = '10px monospace';
                octx.textAlign = 'center';
                for (let i = -20; i <= 20; i += 5) {
                    if (i === 0) continue;
                    octx.fillText(i, cx + i * SCALE, cy + 15);
                }
                octx.textAlign = 'left';
                for (let i = -10; i <= 10; i += 5) {
                    const py = cy - i * SCALE;
                    if (i === 0 || py < 10 || py > H - 4) continue;
                    octx.fillText(i, cx + 8, py + 3);
                }
                octx.fillText('0', cx + 6, cy + 14);
                octx.fillText('x', W - 12, cy - 8);
                octx.fillText('y', cx + 8, 12);
            }
        }
        function toggleGrid() {
            showGrid = !showGrid;
            document.getElementById('btn-grid').classList.toggle('active', showGrid);
            drawOverlay();
        }
        function toggleCartesian() {
            showCartesian = !showCartesian;
            document.getElementById('btn-cartesian').classList.toggle('active', showCartesian);
            drawOverlay();
        }

        /* ---------- Wykres funkcji ---------- */
        function commitFunctionToCanvas() {
            commitText();
            if (!showCartesian) toggleCartesian(); // włączamy układ automatycznie

            const type = document.getElementById('funcType').value;
            const a = parseFloat(document.getElementById('paramA').value) || 0;
            const b = parseFloat(document.getElementById('paramB').value) || 0;
            const c = parseFloat(document.getElementById('paramC').value) || 0;
            const cx = W / 2, cy = H / 2;

            saveState();
            ctx.save();
            ctx.strokeStyle = color;
            ctx.lineWidth = size;
            ctx.globalCompositeOperation = 'source-over';
            ctx.shadowBlur = 0;
            ctx.beginPath();

            let first = true;
            for (let px = 0; px <= W; px += 0.5) {
                const x = (px - cx) / SCALE;
                let y;
                if (type === 'linear') y = a * x + b;
                else if (type === 'quadratic') y = a * x * x + b * x + c;
                else if (type === 'sine') y = a * Math.sin(b * x) + c;
                else if (type === 'log') y = x > 0 ? a * Math.log10(x) + b : NaN;
                else y = x > 0 ? a * Math.log(x) + b : NaN;

                const py = cy - y * SCALE;
                if (!isFinite(py) || Math.abs(py) > 1e5) { first = true; continue; }
                if (first) { ctx.moveTo(px, py); first = false; } else ctx.lineTo(px, py);
            }
            ctx.stroke(); // części poza płótnem są po prostu przycięte
            ctx.restore();
        }

        /* ---------- Kubełek (wypełnianie liniami skanowania) ---------- */
        function floodFill(sx, sy, fc) {
            const img = ctx.getImageData(0, 0, W, H), d = img.data;
            const i0 = (sy * W + sx) * 4;
            const t = [d[i0], d[i0 + 1], d[i0 + 2], d[i0 + 3]];
            const TOL = +$('tol').value, fa = opacity();
            if (fa === 1 && t[3] === 255 && Math.abs(t[0] - fc[0]) <= 2 && Math.abs(t[1] - fc[1]) <= 2 && Math.abs(t[2] - fc[2]) <= 2) return;

            const match = i => Math.abs(d[i] - t[0]) <= TOL && Math.abs(d[i + 1] - t[1]) <= TOL &&
                               Math.abs(d[i + 2] - t[2]) <= TOL && Math.abs(d[i + 3] - t[3]) <= TOL;
            const seen = new Uint8Array(W * H);
            const stack = [[sx, sy]];

            while (stack.length) {
                let [x, y] = stack.pop();
                if (seen[y * W + x] || !match((y * W + x) * 4)) continue;
                while (x > 0 && !seen[y * W + x - 1] && match((y * W + x - 1) * 4)) x--;
                let up = false, down = false;
                while (x < W && !seen[y * W + x] && match((y * W + x) * 4)) {
                    const i = (y * W + x) * 4;
                    const oa = d[i + 3] / 255, na = fa + oa * (1 - fa); // mieszanie z istniejącym kolorem przy kryciu < 100%
                    d[i] = (fc[0] * fa + d[i] * oa * (1 - fa)) / na; d[i + 1] = (fc[1] * fa + d[i + 1] * oa * (1 - fa)) / na;
                    d[i + 2] = (fc[2] * fa + d[i + 2] * oa * (1 - fa)) / na; d[i + 3] = na * 255;
                    seen[y * W + x] = 1;
                    if (y > 0) {
                        const ok = !seen[(y - 1) * W + x] && match(((y - 1) * W + x) * 4);
                        if (ok && !up) { stack.push([x, y - 1]); up = true; } else if (!ok) up = false;
                    }
                    if (y < H - 1) {
                        const ok = !seen[(y + 1) * W + x] && match(((y + 1) * W + x) * 4);
                        if (ok && !down) { stack.push([x, y + 1]); down = true; } else if (!ok) down = false;
                    }
                    x++;
                }
            }
            saveState(); // kontekst jeszcze niezmieniony, więc zapisuje stan sprzed wypełnienia
            ctx.putImageData(img, 0, 0);
        }

        function hexToRgb(hex) {
            const n = parseInt(hex.slice(1), 16);
            return [(n >> 16) & 255, (n >> 8) & 255, n & 255, 255];
        }
        function rgbToHex(r, g, b) { return '#' + ((1 << 24) + (r << 16) + (g << 8) + b).toString(16).slice(1); }

        function clearCanvas() {
            commitText();
            saveState();
            ctx.clearRect(0, 0, W, H); // siatka/układ są na osobnej warstwie, więc zostają
            objs = []; sel = null; renderVec();
        }

        /* ---------- Zapis i otwieranie ---------- */
        function exportBlob() {
            const out = document.createElement('canvas');
            out.width = W; out.height = H;
            const o = out.getContext('2d');
            o.fillStyle = '#ffffff';
            o.fillRect(0, 0, W, H);
            renderVec(false);
            o.drawImage(canvas, 0, 0);
            o.drawImage(vecCanvas, 0, 0);
            renderVec();
            o.drawImage(overlay, 0, 0);
            return new Promise(res => out.toBlob(res, 'image/png'));
        }

        function downloadBlob(blob, name = 'rysunek.png') {
            const a = document.createElement('a');
            a.href = URL.createObjectURL(blob);
            a.download = name;
            document.body.appendChild(a);
            a.click();
            a.remove();
            setTimeout(() => URL.revokeObjectURL(a.href), 1000);
            toast('Pobrano plik ' + name);
        }

        async function saveToFolder() {
            commitText();
            const blob = await exportBlob();
            try {
                if (window.showSaveFilePicker) {
                    if (!fileHandle) {
                        fileHandle = await window.showSaveFilePicker({
                            suggestedName: 'rysunek.png',
                            types: [{ description: 'Obraz PNG', accept: { 'image/png': ['.png'] } }]
                        });
                    }
                    const w = await fileHandle.createWritable();
                    await w.write(blob);
                    await w.close();
                    toast('Zapisano pomyślnie!');
                    return;
                }
            } catch (err) {
                if (err.name === 'AbortError') return;
                fileHandle = null; // inny błąd (np. brak uprawnień) → pobieranie zwykłym plikiem
            }
            downloadBlob(blob);
        }

        async function loadImageFile(file) {
            commitText();
            try {
                const bmp = await createImageBitmap(file);
                const s = Math.min(1, W / bmp.width, H / bmp.height); // dopasuj, nie obcinaj
                const w = bmp.width * s, h = bmp.height * s;
                saveState();
                ctx.clearRect(0, 0, W, H);
                ctx.drawImage(bmp, (W - w) / 2, (H - h) / 2, w, h);
            } catch (err) {
                toast('Nie udało się otworzyć pliku');
            }
        }

        async function openFromFolder() {
            try {
                if (window.showOpenFilePicker) {
                    const [h] = await window.showOpenFilePicker({
                        types: [{ description: 'Obrazy', accept: { 'image/*': ['.png', '.jpg', '.jpeg', '.webp'] } }]
                    });
                    fileHandle = null; // zapis nie nadpisze po cichu otwartego pliku
                    await loadImageFile(await h.getFile());
                    return;
                }
            } catch (err) {
                if (err.name === 'AbortError') return;
            }
            document.getElementById('fileInput').click();
        }
        document.getElementById('fileInput').addEventListener('change', e => {
            if (e.target.files[0]) loadImageFile(e.target.files[0]);
            e.target.value = '';
        });

        /* ---------- Przyciski i skróty ---------- */
        document.getElementById('btn-undo').addEventListener('click', undo);
        document.getElementById('btn-redo').addEventListener('click', redo);
        document.getElementById('btn-grid').addEventListener('click', toggleGrid);
        document.getElementById('btn-cartesian').addEventListener('click', toggleCartesian);
        document.getElementById('btn-clear').addEventListener('click', clearCanvas);
        document.getElementById('btn-save').addEventListener('click', saveToFolder);
        document.getElementById('btn-open').addEventListener('click', openFromFolder);
        document.getElementById('btn-func').addEventListener('click', commitFunctionToCanvas);

        window.addEventListener('keydown', e => {
            if (/^(INPUT|SELECT|TEXTAREA)$/.test(e.target.tagName)) return;
            if (!(e.ctrlKey || e.metaKey)) return;
            const k = e.key.toLowerCase();
            if (k === 'z' && !e.shiftKey) { e.preventDefault(); undo(); }
            else if (k === 'y' || (k === 'z' && e.shiftKey)) { e.preventDefault(); redo(); }
        });

        /* ---------- Grafika wektorowa ---------- */
        function curStyle() {
            const fm = $('fillMode').value;
            return { stroke: color, fill: fm === 'stroke' ? null : $('fillColor').value, sw: fm === 'fill' ? 0 : size, op: opacity(), dash: $('dashSel').value, cap: $('capSel').value, r: +$('radius').value };
        }
        function shapeObj(t, x0, y0, x1, y1) {
            const st = curStyle(), w = x1 - x0, h = y1 - y0, mx = x0 + w / 2, my = y0 + h / 2, sides = +$('sides').value;
            const bb = { x: Math.min(x0, x1), y: Math.min(y0, y1), w: Math.abs(w), h: Math.abs(h) };
            const np = a => a.map(([u, v]) => [x0 + u * w, y0 + v * h]); // punkty w układzie 0..1 ramki
            const poly = (pp, smooth = false) => Object.assign({ t: 'poly', pts: pp, closed: true, smooth }, st);
            switch (t) {
                case 'line': st.fill = null; st.sw = size; return Object.assign({ t: 'poly', pts: [[x0, y0], [x1, y1]], closed: false, smooth: false }, st);
                case 'rect': return Object.assign({ t: 'rect' }, bb, st);
                case 'circle': { const r = Math.hypot(w, h); return Object.assign({ t: 'ellipse', x: x0 - r, y: y0 - r, w: 2 * r, h: 2 * r }, st); }
                case 'ellipse': return Object.assign({ t: 'ellipse' }, bb, st);
                case 'triangle': return poly([[x0, y1], [mx, y0], [x1, y1]]);
                case 'rombus': return poly([[mx, y0], [x1, my], [mx, y1], [x0, my]]);
                case 'trapezoid': return poly([[x0 + w * 0.2, y0], [x0 + w * 0.8, y0], [x1, y1], [x0, y1]]);
                case 'parallelogram': return poly(np([[0.25, 0], [1, 0], [0.75, 1], [0, 1]]));
                case 'polygon': case 'star': {
                    const k = t === 'star' ? sides * 2 : sides, pp = [];
                    for (let i = 0; i < k; i++) {
                        const a = -Math.PI / 2 + i * 2 * Math.PI / k, f = t === 'star' && i % 2 ? 0.45 : 1;
                        pp.push([mx + w / 2 * f * Math.cos(a), my + h / 2 * f * Math.sin(a)]);
                    }
                    return poly(pp);
                }
                case 'arrow': return poly(np([[0, 0.35], [0.6, 0.35], [0.6, 0], [1, 0.5], [0.6, 1], [0.6, 0.65], [0, 0.65]]));
                case 'heart': return poly(np([[0.5, 0.28], [0.38, 0.06], [0.15, 0.04], [0.02, 0.28], [0.1, 0.52], [0.5, 0.98], [0.9, 0.52], [0.98, 0.28], [0.85, 0.04], [0.62, 0.06]]), true);
                case 'cross': return poly(np([[1/3, 0], [2/3, 0], [2/3, 1/3], [1, 1/3], [1, 2/3], [2/3, 2/3], [2/3, 1], [1/3, 1], [1/3, 2/3], [0, 2/3], [0, 1/3], [1/3, 1/3]]));
                default: return Object.assign({ t: 'd3', k: t }, bb, st); // bryły 3D
            }
        }
        function shade(hex, s) { // s>0 rozjaśnia, s<0 przyciemnia
            const n = parseInt(hex.slice(1), 16), tg = s < 0 ? 0 : 255, k = Math.abs(s), f = c => Math.round(c + (tg - c) * k);
            return `rgb(${f(n >> 16 & 255)},${f(n >> 8 & 255)},${f(n & 255)})`;
        }
        // Bryły 3D jako zestaw ścian (kolejność = od tyłu do przodu), każda z własnym cieniowaniem
        function geo3d(o) {
            const { x, y, w, h, k } = o, P = a => 'M' + a.map(q => q.join(' ')).join('L') + 'z';
            const E = (cx, cy, rx, ry) => `M${cx - rx} ${cy}a${rx} ${ry} 0 1 0 ${2 * rx} 0a${rx} ${ry} 0 1 0 ${-2 * rx} 0z`;
            const rx = w / 2, e = Math.min(h * 0.15, w * 0.25);
            if (k === 'cube') {
                const d = Math.min(w, h) * 0.3;
                return [{ d: P([[x, y + d], [x + w - d, y + d], [x + w - d, y + h], [x, y + h]]), s: 0 },
                        { d: P([[x, y + d], [x + d, y], [x + w, y], [x + w - d, y + d]]), s: 0.35 },
                        { d: P([[x + w - d, y + d], [x + w, y], [x + w, y + h - d], [x + w - d, y + h]]), s: -0.3 }];
            }
            if (k === 'cylinder') return [{ d: `M${x} ${y + e}V${y + h - e}A${rx} ${e} 0 0 0 ${x + w} ${y + h - e}V${y + e}z`, s: -0.15 }, { d: E(x + rx, y + e, rx, e), s: 0.3 }];
            if (k === 'cone') return [{ d: `M${x + rx} ${y}L${x + w} ${y + h - e}A${rx} ${e} 0 0 1 ${x} ${y + h - e}z`, s: 0 }];
            if (k === 'pyramid') {
                const A = [x + w * 0.5, y], L = [x, y + h * 0.8], F = [x + w * 0.55, y + h], R = [x + w, y + h * 0.75];
                return [{ d: P([A, L, F]), s: 0.3 }, { d: P([A, F, R]), s: -0.25 }];
            }
            const cx = x + rx, cy = y + h / 2, ry = h / 2; // kula: warstwy rozjaśnienia
            return [{ d: E(cx, cy, rx, ry), s: -0.3 }, { d: E(cx - rx * 0.12, cy - ry * 0.12, rx * 0.8, ry * 0.8), s: -0.1, n: 1 },
                    { d: E(cx - rx * 0.25, cy - ry * 0.25, rx * 0.55, ry * 0.55), s: 0.15, n: 1 }, { d: E(cx - rx * 0.35, cy - ry * 0.35, rx * 0.25, ry * 0.25), s: 0.5, n: 1 }];
        }
                // Jedna definicja ścieżki (SVG "d") służy do rysowania, trafiania myszą i eksportu SVG
        function pathD(o) {
            if (o.t === 'rect' && o.r > 0) {
                const r = Math.min(o.r, o.w / 2, o.h / 2), w2 = o.w - 2 * r, h2 = o.h - 2 * r;
                return `M${o.x + r} ${o.y}h${w2}a${r} ${r} 0 0 1 ${r} ${r}v${h2}a${r} ${r} 0 0 1 ${-r} ${r}h${-w2}a${r} ${r} 0 0 1 ${-r} ${-r}v${-h2}a${r} ${r} 0 0 1 ${r} ${-r}z`;
            }
            if (o.t === 'rect' || o.t === 'img' || o.t === 'd3') return `M${o.x} ${o.y}h${o.w}v${o.h}h${-o.w}z`;
            if (o.t === 'ellipse') { const rx = o.w / 2, ry = o.h / 2; return `M${o.x} ${o.y + ry}a${rx} ${ry} 0 1 0 ${o.w} 0a${rx} ${ry} 0 1 0 ${-o.w} 0z`; }
            const p = o.pts, n = p.length, m = (a, b) => [(a[0] + b[0]) / 2, (a[1] + b[1]) / 2], j = q => q.join(' ');
            let d;
            if (!o.smooth || n < 3) d = 'M' + p.map(j).join('L');
            else if (o.closed) { d = 'M' + j(m(p[n - 1], p[0])); for (let i = 0; i < n; i++) d += 'Q' + j(p[i]) + ' ' + j(m(p[i], p[(i + 1) % n])); }
            else { d = 'M' + j(p[0]); for (let i = 1; i < n - 1; i++) d += 'Q' + j(p[i]) + ' ' + j(m(p[i], p[i + 1])); d += 'L' + j(p[n - 1]); }
            return d + (o.closed ? 'z' : '');
        }
        function bbox(o) {
            if (o.t !== 'poly') return { x: o.x, y: o.y, w: o.w, h: o.h };
            const xs = o.pts.map(q => q[0]), ys = o.pts.map(q => q[1]), x = Math.min(...xs), y = Math.min(...ys);
            return { x, y, w: Math.max(...xs) - x, h: Math.max(...ys) - y };
        }
        const corners = b => [[b.x, b.y], [b.x + b.w, b.y], [b.x, b.y + b.h], [b.x + b.w, b.y + b.h]];
        // Przekształca współrzędne obiektu (przesunięcie i skalowanie)
        function xf(o, fx, fy) {
            if (o.t === 'poly') o.pts = o.pts.map(([x, y]) => [fx(x), fy(y)]);
            else { const x0 = o.x, y0 = o.y; o.x = fx(x0); o.y = fy(y0); o.w = fx(x0 + o.w) - o.x; o.h = fy(y0 + o.h) - o.y; }
        }
        function drawObj(c, o) {
            c.save();
            c.globalAlpha = o.op;
            if (o.t === 'img') c.drawImage(imgStore[o.im], o.x, o.y, o.w, o.h);
            else {
                const d3 = o.t === 'd3', parts = d3 ? geo3d(o) : [{ d: pathD(o), s: 0 }];
                parts.forEach(pt => {
                    const pa = new Path2D(pt.d);
                    if (o.fill) { c.fillStyle = d3 ? shade(o.fill, pt.s) : o.fill; c.fill(pa); }
                    if (o.sw > 0 && !pt.n) {
                        c.strokeStyle = o.stroke; c.lineWidth = o.sw; c.lineCap = o.cap || 'round';
                        c.lineJoin = c.lineCap === 'square' ? 'miter' : 'round';
                        c.setLineDash(dashFor(o.dash, o.sw)); c.stroke(pa);
                    }
                });
            }
            c.restore();
        }
                function renderVec(ui = true) {
            vctx.clearRect(0, 0, W, H);
            objs.forEach(o => drawObj(vctx, o));
            if (vecTemp) drawObj(vctx, vecTemp);
            if (!ui) return;
            vctx.save();
            if (penPts.length) {
                drawObj(vctx, Object.assign({ t: 'poly', pts: [...penPts, [curX, curY]], closed: false, smooth: $('smoothPen').checked }, curStyle(), { fill: null, sw: size }));
                vctx.fillStyle = '#0077ff';
                penPts.forEach(([x, y]) => { vctx.beginPath(); vctx.arc(x, y, 3.5, 0, 7); vctx.fill(); });
            }
            if (sel !== null && objs[sel]) {
                const o = objs[sel], b = bbox(o);
                vctx.strokeStyle = '#0077ff'; vctx.lineWidth = 1; vctx.fillStyle = '#fff';
                vctx.setLineDash([5, 4]); vctx.strokeRect(b.x, b.y, b.w, b.h); vctx.setLineDash([]);
                corners(b).forEach(([x, y]) => { vctx.fillRect(x - 4, y - 4, 8, 8); vctx.strokeRect(x - 4, y - 4, 8, 8); });
                if (o.t === 'poly') o.pts.forEach(([x, y]) => { vctx.beginPath(); vctx.arc(x, y, 4, 0, 7); vctx.fill(); vctx.stroke(); });
            }
            vctx.restore();
        }
        function hit(o, p) {
            const b = bbox(o);
            if (o.t === 'img' || o.t === 'd3') return p.x >= b.x && p.x <= b.x + b.w && p.y >= b.y && p.y <= b.y + b.h;
            const pa = new Path2D(pathD(o));
            vctx.save(); vctx.lineWidth = Math.max(o.sw, 10);
            const r = vctx.isPointInStroke(pa, p.x, p.y) || (o.fill && vctx.isPointInPath(pa, p.x, p.y));
            vctx.restore();
            return !!r;
        }
        function syncControls() {
            const o = objs[sel];
            if (!o) return;
            $('opacity').value = o.op * 100; refreshLabels();
            if (o.t === 'img') return;
            color = o.stroke; colorPicker.value = color;
            if (o.fill) $('fillColor').value = o.fill;
            $('fillMode').value = o.fill ? (o.sw > 0 ? 'both' : 'fill') : 'stroke';
            if (o.sw > 0) { size = o.sw; $('brushSize').value = size; sizeVal.textContent = size + 'px'; }
            $('dashSel').value = o.dash; $('capSel').value = o.cap || 'round';
        }
        function selectDown(e, p) {
            canvas.setPointerCapture(e.pointerId);
            const near = q => Math.hypot(q[0] - p.x, q[1] - p.y) < 8;
            if (sel !== null && objs[sel]) {
                const o = objs[sel], b = bbox(o), cs = corners(b);
                const ni = o.t === 'poly' ? o.pts.findIndex(near) : -1;
                if (ni >= 0) { saveState(); drag = { k: 'node', i: ni }; return; }
                const ci = cs.findIndex(near);
                if (ci >= 0) { saveState(); drag = { k: 'resize', anchor: cs[3 - ci], orig: JSON.parse(JSON.stringify(o)), ob: b }; return; }
            }
            sel = null;
            for (let i = objs.length - 1; i >= 0; i--) if (hit(objs[i], p)) { sel = i; break; }
            if (sel !== null) { saveState(); drag = { k: 'move', lx: p.x, ly: p.y }; syncControls(); }
            renderVec();
        }
        function vecMove() {
            if (!drag) { renderVec(); return; }
            if (drag.k === 'create') vecTemp = shapeObj(currentTool, startX, startY, curX, curY);
            else if (drag.k === 'move') { const dx = curX - drag.lx, dy = curY - drag.ly; drag.lx = curX; drag.ly = curY; xf(objs[sel], x => x + dx, y => y + dy); }
            else if (drag.k === 'node') objs[sel].pts[drag.i] = [curX, curY];
            else {
                const [ax, ay] = drag.anchor, ob = drag.ob;
                const nx = Math.min(ax, curX), ny = Math.min(ay, curY), nw = Math.max(Math.abs(curX - ax), 4), nh = Math.max(Math.abs(curY - ay), 4);
                const kx = ob.w ? nw / ob.w : 1, ky = ob.h ? nh / ob.h : 1;
                const o = JSON.parse(JSON.stringify(drag.orig));
                xf(o, x => nx + (x - ob.x) * kx, y => ny + (y - ob.y) * ky);
                objs[sel] = o;
            }
            renderVec();
        }
        function vecUp() {
            if (drag.k === 'create' && Math.hypot(curX - startX, curY - startY) > 3) { saveState(); objs.push(vecTemp); }
            vecTemp = null; drag = null;
            renderVec();
        }
        function penClick() {
            if (penPts.length > 2 && Math.hypot(penPts[0][0] - curX, penPts[0][1] - curY) < 10) { finishPen(true); return; }
            penPts.push([curX, curY]);
            renderVec();
        }
        function finishPen(closed) {
            const pp = penPts; penPts = [];
            const q = pp.filter((c, i) => !i || Math.hypot(c[0] - pp[i - 1][0], c[1] - pp[i - 1][1]) > 2);
            if (q.length > 1) {
                saveState();
                objs.push(Object.assign({ t: 'poly', pts: q, closed, smooth: $('smoothPen').checked }, curStyle(), closed ? {} : { fill: null, sw: size }));
            }
            renderVec();
        }
        canvas.addEventListener('dblclick', () => { if (currentTool === 'pen') finishPen(false); });

        function updateSel() {
            if (sel === null || currentTool !== 'select' || !objs[sel]) return;
            if (!updateSel.t) saveState(); // jeden punkt cofania na serię zmian
            clearTimeout(updateSel.t); updateSel.t = setTimeout(() => updateSel.t = 0, 800);
            const o = objs[sel], st = curStyle(), open = o.t === 'poly' && !o.closed;
            if (o.t === 'img') o.op = st.op;
            else Object.assign(o, { stroke: st.stroke, fill: open ? null : st.fill, sw: open ? size : st.sw, op: st.op, dash: st.dash, cap: st.cap, r: st.r });
            renderVec();
        }
        ['brushSize', 'colorPicker', 'fillColor', 'fillMode', 'dashSel', 'opacity', 'capSel', 'radius'].forEach(id => $(id).addEventListener('input', updateSel));

        function delSel() { if (sel === null) return; saveState(); objs.splice(sel, 1); sel = null; renderVec(); }
        function dupSel() {
            if (sel === null) return;
            saveState();
            const o = JSON.parse(JSON.stringify(objs[sel]));
            xf(o, x => x + 15, y => y + 15);
            objs.push(o); sel = objs.length - 1; renderVec();
        }
        function order(dir) {
            if (sel === null) return;
            saveState();
            const [o] = objs.splice(sel, 1);
            sel = Math.max(0, Math.min(objs.length, sel + dir));
            objs.splice(sel, 0, o); renderVec();
        }
        function flatten() { saveState(); objs.forEach(o => drawObj(ctx, o)); objs = []; sel = null; renderVec(); toast('Obiekty wektorowe wtopione w raster'); }

        function exportSVG() {
            if (!objs.length) { toast('Brak obiektów wektorowych'); return; }
            const body = objs.map(o => {
                const op = o.op < 1 ? ` opacity="${o.op}"` : '';
                if (o.t === 'img') {
                    const b = imgStore[o.im], c = document.createElement('canvas');
                    c.width = b.width; c.height = b.height; c.getContext('2d').drawImage(b, 0, 0);
                    return `<image x="${o.x}" y="${o.y}" width="${o.w}" height="${o.h}" preserveAspectRatio="none" href="${c.toDataURL('image/png')}"${op}/>`;
                }
                const da = dashFor(o.dash, o.sw).join(' '), d3 = o.t === 'd3';
                const parts = d3 ? geo3d(o) : [{ d: pathD(o), s: 0 }];
                return parts.map(pt => `<path d="${pt.d}" fill="${o.fill ? (d3 ? shade(o.fill, pt.s) : o.fill) : 'none'}" stroke="${o.sw > 0 && !pt.n ? o.stroke : 'none'}" stroke-width="${o.sw}" stroke-linejoin="round" stroke-linecap="${o.cap || 'round'}"${da ? ` stroke-dasharray="${da}"` : ''}${op}/>`).join('');
            }).join('\n');
            const svg = `<svg xmlns="http://www.w3.org/2000/svg" width="${W}" height="${H}" viewBox="0 0 ${W} ${H}">\n<rect width="100%" height="100%" fill="#fff"/>\n${body}\n</svg>`;
            downloadBlob(new Blob([svg], { type: 'image/svg+xml' }), 'rysunek.svg');
        }

        /* ---------- Zdjęcia (obiekty, które można przesuwać i skalować) ---------- */
        async function addPhotos(files) {
            commitText();
            setTool('select');
            for (const f of files) {
                if (!f.type.startsWith('image/')) continue;
                try {
                    const bmp = await createImageBitmap(f);
                    const k = Math.min(1, W * 0.6 / bmp.width, H * 0.8 / bmp.height), w = bmp.width * k, h = bmp.height * k;
                    saveState();
                    imgStore.push(bmp);
                    objs.push({ t: 'img', im: imgStore.length - 1, x: (W - w) / 2, y: (H - h) / 2, w, h, op: 1 });
                    sel = objs.length - 1;
                } catch (err) { toast('Nie udało się wczytać zdjęcia'); }
            }
            renderVec();
        }
        $('btn-photo').addEventListener('click', () => $('photoInput').click());
        $('photoInput').addEventListener('change', e => { addPhotos([...e.target.files]); e.target.value = ''; });
        stack.addEventListener('dragover', e => e.preventDefault());
        stack.addEventListener('drop', e => { e.preventDefault(); addPhotos([...e.dataTransfer.files]); });
        window.addEventListener('paste', e => {
            if (/^(INPUT|TEXTAREA)$/.test(e.target.tagName)) return;
            const fs = [...(e.clipboardData ? e.clipboardData.files : [])].filter(f => f.type.startsWith('image/'));
            if (fs.length) { e.preventDefault(); addPhotos(fs); }
        });

        /* ---------- Raster: filtry i odbicia ---------- */
        function rasterCopy() {
            const t = document.createElement('canvas');
            t.width = W; t.height = H;
            t.getContext('2d').drawImage(canvas, 0, 0);
            return t;
        }
        function applyFilter() {
            commitText(); saveState();
            const t = rasterCopy();
            ctx.clearRect(0, 0, W, H);
            ctx.filter = $('filterSel').value;
            ctx.drawImage(t, 0, 0);
            ctx.filter = 'none';
        }
        function flip(horizontal) {
            commitText(); saveState();
            const t = rasterCopy();
            ctx.save();
            ctx.clearRect(0, 0, W, H);
            if (horizontal) { ctx.translate(W, 0); ctx.scale(-1, 1); } else { ctx.translate(0, H); ctx.scale(1, -1); }
            ctx.drawImage(t, 0, 0);
            ctx.restore();
        }

        $('btn-filter').addEventListener('click', applyFilter);
        $('btn-fliph').addEventListener('click', () => flip(true));
        $('btn-flipv').addEventListener('click', () => flip(false));
        $('btn-dup').addEventListener('click', dupSel);
        $('btn-del').addEventListener('click', delSel);
        $('btn-up').addEventListener('click', () => order(1));
        $('btn-down').addEventListener('click', () => order(-1));
        $('btn-flat').addEventListener('click', flatten);
        $('btn-svg').addEventListener('click', exportSVG);
        document.querySelectorAll('input[data-out]').forEach(r => r.addEventListener('input', refreshLabels));
        window.addEventListener('keydown', e => {
            if (/^(INPUT|SELECT|TEXTAREA)$/.test(e.target.tagName)) return;
            if (e.key === 'Enter' && penPts.length) finishPen(false);
            else if (e.key === 'Escape') { penPts = []; sel = null; renderVec(); }
            else if ((e.key === 'Delete' || e.key === 'Backspace') && sel !== null) { e.preventDefault(); delSel(); }
            else if (e.key === '[' || e.key === ']') { // szybka zmiana rozmiaru narzędzia
                const k = keyOf(currentTool);
                if (!SHOW[k].includes('size')) return;
                const st = size >= 50 ? 10 : size >= 10 ? 5 : 1;
                size = Math.max(1, Math.min(+$('brushSize').max, size + (e.key === ']' ? st : -st)));
                $('brushSize').value = size; prof[k].size = size; sizeVal.textContent = size + 'px'; refreshLabels();
            }
        });

        /* ---------- Gumka obiektów i podgląd rozmiaru ---------- */
        function eraseObjects() {
            const r = size / 2, offs = [[0, 0], [r, 0], [-r, 0], [0, r], [0, -r]];
            for (let i = objs.length - 1; i >= 0; i--)
                if (offs.some(([dx, dy]) => hit(objs[i], { x: curX + dx, y: curY + dy }))) objs.splice(i, 1);
            sel = null; renderVec();
        }
        const ring = $('ring');
        canvas.addEventListener('pointermove', e => {
            if (!['pencil', 'brush', 'spray', 'eraser'].includes(currentTool)) { ring.style.display = 'none'; return; }
            const p = getPos(e);
            ring.style.display = 'block';
            ring.style.setProperty('--d', currentTool === 'spray' ? size * 2 : size);
            ring.style.left = p.x / W * 100 + '%'; ring.style.top = p.y / H * 100 + '%';
            ring.style.borderRadius = currentTool === 'eraser' && $('eshape').value === 'square' ? '0' : '50%';
        });
        canvas.addEventListener('pointerleave', () => { ring.style.display = 'none'; });

        /* ---------- Osobny profil ustawień dla każdego narzędzia ---------- */
        const CTRL = { size: 'brushSize', opacity: 'opacity', hardness: 'hardness', smooth: 'smooth', cap: 'capSel', dash: 'dashSel', fillMode: 'fillMode',
                       density: 'density', tol: 'tol', avg: 'avg', eshape: 'eshape', emode: 'emode', radius: 'radius', sides: 'sides' };
        const SHOW = {
            pencil: ['size', 'opacity', 'smooth', 'cap', 'dash'],
            brush: ['size', 'opacity', 'hardness', 'smooth', 'cap', 'dash'],
            spray: ['size', 'opacity', 'density'],
            eraser: ['size', 'opacity', 'hardness', 'smooth', 'eshape', 'emode'],
            fill: ['tol', 'opacity'], picker: ['avg'], text: [],
            shape: ['size', 'opacity', 'cap', 'dash', 'fillMode', 'radius', 'sides']
        };
        const DEF = { size: 5, opacity: 100, hardness: 60, smooth: 0, cap: 'round', dash: 'solid', fillMode: 'stroke', density: 50, tol: 40, avg: 1, eshape: 'round', emode: 'pixel', radius: 0, sides: 5 };
        const prof = {
            pencil: { ...DEF, size: 3 }, brush: { ...DEF, size: 20, hardness: 40, smooth: 25 }, spray: { ...DEF, size: 20 },
            eraser: { ...DEF, size: 30, hardness: 100 }, fill: { ...DEF }, picker: { ...DEF }, text: { ...DEF }, shape: { ...DEF }
        };
        const SIZEMAX = { eraser: 300, brush: 100, spray: 100 };
        const keyOf = t => (SHAPES.includes(t) || t === 'pen' || t === 'select') ? 'shape' : t;

        function refreshLabels() {
            document.querySelectorAll('input[data-out]').forEach(r => { $(r.dataset.out).textContent = r.value + (r.dataset.u ?? '%'); });
        }
        function loadProfile() {
            const k = keyOf(currentTool), pr = prof[k];
            $('brushSize').max = SIZEMAX[k] || 50;
            for (const n in CTRL) $(CTRL[n]).value = pr[n];
            size = +pr.size;
            sizeVal.textContent = size + 'px';
            sizeVal.style.visibility = SHOW[k].includes('size') ? 'visible' : 'hidden';
            document.querySelectorAll('[data-p]').forEach(r => { r.style.display = SHOW[k].includes(r.dataset.p) ? '' : 'none'; });
            $('optTitle').textContent = 'Ustawienia: ' + (toolNames[currentTool] || '');
            refreshLabels();
        }
        for (const n in CTRL) $(CTRL[n]).addEventListener('input', e => {
            const v = e.target.value;
            prof[keyOf(currentTool)][n] = isNaN(v) ? v : +v;
        });

        drawOverlay();
        renderVec();
        loadProfile();
    </script>
</body>
</html>
