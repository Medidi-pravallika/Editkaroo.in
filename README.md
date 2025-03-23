# Editkaroo.in
#page like editkaro
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Editkaro Portfolio</title>
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            text-align: center;
            background-color: #0d0d0d;
            color: white;
            margin: 0;
            padding: 0;
            transition: background 0.3s ease-in-out;
        }

        .dark-mode {
            background-color: #ffffff;
            color: #0d0d0d;
        }

        header {
            padding: 20px;
            background: linear-gradient(90deg, #ff416c, #ff4b2b);
            font-size: 24px;
            font-weight: bold;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 28px;
            font-weight: bold;
        }

        .toggle-btn {
            padding: 10px;
            background: #ff416c;
            border: none;
            color: white;
            cursor: pointer;
            border-radius: 20px;
            font-size: 16px;
            transition: 0.3s;
        }

        .toggle-btn:hover {
            background: #ff4b2b;
        }

        nav {
            margin: 20px;
        }

        .filter-btn {
            padding: 12px 20px;
            margin: 5px;
            border: none;
            background: #ff416c;
            color: white;
            cursor: pointer;
            border-radius: 25px;
            font-size: 16px;
            transition: 0.3s;
        }

        .filter-btn:hover {
            background: #ff4b2b;
            transform: scale(1.1);
        }

        .search-bar {
            margin: 20px;
            padding: 10px;
            width: 50%;
            font-size: 16px;
            border-radius: 5px;
            border: none;
        }

        .portfolio {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
            margin: 20px auto;
            max-width: 1200px;
            transition: opacity 0.5s ease-in-out;
        }

        .video-item {
            width: 300px;
            background: #222;
            padding: 10px;
            border-radius: 10px;
            transition: transform 0.3s;
            cursor: pointer;
            box-shadow: 0 4px 10px rgba(255, 75, 43, 0.5);
            opacity: 0;
            animation: fadeIn 0.5s forwards;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        video {
            width: 100%;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <header>
        <div class="logo">Editkaro Portfolio</div>
        <input type="text" class="search-bar" placeholder="Search videos..." onkeyup="searchVideos()">
        <button class="toggle-btn" onclick="toggleDarkMode()">Toggle Dark Mode</button>
    </header>

    <nav>
        <button class="filter-btn" data-category="all">All</button>
        <button class="filter-btn" data-category="short">Short Videos</button>
        <button class="filter-btn" data-category="long">Long Videos</button>
        <button class="filter-btn" data-category="gaming">Gaming Videos</button>
        <button class="filter-btn" data-category="football">Football Edits</button>
        <button class="filter-btn" data-category="music">Music Videos</button>
        <button class="filter-btn" data-category="ads">Advertisements</button>
    </nav>

    <section class="portfolio">
        <div class="video-item" data-category="short" data-src="short.mp4">
            <video src="short.mp4" muted autoplay loop></video>
            <p>Short Video</p>
        </div>
        <div class="video-item" data-category="long" data-src="long.mp4">
            <video src="long.mp4" muted autoplay loop></video>
            <p>Long Video</p>
        </div>
        <div class="video-item" data-category="gaming" data-src="gaming.mp4">
            <video src="gaming.mp4" muted autoplay loop></video>
            <p>Gaming Video</p>
        </div>
        <div class="video-item" data-category="football" data-src="football.mp4">
            <video src="football.mp4" muted autoplay loop></video>
            <p>Football Edit</p>
        </div>
        <div class="video-item" data-category="music" data-src="music.mp4">
            <video src="music.mp4" muted autoplay loop></video>
            <p>Music Video</p>
        </div>
        <div class="video-item" data-category="ads" data-src="ad.mp4">
            <video src="ad.mp4" muted autoplay loop></video>
            <p>Advertisement</p>
        </div>
    </section>

    <script>
        function searchVideos() {
            let input = document.querySelector(".search-bar").value.toLowerCase();
            let videos = document.querySelectorAll(".video-item");
            videos.forEach(video => {
                let title = video.querySelector("p").innerText.toLowerCase();
                video.style.display = title.includes(input) ? "block" : "none";
            });
        }
    </script>
</body>
</html>

