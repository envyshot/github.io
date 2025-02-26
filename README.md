<!DOCTYPE html>

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ahsan’s Travel Page</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #111;
            color: white;
            text-align: center;
        }

        /* Navigation Bar */
nav {
            background-color: #222;
            padding: 15px 0;
            text-align: center;
            position: fixed;
            width: 100%;
            top: 0;
            left: 0;
            z-index: 1000;
        }
.menu {
            list-style: none;
            padding: 0;
            margin: 0;
        }

.menu li {
            display: inline-block;
            margin: 0 15px;
            position: relative;
        }

.menu li a {
            text-decoration: none;
            color: white;
            font-size: 18px;
            padding: 12px 18px;
            transition: all 0.3s ease-in-out;
            border-radius: 8px;
        }

.menu li a:hover {
            background-color: #e67e22;
            color: #fff;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
        }

/* Dropdown menu */
.dropdown-content {
            display: none;
            position: absolute;
            background-color: #333;
            min-width: 150px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
            border-radius: 5px;
        }

.dropdown-content a {
            color: white;
            padding: 12px;
            display: block;
            text-align: left;
            text-decoration: none;
        }

.dropdown-content a:hover {
            background-color: #e67e22;
        }

.menu li:hover .dropdown-content {
            display: block;
        }

/* Slideshow */
.slideshow-container {
            position: relative;
            max-width: 1000px;
            margin: 80px auto;
        }

.slides {
            display: none;
            width: 100%;
            height: 500px;
            object-fit: cover;
            border-radius: 10px;
        }

.prev, .next {
            cursor: pointer;
            position: absolute;
            top: 50%;
            width: auto;
            padding: 10px;
            color: white;
            font-size: 20px;
            transition: 0.3s;
            border-radius: 5px;
            user-select: none;
        }

.prev { left: 0; }
.next { right: 0; }

.prev:hover, .next:hover {
            background-color: rgba(0, 0, 0, 0.5);
        }

/* Gallery */
.gallery {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            margin-top: 20px;
        }

.gallery img {
            width: 200px;
            height: 150px;
            margin: 10px;
            border-radius: 5px;
            transition: transform 0.3s;
        }

.gallery img:hover {
            transform: scale(2);
        }

</style>
</head>
<body>

<!-- Navigation Bar -->
<nav>
        <ul class="menu">
            <li><a href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li>
                <a href="#">Gallery</a>
                <div class="dropdown-content">
                    <a href="#">Travel</a>
                    <a href="#">Portrait</a>
                </div>
            </li>
            <li><a href="#">Equipment</a></li>
            <li>
                <a href="#">Contact</a>
                <div class="dropdown-content">
                    <a href="#">General Contact</a>
                    <a href="#">Appointment</a>
                </div>
            </li>
        </ul>
    </nav>
<!-- Home Page Header -->
<h1>Welcome to Ahsan’s Photo Gallery</h1>
 <!-- Slideshow -->
<div class="slideshow-container">
<img class="slides" src="image1.jpg" alt="Slide 1">
<img class="slides" src="image2.jpg" alt="Slide 2">
<img class="slides" src="image3.jpg" alt="Slide 3">
<img class="slides" src="image4.jpg" alt="Slide 4">
<img class="slides" src="image5.jpg" alt="Slide 5">

<a class="prev" onclick="plusSlides(-1)">&#10094;</a>
<a class="next" onclick="plusSlides(1)">&#10095;</a>
</div>
<!-- Travel Gallery -->
<h2>Travel Gallery</h2>
<div class="gallery">
<img src="travel1.jpg" alt="Amsterdam">
<img src="travel2.jpg" alt="England">
<img src="travel3.jpg" alt="Japan">
<img src="travel4.jpg" alt="Paris">
<img src="travel5.jpg" alt="Italy">
</div>
<!-- Portrait Gallery -->
<h2>Portrait Gallery</h2>
<div class="gallery">
<img src="portrait1.jpg" alt="Portrait 1">
<img src="portrait2.jpg" alt="Portrait 2">
<img src="portrait3.jpg" alt="Portrait 3">
<img src="portrait4.jpg" alt="Portrait 4">
<img src="portrait5.jpg" alt="Portrait 5">
</div>

<script>
        let slideIndex = 0;
        showSlides();

        function showSlides() {
            let slides = document.getElementsByClassName("slides");
            for (let i = 0; i < slides.length; i++) {
                slides[i].style.display = "none";
            }
            slideIndex++;
            if (slideIndex > slides.length) { slideIndex = 1 }
            slides[slideIndex - 1].style.display = "block";
            setTimeout(showSlides, 3000); // Change image every 3 seconds
        }

        function plusSlides(n) {
            slideIndex += n;
            let slides = document.getElementsByClassName("slides");
            if (slideIndex > slides.length) { slideIndex = 1 }
            if (slideIndex < 1) { slideIndex = slides.length }
            for (let i = 0; i < slides.length; i++) {
                slides[i].style.display = "none";
            }
            slides[slideIndex - 1].style.display = "block";
        }
    </script>

</body>
</html>
