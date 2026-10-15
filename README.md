<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Seaborne MCS - Air Travel & Flight Bookings</title>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <!-- FontAwesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        /* Global Reset */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background-color: #f9fbfd;
            color: #333;
            line-height: 1.6;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
        }

        /* Navbar */
        .navbar {
            background: #ffffff;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
            position: sticky;
            top: 0;
            z-index: 1000;
            padding: 15px 0;
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo h2 {
            color: #0b2545;
            font-weight: 700;
        }

        .logo span {
            color: #134074;
            font-weight: 400;
            font-size: 0.9rem;
            display: block;
        }

        .nav-links {
            display: flex;
            align-items: center;
            gap: 30px;
        }

        .nav-links a {
            text-decoration: none;
            color: #495057;
            font-weight: 500;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: #134074;
        }

        .btn-nav {
            background-color: #134074;
            color: #fff !important;
            padding: 8px 20px;
            border-radius: 4px;
            transition: background 0.3s;
        }

        .btn-nav:hover {
            background-color: #0b2545;
        }

        /* Hero Section */
        .hero {
            position: relative;
            background: linear-gradient(rgba(11, 37, 69, 0.75), rgba(19, 64, 116, 0.75)), url('https://images.unsplash.com/photo-1436491865332-7a61a109cc05?auto=format&fit=crop&w=1920&q=80') no-repeat center center/cover;
            height: 80vh;
            display: flex;
            align-items: center;
            text-align: center;
            color: #fff;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 800px;
            margin: 0 auto;
        }

        .hero-content h1 {
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 20px;
        }

        .hero-content p {
            font-size: 1.1rem;
            margin-bottom: 30px;
            color: #e2e8f0;
        }

        .hero-buttons {
            display: flex;
            justify-content: center;
            gap: 15px;
        }

        /* Buttons */
        .btn {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            padding: 12px 28px;
            font-size: 1rem;
            font-weight: 600;
            border-radius: 6px;
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .btn-primary {
            background-color: #ee6c4d;
            color: #fff;
        }

        .btn-primary:hover {
            background-color: #d95332;
            transform: translateY(-2px);
        }

        .btn-secondary {
            background-color: rgba(255, 255, 255, 0.15);
            color: #fff;
            border: 1px solid rgba(255, 255, 255, 0.4);
        }

        .btn-secondary:hover {
            background-color: rgba(255, 255, 255, 0.3);
        }

        /* Features Section */
        .features {
            padding: 80px 0;
            background: #ffffff;
        }

        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }

        .section-title h2 {
            font-size: 2.2rem;
            color: #0b2545;
            margin-bottom: 10px;
        }

        .section-title p {
            color: #6c757d;
        }

        .feature-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .feature-card {
            background: #f8f9fa;
            padding: 40px 30px;
            border-radius: 8px;
            text-align: center;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .feature-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.08);
        }

        .feature-card .icon {
            font-size: 2.5rem;
            color: #134074;
            margin-bottom: 20px;
        }

        .feature-card h3 {
            font-size: 1.25rem;
            color: #0b2545;
            margin-bottom: 15px;
        }

        .feature-card p {
            color: #6c757d;
            font-size: 0.95rem;
        }

        /* CTA Banner */
        .cta-banner {
            background: #0b2545;
            color: #fff;
            padding: 60px 0;
            text-align: center;
        }

        .cta-content h2 {
            font-size: 2rem;
            margin-bottom: 15px;
        }

        .cta-content p {
            color: #cbd5e1;
            margin-bottom: 25px;
        }

        /* Footer */
        .footer {
            background: #05162a;
            color: #94a3b8;
            padding: 20px 0;
            font-size: 0.9rem;
        }

        .footer-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .social-links {
            display: flex;
            gap: 15px;
        }

        .social-links a {
            color: #94a3b8;
            text-decoration: none;
            transition: color 0.3s;
        }

        .social-links a:hover {
            color: #fff;
        }

        /* Responsive Media Query */
        @media (max-width: 768px) {
            .hero-content h1 {
                font-size: 2.2rem;
            }
            .nav-links {
                display: none;
            }
            .footer-container {
                flex-direction: column;
                gap: 10px;
                text-align: center;
            }
        }
    </style>
</head>
<body>

    <!-- Header / Navbar -->
    <header class="navbar">
        <div class="container nav-container">
            <div class="logo">
                <h2>Seaborne MCS <span>Air Travel</span></h2>
            </div>
            <nav class="nav-links">
                <a href="#home">Home</a>
                <a href="#features">Why Us</a>
                <a href="#services">Services</a>
                <a href="https://www.seabornemcs.in/air-travel.html" class="btn-nav" target="_blank">Book Now</a>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-overlay"></div>
        <div class="container hero-content">
            <h1>Your Journey Begins With The Best Flights</h1>
            <p>Experience seamless flight bookings, affordable global airfares, and trusted travel support tailored for your professional and personal trips.</p>
            <div class="hero-buttons">
                <!-- Direct link to your existing flight booking page -->
                <a href="https://www.seabornemcs.in/air-travel.html" target="_blank" class="btn btn-primary">
                    <i class="fa-solid fa-plane-departure"></i> Find Flight
                </a>
                <a href="#features" class="btn btn-secondary">Learn More</a>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section id="features" class="features">
        <div class="container">
            <div class="section-title">
                <h2>Why Book With Us</h2>
                <p>We make air travel comfortable, reliable, and cost-effective.</p>
            </div>
            <div class="feature-grid">
                <div class="feature-card">
                    <div class="icon"><i class="fa-solid fa-tags"></i></div>
                    <h3>Best Price Guarantee</h3>
                    <p>Get unbeatable airfares and exclusive discounts on international and domestic flights.</p>
                </div>
                <div class="feature-card">
                    <div class="icon"><i class="fa-solid fa-headset"></i></div>
                    <h3>24/7 Travel Support</h3>
                    <p>Our dedicated team is always here to assist you with rescheduling, cancellations, and queries.</p>
                </div>
                <div class="feature-card">
                    <div class="icon"><i class="fa-solid fa-shield-halved"></i></div>
                    <h3>Secure & Fast Booking</h3>
                    <p>Quick processing with secure pathways to ensure your travel plans are stress-free.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Call to Action Banner -->
    <section class="cta-banner">
        <div class="container cta-content">
            <h2>Ready to Explore the Skies?</h2>
            <p>Search schedules, compare airlines, and secure your tickets in just a few clicks.</p>
            <a href="https://www.seabornemcs.in/air-travel.html" target="_blank" class="btn btn-primary">
                <i class="fa-solid fa-magnifying-glass"></i> Find Flight Now
            </a>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="container footer-container">
            <p>&copy; 2026 Seaborne MCS Air Travel. All Rights Reserved.</p>
            <div class="social-links">
                <a href="#"><i class="fa-brands fa-facebook-f"></i></a>
                <a href="#"><i class="fa-brands fa-twitter"></i></a>
                <a href="#"><i class="fa-brands fa-instagram"></i></a>
                <a href="#"><i class="fa-brands fa-linkedin-in"></i></a>
            </div>
        </div>
    </footer>

</body>
</html>
