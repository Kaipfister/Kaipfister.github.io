        }

        #ziel {
            width: 50px;
            height: 50px;
            background-color: red;
            position: absolute;
            top: 175px;
            left: 175px;
            border-radius: 50%;
        }

        #logo {
            width: 50px;
            height: 50px;
            background-color: blue;
            position: absolute;
            top: 175px;
            left: 10px;
            border-radius: 50%;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>Kaipfister Spiel</h1>
    <div id="spielbereich">
        <div id="ziel"></div>
        <div id="logo" draggable="true" ondragstart="startDrag(event)"></div>
    </div>

    <script>
        var logo = document.getElementById("logo");
        var ziel = document.getElementById("ziel");

        function startDrag(event) {
            event.dataTransfer.setData("text/plain", event.target.id);
        }

        ziel.addEventListener("dragover", function (event) {
            event.preventDefault();
        });

        ziel.addEventListener("drop", function (event) {
            event.preventDefault();
            var draggedElementId = event.dataTransfer.getData("text/plain");
            if (draggedElementId === "logo") {
                alert("Gewonnen! Du hast das Kaipfister-Logo ins Ziel geworfen!");
            }
        });
    </script>
</body>
</html>
