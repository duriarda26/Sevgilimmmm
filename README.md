<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Beni Seviyor Musun?</title>
    <style>
        /* Minimal ve Pastel Tasarım */
        body {
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #fce4ec; /* Soft pembe */
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            overflow: hidden;
            text-align: center;
        }

        .container {
            padding: 20px;
        }

        h1 {
            color: #d81b60;
            font-size: 2.5rem;
            margin-bottom: 30px;
        }

        .buttons {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 20px;
            height: 100px;
        }

        button {
            padding: 15px 35px;
            font-size: 1.2rem;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: transform 0.2s;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }

        #yesBtn {
            background-color: #ff80ab;
            color: white;
        }

        #noBtn {
            background-color: #fff;
            color: #d81b60;
            position: absolute; /* Kaçması için önemli */
        }

        /* Sonuç Ekranı */
        #result {
            display: none;
            flex-direction: column;
            align-items: center;
        }

        .heart {
            font-size: 100px;
            animation: beat 0.8s infinite;
        }

        @keyframes beat {
            0% { transform: scale(1); }
            50% { transform: scale(1.2); }
            100% { transform: scale(1); }
        }

        h2 {
            color: #ad1457;
            margin-top: 20px;
        }
    </style>
</head>
<body>

    <div class="container" id="questionArea">
        <h1>Beni seviyor musun?</h1>
        <div class="buttons">
            <button id="yesBtn" onclick="showLove()">Evet</button>
            <button id="noBtn" onmouseover="moveButton()" onclick="moveButton()">Hayır</button>
        </div>
    </div>

    <div id="result">
        <div class="heart">❤️</div>
        <h2>Ben de seni seviyorum!</h2>
    </div>

    <script>
        function moveButton() {
            const btn = document.getElementById('noBtn');
            // Butonun ekran dışına taşmaması için sınırlar
            const x = Math.random() * (window.innerWidth - btn.offsetWidth);
            const y = Math.random() * (window.innerHeight - btn.offsetHeight);
            
            btn.style.left = x + 'px';
            btn.style.top = y + 'px';
        }

        function showLove() {
            document.getElementById('questionArea').style.display = 'none';
            document.getElementById('result').style.display = 'flex';
            // Arka planı biraz daha canlandıralım
            document.body.style.backgroundColor = "#f8bbd0";
        }
    </script>
</body>
</html>
