<html>
<head>
    <title>Glücksrad</title>
    <style>
        #gluecksrad {
            width: 200px;
            height: 200px;
            background-color: #f0f0f0;
            border: 5px solid #333;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 24px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>Glücksrad</h1>
    <div id="gluecksrad" onclick="drehen()">Drehen</div>

    <script>
        var segmente = ["Gewonnen!", "Verloren", "Nochmal versuchen", "Glück gehabt", "Leider Pech"];

        function drehen() {
            var gluecksrad = document.getElementById("gluecksrad");
            var zufallsIndex = Math.floor(Math.random() * segmente.length);
            var gewinn = segmente[zufallsIndex];
            gluecksrad.innerHTML = gewinn;
        }
    </script>
</body>
</html>
