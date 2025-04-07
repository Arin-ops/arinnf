<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Motivasi Harian</title>
    <style>
        :root {
            --pink-light: #fff0f5;
            --pink-medium: #ffcce6;
            --pink-dark: #ff99cc;
            --purple: #d9b3ff;
            --text-dark: #4d004d;
            --text-light: #f5f5f5;
        }
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--pink-light);
            color: var(--text-dark);
            margin: 0;
            padding: 0;
            line-height: 1.6;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }

        header {
            background: linear-gradient(135deg, var(--pink-dark), var(--purple));
            color: white;
            padding: 20px 0;
            border-radius: 0 0 20px 20px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            text-align: center;
            position: relative;
        }

        h1 {
            margin: 0;
            font-size: 2.5rem;
            font-weight: 300;
            letter-spacing: 1px;
        }

        .subtitle {
            font-style: italic;
            margin-top: 5px;
            opacity: 0.9;
        }

        .main-content {
            background-color: white;
            border-radius: 15px;
            padding: 30px;
            margin-top: 30px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.05);
            text-align: center;
        }

        .motivation-card {
            background: linear-gradient(135deg, var(--pink-light), white);
            border-radius: 15px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            border-left: 5px solid var(--purple);
        }

        .motivation-text {
            font-size: 1.3rem;
            font-style: italic;
            line-height: 1.8;
            margin-bottom: 20px;
        }

        .motivation-author {
            font-weight: bold;
            color: var(--purple);
        }

        .btn {
            background: linear-gradient(to right, var(--pink-dark), var(--purple));
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 30px;
            cursor: pointer;
            font-size: 1rem;
            transition: all 0.3s;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            margin: 10px;
        }

        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
        }

        footer {
            text-align: center;
            margin-top: 50px;
            padding: 20px;
            color: var(--text-dark);
            font-size: 0.9rem;
        }

        /* Hamburger Menu Styles - Revisi */
        .menu-btn {
            position: absolute;
            top: 25px;
            right: 25px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            width: 30px;
            height: 21px;
            cursor: pointer;
            z-index: 100;
            background: transparent;
            border: none;
            padding: 0;
        }

        .menu-btn span {
            display: block;
            height: 3px;
            width: 100%;
            background-color: white;
            border-radius: 3px;
            transition: all 0.3s;
        }

        .menu-btn.active span:nth-child(1) {
            transform: translateY(9px) rotate(45deg);
        }

        .menu-btn.active span:nth-child(2) {
            opacity: 0;
        }

        .menu-btn.active span:nth-child(3) {
            transform: translateY(-9px) rotate(-45deg);
        }

        .menu {
            position: fixed;
            top: 0;
            right: -100%; /* Diubah dari -300px ke -100% untuk memastikan tersembunyi */
            width: 250px;
            height: 100%;
            background-color: white;
            transition: right 0.3s ease-out;
            z-index: 99;
            padding: 80px 20px 20px;
            overflow-y: auto;
            box-shadow: -5px 0 25px rgba(0, 0, 0, 0.1);
            visibility: hidden; /* Tambahkan ini untuk memastikan tersembunyi */
        }

        .menu.active {
            right: 0;
            visibility: visible; /* Tambahkan ini saat menu aktif */
        }

        .menu-item {
            padding: 15px;
            margin-bottom: 10px;
            background-color: var(--pink-light);
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: 500;
            color: var(--text-dark);
            text-align: left;
        }

        .menu-item:hover {
            background-color: var(--pink-medium);
            transform: translateX(5px);
        }

        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 98;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s;
        }

        .overlay.active {
            opacity: 1;
            visibility: visible;
        }

        /* Responsive adjustments */
        @media (max-width: 600px) {
            h1 {
                font-size: 2rem;
            }
            .menu {
                width: 80%;
                right: -80%;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <h1>Motivasi Harian</h1>
            <p class="subtitle">Dosis harian inspirasi untuk semangatmu</p>
        </div>
        <!-- Hamburger Menu Button -->
        <button class="menu-btn">
            <span></span>
            <span></span>
            <span></span>
        </button>
    </header>

    <!-- Menu Overlay -->
    <div class="overlay"></div>

    <!-- Side Menu - Awalnya tersembunyi -->
    <div class="menu">
        <div class="menu-item" onclick="alert('Web Curhat akan dibuka!')">Web Curhat Sini Nih</div>
        <div class="menu-item" onclick="alert('Blog Cerita Kehidupan akan dibuka!')">Blog Cerita Kehidupan</div>
        <div class="menu-item" onclick="alert('Web Tugas Sekolah akan dibuka!')">Web Tugas Sekolah</div>
        <div class="menu-item" onclick="alert('Galeri Rangkaian Kata akan dibuka!')">Galeri Rangkaian Kata</div>
    </div>

    <div class="container">
        <div class="main-content">
            <div class="motivation-card">
                <p class="motivation-text">Klik tombol di bawah untuk melihat motivasi</p>
                <p class="motivation-author"></p>
            </div>
            <button class="btn" id="newMotivation">Tampilkan Motivasi Baru</button>
            <button class="btn" id="saveMotivation">Simpan Motivasi</button>

            <div style="margin-top: 40px;">
                <h3>Tambahkan Motivasi Versimu</h3>
                <input type="text" id="userQuote" placeholder="Tulis kutipan motivasi..." style="width: 100%; padding: 10px; margin: 10px 0;">
                <input type="text" id="userAuthor" placeholder="Nama penulis (opsional)" style="width: 100%; padding: 10px; margin-bottom: 10px;">
                <button class="btn" id="submitMotivation">Kirim Motivasi</button>
            </div>
        </div>
    </div>

    <script>
        const motivations = [
            {
                text: '"Hidup adalah perjalanan yang harus dinikmati langkah demi langkah, bukan hanya tujuan akhirnya."',
                author: "- Unknown"
            },
            {
                text: '"Kamu tidak perlu sempurna untuk memulai, tapi kamu harus memulai untuk menjadi sempurna."',
                author: "- Zig Ziglar"
            },
            {
                text: '"Masalah adalah kesempatan bagimu untuk tumbuh lebih kuat."',
                author: "- Unknown"
            },
            {
                text: '"Jangan bandingkan babak pertamamu dengan babak kelima orang lain."',
                author: "- Tim Hill"
            },
            {
                text: '"Kegagalan adalah bumbu yang memberi rasa kesuksesan."',
                author: "- Truman Capote"
            },
            {
                text: '"Setiap hari adalah kesempatan baru untuk menjadi versi terbaik dari dirimu."',
                author: "- ChatGPT"
            }
        ];

        const motivationText = document.querySelector('.motivation-text');
        const motivationAuthor = document.querySelector('.motivation-author');
        const newMotivationBtn = document.getElementById('newMotivation');
        const menuBtn = document.querySelector('.menu-btn');
        const menu = document.querySelector('.menu');
        const overlay = document.querySelector('.overlay');

        function getRandomMotivation() {
            const randomIndex = Math.floor(Math.random() * motivations.length);
            return motivations[randomIndex];
        }

        newMotivationBtn.addEventListener('click', function () {
            const newMotivation = getRandomMotivation();
            motivationText.textContent = newMotivation.text;
            motivationAuthor.textContent = newMotivation.author;
        });

        document.getElementById('saveMotivation').addEventListener('click', function () {
            alert('Motivasi ini telah disimpan ke favoritmu!');
        });

        document.getElementById('submitMotivation').addEventListener('click', function () {
            const quote = document.getElementById('userQuote').value.trim();
            const author = document.getElementById('userAuthor').value.trim() || "- Anonim";

            if (quote) {
                motivations.push({
                    text: `"${quote}"`,
                    author: author
                });
                alert('Motivasi kamu sudah ditambahkan! Terima kasih!');
                document.getElementById('userQuote').value = '';
                document.getElementById('userAuthor').value = '';
            } else {
                alert('Tolong isi dulu motivasinya ya!');
            }
        });

        // Hamburger menu functionality
        menuBtn.addEventListener('click', function() {
            menu.classList.toggle('active');
            overlay.classList.toggle('active');
            menuBtn.classList.toggle('active');
            
            // Tambahkan untuk mencegah scroll body saat menu terbuka
            document.body.style.overflow = menu.classList.contains('active') ? 'hidden' : '';
        });

        overlay.addEventListener('click', function() {
            menu.classList.remove('active');
            overlay.classList.remove('active');
            menuBtn.classList.remove('active');
            document.body.style.overflow = ''; // Kembalikan scroll body
        });
    </script>

    <footer>
        &copy; 2025 Motivasi Harian. Dibuat dengan semangat dari Rembang.
    </footer>
</body>
</html>
