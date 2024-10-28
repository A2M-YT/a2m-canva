<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Unlock Content - A2M YT</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #333, #111);
            color: #fff;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .container {
            background-color: #222;
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            text-align: center;
            max-width: 400px;
            width: 100%;
            animation: fadeIn 1s ease-in-out;
        }
        h1 {
            font-size: 24px;
            color: #fff;
            margin-bottom: 20px;
        }
        h2 {
            font-size: 20px;
            margin-bottom: 15px;
            color: #00e676;
        }
        p {
            color: #ccc;
            margin-bottom: 30px;
        }
        #lock-icon {
            font-size: 100px;
            margin: 20px 0;
            color: #fff;
            transition: all 0.3s ease;
        }
        #progress-container {
            width: 100%;
            background-color: #444;
            border-radius: 30px;
            overflow: hidden;
            margin-bottom: 20px;
        }
        #progress-bar {
            width: 0%;
            height: 15px;
            background-color: #00e676;
            border-radius: 30px;
            transition: width 1s ease;
            animation: pulse 1.5s infinite;
        }
        .button-container {
            display: flex;
            flex-direction: column; /* Ubah menjadi kolom */
            align-items: center; /* Rata tengah */
            width: 100%; /* Penuhi lebar kontainer */
        }
        button {
            padding: 15px 30px;
            font-size: 16px;
            margin: 10px 0; /* Spasi antar tombol */
            cursor: pointer;
            border: none;
            border-radius: 50px;
            background-color: #555;
            color: white;
            transition: background-color 0.3s ease, transform 0.3s ease;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
            width: calc(100% - 40px); /* Atur lebar tombol */
        }
        button:hover {
            background-color: #00e676;
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0, 230, 118, 0.4);
        }
        button:disabled {
            background-color: #777; /* Warna saat dinonaktifkan */
            cursor: not-allowed; /* Ubah kursor saat dinonaktifkan */
        }
        .icon {
            width: 20px; /* Ukuran ikon */
            margin-right: 8px; /* Spasi antara ikon dan teks */
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
        .checkmark {
            display: none;
            stroke-width: 3;
            stroke: #00e676;
            animation: dash 0.5s ease-in-out;
        }
        @keyframes dash {
            0% { stroke-dasharray: 0, 100; }
            100% { stroke-dasharray: 100, 0; }
        }
        .youtube-logo {
            width: 60px; /* Ukuran logo YouTube */
            margin-bottom: 15px;
        }
    </style>
</head>
<body>
    <div class="container">
        <img src="https://upload.wikimedia.org/wikipedia/commons/4/42/YouTube_icon_%282013-2017%29.png" alt="YouTube Logo" class="youtube-logo">
        <h2>A2M YT</h2>
        <h1>Unlock Exclusive Content!</h1>
        <p>Like and Subscribe to access the hidden content!</p>
        
        <div id="lock-icon">
            <svg width="100" height="100" viewBox="0 0 100 100">
                <circle cx="50" cy="50" r="40" stroke="#555" stroke-width="10" fill="none"></circle>
                <polyline class="checkmark" points="30,50 45,65 70,40" stroke-linecap="round" stroke-linejoin="round" fill="none"></polyline>
            </svg>
        </div>
        
        <div id="progress-container">
            <div id="progress-bar"></div>
        </div>

        <div class="button-container">
            <button id="like-button" onclick="handleLike()">👍 Like</button>
            <button id="subscribe-button" onclick="handleSubscribe()">🔔 Subscribe</button>
            <button id="go-to-canva" onclick="goToCanva()" disabled>
                <span class="icon">🔒</span> Go to Canva
            </button>
        </div>
    </div>

    <script>
        // Memeriksa status Like dan Subscribe di sessionStorage
        let isLiked = sessionStorage.getItem('isLiked') === 'true';
        let isSubscribed = sessionStorage.getItem('isSubscribed') === 'true';

        window.onload = function() {
            // Update status progress dan tombol saat halaman dimuat
            if (isLiked) {
                document.getElementById('progress-bar').style.width = '50%';
            }
            if (isSubscribed) {
                document.getElementById('progress-bar').style.width = '100%';
                document.querySelector('.checkmark').style.display = 'block';
                
                // Mengaktifkan tombol "Go to Canva" setelah subscribe
                document.getElementById('go-to-canva').disabled = false; // Mengaktifkan tombol
                document.getElementById('go-to-canva').innerHTML = '<span class="icon">🔓</span> Go to Canva'; // Ganti ikon gembok dengan ikon terbuka
            }
        };

        function handleLike() {
            if (isLiked) return;
            isLiked = true;
            sessionStorage.setItem('isLiked', true);

            // Mengarahkan pengguna ke YouTube setelah menekan tombol "Like"
            window.open("https://youtube.com/@a2m_yt?si=m4JeBvp9lLEA1UHb", "_blank");
            document.getElementById('progress-bar').style.width = '50%'; 
        }

        function handleSubscribe() {
            if (!isLiked || isSubscribed) return;
            isSubscribed = true;
            sessionStorage.setItem('isSubscribed', true);

            let lockIcon = document.querySelector('.checkmark');
            lockIcon.style.display = 'block';
            lockIcon.style.animation = 'dash 1s forwards';

            let progressBar = document.getElementById('progress-bar');
            progressBar.style.width = '100%'; 

            // Mengarahkan pengguna ke YouTube setelah menekan tombol "Subscribe"
            window.open("https://youtube.com/@a2m_yt?si=m4JeBvp9lLEA1UHb", "_blank");

            // Mengaktifkan tombol "Go to Canva" setelah subscribe
            document.getElementById('go-to-canva').disabled = false; // Mengaktifkan tombol
            document.getElementById('go-to-canva').innerHTML = '<span class="icon">🔓</span> Go to Canva'; // Ganti ikon gembok dengan ikon terbuka
        }

        function goToCanva() {
            window.location.href = "https://www.canva.com/brand/join?token=5a_e5VPxKqNZ-m7onsEsTg&referrer=team-invite"; // Ganti dengan link Canva pro lo
        }
    </script>
</body>
</html>
