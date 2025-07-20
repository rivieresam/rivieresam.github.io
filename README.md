<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Purple Sky - B2B Marketing Solutions</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
            font-feature-settings: 'cv02', 'cv03', 'cv04', 'cv11';
        }

        /* Animated purple sky background */
        .sky-background {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, 
                #1a1a2e 0%, 
                #16213e 20%, 
                #0f3460 40%, 
                #533483 60%, 
                #7209b7 80%, 
                #a663cc 100%);
            animation: skyShift 20s ease-in-out infinite;
            z-index: -2;
        }

        @keyframes skyShift {
            0%, 100% { background: linear-gradient(45deg, #1a1a2e 0%, #16213e 20%, #0f3460 40%, #533483 60%, #7209b7 80%, #a663cc 100%); }
            50% { background: linear-gradient(45deg, #0f0f23 0%, #1a1a2e 20%, #16213e 40%, #0f3460 60%, #533483 80%, #7209b7 100%); }
        }

        /* Floating clouds */
        .clouds {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .cloud {
            position: absolute;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50px;
            animation: float 30s linear infinite;
        }

        .cloud:before, .cloud:after {
            content: '';
            position: absolute;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50px;
        }

        .cloud1 {
            width: 100px;
            height: 40px;
            top: 20%;
            left: -120px;
            animation-duration: 25s;
        }

        .cloud1:before {
            width: 50px;
            height: 50px;
            top: -25px;
            left: 10px;
        }

        .cloud1:after {
            width: 60px;
            height: 40px;
            top: -15px;
            right: 10px;
        }

        .cloud2 {
            width: 80px;
            height: 30px;
            top: 50%;
            left: -100px;
            animation-duration: 35s;
            animation-delay: -10s;
        }

        .cloud2:before {
            width: 40px;
            height: 40px;
            top: -20px;
            left: 15px;
        }

        .cloud2:after {
            width: 50px;
            height: 30px;
            top: -10px;
            right: 15px;
        }

        @keyframes float {
            0% { left: -120px; }
            100% { left: 100%; }
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 1rem 2rem;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            transition: all 0.3s ease;
        }

        nav.scrolled {
            background: rgba(255, 255, 255, 0.98);
            box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo-icon {
            width: 40px;
            height: 40px;
            background: linear-gradient(45deg, #8B5CF6, #A855F7);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            font-size: 18px;
        }

        .logo-text {
            font-size: 1.5rem;
            font-weight: bold;
            background: linear-gradient(45deg, #6B46C1, #8B5CF6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #6B46C1;
            font-weight: 500;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: #8B5CF6;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(45deg, #6B46C1, #8B5CF6);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Sections */
        section {
            min-height: 100vh;
            padding: 6rem 2rem 4rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .container {
            max-width: 1200px;
            width: 100%;
            text-align: center;
        }

        /* Hero Section */
        .hero {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 4rem 2rem;
            margin: 2rem auto;
            max-width: 800px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: bold;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #ffffff, #e0e7ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            line-height: 1.2;
        }

        .hero p {
            font-size: 1.3rem;
            color: #e0e7ff;
            margin-bottom: 2rem;
            font-weight: 300;
        }

        .cta-button {
            display: inline-block;
            padding: 1rem 2rem;
            background: linear-gradient(45deg, #6B46C1, #8B5CF6);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(107, 70, 193, 0.3);
            animation: pulse 2s infinite;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(107, 70, 193, 0.4);
        }

        @keyframes pulse {
            0%, 100% { box-shadow: 0 10px 30px rgba(107, 70, 193, 0.3); }
            50% { box-shadow: 0 10px 40px rgba(107, 70, 193, 0.5); }
        }

        /* Content Sections */
        .content-section {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 3rem;
            margin: 2rem auto;
            max-width: 900px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .content-section h2 {
            font-size: 2.5rem;
            font-weight: bold;
            margin-bottom: 2rem;
            background: linear-gradient(45deg, #6B46C1, #8B5CF6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .content-section p {
            font-size: 1.1rem;
            color: #4B5563;
            line-height: 1.8;
            margin-bottom: 1.5rem;
        }

        /* Contact Info */
        .contact-info {
            background: linear-gradient(45deg, #6B46C1, #8B5CF6);
            color: white;
            padding: 2rem;
            border-radius: 15px;
            margin-top: 2rem;
        }

        .contact-info h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        .contact-details {
            display: grid;
            gap: 0.8rem;
            text-align: left;
            max-width: 400px;
            margin: 0 auto;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 0.5rem;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 8px;
            transition: background 0.3s ease;
        }

        .contact-item:hover {
            background: rgba(255, 255, 255, 0.2);
        }

        .contact-icon {
            width: 20px;
            height: 20px;
            flex-shrink: 0;
        }

        /* Mobile Responsiveness */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            section {
                padding: 4rem 1rem 2rem;
            }

            .content-section {
                padding: 2rem 1.5rem;
            }

            .contact-details {
                text-align: center;
            }
        }

        /* Smooth scrolling */
        html {
            scroll-behavior: smooth;
        }

        /* Stars animation */
        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .star {
            position: absolute;
            width: 2px;
            height: 2px;
            background: white;
            border-radius: 50%;
            animation: twinkle 3s infinite;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.3; }
            50% { opacity: 1; }
        }
    </style>
</head>
<body>
    <!-- Sky background with floating clouds -->
    <div class="sky-background"></div>
    <div class="clouds">
        <div class="cloud cloud1"></div>
        <div class="cloud cloud2"></div>
    </div>
    <div class="stars" id="stars"></div>

    <!-- Navigation -->
    <nav id="navbar">
        <div class="nav-container">
            <div class="logo">
                <div class="logo-icon">☀</div>
                <div class="logo-text">Purple Sky</div>
            </div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home">
        <div class="container">
            <div class="hero">
                <h1>Purple Sky</h1>
                <p>B2B Marketing Solutions for emerging businesses</p>
                <a href="#about" class="cta-button">Learn More</a>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about">
        <div class="container">
            <div class="content-section">
                <h2>About Us</h2>
                <p>We are a Virginia-based Marketing company focused on demand generation services for emerging and midmarket B2B firms. We help with technology assessments, new project implementation, and G2M for demand generation teams.</p>
                <p>Our expertise lies in understanding the unique challenges that growing businesses face in today's competitive landscape. We provide tailored solutions that drive measurable results and sustainable growth.</p>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <div class="container">
            <div class="content-section">
                <h2>Contact Us</h2>
                <p>Ready to elevate your B2B marketing strategy? Get in touch with our team to discuss how we can help your business grow.</p>
                
                <div class="contact-info">
                    <h3>Get In Touch</h3>
                    <div class="contact-details">
                        <div class="contact-item">
                            <svg class="contact-icon" fill="currentColor" viewBox="0 0 20 20">
                                <path d="M10 9a3 3 0 100-6 3 3 0 000 6zm-7 9a7 7 0 1114 0H3z"/>
                            </svg>
                            <span>Samuel Riviere</span>
                        </div>
                        <div class="contact-item">
                            <svg class="contact-icon" fill="currentColor" viewBox="0 0 20 20">
                                <path d="M2.003 5.884L10 9.882l7.997-3.998A2 2 0 0016 4H4a2 2 0 00-1.997 1.884z"/>
                                <path d="M18 8.118l-8 4-8-4V14a2 2 0 002 2h12a2 2 0 002-2V8.118z"/>
                            </svg>
                            <span>riviere@purplesky.biz</span>
                        </div>
                        <div class="contact-item">
                            <svg class="contact-icon" fill="currentColor" viewBox="0 0 20 20">
                                <path d="M2 3a1 1 0 011-1h2.153a1 1 0 01.986.836l.74 4.435a1 1 0 01-.54 1.06l-1.548.773a11.037 11.037 0 006.105 6.105l.774-1.548a1 1 0 011.059-.54l4.435.74a1 1 0 01.836.986V17a1 1 0 01-1 1h-2C7.82 18 2 12.18 2 5V3z"/>
                            </svg>
                            <span>(571) 583-9715</span>
                        </div>
                        <div class="contact-item">
                            <svg class="contact-icon" fill="currentColor" viewBox="0 0 20 20">
                                <path fillRule="evenodd" d="M5.05 4.05a7 7 0 119.9 9.9L10 18.9l-4.95-4.95a7 7 0 010-9.9zM10 11a2 2 0 100-4 2 2 0 000 4z" clipRule="evenodd"/>
                            </svg>
                            <span>1405 S Fern St #92805<br>Arlington, VA 22202</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <script>
        // Create stars
        function createStars() {
            const starsContainer = document.getElementById('stars');
            const numberOfStars = 50;

            for (let i = 0; i < numberOfStars; i++) {
                const star = document.createElement('div');
                star.className = 'star';
                star.style.left = Math.random() * 100 + '%';
                star.style.top = Math.random() * 100 + '%';
                star.style.animationDelay = Math.random() * 3 + 's';
                starsContainer.appendChild(star);
            }
        }

        // Navbar scroll effect
        window.addEventListener('scroll', function() {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Initialize stars when page loads
        document.addEventListener('DOMContentLoaded', createStars);

        // Add some interactivity to contact items
        document.querySelectorAll('.contact-item').forEach(item => {
            item.addEventListener('click', function() {
                const text = this.querySelector('span').textContent;
                if (text.includes('@')) {
                    window.location.href = 'mailto:' + text;
                } else if (text.match(/\(\d{3}\)/)) {
                    window.location.href = 'tel:' + text.replace(/\D/g, '');
                }
            });
        });
    </script>
</body>
</html>
