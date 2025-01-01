<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cricket Player Info</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        header {
            background-color: #4CAF50;
            color: white;
            text-align: center;
            padding: 15px 0;
        }
        .container {
            width: 80%;
            margin: 20px auto;
        }
        input[type="text"] {
            padding: 10px;
            width: 50%;
            margin-bottom: 20px;
            font-size: 16px;
        }
        button {
            padding: 10px 20px;
            background-color: #4CAF50;
            color: white;
            font-size: 16px;
            cursor: pointer;
            border: none;
        }
        .player-info {
            background-color: white;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .player-info p {
            font-size: 18px;
            margin: 5px 0;
        }
    </style>
</head>
<body>

    <header>
        <h1>Cricket Player Information</h1>
    </header>

    <div class="container">
        <input type="text" id="playerName" placeholder="Search Player (e.g., Virat Kohli)">
        <button onclick="getPlayerInfo()">Search</button>

        <div id="playerInfo" class="player-info"></div>
    </div>

    <script>
        const playersData = {
            "Virat Kohli": {
                rank: 1,
                debut: "2008",
                runs: 12000
            },
            "Rohit Sharma": {
                rank: 2,
                debut: "2007",
                runs: 10000
            },
            "Jasprit Bumrah": {
                rank: 5,
                debut: "2016",
                runs: 500
            },
            "MS Dhoni": {
                rank: 3,
                debut: "2004",
                runs: 10000
            }
        };

        function getPlayerInfo() {
            const playerName = document.getElementById('playerName').value.trim();
            const playerInfoDiv = document.getElementById('playerInfo');

            if (playerName && playersData[playerName]) {
                const player = playersData[playerName];
                playerInfoDiv.innerHTML = `
                    <h3>${playerName}</h3>
                    <p><strong>Rank:</strong> ${player.rank}</p>
                    <p><strong>Debut Date:</strong> ${player.debut}</p>
                    <p><strong>Runs Scored:</strong> ${player.runs}</p>
                `;
            } else {
                playerInfoDiv.innerHTML = "<p>No data found for this player.</p>";
            }
        }
    </script>

</body>
</html>
