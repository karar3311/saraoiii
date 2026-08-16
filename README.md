# saraoiii
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>عالم سُرى الفني الفاخر</title>
    <style>
        :root {
            --bg-color: #0f0f13;
            --card-bg: #1a1a24;
            --gold: #d4af37;
            --gold-light: #f3e5ab;
            --text-color: #f1f1f1;
            --pink-accent: #ffb6c1;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            text-align: center;
            padding: 20px;
        }

        header {
            background: linear-gradient(135deg, #1f1f2e, #2d1f3d);
            border: 2px solid var(--gold);
            padding: 40px 20px;
            border-radius: 20px;
            max-width: 800px;
            margin: 0 auto 30px auto;
            box-shadow: 0 10px 30px rgba(212, 175, 55, 0.2);
        }

        h1 {
            color: var(--gold);
            font-size: 2.5rem;
            margin-bottom: 15px;
        }

        .special-message {
            font-size: 1.3rem;
            color: var(--pink-accent);
            line-height: 1.8;
            font-weight: bold;
            background: rgba(255, 182, 193, 0.1);
            padding: 15px;
            border-radius: 10px;
            border-right: 5px solid var(--gold);
            margin-top: 15px;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
        }

        .section {
            background-color: var(--card-bg);
            border: 1px solid #33334d;
            padding: 25px;
            margin-bottom: 25px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
        }

        h2 {
            color: var(--gold);
            margin-bottom: 15px;
            font-size: 1.8rem;
        }

        p {
            color: #b3b3cc;
            margin-bottom: 15px;
        }

        /* Drawing Canvas Styles */
        canvas {
            background-color: #ffffff;
            border-radius: 10px;
            cursor: crosshair;
            box-shadow: 0 4px 10px rgba(0,0,0,0.5);
            max-width: 100%;
        }

        .palette {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin: 15px 0;
        }

        .color-btn {
            width: 35px;
            height: 35px;
            border-radius: 50%;
            border: 2px solid white;
            cursor: pointer;
            transition: transform 0.2s;
        }

        .color-btn:hover {
            transform: scale(1.1);
        }

        /* Number Painting Grid */
        .number-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
            margin-top: 15px;
        }

        .number-box {
            background-color: #2b2b3d;
            border: 2px dashed var(--gold);
            padding: 30px;
            border-radius: 10px;
            font-size: 1.5rem;
            color: var(--gold-light);
            cursor: pointer;
            transition: 0.3s;
        }

        .number-box:hover {
            background-color: var(--gold);
            color: #000;
        }

        .btn-gold {
            background-color: var(--gold);
            color: #000;
            border: none;
            padding: 12px 25px;
            font-size: 1.1rem;
            font-weight: bold;
            border-radius: 25px;
            cursor: pointer;
            transition: 0.3s;
            margin-top: 10px;
        }

        .btn-gold:hover {
            background-color: var(--gold-light);
        }
    </style>
