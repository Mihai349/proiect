# proiect
<!DOCTYPE html>
<html lang="ro">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ceas Digital</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            font-family: Italic sans-serif;
            background-color: #969ba2;
            color: #fdfbfb;
        }
        .cadran {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 40px;
            border: 2px solid #fdfbfb;
            border-radius: 18px;
            background-color: #010101;
            width: 450px;
            box-shadow: 0 8px 4px rgba(0, 0, 0, 0.5);
        }
        .stanga {
            text-align: left;
        }
        .dreapta {
            text-align: right;
            font-size: 2rem;
            color: #61dafb;
        }
        .stanga p {
            margin: 5px 0;
            font-size: 1.2rem;
        }
        .cadran h1 {
            margin: 20px 0;
            font-size: 3rem;
            color: #fdfbfb;
        }
        .cadran p {
            margin:3px 0;
            font-size: 1.2rem;
        }
    </style>
</head>
<body>
    <div class="cadran">
        <div class="stanga">
            <p id="ziua">Ziua săptămânii</p>
            <p id="data">01-01-2025</p>
        </div>
        <div class="dreapta">
            <h1 id="ora">00:00:00</h1>
        </div>
    </div>

    <script>
        function actualizeazaCeas() {
            const zileSaptamana = [
                "Luni", "Marți", "Miercuri", "Joi", "Vineri", "Sâmbătă", "Duminică"
            ];

            const acum = new Date();
            const ora = acum.toLocaleTimeString("ro-RO");
            const data = acum.toLocaleDateString("ro-RO");
            const ziua = zileSaptamana[acum.getDay() - 1] || "Duminică";

            document.getElementById("ora").textContent = ora;
            document.getElementById("ziua").textContent = ` ${ziua}`;
            document.getElementById("data").textContent = ` ${data}`;
        }

        // Actualizare ceas la fiecare secundă
        setInterval(actualizeazaCeas, 1000);

        // Inițializare
        actualizeazaCeas();
    </script>
</body>
</html>
