<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EM Friendly - Prayer Spaces & Halal Dining</title>
    <style>
        :root {
            --primary-color: #2E7D32; /* Updated to green palette */
            --secondary-color: #C8E6C9;
            --accent-color: #81C784;
            --light-color: #F1F8E9;
            --food-color: #FF8F00; /* Updated to amber */
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background-color: var(--light-color);
            color: #333;
            scroll-behavior: smooth;
        }
        
        header {
            background-color: var(--primary-color);
            color: white;
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            display: flex;
            align-items: center;
        }
        
        .logo-icon {
            margin-right: 0.5rem;
            font-size: 2rem;
        }
        
        nav ul {
            display: flex;
            list-style: none;
            margin: 0;
            padding: 0;
        }
        
        nav ul li {
            margin-left: 1.5rem;
        }
        
        nav ul li a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            padding: 0.5rem 1rem;
            border-radius: 4px;
            transition: background-color 0.3s;
        }
        
        nav ul li a:hover {
            background-color: rgba(255,255,255,0.2);
        }
        
        nav ul li a.active {
            background-color: rgba(255,255,255,0.3);
        }
        
        .language-selector {
            background: none;
            border: 1px solid white;
            color: white;
            padding: 0.3rem;
            border-radius: 4px;
            margin-left: 1.5rem;
        }
        
        .hero {
            background-image: linear-gradient(rgba(0,0,0,0.3), rgba(0,0,0,0.3)), url('prayer-space.jpg');
            background-size: cover;
            height: 60vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            color: white;
            padding: 0 2rem;
        }
        
        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin-bottom: 2rem;
        }
        
        .quick-nav {
            display: flex;
            justify-content: center;
            margin: 1rem 0;
            position: sticky;
            top: 80px;
            z-index: 90;
            background-color: var(--light-color);
            padding: 1rem 0;
            box-shadow: 0 2px 5px rgba(0,0,0,0.05);
        }
        
        .quick-nav a {
            margin: 0 1rem;
            padding: 0.8rem 1.5rem;
            background-color: var(--primary-color);
            color: white;
            text-decoration: none;
            border-radius: 4px;
            font-weight: bold;
            transition: transform 0.3s, background-color 0.3s;
            display: flex;
            align-items: center;
        }
        
        .quick-nav a:nth-child(2) {
            background-color: var(--food-color);
        }
        
        .quick-nav a:hover {
            transform: translateY(-3px);
        }
        
        .quick-nav a:first-child:hover {
            background-color: #1B5E20;
        }
        
        .quick-nav a:nth-child(2):hover {
            background-color: #E65100;
        }
        
        .quick-nav-icon {
            margin-right: 0.5rem;
        }
        
        .main-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }
        
        .section {
            padding: 2rem 0;
        }
        
        .section-title {
            color: var(--primary-color);
            border-bottom: 2px solid var(--accent-color);
            padding-bottom: 0.5rem;
            margin-top: 0;
            scroll-margin-top: 150px;
            display: flex;
            align-items: center;
        }
        
        .section-title-icon {
            margin-right: 0.5rem;
        }
        
        .dining-section .section-title {
            color: var(--food-color);
            border-bottom-color: var(--food-color);
        }
        
        .room-grid, .restaurant-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }
        
        .room-card, .restaurant-card {
            border: 1px solid var(--accent-color);
            border-radius: 8px;
            overflow: hidden;
            transition: transform 0.3s, box-shadow 0.3s;
            background-color: white;
        }
        
        .restaurant-card {
            border-color: var(--food-color);
        }
        
        .room-card:hover, .restaurant-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .room-image, .restaurant-image {
            height: 200px;
            background-color: var(--secondary-color);
            background-size: cover;
            background-position: center;
        }
        
        .restaurant-image {
            background-color: #FFE0B2;
        }
        
        .room-info, .restaurant-info {
            padding: 1.5rem;
        }
        
        .room-info h3, .restaurant-info h3 {
            margin-top: 0;
        }
        
        .room-info h3 {
            color: var(--primary-color);
        }
        
        .restaurant-info h3 {
            color: var(--food-color);
        }
        
        .availability, .halal-status {
            display: flex;
            align-items: center;
            margin: 0.5rem 0;
        }
        
        .availability-indicator, .halal-indicator {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            margin-right: 0.5rem;
        }
        
        .available {
            background-color: #4CAF50;
        }
        
        .unavailable {
            background-color: #F44336;
        }
        
        .halal-certified {
            background-color: #2ECC71;
        }
        
        .non-halal {
            background-color: #E74C3C;
        }
        
        .vegetarian-friendly {
            background-color: #27AE60;
        }
        
        .book-btn, .view-menu-btn {
            color: white;
            border: none;
            padding: 0.7rem 1.5rem;
            border-radius: 4px;
            cursor: pointer;
            font-weight: bold;
            width: 100%;
            margin-top: 1rem;
            transition: background-color 0.3s;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        
        .book-btn {
            background-color: var(--primary-color);
        }
        
        .view-menu-btn {
            background-color: var(--food-color);
        }
        
        .book-btn:hover {
            background-color: #1B5E20;
        }
        
        .view-menu-btn:hover {
            background-color: #E65100;
        }
        
        .btn-icon {
            margin-right: 0.5rem;
        }
        
        .restaurant-meta {
            display: flex;
            justify-content: space-between;
            margin: 0.5rem 0;
        }
        
        .distance, .price-range {
            display: flex;
            align-items: center;
        }
        
        .distance svg, .price-range svg {
            margin-right: 0.3rem;
        }
        
        footer {
            background-color: var(--primary-color);
            color: white;
            text-align: center;
            padding: 2rem;
            margin-top: 3rem;
        }
        
        .back-to-top {
            display: block;
            text-align: center;
            margin: 2rem 0;
        }
        
        .back-to-top a {
            color: var(--primary-color);
            text-decoration: none;
            font-weight: bold;
            padding: 0.5rem 1rem;
            border: 1px solid var(--primary-color);
            border-radius: 4px;
            transition: all 0.3s;
        }
        
        .back-to-top a:hover {
            background-color: var(--primary-color);
            color: white;
        }

        /* New Coupon Section Styles */
        .coupon-section {
            background-color: white;
            padding: 1.5rem;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            margin-bottom: 2rem;
            border: 1px dashed var(--food-color);
        }

        .coupon-section h3 {
            color: var(--food-color);
            margin-top: 0;
            margin-bottom: 1rem;
        }

        #coupon-code {
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 4px;
            width: 200px;
            margin-right: 0.5rem;
            font-size: 1rem;
        }

        #apply-coupon-btn {
            background-color: var(--food-color);
            color: white;
            border: none;
            padding: 0.8rem 1.5rem;
            border-radius: 4px;
            cursor: pointer;
            font-weight: bold;
            transition: background-color 0.3s;
        }

        #apply-coupon-btn:hover {
            background-color: #E65100;
        }

        #discount-message {
            margin-top: 1rem;
            padding: 0.5rem;
            border-radius: 4px;
            display: none;
        }

        .active-discount {
            background-color: #E8F5E9;
            padding: 1rem;
            border-radius: 8px;
            margin-top: 1rem;
            border-left: 4px solid var(--primary-color);
        }
    </style>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" rel="stylesheet">