</head>
<body>

    <header>
        <h1>✨ عالم سُرى الفني الفاخر ✨</h1>
        <div class="special-message">
            "يولون حتى لو ميلعبون وياج ولان تحبين الوحده متحبين تلعبين وياهم هذا كلههه بس الجججج"
        </div>
    </header>

    <div class="container">
        
        <!-- قسم التلوين بالأصبع / الرسم الحر -->
        <div class="section">
            <h2>🎨 تلوين سُرى بالأصبع (الرسم الحر)</h2>
            <p>اختاري لونكِ المفضلين وابدعي برسمتكِ الخاصة بكل حرية</p>
            <div class="palette">
                <div class="color-btn" style="background: #ff4d4d;" onclick="setPenColor('#ff4d4d')"></div>
                <div class="color-btn" style="background: #ffb84d;" onclick="setPenColor('#ffb84d')"></div>
                <div class="color-btn" style="background: #4da6ff;" onclick="setPenColor('#4da6ff')"></div>
                <div class="color-btn" style="background: #bf80ff;" onclick="setPenColor('#bf80ff')"></div>
                <div class="color-btn" style="background: #ff80bf;" onclick="setPenColor('#ff80bf')"></div>
                <div class="color-btn" style="background: #d4af37;" onclick="setPenColor('#d4af37')"></div>
            </div>
            <canvas id="paintCanvas" width="400" height="300"></canvas>
            <br>
            <button class="btn-gold" onclick="clearCanvas()">مسح اللوحة</button>
        </div>

        <!-- قسم التلوين بالضغط الرقمي -->
        <div class="section">
            <h2>🔢 تلوين سُرى بالضغط الرقمي</h2>
            <p>اضغطي على الأرقام أدناه لتتلون اللوحة بأجمل الألوان المخصصة لسُرى</p>
            <div class="number-grid">
                <div class="number-box" onclick="colorBox(this, 'رقم 1: لون الذهب الخالص ✨')">1</div>
                <div class="number-box" onclick="colorBox(this, 'رقم 2: لون الهدوء والورد 🌸')">2</div>
                <div class="number-box" onclick="colorBox(this, 'رقم 3: لون الفخامة والسمو 👑')">3</div>
            </div>
            <div id="numResult" style="margin-top: 15px; font-size: 1.2rem; color: var(--gold);"></div>
        </div>

        <!-- القسم الفاخر الأول -->
        <div class="section">
            <h2>💎 معرض سُرى الملكي</h2>
            <p>مساحة خاصة ممتلئة بالهدوء والذوق الرفيع الذي يليق بكِ وحدكِ.</p>
            <div style="font-size: 3rem; margin: 15px 0;">👑 📚 ☕</div>
        </div>

        <!-- القسم الفاخر الثاني -->
        <div class="section">
            <h2>🌸 ركن رسائل سُرى السرية</h2>
            <p>اضغطي الزر أدناه لمعرفة رسالة اليوم الخاصة بكِ</p>
            <button class="btn-gold" onclick="showSecretMessage()">اطبعي رسالة اليوم</button>
            <div id="secretBox" style="margin-top: 15px; font-size: 1.2px; color: var(--pink-accent);"></div>
        </div>

    </div>

    <script>
        // إعدادات اللوحة (التلوين بالأصبع/الماوس)
        const canvas = document.getElementById('paintCanvas');
        const ctx = canvas.getContext('2d');
        let painting = false;
        let penColor = '#d4af37';

        function setPenColor(color) {
            penColor = color;
        }

        canvas.addEventListener('mousedown', (e) => {
            painting = true;
            draw(e);
        });

        canvas.addEventListener('mouseup', () => {
            painting = false;
            ctx.beginPath();
        });

        canvas.addEventListener('mousemove', draw);

        function draw(e) {
            if (!painting) return;
            ctx.lineWidth = 5;
            ctx.lineCap = 'round';
            ctx.strokeStyle = penColor;

            const rect = canvas.getBoundingClientRect();
            ctx.lineTo(e.clientX - rect.left, e.clientY - rect.top);
            ctx.stroke();
            ctx.beginPath();
            ctx.moveTo(e.clientX - rect.left, e.clientY - rect.top);
        }

        function clearCanvas() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
        }

        // تفاعل التلوين بالأرقام
        function colorBox(element, text) {
            element.style.backgroundColor = 'var(--gold)';
            element.style.color = '#000';
            document.getElementById('numResult').innerText = "تم تلوين القطعة بنجاح: " + text;
        }

        // رسائل سرية
        function showSecretMessage() {
            const messages = [
                "سُرى.. أنتِ القوة والهدوء في عالم مليء بالصخب.",
                "لا تقارني نفسكِ بأحد، فأنتِ العالم بأسره وحدكِ.",
                "الجمال الحقيقي هو ما تملوينه بعقلكِ وخصوصيتكِ الرائعة."
            ];
            let randomMsg = messages[Math.floor(Math.random() * messages.length)];
            const box = document.getElementById('secretBox');
            box.style.fontSize = "1.2rem";
            box.innerText = randomMsg;
        }
    </script>
</body>
</html>