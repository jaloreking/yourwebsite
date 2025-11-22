<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta name="description" content="Online store for kids clothing - Kidswear" />
    <title>Kids Clothing - Children's Apparel Store</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" />
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary: #FF6B8B;
            --secondary: #4ECDC4;
            --accent: #FFD166;
            --light: #F7F9FC;
            --dark: #2D3047;
            --text: #333333;
            --text-light: #6c757d;
        }
        
        body {
            background-color: #f5f5f5;
            color: var(--text);
            line-height: 1.6;
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header Styles */
        header {
            background-color: white;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-top {
            background-color: var(--primary);
            color: white;
            padding: 8px 0;
            font-size: 14px;
        }
        
        .header-top-content {
            display: flex;
            justify-content: space-between;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }
        
        .logo {
            display: flex;
            align-items: center;
            text-decoration: none;
        }
        
        .logo-text {
            font-size: 24px;
            font-weight: 700;
            color: var(--primary);
        }
        
        .logo-text span {
            color: var(--secondary);
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 25px;
        }
        
        nav ul li a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            transition: color 0.3s;
            position: relative;
        }
        
        nav ul li a:hover {
            color: var(--primary);
        }
        
        nav ul li a.active {
            color: var(--primary);
        }
        
        nav ul li a.active:after {
            content: '';
            position: absolute;
            width: 100%;
            height: 2px;
            background-color: var(--primary);
            bottom: -5px;
            left: 0;
        }
        
        .header-icons {
            display: flex;
            gap: 20px;
        }
        
        .icon {
            font-size: 20px;
            color: var(--dark);
            cursor: pointer;
            transition: color 0.3s;
            position: relative;
        }
        
        .icon:hover {
            color: var(--primary);
        }
        
        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background-color: var(--primary);
            color: white;
            border-radius: 50%;
            width: 18px;
            height: 18px;
            font-size: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .mobile-menu {
            display: none;
            font-size: 24px;
            cursor: pointer;
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url('https://images.unsplash.com/photo-1558769132-cb25e5b8b7b7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1200&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            padding: 100px 0;
            text-align: center;
            margin-bottom: 50px;
        }
        
        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .hero h1 {
            font-size: 3rem;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }
        
        .hero p {
            font-size: 1.3rem;
            margin-bottom: 30px;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.5);
        }
        
        .btn {
            display: inline-block;
            background-color: var(--accent);
            color: var(--dark);
            padding: 12px 25px;
            border-radius: 5px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
        }
        
        .btn:hover {
            background-color: #ffc145;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .btn-primary {
            background-color: var(--primary);
            color: white;
        }
        
        .btn-primary:hover {
            background-color: #ff5580;
        }
        
        /* Categories Section */
        .section-title {
            text-align: center;
            margin-bottom: 40px;
            position: relative;
        }
        
        .section-title h2 {
            font-size: 2.2rem;
            color: var(--dark);
            display: inline-block;
            padding-bottom: 10px;
        }
        
        .section-title h2:after {
            content: '';
            position: absolute;
            width: 80px;
            height: 3px;
            background-color: var(--primary);
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
        }
        
        .categories {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 20px;
            margin-bottom: 50px;
        }
        
        .category {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s;
            text-align: center;
            padding: 20px;
            text-decoration: none;
            color: inherit;
        }
        
        .category:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
        }
        
        .category-icon {
            font-size: 40px;
            margin-bottom: 15px;
            color: var(--primary);
        }
        
        .category h3 {
            font-size: 1.2rem;
            margin-bottom: 10px;
        }
        
        /* Featured Products */
        .products {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 25px;
            margin-bottom: 50px;
        }
        
        .product {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s;
            position: relative;
        }
        
        .product:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }
        
        .product-image {
            width: 100%;
            height: 200px;
            background-color: #e9ecef;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text-light);
            position: relative;
            overflow: hidden;
        }
        
        .product-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }
        
        .product:hover .product-image img {
            transform: scale(1.05);
        }
        
        .product-tag {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: var(--primary);
            color: white;
            padding: 5px 10px;
            border-radius: 3px;
            font-size: 12px;
            z-index: 2;
        }
        
        .product-content {
            padding: 15px;
        }
        
        .product-title {
            font-size: 1.1rem;
            margin-bottom: 10px;
            color: var(--dark);
            height: 40px;
            overflow: hidden;
        }
        
        .product-price {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .current-price {
            font-size: 1.2rem;
            font-weight: 700;
            color: var(--primary);
            margin-right: 10px;
        }
        
        .original-price {
            font-size: 0.9rem;
            color: var(--text-light);
            text-decoration: line-through;
        }
        
        .product-actions {
            display: flex;
            justify-content: space-between;
        }
        
        .add-to-cart {
            background-color: var(--secondary);
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
            transition: background-color 0.3s;
            flex-grow: 1;
            margin-right: 10px;
        }
        
        .add-to-cart:hover {
            background-color: #3db9af;
        }
        
        .wishlist {
            background-color: var(--light);
            color: var(--dark);
            border: none;
            width: 40px;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .wishlist:hover, .wishlist.active {
            background-color: #ff6b8b;
            color: white;
        }
        
        /* Age Groups Section */
        .age-groups {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            margin-bottom: 50px;
        }
        
        .age-group {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            text-align: center;
            padding: 30px 20px;
            transition: transform 0.3s;
            text-decoration: none;
            color: inherit;
        }
        
        .age-group:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }
        
        .age-group-icon {
            font-size: 50px;
            margin-bottom: 15px;
            color: var(--secondary);
        }
        
        .age-group h3 {
            font-size: 1.3rem;
            margin-bottom: 10px;
        }
        
        /* Testimonials */
        .testimonials {
            background-color: var(--light);
            padding: 50px 0;
            margin-bottom: 50px;
        }
        
        .testimonial-container {
            max-width: 800px;
            margin: 0 auto;
            position: relative;
        }
        
        .testimonial {
            background-color: white;
            border-radius: 8px;
            padding: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            text-align: center;
            margin: 0 20px;
        }
        
        .testimonial-text {
            font-style: italic;
            margin-bottom: 20px;
            color: var(--text);
            font-size: 1.1rem;
        }
        
        .testimonial-author {
            font-weight: 600;
            color: var(--dark);
        }
        
        .testimonial-rating {
            color: var(--accent);
            margin-bottom: 10px;
        }
        
        /* Newsletter */
        .newsletter {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 50px 0;
            text-align: center;
            margin-bottom: 50px;
        }
        
        .newsletter h2 {
            font-size: 2rem;
            margin-bottom: 20px;
        }
        
        .newsletter p {
            max-width: 600px;
            margin: 0 auto 30px;
            font-size: 1.1rem;
        }
        
        .newsletter-form {
            display: flex;
            max-width: 500px;
            margin: 0 auto;
        }
        
        .newsletter-form input {
            flex-grow: 1;
            padding: 12px 15px;
            border: none;
            border-radius: 5px 0 0 5px;
            font-size: 16px;
        }
        
        .newsletter-form button {
            background-color: var(--accent);
            color: var(--dark);
            border: none;
            padding: 12px 25px;
            border-radius: 0 5px 5px 0;
            cursor: pointer;
            font-weight: 600;
            transition: background-color 0.3s;
        }
        
        .newsletter-form button:hover {
            background-color: #ffc145;
        }
        
        /* Footer */
        footer {
            background-color: var(--dark);
            color: white;
            padding: 50px 0 20px;
        }
        
        .footer-content {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            margin-bottom: 30px;
        }
        
        .footer-column {
            flex: 1;
            min-width: 250px;
            margin-bottom: 30px;
        }
        
        .footer-column h3 {
            font-size: 1.2rem;
            margin-bottom: 20px;
            color: white;
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 10px;
        }
        
        .footer-links a {
            color: #adb5bd;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-links a:hover {
            color: white;
        }
        
        .contact-info li {
            display: flex;
            align-items: flex-start;
            margin-bottom: 15px;
        }
        
        .contact-icon {
            margin-right: 10px;
            color: var(--secondary);
            width: 20px;
        }
        
        .social-links {
            display: flex;
            gap: 15px;
        }
        
        .social-links a {
            display: inline-block;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            text-align: center;
            line-height: 40px;
            color: white;
            transition: background-color 0.3s;
        }
        
        .social-links a:hover {
            background-color: var(--primary);
        }
        
        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #adb5bd;
            font-size: 14px;
        }
        
        /* Page Sections */
        .page-section {
            display: none;
            padding: 50px 0;
        }
        
        .page-section.active {
            display: block;
        }
        
        /* Cart Sidebar */
        .cart-sidebar {
            position: fixed;
            top: 0;
            right: -400px;
            width: 380px;
            height: 100vh;
            background-color: white;
            box-shadow: -5px 0 15px rgba(0,0,0,0.1);
            z-index: 1000;
            transition: right 0.3s ease;
            padding: 20px;
            overflow-y: auto;
        }
        
        .cart-sidebar.active {
            right: 0;
        }
        
        .cart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            padding-bottom: 15px;
            border-bottom: 1px solid #eee;
        }
        
        .close-cart {
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: var(--text-light);
        }
        
        .cart-items {
            margin-bottom: 20px;
        }
        
        .cart-item {
            display: flex;
            margin-bottom: 15px;
            padding-bottom: 15px;
            border-bottom: 1px solid #eee;
        }
        
        .cart-item-image {
            width: 80px;
            height: 80px;
            background-color: #f5f5f5;
            border-radius: 5px;
            margin-right: 15px;
            overflow: hidden;
        }
        
        .cart-item-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .cart-item-details {
            flex-grow: 1;
        }
        
        .cart-item-title {
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .cart-item-price {
            color: var(--primary);
            font-weight: 600;
        }
        
        .cart-item-actions {
            display: flex;
            align-items: center;
            margin-top: 5px;
        }
        
        .quantity-btn {
            background: none;
            border: 1px solid #ddd;
            width: 25px;
            height: 25px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
        }
        
        .quantity-input {
            width: 40px;
            text-align: center;
            border: 1px solid #ddd;
            height: 25px;
            margin: 0 5px;
        }
        
        .remove-item {
            color: var(--primary);
            background: none;
            border: none;
            margin-left: 10px;
            cursor: pointer;
        }
        
        .cart-total {
            display: flex;
            justify-content: space-between;
            font-weight: 600;
            font-size: 1.2rem;
            margin-bottom: 20px;
            padding-top: 15px;
            border-top: 1px solid #eee;
        }
        
        .checkout-btn {
            width: 100%;
            padding: 12px;
            background-color: var(--primary);
            color: white;
            border: none;
            border-radius: 5px;
            font-weight: 600;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .checkout-btn:hover {
            background-color: #ff5580;
        }
        
        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.5);
            z-index: 999;
            display: none;
        }
        
        .overlay.active {
            display: block;
        }
        
        /* Responsive Styles */
        @media (max-width: 992px) {
            .categories, .products {
                grid-template-columns: repeat(3, 1fr);
            }
            
            .age-groups {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .cart-sidebar {
                width: 320px;
            }
        }
        
        @media (max-width: 768px) {
            nav ul {
                display: none;
                flex-direction: column;
                position: absolute;
                top: 100%;
                left: 0;
                right: 0;
                background-color: white;
                box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
                padding: 20px;
                z-index: 99;
            }
            
            nav ul.active {
                display: flex;
            }
            
            nav ul li {
                margin: 10px 0;
            }
            
            .mobile-menu {
                display: block;
            }
            
            .header-content {
                padding: 10px 0;
            }
            
            .hero {
                padding: 80px 0;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .categories, .products {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .age-groups {
                grid-template-columns: 1fr;
            }
            
            .newsletter-form {
                flex-direction: column;
            }
            
            .newsletter-form input {
                border-radius: 5px;
                margin-bottom: 10px;
            }
            
            .newsletter-form button {
                border-radius: 5px;
            }
            
            .cart-sidebar {
                width: 100%;
                right: -100%;
            }
        }
        
        @media (max-width: 576px) {
            .categories, .products {
                grid-template-columns: 1fr;
            }
            
            .header-top {
                display: none;
            }
            
            .header-icons {
                gap: 15px;
            }
            
            .hero h1 {
                font-size: 1.8rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header Top -->
    <div class="header-top">
        <div class="container">
            <div class="header-top-content">
                <div>Free shipping on all orders over ₹499</div>
                <div>Helpline: +91 98765 43210</div>
            </div>
        </div>
    </div>

    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-content">
                <a href="#" class="logo" data-page="home">
                    <div class="logo-text">Kids<span>Wear</span></div>
                </a>
                <div class="mobile-menu">☰</div>
                <nav>
                    <ul>
                        <li><a href="#" class="active" data-page="home">Home</a></li>
                        <li><a href="#" data-page="boys">Boys</a></li>
                        <li><a href="#" data-page="girls">Girls</a></li>
                        <li><a href="#" data-page="new">New Collection</a></li>
                        <li><a href="#" data-page="bestseller">Bestsellers</a></li>
                        <li><a href="#" data-page="offers">Offers</a></li>
                    </ul>
                </nav>
                <div class="header-icons">
                    <div class="icon search-icon">🔍</div>
                    <div class="icon user-icon">👤</div>
                    <div class="icon wishlist-icon">❤️</div>
                    <div class="icon cart-icon">
                        🛒
                        <span class="cart-count">0</span>
                    </div>
                </div>
            </div>
        </div>
    </header>

    <!-- Overlay for cart -->
    <div class="overlay"></div>

    <!-- Cart Sidebar -->
    <div class="cart-sidebar">
        <div class="cart-header">
            <h3>Your Shopping Cart</h3>
            <button class="close-cart">×</button>
        </div>
        <div class="cart-items">
            <!-- Cart items will be added here dynamically -->
        </div>
        <div class="cart-total">
            <span>Total:</span>
            <span>₹<span id="cart-total-price">0</span></span>
        </div>
        <button class="checkout-btn">Checkout</button>
    </div>

    <!-- Home Page -->
    <section id="home" class="page-section active">
        <!-- Hero Section -->
        <section class="hero">
            <div class="container">
                <div class="hero-content">
                    <h1>Comfortable & Stylish Clothing for Kids</h1>
                    <p>High-quality clothing for children from newborns up to 12 years old</p>
                    <a href="#" class="btn" data-page="new">View New Collection</a>
                </div>
            </div>
        </section>

        <!-- Categories Section -->
        <section class="container">
            <div class="section-title">
                <h2>Categories</h2>
            </div>
            <div class="categories">
                <a href="#" class="category" data-page="boys">
                    <div class="category-icon">👕</div>
                    <h3>Tops & T-Shirts</h3>
                    <p>Comfortable and trendy</p>
                </a>
                <a href="#" class="category" data-page="boys">
                    <div class="category-icon">👖</div>
                    <h3>Bottoms</h3>
                    <p>Pants, shorts and leggings</p>
                </a>
                <a href="#" class="category" data-page="girls">
                    <div class="category-icon">👗</div>
                    <h3>Dresses</h3>
                    <p>Beautiful and charming</p>
                </a>
                <a href="#" class="category" data-page="new">
                    <div class="category-icon">🧥</div>
                    <h3>Outerwear</h3>
                    <p>Jackets and sweaters</p>
                </a>
            </div>
        </section>

        <!-- Featured Products -->
        <section class="container">
            <div class="section-title">
                <h2>Featured Products</h2>
            </div>
            <div class="products">
                <!-- Product 1 -->
                <div class="product">
                    <div class="product-image">
                        <div class="product-tag">New</div>
                        <img src="https://images.unsplash.com/photo-1586366775916-301ff2e4d913?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80" alt="Cotton Printed T-Shirt">
                    </div>
                    <div class="product-content">
                        <h3 class="product-title">Cotton Printed T-Shirt</h3>
                        <div class="product-price">
                            <span class="current-price">₹499</span>
                            <span class="original-price">₹799</span>
                        </div>
                        <div class="product-actions">
                            <button class="add-to-cart" data-id="1" data-name="Cotton Printed T-Shirt" data-price="499" data-image="https://images.unsplash.com/photo-1586366775916-301ff2e4d913?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80">Add to Cart</button>
                            <button class="wishlist">❤️</button>
                        </div>
                    </div>
                </div>

                <!-- Product 2 -->
                <div class="product">
                    <div class="product-image">
                        <div class="product-tag">Bestseller</div>
                        <img src="https://images.unsplash.com/photo-1594633312681-425c7b97ccd1?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80" alt="Denim Jeans">
                    </div>
                    <div class="product-content">
                        <h3 class="product-title">Denim Jeans</h3>
                        <div class="product-price">
                            <span class="current-price">₹899</span>
                            <span class="original-price">₹1199</span>
                        </div>
                        <div class="product-actions">
                            <button class="add-to-cart" data-id="2" data-name="Denim Jeans" data-price="899" data-image="https://images.unsplash.com/photo-1594633312681-425c7b97ccd1?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80">Add to Cart</button>
                            <button class="wishlist">❤️</button>
                        </div>
                    </div>
                </div>

                <!-- Product 3 -->
                <div class="product">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1594736797933-d0e6e4f6f6de?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80" alt="Frock Dress">
                    </div>
                    <div class="product-content">
                        <h3 class="product-title">Frock Dress</h3>
                        <div class="product-price">
                            <span class="current-price">₹799</span>
                            <span class="original-price">₹999</span>
                        </div>
                        <div class="product-actions">
                            <button class="add-to-cart" data-id="3" data-name="Frock Dress" data-price="799" data-image="https://images.unsplash.com/photo-1594736797933-d0e6e4f6f6de?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80">Add to Cart</button>
                            <button class="wishlist">❤️</button>
                        </div>
                    </div>
                </div>

                <!-- Product 4 -->
                <div class="product">
                    <div class="product-image">
                        <div class="product-tag">Offer</div>
                        <img src="https://images.unsplash.com/photo-1556821840-3a63f95609a7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80" alt="Winter Jacket">
                    </div>
                    <div class="product-content">
                        <h3 class="product-title">Winter Jacket</h3>
                        <div class="product-price">
                            <span class="current-price">₹1299</span>
                            <span class="original-price">₹1799</span>
                        </div>
                        <div class="product-actions">
                            <button class="add-to-cart" data-id="4" data-name="Winter Jacket" data-price="1299" data-image="https://images.unsplash.com/photo-1556821840-3a63f95609a7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80">Add to Cart</button>
                            <button class="wishlist">❤️</button>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Age Groups -->
        <section class="container">
            <div class="section-title">
                <h2>By Age</h2>
            </div>
            <div class="age-groups">
                <a href="#" class="age-group" data-page="new">
                    <div class="age-group-icon">👶</div>
                    <h3>0-2 Years</h3>
                    <p>For newborns and toddlers</p>
                    <div class="btn" style="margin-top: 15px; padding: 8px 15px;">View</div>
                </a>
                <a href="#" class="age-group" data-page="new">
                    <div class="age-group-icon">🧒</div>
                    <h3>2-6 Years</h3>
                    <p>For preschool kids</p>
                    <div class="btn" style="margin-top: 15px; padding: 8px 15px;">View</div>
                </a>
                <a href="#" class="age-group" data-page="new">
                    <div class="age-group-icon">👦</div>
                    <h3>6-12 Years</h3>
                    <p>For older kids</p>
                    <div class="btn" style="margin-top: 15px; padding: 8px 15px;">View</div>
                </a>
            </div>
        </section>

        <!-- Testimonials -->
        <section class="testimonials">
            <div class="container">
                <div class="section-title">
                    <h2>Customer Reviews</h2>
                </div>
                <div class="testimonial-container">
                    <div class="testimonial">
                        <div class="testimonial-rating">★★★★★</div>
                        <p class="testimonial-text">"The quality of these clothes is very good. My daughter loved this dress and it is long-lasting. Will definitely buy again!"</p>
                        <p class="testimonial-author">- Priya Sharma, Mumbai</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Newsletter -->
        <section class="newsletter">
            <div class="container">
                <h2>Sign up for our Newsletter</h2>
                <p>Be the first to know about new products, exclusive offers and discounts</p>
                <form class="newsletter-form">
                    <input type="email" placeholder="Your email address" required>
                    <button type="submit">Subscribe</button>
                </form>
            </div>
        </section>
    </section>

    <!-- Other Pages (initially hidden) -->
    <section id="boys" class="page-section">
        <div class="container">
            <div class="section-title">
                <h2>Boys</h2>
            </div>
            <div class="products">
                <!-- Boys products will be loaded here -->
            </div>
        </div>
    </section>

    <section id="girls" class="page-section">
        <div class="container">
            <div class="section-title">
                <h2>Girls</h2>
            </div>
            <div class="products">
                <!-- Girls products will be loaded here -->
            </div>
        </div>
    </section>

    <section id="new" class="page-section">
        <div class="container">
            <div class="section-title">
                <h2>New Collection</h2>
            </div>
            <div class="products">
                <!-- New collection products will be loaded here -->
            </div>
        </div>
    </section>

    <section id="bestseller" class="page-section">
        <div class="container">
            <div class="section-title">
                <h2>Bestsellers</h2>
            </div>
            <div class="products">
                <!-- Bestseller products will be loaded here -->
            </div>
        </div>
    </section>

    <section id="offers" class="page-section">
        <div class="container">
            <div class="section-title">
                <h2>Offers</h2>
            </div>
            <div class="products">
                <!-- Offer products will be loaded here -->
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Kids Wear</h3>
                    <p>Best quality clothing for children. Our mission is to provide every child with comfortable and stylish clothes.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-pinterest"></i></a>
                    </div>
                </div>
                <div class="footer-column">
                    <h3>Links</h3>
                    <ul class="footer-links">
                        <li><a href="#" data-page="home">Home</a></li>
                        <li><a href="#" data-page="about">About Us</a></li>
                        <li><a href="#" data-page="new">Products</a></li>
                        <li><a href="#" data-page="offers">Offers</a></li>
                        <li><a href="#" data-page="contact">Contact</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Customer Service</h3>
                    <ul class="footer-links">
                        <li><a href="#">My Account</a></li>
                        <li><a href="#">Track Order</a></li>
                        <li><a href="#">Shipping Policy</a></li>
                        <li><a href="#">Return Policy</a></li>
                        <li><a href="#">Help</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Contact</h3>
                    <ul class="footer-links contact-info">
                        <li>
                            <span class="contact-icon"><i class="fas fa-phone"></i></span>
                            <span>+91 98765 43210</span>
                        </li>
                        <li>
                            <span class="contact-icon"><i class="fas fa-envelope"></i></span>
                            <span>info@kidswear.com</span>
                        </li>
                        <li>
                            <span class="contact-icon"><i class="fas fa-map-marker-alt"></i></span>
                            <span>123 Shopping Street, Delhi, India</span>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                &copy; 2023 Kids Wear. All rights reserved.
            </div>
        </div>
    </footer>

    <script>
        // Product Data
        const products = {
            home: [
                {
                    id: 1,
                    name: "Cotton Printed T-Shirt",
                    price: 499,
                    originalPrice: 799,
                    image: "https://images.unsplash.com/photo-1586366775916-301ff2e4d913?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    tag: "New"
                },
                {
                    id: 2,
                    name: "Denim Jeans",
                    price: 899,
                    originalPrice: 1199,
                    image: "https://images.unsplash.com/photo-1594633312681-425c7b97ccd1?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    tag: "Bestseller"
                },
                {
                    id: 3,
                    name: "Frock Dress",
                    price: 799,
                    originalPrice: 999,
                    image: "https://images.unsplash.com/photo-1594736797933-d0e6e4f6f6de?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80"
                },
                {
                    id: 4,
                    name: "Winter Jacket",
                    price: 1299,
                    originalPrice: 1799,
                    image: "https://images.unsplash.com/photo-1556821840-3a63f95609a7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    tag: "Offer"
                }
            ],
            boys: [
                {
                    id: 5,
                    name: "Boys Casual Shirt",
                    price: 699,
                    originalPrice: 999,
                    image: "https://images.unsplash.com/photo-1586366775916-301ff2e4d913?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    tag: "New"
                },
                {
                    id: 6,
                    name: "Boys Track Pants",
                    price: 849,
                    originalPrice: 1199,
                    image: "https://images.unsplash.com/photo-1594633312681-425c7b97ccd1?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80"
                },
                {
                    id: 7,
                    name: "Boys Sweatshirt",
                    price: 899,
                    originalPrice: 1299,
                    image: "https://images.unsplash.com/photo-1556821840-3a63f95609a7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    tag: "Bestseller"
                },
                {
                    id: 8,
                    name: "Boys Shorts",
                    price: 549,
                    originalPrice: 799,
                    image: "https://images.unsplash.com/photo-1594736797933-d0e6e4f6f6de?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    tag: "Offer"
                }
            ],
            girls: [
                {
                    id: 9,
                    name: "Girls Frock Dress",
                    price: 999,
                    originalPrice: 1499,
                    image: "https://images.unsplash.com/photo-1594736797933-d0e6e4f6f6de?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    tag: "New"
                },
                {
                    id: 10,
                    name: "Girls Leggings",
                    price: 599,
                    originalPrice: 899,
                    image: "https://images.unsplash.com/photo-1586366775916-301ff2e4d913?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80"
                },
                {
                    id: 11,
                    name: "Girls Top",
                    price: 449,
                    originalPrice: 699,
                    image: "https://images.unsplash.com/photo-1594633312681-425c7b97ccd1?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    tag: "Bestseller"
                },
                {
                    id: 12,
                    name: "Girls Skirt",
                    price: 749,
                    originalPrice: 1099,
                    image: "https://images.unsplash.com/photo-1556821840-3a63f95609a7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    tag: "Offer"
                }
            ],
            new: [
                {
                    id: 13,
                    name: "Newborn Baby Set",
                    price: 1299,
                    originalPrice: 1899,
                    image: "https://images.unsplash.com/photo-1594736797933-d0e6e4f6f6de?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    tag: "New"
                },
                {
                    id: 14,
                    name: "Toddler Playsuit",
                    price: 899,
                    originalPrice: 1299,
                    image: "https://images.unsplash.com/photo-1586366775916-301ff2e4d913?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    tag: "New"
                },
                {
                    id: 15,
                    name: "Kids Athletic Set",
                    price: 1499,
                    originalPrice: 1999,
                    image: "https://images.unsplash.com/photo-1594633312681-425c7b97ccd1?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    tag: "New"
                },
                {
                    id: 16,
                    name: "Designer Kids Outfit",
                    price: 1799,
                    originalPrice: 2499,
                    image: "https://images.unsplash.com/photo-1556821840-3a63f95609a7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    tag: "New"
                }
            ],
            bestseller: [
                {
                    id: 17,
                    name: "Cotton Comfort T-Shirt",
                    price: 399,
                    originalPrice: 599,
                    image: "https://images.unsplash.com/photo-1586366775916-301ff2e4d913?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    tag: "Bestseller"
                },
                {
                    id: 18,
                    name: "Stretchable Jeans",
                    price: 799,
                    originalPrice: 1199,
                    image: "https://images.unsplash.com/photo-1594633312681-425c7b97ccd1?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    tag: "Bestseller"
                },
                {
                    id: 19,
                    name: "Party Wear Dress",
                    price: 1299,
                    originalPrice: 1799,
                    image: "https://images.unsplash.com/photo-1594736797933-d0e6e4f6f6de?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    tag: "Bestseller"
                },
                {
                    id: 20,
                    name: "Winter Hoodie",
                    price: 999,
                    originalPrice: 1499,
                    image: "https://images.unsplash.com/photo-1556821840-3a63f95609a7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    tag: "Bestseller"
                }
            ],
            offers: [
                {
                    id: 21,
                    name: "Discount T-Shirt Pack",
                    price: 999,
                    originalPrice: 1599,
                    image: "https://images.unsplash.com/photo-1586366775916-301ff2e4d913?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    tag: "Offer"
                },
                {
                    id: 22,
                    name: "Bundle Offer - 3 Dresses",
                    price: 1999,
                    originalPrice: 2999,
                    image: "https://images.unsplash.com/photo-1594736797933-d0e6e4f6f6de?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    tag: "Offer"
                },
                {
                    id: 23,
                    name: "Jeans on Sale",
                    price: 699,
                    originalPrice: 1199,
                    image: "https://images.unsplash.com/photo-1594633312681-425c7b97ccd1?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    tag: "Offer"
                },
                {
                    id: 24,
                    name: "Winter Sale - Jacket",
                    price: 1499,
                    originalPrice: 2199,
                    image: "https://images.unsplash.com/photo-1556821840-3a63f95609a7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    tag: "Offer"
                }
            ]
        };

        // Cart functionality
        let cart = [];
        const cartIcon = document.querySelector('.cart-icon');
        const cartSidebar = document.querySelector('.cart-sidebar');
        const closeCart = document.querySelector('.close-cart');
        const overlay = document.querySelector('.overlay');
        const cartCount = document.querySelector('.cart-count');
        const cartTotalPrice = document.getElementById('cart-total-price');
        const cartItemsContainer = document.querySelector('.cart-items');

        // Navigation functionality
        const navLinks = document.querySelectorAll('nav a, .logo, .category, .age-group, .footer-links a');
        const pageSections = document.querySelectorAll('.page-section');

        // Mobile menu functionality
        const mobileMenu = document.querySelector('.mobile-menu');
        const navMenu = document.querySelector('nav ul');

        // Initialize the website
        document.addEventListener('DOMContentLoaded', function() {
            // Set up event listeners
            setupEventListeners();
            
            // Load products for each page
            loadProductsForPages();
        });

        function setupEventListeners() {
            // Mobile menu toggle
            mobileMenu.addEventListener('click', function() {
                navMenu.classList.toggle('active');
            });

            // Navigation
            navLinks.forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    const page = this.getAttribute('data-page');
                    if (page) {
                        showPage(page);
                        // Close mobile menu if open
                        navMenu.classList.remove('active');
                    }
                });
            });

            // Cart functionality
            cartIcon.addEventListener('click', function() {
                cartSidebar.classList.add('active');
                overlay.classList.add('active');
            });

            closeCart.addEventListener('click', function() {
                cartSidebar.classList.remove('active');
                overlay.classList.remove('active');
            });

            overlay.addEventListener('click', function() {
                cartSidebar.classList.remove('active');
                overlay.classList.remove('active');
            });

            // Add to cart buttons
            document.addEventListener('click', function(e) {
                if (e.target.classList.contains('add-to-cart')) {
                    const id = e.target.getAttribute('data-id');
                    const name = e.target.getAttribute('data-name');
                    const price = parseInt(e.target.getAttribute('data-price'));
                    const image = e.target.getAttribute('data-image');
                    
                    addToCart(id, name, price, image);
                }
                
                if (e.target.classList.contains('wishlist')) {
                    e.target.classList.toggle('active');
                }
            });

            // Newsletter form
            const newsletterForm = document.querySelector('.newsletter-form');
            newsletterForm.addEventListener('submit', function(e) {
                e.preventDefault();
                const email = this.querySelector('input[type="email"]').value;
                alert(`Thank you! ${email} has been subscribed.`);
                this.reset();
            });
        }

        function showPage(page) {
            // Hide all pages
            pageSections.forEach(section => {
                section.classList.remove('active');
            });
            
            // Show selected page
            document.getElementById(page).classList.add('active');
            
            // Update active nav link
            document.querySelectorAll('nav a').forEach(link => {
                link.classList.remove('active');
            });
            document.querySelector(`nav a[data-page="${page}"]`).classList.add('active');
            
            // Scroll to top
            window.scrollTo(0, 0);
        }

        function loadProductsForPages() {
            for (const page in products) {
                const container = document.querySelector(`#${page} .products`);
                if (container) {
                    container.innerHTML = '';
                    products[page].forEach(product => {
                        const productElement = createProductElement(product);
                        container.appendChild(productElement);
                    });
                }
            }
        }

        function createProductElement(product) {
            const productDiv = document.createElement('div');
            productDiv.className = 'product';
            
            let tagHtml = '';
            if (product.tag) {
                tagHtml = `<div class="product-tag">${product.tag}</div>`;
            }
            
            productDiv.innerHTML = `
                <div class="product-image">
                    ${tagHtml}
                    <img src="${product.image}" alt="${product.name}">
                </div>
                <div class="product-content">
                    <h3 class="product-title">${product.name}</h3>
                    <div class="product-price">
                        <span class="current-price">₹${product.price}</span>
                        ${product.originalPrice ? `<span class="original-price">₹${product.originalPrice}</span>` : ''}
                    </div>
                    <div class="product-actions">
                        <button class="add-to-cart" data-id="${product.id}" data-name="${product.name}" data-price="${product.price}" data-image="${product.image}">Add to Cart</button>
                        <button class="wishlist">❤️</button>
                    </div>
                </div>
            `;
            
            return productDiv;
        }

        function addToCart(id, name, price, image) {
            // Check if product already in cart
            const existingItem = cart.find(item => item.id === id);
            
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                cart.push({
                    id,
                    name,
                    price,
                    image,
                    quantity: 1
                });
            }
            
            updateCart();
            showNotification(`${name} has been added to the cart!`);
        }

        function updateCart() {
            // Update cart count
            const totalItems = cart.reduce((total, item) => total + item.quantity, 0);
            cartCount.textContent = totalItems;
            
            // Update cart items
            cartItemsContainer.innerHTML = '';
            
            if (cart.length === 0) {
                cartItemsContainer.innerHTML = '<p>Your cart is empty</p>';
                cartTotalPrice.textContent = '0';
                return;
            }
            
            let totalPrice = 0;
            
            cart.forEach(item => {
                const itemTotal = item.price * item.quantity;
                totalPrice += itemTotal;
                
                const cartItem = document.createElement('div');
                cartItem.className = 'cart-item';
                cartItem.innerHTML = `
                    <div class="cart-item-image">
                        <img src="${item.image}" alt="${item.name}">
                    </div>
                    <div class="cart-item-details">
                        <div class="cart-item-title">${item.name}</div>
                        <div class="cart-item-price">₹${item.price}</div>
                        <div class="cart-item-actions">
                            <button class="quantity-btn minus" data-id="${item.id}">-</button>
                            <input type="text" class="quantity-input" value="${item.quantity}" readonly>
                            <button class="quantity-btn plus" data-id="${item.id}">+</button>
                            <button class="remove-item" data-id="${item.id}">Remove</button>
                        </div>
                    </div>
                `;
                
                cartItemsContainer.appendChild(cartItem);
            });
            
            // Update total price
            cartTotalPrice.textContent = totalPrice;
            
            // Add event listeners to quantity buttons
            document.querySelectorAll('.quantity-btn.minus').forEach(btn => {
                btn.addEventListener('click', function() {
                    const id = this.getAttribute('data-id');
                    updateQuantity(id, -1);
                });
            });
            
            document.querySelectorAll('.quantity-btn.plus').forEach(btn => {
                btn.addEventListener('click', function() {
                    const id = this.getAttribute('data-id');
                    updateQuantity(id, 1);
                });
            });
            
            document.querySelectorAll('.remove-item').forEach(btn => {
                btn.addEventListener('click', function() {
                    const id = this.getAttribute('data-id');
                    removeFromCart(id);
                });
            });
        }

        function updateQuantity(id, change) {
            const item = cart.find(item => item.id === id);
            if (item) {
                item.quantity += change;
                
                if (item.quantity <= 0) {
                    removeFromCart(id);
                } else {
                    updateCart();
                }
            }
        }

        function removeFromCart(id) {
            cart = cart.filter(item => item.id !== id);
            updateCart();
        }

        function showNotification(message) {
            // Create notification element
            const notification = document.createElement('div');
            notification.className = 'notification';
            notification.textContent = message;
            notification.style.cssText = `
                position: fixed;
                top: 100px;
                right: 20px;
                background-color: var(--secondary);
                color: white;
                padding: 15px 20px;
                border-radius: 5px;
                box-shadow: 0 5px 15px rgba(0,0,0,0.1);
                z-index: 1001;
                transition: all 0.3s;
            `;
            
            document.body.appendChild(notification);
            
            // Remove notification after 3 seconds
            setTimeout(() => {
                notification.style.opacity = '0';
                setTimeout(() => {
                    document.body.removeChild(notification);
                }, 300);
            }, 3000);
        }

        // Checkout button
        document.querySelector('.checkout-btn').addEventListener('click', function() {
            if (cart.length === 0) {
                alert('Your cart is empty!');
                return;
            }
            
            alert('Your order has been placed successfully! Thank you!');
            cart = [];
            updateCart();
            cartSidebar.classList.remove('active');
            overlay.classList.remove('active');
        });
    </script>
</body>
</html>
