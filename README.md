<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CricGang</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        body {
            font-family: Arial, sans-serif;
        }
        .hero-section {
            background: linear-gradient(to right, #2c3e50, #3498db);
            color: white;
            text-align: center;
            padding: 50px;
        }
        .player-card:hover {
            transform: scale(1.05);
            transition: transform 0.3s ease;
        }
    </style>
</head>
<body>
    <!-- Hero Section -->
    <div class="hero-section">
        <h1>Welcome to CricGang</h1>
        <p>Your go-to site for cricket stats, news, and updates!</p>
    </div>

    <!-- Announcements Section -->
    <div class="container my-5">
        <h2>Announcements</h2>
        <ul id="announcements">
            <li>Ajman Hunters vs Sharjah Knights match on Thursday, 5:30 PM.</li>
            <li>PSA Warriors announce a new team lineup!</li>
        </ul>
    </div>

    <!-- Player Search -->
    <div class="container my-5">
        <h2>Search Players</h2>
        <input type="text" id="search" class="form-control" placeholder="Search by player name..." onkeyup="searchPlayers()">
        <ul id="playerList" class="mt-3">
            <li>Hasher - Captain</li>
            <li>Ammar - Vice-Captain</li>
            <li>Haziq - Bowler</li>
            <!-- Add more players -->
        </ul>
    </div>

    <!-- Player Stats Section -->
    <div class="container my-5">
        <h2>Team Statistics</h2>
        <canvas id="teamStatsChart"></canvas>
    </div>

    <!-- Footer -->
    <footer class="text-center py-3 bg-dark text-white">
        CricGang © 2024 | All rights reserved.
    </footer>

    <script>
        // Player Search Functionality
        function searchPlayers() {
            const input = document.getElementById('search').value.toLowerCase();
            const players = document.getElementById('playerList').getElementsByTagName('li');
            for (let player of players) {
                if (player.textContent.toLowerCase().includes(input)) {
                    player.style.display = "";
                } else {
                    player.style.display = "none";
                }
            }
        }

        // Team Stats Chart
        const ctx = document.getElementById('teamStatsChart').getContext('2d');
        new Chart(ctx, {
            type: 'bar',
            data: {
                labels: ['Ajman Hunters', 'Sharjah Knights', 'PSA Warriors'],
                datasets: [{
                    label: 'Wins',
                    data: [10, 8, 7],
                    backgroundColor: ['#2ecc71', '#e74c3c', '#3498db']
                }]
            },
            options: {
                responsive: true,
                plugins: {
                    legend: {
                        display: true
                    }
                }
            }
        });
    </script>
</body>
</html>
