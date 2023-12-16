---
layout: page
title: Home
id: home
permalink: /
---
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Your Company Name</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }
        nav ul {
            list-style-type: none;
            margin: 0;
            padding: 0;
            overflow: hidden;
            background-color: #333;
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
        nav ul li a:hover {
            background-color: #111;
        }
        .service-item, .team-member {
            margin-bottom: 15px;
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
        .wrapper {
            max-width: 46em;
            margin: auto;
        }
    </style>
</head>
<body>
    <nav>
        <ul>
            <li><a href="{{ site.baseurl }}/home">Home</a></li>
            <li><a href="{{ site.baseurl }}/about">About Us</a></li>
            <li><a href="{{ site.baseurl }}/services">Services</a></li>
            <li><a href="{{ site.baseurl }}/blog">Blog</a></li>
            <li><a href="{{ site.baseurl }}/contact">Contact</a></li>
        </ul>
    </nav>

    <div class="wrapper">
        <h1>Welcome! 🌱</h1>

        <p style="padding: 3em 1em; background: #f5f7ff; border-radius: 4px;">
            Take a look at <span style="font-weight: bold">[[Your first note]]</span> to get started on your exploration.
        </p>

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
    </div>
</body>
</html>
