<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Complete Website</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        /* CSS Styles */
        :root {
            --primary-color: #3498db;
            --secondary-color: #2c3e50;
            --light-color: #ecf0f1;
            --dark-color: #2c3e50;
            --accent-color: #e74c3c;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
        }

        .container {
            width: 85%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        a {
            text-decoration: none;
            color: var(--primary-color);
        }

        .btn {
            display: inline-block;
            background: var(--primary-color);
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .btn:hover {
            background: var(--secondary-color);
            transform: translateY(-2px);
        }

        .section {
            padding: 80px 0;
        }

        .section h2 {
            text-align: center;
            margin-bottom: 40px;
            font-size: 2.5rem;
            color: var(--dark-color);
        }

        .dark {
            background-color: var(--secondary-color);
            color: white;
        }

        .dark h2 {
            color: white;
        }

        /* Header Styles */
        header {
            background-color: white;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            transition: all 0.3s ease;
        }

        header.scrolled {
            padding: 10px 0;
            background-color: rgba(255, 255, 255, 0.95);
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
        }

        header .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 20px;
            transition: all 0.3s ease;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: var(--primary-color);
        }

        nav ul {
            display: flex;
            list-style: none;
        }

        nav ul li {
            margin-left: 30px;
        }

        nav ul li a {
            color: var(--dark-color);
            font-weight: 500;
            transition: color 0.3s;
        }

        nav ul li a:hover {
            color: var(--primary-color);
        }

        /* Mobile Menu */
        .menu-toggle {
            display: none;
            cursor: pointer;
            font-size: 1.5rem;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), url('https://images.unsplash.com/photo-1499750310107-5fef28a66643?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80') no-repeat center center/cover;
            color: white;
            text-align: center;
            margin-top: 0;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            animation: fadeInDown 1s ease;
        }

        .hero p {
            font-size: 1.5rem;
            margin-bottom: 30px;
            animation: fadeInUp 1s ease 0.3s forwards;
            opacity: 0;
        }

        .hero .btn {
            animation: fadeIn 1s ease 0.6s forwards;
            opacity: 0;
        }

        /* About Section */
        .about-content {
            display: flex;
            align-items: center;
            gap: 40px;
        }

        .about-text {
            flex: 1;
        }

        .about-image {
            flex: 1;
        }

        .about-image img {
            width: 100%;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.5s ease;
        }

        .about-image img:hover {
            transform: scale(1.03);
        }

        /* Services Section */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .service {
            background: white;
            padding: 30px;
            border-radius: 10px;
            text-align: center;
            transition: transform 0.3s, box-shadow 0.3s;
            color: var(--dark-color);
        }

        .service:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }

        .service i {
            font-size: 3rem;
            color: var(--primary-color);
            margin-bottom: 20px;
        }

        .service h3 {
            margin-bottom: 15px;
            font-size: 1.5rem;
        }

        /* Testimonials */
        .testimonials {
            background-color: #f9f9f9;
        }

        .testimonial-slider {
            max-width: 800px;
            margin: 0 auto;
            position: relative;
            overflow: hidden;
        }

        .testimonial {
            padding: 20px;
            text-align: center;
            display: none;
        }

        .testimonial.active {
            display: block;
            animation: fadeIn 1s ease;
        }

        .testimonial img {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            object-fit: cover;
            margin: 0 auto 20px;
            border: 5px solid var(--primary-color);
        }

        .testimonial p {
            font-style: italic;
            margin-bottom: 20px;
        }

        .testimonial-author {
            font-weight: bold;
        }

        .slider-controls {
            text-align: center;
            margin-top: 20px;
        }

        .slider-dots {
            display: flex;
            justify-content: center;
            margin-top: 20px;
        }

        .dot {
            width: 12px;
            height: 12px;
            background-color: #ccc;
            border-radius: 50%;
            margin: 0 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .dot.active {
            background-color: var(--primary-color);
        }

        /* Contact Section */
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: 500;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-family: inherit;
        }

        .form-group textarea {
            height: 150px;
            resize: vertical;
        }

        /* Footer */
        footer {
            background: var(--dark-color);
            color: white;
            padding: 30px 0;
            text-align: center;
        }

        .social-links {
            margin-top: 20px;
        }

        .social-links a {
            color: white;
            margin: 0 10px;
            font-size: 1.5rem;
            transition: color 0.3s;
        }

        .social-links a:hover {
            color: var(--primary-color);
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            header .container {
                flex-direction: row;
            }

            .menu-toggle {
                display: block;
            }

            nav {
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background: white;
                box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
                clip-path: polygon(0 0, 100% 0, 100% 0, 0 0);
                transition: all 0.3s ease;
            }

            nav.active {
                clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%);
            }

            nav ul {
                flex-direction: column;
                padding: 20px;
            }

            nav ul li {
                margin: 10px 0;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .about-content {
                flex-direction: column;
            }

            .services-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <header id="main-header">
        <div class="container">
            <div class="logo">MySite</div>
            <div class="menu-toggle">
                <i class="fas fa-bars"></i>
            </div>
            <nav id="main-nav">
                <ul>
                    <li><a href="#home" class="nav-link">Home</a></li>
                    <li><a href="#about" class="nav-link">About</a></li>
                    <li><a href="#services" class="nav-link">Services</a></li>
                    <li><a href="#testimonials" class="nav-link">Testimonials</a></li>
                    <li><a href="#contact" class="nav-link">Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <section id="home" class="hero">
        <div class="container">
            <h1>Welcome to My Complete Website</h1>
            <p>A responsive template with HTML, CSS, and JavaScript</p>
            <a href="#about" class="btn">Explore More</a>
        </div>
    </section>

    <section id="about" class="section">
        <div class="container">
            <h2>About Us</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>We are a creative team dedicated to building amazing websites. Our goal is to provide the best solutions for our clients.</p>
                    <p>With years of experience in web development, we know how to create websites that are both beautiful and functional.</p>
                    <p>Our team consists of passionate designers and developers who stay up-to-date with the latest web technologies.</p>
                </div>
                <div class="about-image">
                    <img src="https://images.unsplash.com/photo-1522071820081-009f0129c71c?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Our Team">
                </div>
            </div>
        </div>
    </section>

    <section id="services" class="section dark">
        <div class="container">
            <h2>Our Services</h2>
            <div class="services-grid">
                <div class="service">
                    <i class="fas fa-code"></i>
                    <h3>Web Development</h3>
                    <p>Custom websites built with modern technologies like HTML5, CSS3, and JavaScript.</p>
                </div>
                <div class="service">
                    <i class="fas fa-mobile-alt"></i>
                    <h3>Responsive Design</h3>
                    <p>Websites that look and function perfectly on all devices from mobile to desktop.</p>
                </div>
                <div class="service">
                    <i class="fas fa-search"></i>
                    <h3>SEO Optimization</h3>
                    <p>Get found on search engines with our comprehensive SEO services.</p>
                </div>
                <div class="service">
                    <i class="fas fa-paint-brush"></i>
                    <h3>UI/UX Design</h3>
                    <p>Beautiful, intuitive interfaces designed with user experience in mind.</p>
                </div>
                <div class="service">
                    <i class="fas fa-server"></i>
                    <h3>Web Hosting</h3>
                    <p>Reliable, fast hosting solutions for your website with 99.9% uptime.</p>
                </div>
                <div class="service">
                    <i class="fas fa-chart-line"></i>
                    <h3>Analytics</h3>
                    <p>Track your website's performance and make data-driven decisions.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="testimonials" class="section testimonials">
        <div class="container">
            <h2>What Our Clients Say</h2>
            <div class="testimonial-slider">
                <div class="testimonial active">
                    <img src="https://randomuser.me/api/portraits/women/32.jpg" alt="Client 1">
                    <p>"This team transformed our online presence completely. Our website traffic has increased by 300% since they redesigned our site!"</p>
                    <div class="testimonial-author">- Sarah Johnson, Marketing Director</div>
                </div>
                <div class="testimonial">
                    <img src="https://randomuser.me/api/portraits/men/45.jpg" alt="Client 2">
                    <p>"The attention to detail and customer service is exceptional. They delivered our project ahead of schedule and under budget."</p>
                    <div class="testimonial-author">- Michael Chen, CEO</div>
                </div>
                <div class="testimonial">
                    <img src="https://randomuser.me/api/portraits/women/68.jpg" alt="Client 3">
                    <p>"We've worked with many web developers, but none have matched the quality and professionalism of this team."</p>
                    <div class="testimonial-author">- Emily Rodriguez, Small Business Owner</div>
                </div>
            </div>
            <div class="slider-dots">
                <span class="dot active" data-slide="0"></span>
                <span class="dot" data-slide="1"></span>
                <span class="dot" data-slide="2"></span>
            </div>
        </div>
    </section>

    <section id="contact" class="section">
        <div class="container">
            <h2>Contact Us</h2>
            <form id="contactForm" class="contact-form">
                <div class="form-group">
                    <label for="name">Name</label>
                    <input type="text" id="name" name="name" required>
                </div>
                <div class="form-group">
                    <label for="email">Email</label>
                    <input type="email" id="email" name="email" required>
                </div>
                <div class="form-group">
                    <label for="subject">Subject</label>
                    <input type="text" id="subject" name="subject" required>
                </div>
                <div class="form-group">
                    <label for="message">Message</label>
                    <textarea id="message" name="message" required></textarea>
                </div>
                <button type="submit" class="btn">Send Message</button>
                <div id="form-message" class="form-message"></div>
            </form>
        </div>
    </section>

    <footer>
        <div class="container">
            <p>&copy; <span id="year"></span> My Complete Website. All rights reserved.</p>
            <div class="social-links">
                <a href="#"><i class="fab fa-facebook"></i></a>
                <a href="#"><i class="fab fa-twitter"></i></a>
                <a href="#"><i class="fab fa-instagram"></i></a>
                <a href="#"><i class="fab fa-linkedin"></i></a>
                <a href="#"><i class="fab fa-github"></i></a>
            </div>
        </div>
    </footer>

    <script>
        // JavaScript for the website
        document.addEventListener('DOM
