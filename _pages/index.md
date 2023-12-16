---
layout: page
title: Home
id: home
permalink: /
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Your Company Name</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }
        nav {
            background-color: #333;
            overflow: hidden;
        }
        .banner-content {
            float: left;
            padding: 14px 16px;
            color: white;
            font-weight: bold;
        }
        nav ul {
            list-style-type: none;
            margin: 0;
            padding: 0;
            float: right;
        }
        nav ul li {
            float: left;
        }
        nav ul li a {
            display: block;
            color: white;
            text-align: center;
            padding: 14px 16px;
            text-decoration: none;
        }
        .sub-menu {
            display: none;
            position: absolute;
            background-color: #f9f9f9;
            box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
        }
        .sub-menu a {
            color: black;
            padding: 12px 16px;
            text-decoration: none;
            display: block;
            text-align: left;
        }
        nav ul li:hover .sub-menu {
            display: block;
        }
        .slider {
            width: 100%;
            overflow: hidden;
        }
        .slides {
            display: flex;
            transition: transform 0.5s ease;
        }
        .slide {
            min-width: 100%;
            height: 300px;
            background-size: cover;
            background-position: center;
        }
        .indicators {
            text-align: center;
        }
        .indicator {
            display: inline-block;
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background-color: lightgray;
            margin: 5px;
            cursor: pointer;
        }
        .active {
            background-color: darkgray;
        }
        section {
            margin: 20px;
            padding: 20px;
            background-color: #f5f5f5;
            border-radius: 10px;
        }
        h2 {
            color: #333;
        }
        footer {
            text-align: center;
            padding: 20px;
            background-color: #333;
            color: white;
            position: relative;
            bottom: 0;
            width: 100%;
        }
    </style>
</head>
<body>
    <nav>
        <div class="banner-content">Banner Content Here</div>
        <ul>
            <li><a href="#">Home</a>
                <div class="sub-menu">
                    <a href="#">Sub Menu 1</a>
                    <a href="#">Sub Menu 2</a>
                    <a href="#">Sub Menu 3</a>
                </div>
            </li>
            <!-- 추가 메뉴 항목들 ... -->
        </ul>
    </nav>

    <div class="slider">
        <div class="slides">
            <div class="slide" style="background-image: url(''_images/_Pic/Image_Main_0.png'');"></div>
            <div class="slide" style="background-image: url('image2.jpg');"></div>
            <div class="slide" style="background-image: url('image3.jpg');"></div>
            <div class="slide" style="background-image: url('image4.jpg');"></div>
        </div>
        <div class="indicators">
            <span class="indicator active"></span>
            <span class="indicator"></span>
            <span class="indicator"></span>
            <span class="indicator"></span>
        </div>
    </div>

    <section id="about">
        <h2>About Our Company</h2>
        <p>We are a leading firm in our field, committed to providing quality services...</p>
    </section>

    <section id="services">
        <h2>Our Services</h2>
        <div class="service-item">Service 1 Description</div>
        <div class="service-item">Service 2 Description</div>
        <div class="service-item">Service 3 Description</div>
    </section>

    <section id="team">
        <h2>Meet Our Team</h2>
        <div class="team-member">Member 1 Bio</div>
        <div class="team-member">Member 2 Bio</div>
    </section>

    <section id="contact">
        <h2>Contact Us</h2>
        <form>
            <input type="text" placeholder="Your Name" required>
            <input type="email" placeholder="Your Email" required>
            <textarea placeholder="Your Message"></textarea>
            <button type="submit">Send Message</button>
        </form>
    </section>

    <footer>
        <p>&copy; 2023 Company Name. All rights reserved.</p>
    </footer>

    <script>
        let currentSlide = 0;
        const slides = document.querySelectorAll(".slide");
        const indicators = document.querySelectorAll(".indicator");

        function updateSlide() {
            let slideWidth = slides[0].offsetWidth;
            document.querySelector(".slides").style.transform = `translateX(-${currentSlide * slideWidth}px)`;
            indicators.forEach(ind => ind.classList.remove("active"));
            indicators[currentSlide].classList.add("active");
        }

        function nextSlide() {
            currentSlide = (currentSlide + 1) % slides.length;
            updateSlide();
        }

        setInterval(nextSlide, 10000); // 10초마다 슬라이드 변경

        indicators.forEach((indicator, idx) => {
            indicator.addEventListener("click", () => {
                currentSlide = idx;
                updateSlide();
            });
        });
    </script>
</body>
</html>
