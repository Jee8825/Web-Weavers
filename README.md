<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Blog</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html, body {
            height: 100%;
        }

        body {
            display: flex;
            flex-direction: column;
            font-family: Arial, sans-serif;
            background-color: #121212;
            color: #e0e0e0;
        }

        header {
            text-align: center;
            padding: 20px 0;
            background: #1f1f1f;
            border-bottom: 2px solid #333333;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.4);
        }

        header h1 {
            margin: 0;
            font-size: 2.5em;
            color: #20c997; /* Teal color for title */
        }

        nav {
            display: flex;
            justify-content: center;
            gap: 20px;
            padding: 10px 0;
            background: #1f1f1f;
            border-bottom: 2px solid #333333;
            position: relative;
            margin-top: 15px;
        }

        nav a {
            text-decoration: none;
            color: #20c997; /* Teal color for links */
            padding: 10px 20px;
            border-radius: 15px;
            background: rgba(32, 201, 151, 0.1);
            transition: all 0.3s ease;
            font-weight: bold;
        }

        nav a:hover {
            background: #20c997;
            color: #121212;
        }

        .nav-slider {
            position: absolute;
            height: 5px;
            background: #20c997; /* Teal color for slider */
            width: 80px;
            bottom: 0;
            left: 0;
            transition: all 0.3s ease;
        }

        .gallery {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            padding: 30px;
            max-width: 1200px;
            margin: 0 auto;
            flex: 1;
        }

        .gallery-item {
            text-decoration: none;
            color: #e0e0e0;
            background: #1f1f1f;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            height: 350px;
        }

        .gallery-item:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.8);
        }

        .gallery-item img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-bottom: 2px solid rgba(32, 201, 151, 0.2);
        }

        .gallery-info {
            padding: 15px;
            text-align: center;
        }

        .gallery-info h3 {
            margin: 10px 0;
            font-size: 1.5em;
            color: #20c997; /* Teal color for headings */
        }

        .gallery-info p {
            font-size: 0.9em;
            color: #8ab4f8; /* Light grayish-blue for text */
        }

        footer {
            text-align: center;
            padding: 15px;
            background: #1f1f1f;
            border-top: 2px solid #333333;
            box-shadow: 0 -4px 10px rgba(0, 0, 0, 0.4);
        }

        footer p {
            margin: 0;
            color: #e0e0e0;
        }
    </style>
</head>
<body>
    <header>
        <h1>Interactive Blog</h1>
    </header>
    <nav>
        <a href="movies.html">Movies</a>
        <a href="rating.html">Rating</a>
        <a href="reviews.html">Reviews</a>
        <div class="nav-slider" id="slider"></div>
    </nav>

    <section class="gallery">
        <a href="movies.html" class="gallery-item" id="movies">
            <img src="movie thumbnail1.jpeg" alt="Movies" />
            <div class="gallery-info">
                <h3>Movies</h3>
                <p>Explore the latest and greatest movies from around the world.</p>
            </div>
        </a>
        <a href="rating.html" class="gallery-item" id="rating">
            <img src="imdb.jpeg.webp" alt="Rating" />
            <div class="gallery-info">
                <h3>Rating</h3>
                <p>Rate your favorite movies and shows out of 10.</p>
            </div>
        </a>
        <a href="reviews.html" class="gallery-item" id="reviews">
            <img src="review.jpg.webp" alt="Reviews" />
            <div class="gallery-info">
                <h3>Reviews</h3>
                <p>Read and share detailed reviews on the latest movies.</p>
            </div>
        </a>
    </section>

    <footer>
        <p>&copy; 2024 Interactive Blog. All rights reserved.</p>
    </footer>

    <script>
        function moveSlider(index) {
            const slider = document.getElementById('slider');
            const navLinks = document.querySelectorAll('nav a');
            slider.style.width = navLinks[index].offsetWidth + 'px';
            slider.style.transform = `translateX(${navLinks[index].offsetLeft}px)`;
        }

        // Initialize the slider to start at the first option
        document.addEventListener("DOMContentLoaded", () => moveSlider(0));
    </script>
</body>
</html>