</head>
<body>
    <header>
        <div class="logo">
            <span class="logo-icon"><i class="fas fa-hands-praying"></i></span>
            EM Friendly
        </div>
        <nav>
            <ul>
                <li><a href="#" class="active">Home</a></li>
                <li><a href="#prayer-rooms">Prayer Spaces</a></li>
                <li><a href="#dining">Dining</a></li>
                <li><a href="#">FAQ</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>
        <select class="language-selector">
            <option value="en">English</option>
            <option value="ar">العربية</option>
            <option value="ur">اردو</option>
            <option value="fr">Français</option>
        </select>
    </header>
    
    <section class="hero">
        <h1>EM Friendly Spaces</h1>
        <p>Discover welcoming prayer spaces and halal dining options designed for your comfort</p>
    </section>
    
    <div class="quick-nav">
        <a href="#prayer-rooms">
            <span class="quick-nav-icon"><i class="fas fa-mosque"></i></span>
            Find Prayer Spaces
        </a>
        <a href="#dining">
            <span class="quick-nav-icon"><i class="fas fa-utensils"></i></span>
            Explore Dining Options
        </a>
    </div>
    
    <div class="main-container">
        <section id="prayer-rooms" class="section">
            <h2 class="section-title">
                <span class="section-title-icon"><i class="fas fa-mosque"></i></span>
                EM Friendly Prayer Spaces
            </h2>
            <p>Clean, comfortable spaces with real-time availability tracking</p>
            
            <div class="room-grid">
                <div class="room-card">
                    <div class="room-image" style="background-image: url('prayer-space1.jpg');"></div>
                    <div class="room-info">
                        <h3>Tranquility Space</h3>
                        <p>Capacity: 8 people • Wudu facilities available</p>
                        <div class="availability">
                            <div class="availability-indicator available"></div>
                            <span>Available - 45 mins remaining</span>
                        </div>
                        <button class="book-btn">
                            <span class="btn-icon"><i class="far fa-calendar-check"></i></span>
                            Book Now
                        </button>
                    </div>
                </div>
                
                <div class="room-card">
                    <div class="room-image" style="background-image: url('prayer-space2.jpg');"></div>
                    <div class="room-info">
                        <h3>Harmony Space</h3>
                        <p>Capacity: 6 people • Separate family area</p>
                        <div class="availability">
                            <div class="availability-indicator unavailable"></div>
                            <span>Occupied - 15 mins remaining</span>
                        </div>
                        <button class="book-btn" disabled>
                            <span class="btn-icon"><i class="fas fa-clock"></i></span>
                            Currently Occupied
                        </button>
                    </div>
                </div>
                
                <div class="room-card">
                    <div class="room-image" style="background-image: url('prayer-space3.jpg');"></div>
                    <div class="room-info">
                        <h3>Serenity Corner</h3>
                        <p>Capacity: 4 people • Quiet meditation space</p>
                        <div class="availability">
                            <div class="availability-indicator available"></div>
                            <span>Available - 60 mins remaining</span>
                        </div>
                        <button class="book-btn">
                            <span class="btn-icon"><i class="far fa-calendar-check"></i></span>
                            Book Now
                        </button>
                    </div>
                </div>
            </div>
            
            <div class="back-to-top">
                <a href="#"><i class="fas fa-arrow-up"></i> Back to Top</a>
            </div>
        </section>
        
        <section id="dining" class="section dining-section">
            <h2 class="section-title">
                <span class="section-title-icon"><i class="fas fa-utensils"></i></span>
                EM Friendly Dining
            </h2>
            <p>Halal-certified and Muslim-friendly restaurants near our prayer spaces</p>

            <!-- Coupon Section -->
            <div class="coupon-section">
                <h3><i class="fas fa-tag"></i> Special Offers</h3>
                <div style="display: flex; align-items: center; margin-bottom: 1rem;">
                    <input type="text" id="coupon-code" placeholder="Enter coupon code">
                    <button id="apply-coupon-btn">Apply</button>
                </div>
                <div id="discount-message"></div>
                <div id="active-discount" class="active-discount" style="display: none;">
                    <strong>Active Discount:</strong> <span id="discount-details"></span>
                </div>
                <p style="font-size: 0.9rem; margin-top: 0.5rem;">Try codes: HALAL10 (10% off), EMFREESHIP ($5 off), HALAL20 (20% off)</p>
            </div>
            
            <div class="restaurant-grid">
                <div class="restaurant-card">
                    <div class="restaurant-image" style="background-image: url('halal-restaurant1.jpg');"></div>
                    <div class="restaurant-info">
                        <h3>Zaitoun Kitchen</h3>
                        <div class="restaurant-meta">
                            <div class="distance">
                                <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                    <circle cx="12" cy="10" r="3"/><path d="M12 2a8 8 0 0 0-8 8c0 1.892.402 3.13 1.5 4.5L12 22l6.5-7.5c1.098-1.37 1.5-2.608 1.5-4.5a8 8 0 0 0-8-8z"/>
                                </svg>
                                <span>0.2 miles</span>
                            </div>
                            <div class="price-range">
                                <span>$$</span>
                            </div>
                        </div>
                        <div class="halal-status">
                            <div class="halal-indicator halal-certified"></div>
                            <span>Halal Certified • Prayer space available</span>
                        </div>
                        <button class="view-menu-btn">
                            <span class="btn-icon"><i class="fas fa-book-open"></i></span>
                            View Menu
                        </button>
                    </div>
                </div>
                
                <div class="restaurant-card">
                    <div class="restaurant-image" style="background-image: url('halal-restaurant2.jpg');"></div>
                    <div class="restaurant-info">
                        <h3>Green Leaf Bistro</h3>
                        <div class="restaurant-meta">
                            <div class="distance">
                                <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                    <circle cx="12" cy="10" r="3"/><path d="M12 2a8 8 0 0 0-8 8c0 1.892.402 3.13 1.5 4.5L12 22l6.5-7.5c1.098-1.37 1.5-2.608 1.5-4.5a8 8 0 0 0-8-8z"/>
                                </svg>
                                <span>0.5 miles</span>
                            </div>
                            <div class="price-range">
                                <span>$</span>
                            </div>
                        </div>
                        <div class="halal-status">
                            <div class="halal-indicator vegetarian-friendly"></div>
                            <span>Vegetarian Friendly • Halal options</span>
                        </div>
                        <button class="view-menu-btn">
                            <span class="btn-icon"><i class="fas fa-book-open"></i></span>
                            View Menu
                        </button>
                    </div>
                </div>
                
                <div class="restaurant-card">
                    <div class="restaurant-image" style="background-image: url('halal-restaurant3.jpg');"></div>
                    <div class="restaurant-info">
                        <h3>Sultan's Table</h3>
                        <div class="restaurant-meta">
                            <div class="distance">
                                <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                    <circle cx="12" cy="10" r="3"/><path d="M12 2a8 8 0 0 0-8 8c0 1.892.402 3.13 1.5 4.5L12 22l6.5-7.5c1.098-1.37 1.5-2.608 1.5-4.5a8 8 0 0 0-8-8z"/>
                                </svg>
                                <span>0.3 miles</span>
                            </div>
                            <div class="price-range">
                                <span>$$$</span>
                            </div>
                        </div>
                        <div class="halal-status">
                            <div class="halal-indicator halal-certified"></div>
                            <span>Halal Certified • Prayer room available</span>
                        </div>
                        <button class="view-menu-btn">
                            <span class="btn-icon"><i class="fas fa-book-open"></i></span>
                            View Menu
                        </button>
                    </div>
                </div>
            </div>
            
            <div class="back-to-top">
                <a href="#"><i class="fas fa-arrow-up"></i> Back to Top</a>
            </div>
        </section>
    </div>
    
    <footer>
        <p>&copy; 2023 EM Friendly - Welcoming Spaces for All. All rights reserved.</p>
    </footer>

    <script>
        // Highlight active navigation link based on scroll position
        window.addEventListener('scroll', function() {
            const sections = document.querySelectorAll('section');
            const navLinks = document.querySelectorAll('nav ul li a');
            
            let currentSection = '';
            
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                if (window.scrollY >= sectionTop - 150) {
                    currentSection = section.getAttribute('id');
                }
            });
            
            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href') === `#${currentSection}` || 
                   (currentSection === '' && link.getAttribute('href') === '#')) {
                    link.classList.add('active');
                }
            });
        });

        // Coupon System JavaScript
        document.addEventListener('DOMContentLoaded', function() {
            const validCoupons = {
                'HALAL10': { type: 'percentage', value: 10, description: '10% off your meal' },
                'EMFREESHIP': { type: 'fixed', value: 5, description: '$5 off your order' },
                'HALAL20': { type: 'percentage', value: 20, description: '20% off your meal' }
            };

            const applyCouponBtn = document.getElementById('apply-coupon-btn');
            const couponInput = document.getElementById('coupon-code');
            const discountMessage = document.getElementById('discount-message');
            const activeDiscount = document.getElementById('active-discount');
            const discountDetails = document.getElementById('discount-details');

            applyCouponBtn.addEventListener('click', function() {
                const couponCode = couponInput.value.trim().toUpperCase();
                
                if (validCoupons[couponCode]) {
                    const coupon = validCoupons[couponCode];
                    let message = '';
                    
                    if (coupon.type === 'percentage') {
                        message = `Success! ${coupon.value}% discount applied.`;
                    } else {
                        message = `Success! $${coupon.value} discount applied.`;
                    }
                    
                    discountMessage.textContent = message;
                    discountMessage.style.color = 'green';
                    discountMessage.style.display = 'block';
                    
                    discountDetails.textContent = coupon.description;
                    activeDiscount.style.display = 'block';
                    
                    // Store the active coupon in localStorage
                    localStorage.setItem('activeCoupon', JSON.stringify(coupon));
                    localStorage.setItem('couponCode', couponCode);
                    
                    // Hide message after 5 seconds
                    setTimeout(() => {
                        discountMessage.style.display = 'none';
                    }, 5000);
                } else {
                    discountMessage.textContent = 'Invalid coupon code. Please try again.';
                    discountMessage.style.color = 'red';
                    discountMessage.style.display = 'block';
                    activeDiscount.style.display = 'none';
                    
                    // Clear any stored coupon
                    localStorage.removeItem('activeCoupon');
                    localStorage.removeItem('couponCode');
                    
                    // Hide message after 5 seconds
                    setTimeout(() => {
                        discountMessage.style.display = 'none';
                    }, 5000);
                }
            });

            // Check for existing coupon on page load
            const storedCoupon = localStorage.getItem('activeCoupon');
            const storedCode = localStorage.getItem('couponCode');
            
            if (storedCoupon) {
                const coupon = JSON.parse(storedCoupon);
                discountDetails.textContent = coupon.description;
                activeDiscount.style.display = 'block';
                couponInput.value = storedCode;
            }
        });
    </script>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <!-- ... (keep all existing head content) ... -->
</head>
<body>
    <!-- ... (keep all existing body content until footer) ... -->

    <footer>
        <p>&copy; 2023 EM Friendly - Welcoming Spaces for All. All rights reserved.</p>
        <p style="margin-top: 1rem;">
            <a href="https://translate.google.com/" target="_blank" style="color: white; text-decoration: underline;">
                <i class="fas fa-language"></i> Need translation help?
            </a>
        </p>
    </footer>

    <!-- ... (keep all existing scripts) ... -->
</body>
</html>
