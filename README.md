<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>LuxeStyle - Premium Branded Fashion</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;500;600;700&family=Pacifico&family=Caveat:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #D4A76A;
            --secondary-color: #8B4513;
            --accent-color: #FF6B35;
            --cream-color: #FFF8E7;
            --dark-brown: #5C4033;
            --light-brown: #A67B5B;
            --beige: #F5E6D3;
            --dark-cream: #E8D8B6;
            --white: #FFFFFF;
            --black: #2C1810;
            --success-color: #4CAF50;
            --error-color: #f44336;
            --gray: #999;
            
            --dark-bg: #1a1a1a;
            --dark-card: #2d2d2d;
            --dark-text: #e0e0e0;
            --dark-border: #444;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Caveat', cursive;
            font-size: 22px;
            background-color: var(--cream-color);
            color: var(--dark-brown);
            line-height: 1.4;
            overflow-x: hidden;
            letter-spacing: 0.3px;
            transition: background-color 0.3s ease, color 0.3s ease;
        }

        h1, h2, h3, h4, h5 {
            font-family: 'Dancing Script', cursive;
            font-weight: 600;
            color: var(--secondary-color);
            font-style: italic;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.1);
            transition: color 0.3s ease;
        }

        a {
            text-decoration: none;
            color: inherit;
            transition: all 0.3s ease;
        }

        button {
            font-family: 'Caveat', cursive;
            font-size: 22px;
            cursor: pointer;
            border: none;
            background: none;
        }

        .container {
            width: 100%;
            max-width: 1600px;
            margin: 0 auto;
            padding: 0 40px;
        }

        /* Header */
        header {
            background-color: var(--cream-color);
            position: fixed;
            width: 100%;
            z-index: 1000;
            padding: 15px 0;
            box-shadow: 0 5px 15px rgba(139, 69, 19, 0.1);
            transition: all 0.4s ease;
            border-bottom: 2px solid var(--dark-cream);
        }

        header.scrolled {
            padding: 10px 0;
            background-color: rgba(255, 248, 231, 0.95);
            box-shadow: 0 8px 20px rgba(139, 69, 19, 0.15);
        }

        body.dark-theme header {
            background-color: var(--dark-card);
            border-bottom-color: var(--dark-border);
        }

        body.dark-theme header.scrolled {
            background-color: rgba(45, 45, 45, 0.95);
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-family: 'Pacifico', cursive;
            font-size: 32px;
            font-weight: 400;
            color: var(--primary-color);
            display: flex;
            align-items: center;
            gap: 10px;
            text-shadow: 2px 2px 3px rgba(0,0,0,0.1);
        }

        .logo i {
            color: var(--primary-color);
        }

        /* Compact Search */
        .compact-search {
            position: relative;
        }

        .search-toggle {
            width: 45px;
            height: 45px;
            background-color: var(--beige);
            border: 2px solid var(--dark-cream);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s ease;
            color: var(--secondary-color);
            font-size: 18px;
        }

        .search-toggle:hover {
            background-color: var(--primary-color);
            border-color: var(--primary-color);
            color: var(--dark-brown);
            transform: scale(1.05);
        }

        .search-expanded {
            position: absolute;
            top: 100%;
            right: 0;
            background-color: var(--cream-color);
            border: 2px solid var(--dark-cream);
            border-radius: 10px;
            padding: 15px;
            width: 300px;
            box-shadow: 0 5px 20px rgba(139, 69, 19, 0.2);
            display: none;
            z-index: 1001;
            margin-top: 10px;
        }

        body.dark-theme .search-expanded {
            background-color: var(--dark-card);
            border-color: var(--dark-border);
        }

        .search-expanded.active {
            display: block;
            animation: fadeInDown 0.3s ease;
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-10px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .search-input-wrapper {
            position: relative;
            margin-bottom: 10px;
        }

        .search-input {
            width: 100%;
            padding: 10px 40px 10px 15px;
            background-color: var(--beige);
            border: 2px solid var(--dark-cream);
            border-radius: 25px;
            font-family: 'Caveat', cursive;
            font-size: 18px;
            color: var(--dark-brown);
            transition: all 0.3s ease;
            outline: none;
        }

        .search-input:focus {
            border-color: var(--primary-color);
            background-color: var(--cream-color);
        }

        .search-submit {
            position: absolute;
            right: 5px;
            top: 50%;
            transform: translateY(-50%);
            width: 30px;
            height: 30px;
            background-color: var(--primary-color);
            border: none;
            border-radius: 50%;
            color: var(--dark-brown);
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
        }

        .search-submit:hover {
            background-color: var(--accent-color);
            color: var(--cream-color);
            transform: translateY(-50%) scale(1.1);
        }

        .search-results {
            max-height: 300px;
            overflow-y: auto;
            border-top: 1px solid var(--dark-cream);
            padding-top: 10px;
            display: none;
        }

        .search-results.active {
            display: block;
        }

        .search-result-item {
            display: flex;
            padding: 8px;
            align-items: center;
            border-bottom: 1px solid var(--dark-cream);
            cursor: pointer;
            transition: all 0.2s ease;
            border-radius: 5px;
            margin-bottom: 5px;
        }

        .search-result-item:hover {
            background-color: var(--beige);
            transform: translateX(5px);
        }

        .search-result-img {
            width: 50px;
            height: 50px;
            border-radius: 5px;
            overflow: hidden;
            margin-right: 10px;
            flex-shrink: 0;
        }

        .search-result-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .search-result-info {
            flex: 1;
        }

        .search-result-name {
            font-weight: 600;
            font-size: 16px;
            margin-bottom: 3px;
            color: var(--secondary-color);
        }

        .search-result-price {
            color: var(--primary-color);
            font-weight: 700;
            font-size: 16px;
        }

        .search-overlay {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: transparent;
            z-index: 1000;
            display: none;
        }

        /* Theme Toggle */
        .theme-toggle {
            width: 50px;
            height: 26px;
            background-color: var(--beige);
            border-radius: 13px;
            position: relative;
            cursor: pointer;
            margin-left: 10px;
            border: 2px solid var(--dark-cream);
            transition: all 0.3s ease;
        }

        .theme-toggle.active {
            background-color: var(--primary-color);
            border-color: var(--primary-color);
        }

        .theme-toggle-handle {
            position: absolute;
            left: 3px;
            top: 3px;
            width: 18px;
            height: 18px;
            background-color: var(--white);
            border-radius: 50%;
            transition: transform 0.3s ease;
        }

        .theme-toggle.active .theme-toggle-handle {
            transform: translateX(24px);
        }

        .theme-toggle i {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            font-size: 12px;
            color: var(--dark-brown);
        }

        .theme-toggle .fa-sun {
            left: 6px;
        }

        .theme-toggle .fa-moon {
            right: 6px;
        }

        /* Navigation */
        nav {
            display: flex;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        nav a {
            font-weight: 600;
            font-size: 24px;
            position: relative;
            padding: 5px 0;
            color: var(--secondary-color);
            text-shadow: 1px 1px 1px rgba(0,0,0,0.05);
        }

        nav a:after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            background: var(--primary-color);
            left: 0;
            bottom: 0;
            transition: width 0.3s ease;
        }

        nav a:hover:after {
            width: 100%;
        }

        nav a:hover {
            color: var(--primary-color);
        }

        /* Header Actions */
        .header-actions {
            display: flex;
            gap: 15px;
            align-items: center;
        }

        .cart-icon {
            position: relative;
            font-size: 24px;
            cursor: pointer;
            color: var(--secondary-color);
            transition: color 0.3s ease;
        }

        .cart-icon:hover {
            color: var(--primary-color);
        }

        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background-color: var(--accent-color);
            color: var(--cream-color);
            font-size: 14px;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            font-weight: 700;
            font-family: 'Caveat', cursive;
        }

        /* Language Selector */
        .language-selector {
            position: relative;
            display: flex;
            align-items: center;
            gap: 5px;
            cursor: pointer;
            font-weight: 600;
            color: var(--secondary-color);
            padding: 5px;
            border-radius: 4px;
            font-size: 20px;
            height: 40px;
        }

        .language-selector:hover {
            background-color: rgba(212, 167, 106, 0.1);
        }

        .language-flag {
            width: 30px;
            height: 20px;
            border-radius: 2px;
            overflow: hidden;
            border: 1px solid var(--dark-cream);
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .language-flag img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .language-dropdown {
            position: absolute;
            top: 100%;
            right: 0;
            background-color: var(--beige);
            border-radius: 5px;
            min-width: 120px;
            box-shadow: 0 5px 15px rgba(139, 69, 19, 0.2);
            opacity: 0;
            visibility: hidden;
            transform: translateY(-10px);
            transition: all 0.3s ease;
            z-index: 10;
            border: 1px solid var(--dark-cream);
        }

        body.dark-theme .language-dropdown {
            background-color: var(--dark-card);
            border-color: var(--dark-border);
        }

        .language-selector.active .language-dropdown {
            opacity: 1;
            visibility: visible;
            transform: translateY(5px);
        }

        .language-option {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 10px 15px;
            transition: all 0.2s ease;
            color: var(--dark-brown);
            cursor: pointer;
            font-family: 'Caveat', cursive;
            font-size: 18px;
        }

        .language-option:hover {
            background-color: rgba(212, 167, 106, 0.2);
        }

        /* Mobile Menu */
        .mobile-menu-btn {
            display: none;
            font-size: 28px;
            cursor: pointer;
            color: var(--primary-color);
            background: none;
            border: none;
            padding: 5px;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            background: linear-gradient(rgba(255, 248, 231, 0.9), rgba(255, 248, 231, 0.8)), 
                        url('https://images.unsplash.com/photo-1490481651871-ab68de25d43d?ixlib=rb-4.0.3&auto=format&fit=crop&w=2070&q=80');
            background-size: cover;
            background-position: center;
            position: relative;
            overflow: hidden;
        }

        body.dark-theme .hero {
            background: linear-gradient(rgba(26, 26, 26, 0.9), rgba(26, 26, 26, 0.8)), 
                        url('https://images.unsplash.com/photo-1490481651871-ab68de25d43d?ixlib=rb-4.0.3&auto=format&fit=crop&w=2070&q=80');
        }

        .hero-content {
            max-width: 750px;
            position: relative;
            z-index: 2;
            animation: fadeInUp 1s ease-out;
            background-color: rgba(255, 255, 255, 0.9);
            padding: 50px;
            border-radius: 15px;
            box-shadow: 0 15px 40px rgba(139, 69, 19, 0.2);
            border: 2px solid var(--dark-cream);
        }

        body.dark-theme .hero-content {
            background-color: rgba(45, 45, 45, 0.9);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.2);
            border-color: var(--dark-border);
        }

        .hero h1 {
            font-size: 56px;
            margin-bottom: 20px;
            line-height: 1.2;
            font-weight: 700;
        }

        .hero p {
            font-size: 26px;
            margin-bottom: 30px;
            color: var(--dark-brown);
            text-shadow: 0.5px 0.5px 1px rgba(0,0,0,0.05);
        }

        /* Buttons */
        .btn {
            display: inline-block;
            background-color: var(--primary-color);
            color: var(--dark-brown);
            padding: 15px 35px;
            font-weight: 600;
            border-radius: 30px;
            border: 2px solid var(--primary-color);
            transition: all 0.3s ease;
            cursor: pointer;
            font-size: 22px;
            text-align: center;
            font-family: 'Caveat', cursive;
            text-shadow: 1px 1px 1px rgba(0,0,0,0.1);
        }

        .btn:hover {
            background-color: transparent;
            color: var(--primary-color);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(212, 167, 106, 0.3);
        }

        .btn-outline {
            background-color: transparent;
            color: var(--primary-color);
            margin-left: 15px;
        }

        .btn-outline:hover {
            background-color: var(--primary-color);
            color: var(--dark-brown);
        }

        /* Section Titles */
        .section-title {
            text-align: center;
            margin-bottom: 60px;
            position: relative;
        }

        .section-title h2 {
            font-size: 46px;
            display: inline-block;
            position: relative;
            font-weight: 700;
            background: linear-gradient(45deg, var(--secondary-color), var(--primary-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .section-title h2:after {
            content: '';
            position: absolute;
            width: 80px;
            height: 3px;
            background: var(--primary-color);
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
        }

        /* Sections */
        section {
            padding: 100px 0;
            position: relative;
        }

        /* Categories */
        .categories {
            background-color: var(--beige);
        }

        .categories-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }

        .category-card {
            background-color: var(--cream-color);
            border-radius: 10px;
            overflow: hidden;
            transition: all 0.4s ease;
            height: 350px;
            cursor: pointer;
            border: 2px solid var(--dark-cream);
            box-shadow: 0 5px 15px rgba(139, 69, 19, 0.1);
        }

        .category-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 20px 40px rgba(139, 69, 19, 0.25);
            border-color: var(--primary-color);
        }

        .category-img {
            height: 70%;
            overflow: hidden;
            position: relative;
        }

        .category-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.7s ease;
        }

        .category-card:hover .category-img img {
            transform: scale(1.1);
        }

        .category-content {
            padding: 25px 20px;
            height: 30%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            background-color: var(--cream-color);
        }

        .category-content h3 {
            font-size: 26px;
            margin-bottom: 8px;
            font-weight: 600;
        }

        .category-content p {
            color: var(--light-brown);
            font-size: 18px;
        }

        /* Products */
        .products {
            background-color: var(--cream-color);
        }

        .products-filter {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 40px;
        }

        .filter-btn {
            background-color: var(--beige);
            color: var(--dark-brown);
            border: 1px solid var(--dark-cream);
            padding: 10px 25px;
            border-radius: 30px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
            font-size: 22px;
            font-family: 'Caveat', cursive;
        }

        .filter-btn.active, .filter-btn:hover {
            background-color: var(--primary-color);
            color: var(--dark-brown);
            border-color: var(--primary-color);
        }

        .products-grid {
            display: grid;
            gap: 30px;
            transition: opacity 0.3s ease;
        }

        /* Responsive grid for products */
        .products-grid {
            grid-template-columns: repeat(5, 1fr);
        }

        .product-card {
            background-color: var(--beige);
            border-radius: 10px;
            overflow: hidden;
            transition: all 0.4s ease;
            position: relative;
            border: 2px solid var(--dark-cream);
            box-shadow: 0 5px 15px rgba(139, 69, 19, 0.1);
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(139, 69, 19, 0.2);
            border-color: var(--primary-color);
        }

        .vip-product {
            border: 2px solid transparent;
            background: linear-gradient(var(--beige), var(--beige)) padding-box,
                        linear-gradient(45deg, #D4A76A, #FFD700, #D4A76A) border-box;
        }

        .product-badge {
            position: absolute;
            top: 15px;
            left: 15px;
            background-color: var(--accent-color);
            color: var(--cream-color);
            padding: 5px 12px;
            border-radius: 20px;
            font-weight: 600;
            font-size: 18px;
            z-index: 2;
            font-family: 'Caveat', cursive;
        }

        .vip-badge {
            position: absolute;
            top: 15px;
            right: 15px;
            background: linear-gradient(45deg, #D4A76A, #FFD700, #D4A76A);
            background-size: 200% 200%;
            color: var(--dark-brown);
            padding: 5px 12px;
            border-radius: 20px;
            font-weight: 600;
            font-size: 16px;
            z-index: 2;
            font-family: 'Caveat', cursive;
            animation: goldShine 3s linear infinite;
            border: 1px solid rgba(212, 167, 106, 0.5);
            box-shadow: 0 0 10px rgba(212, 167, 106, 0.3);
        }

        @keyframes goldShine {
            0% { background-position: 0% 50%; }
            100% { background-position: 200% 50%; }
        }

        .product-img {
            height: 250px;
            overflow: hidden;
            position: relative;
        }

        .product-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.7s ease;
        }

        .product-card:hover .product-img img {
            transform: scale(1.08);
        }

        .product-content {
            padding: 20px;
            background-color: var(--cream-color);
        }

        .product-content h3 {
            font-size: 24px;
            margin-bottom: 10px;
            min-height: 48px;
            font-weight: 600;
        }

        .product-description {
            font-size: 18px;
            color: var(--light-brown);
            margin-bottom: 15px;
            min-height: 40px;
        }

        .product-price {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-top: 15px;
        }

        /* Акцент на ценах - крупный жирный шрифт */
        .price {
            font-size: 32px;
            font-weight: 800;
            color: var(--accent-color);
            font-family: 'Caveat', cursive;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.1);
            letter-spacing: 1px;
        }

        .old-price {
            text-decoration: line-through;
            color: var(--gray);
            font-size: 18px;
            margin-right: 8px;
            font-family: 'Caveat', cursive;
        }

        .product-actions {
            display: flex;
            gap: 10px;
        }

        .add-to-cart, .view-details {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: var(--primary-color);
            color: var(--dark-brown);
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 1px solid var(--primary-color);
            position: relative;
            overflow: hidden;
        }

        .add-to-cart:hover {
            background-color: var(--accent-color);
            border-color: var(--accent-color);
            color: var(--cream-color);
            transform: scale(1.1);
        }

        .view-details {
            background-color: transparent;
            color: var(--primary-color);
        }

        .view-details:hover {
            background-color: var(--primary-color);
            color: var(--dark-brown);
            transform: scale(1.1);
        }

        /* Cart Modal */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(44, 24, 16, 0.7);
            z-index: 1500;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s ease;
            backdrop-filter: blur(3px);
        }

        .modal-overlay.active {
            opacity: 1;
            visibility: visible;
        }

        .cart-modal {
            position: fixed;
            top: 0;
            right: -100%;
            width: 100%;
            max-width: 450px;
            height: 100%;
            background-color: var(--beige);
            z-index: 2000;
            transition: right 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            box-shadow: -5px 0 30px rgba(139, 69, 19, 0.3);
            display: flex;
            flex-direction: column;
            border-left: 2px solid var(--dark-cream);
        }

        .cart-modal.active {
            right: 0;
        }

        .cart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 25px 30px;
            border-bottom: 2px solid var(--dark-cream);
            background-color: var(--cream-color);
        }

        .cart-header h3 {
            font-size: 28px;
            margin: 0;
            font-weight: 600;
        }

        .close-cart {
            font-size: 26px;
            cursor: pointer;
            color: var(--primary-color);
            transition: all 0.3s ease;
            background: none;
            border: none;
        }

        .close-cart:hover {
            transform: rotate(90deg);
            color: var(--accent-color);
        }

        .cart-items {
            flex: 1;
            overflow-y: auto;
            padding: 20px 30px;
        }

        .cart-item {
            display: flex;
            padding: 15px 0;
            border-bottom: 1px solid var(--dark-cream);
            align-items: center;
            transition: all 0.3s ease;
        }

        .cart-item-img {
            width: 80px;
            height: 80px;
            border-radius: 5px;
            overflow: hidden;
            margin-right: 15px;
            flex-shrink: 0;
            border: 1px solid var(--dark-cream);
        }

        .cart-item-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .cart-item-details {
            flex: 1;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .cart-item-title {
            font-weight: 600;
            margin-bottom: 5px;
            font-size: 20px;
        }

        .cart-item-price {
            color: var(--accent-color);
            font-weight: 800;
            font-size: 24px;
            font-family: 'Caveat', cursive;
        }

        .cart-item-controls {
            display: flex;
            align-items: center;
            margin-top: 10px;
        }

        .quantity-btn {
            width: 30px;
            height: 30px;
            background-color: var(--cream-color);
            color: var(--dark-brown);
            border: 1px solid var(--dark-cream);
            border-radius: 3px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            transition: all 0.2s ease;
            font-family: 'Caveat', cursive;
            font-size: 18px;
        }

        .quantity-btn:hover {
            background-color: var(--primary-color);
            border-color: var(--primary-color);
        }

        .cart-item-quantity {
            margin: 0 10px;
            font-weight: 600;
            min-width: 20px;
            text-align: center;
            color: var(--dark-brown);
            font-size: 20px;
        }

        .remove-item {
            margin-left: 15px;
            color: var(--error-color);
            cursor: pointer;
            transition: all 0.3s ease;
            background: none;
            border: none;
            font-size: 20px;
            padding: 5px;
            border-radius: 50%;
            width: 35px;
            height: 35px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .remove-item:hover {
            background-color: rgba(244, 67, 54, 0.1);
            transform: scale(1.2);
        }

        .cart-footer {
            padding: 25px 30px;
            border-top: 2px solid var(--dark-cream);
            background-color: var(--cream-color);
        }

        .cart-total {
            display: flex;
            justify-content: space-between;
            margin-bottom: 25px;
            font-size: 22px;
            font-weight: 600;
        }

        .total-amount {
            color: var(--accent-color);
            font-size: 28px;
            font-weight: 800;
            font-family: 'Caveat', cursive;
        }

        .checkout-btn {
            width: 100%;
            padding: 15px;
            background-color: var(--primary-color);
            color: var(--dark-brown);
            border: none;
            border-radius: 5px;
            font-weight: 700;
            font-size: 22px;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 1px solid var(--primary-color);
            font-family: 'Caveat', cursive;
        }

        .checkout-btn:hover {
            background-color: var(--accent-color);
            border-color: var(--accent-color);
            color: var(--cream-color);
            transform: translateY(-3px);
        }

        .cart-empty {
            text-align: center;
            padding: 60px 20px;
            display: block;
        }

        .cart-empty i {
            font-size: 70px;
            color: var(--dark-cream);
            margin-bottom: 20px;
            opacity: 0.5;
        }

        .cart-empty h4 {
            color: var(--secondary-color);
            margin-bottom: 10px;
            font-size: 26px;
        }

        /* About Section */
        .about {
            background-color: var(--beige);
        }

        .about-content {
            display: flex;
            align-items: center;
            gap: 50px;
        }

        .about-text {
            flex: 1;
        }

        .about-text h2 {
            font-size: 46px;
            margin-bottom: 25px;
        }

        .about-text p {
            margin-bottom: 20px;
            font-size: 22px;
            color: var(--dark-brown);
        }

        .about-stats {
            display: flex;
            justify-content: space-between;
            margin-top: 40px;
        }

        .about-stats .stat-item {
            text-align: center;
        }

        .about-stats .stat-number {
            font-size: 40px;
            font-weight: 700;
            color: var(--primary-color);
            display: block;
            margin-bottom: 5px;
            font-family: 'Caveat', cursive;
        }

        .about-stats .stat-label {
            font-size: 20px;
            color: var(--light-brown);
        }

        .about-image {
            flex: 1;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 20px 20px 0 var(--dark-cream);
            border: 2px solid var(--dark-cream);
            position: relative;
        }

        .about-image img {
            width: 100%;
            height: auto;
            display: block;
            transition: transform 0.5s ease;
        }

        .about-image:hover img {
            transform: scale(1.05);
        }

        /* Footer */
        footer {
            background-color: var(--dark-brown);
            padding: 70px 0 30px;
            color: var(--beige);
            transition: background-color 0.3s ease;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 40px;
            margin-bottom: 50px;
        }

        .footer-column h3 {
            font-size: 26px;
            margin-bottom: 25px;
            position: relative;
            padding-bottom: 10px;
            color: var(--primary-color);
            font-weight: 600;
        }

        .footer-column h3:after {
            content: '';
            position: absolute;
            width: 40px;
            height: 2px;
            background: var(--primary-color);
            bottom: 0;
            left: 0;
        }

        .footer-column p {
            margin-bottom: 20px;
            color: var(--beige);
            opacity: 0.9;
            font-size: 20px;
        }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .social-links a {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
            color: var(--beige);
        }

        .social-links a:hover {
            background-color: var(--primary-color);
            color: var(--dark-brown);
            transform: translateY(-5px);
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 12px;
        }

        .footer-links a {
            color: var(--beige);
            transition: all 0.3s ease;
            opacity: 0.9;
            font-size: 20px;
        }

        .footer-links a:hover {
            color: var(--primary-color);
            padding-left: 5px;
            opacity: 1;
        }

        .newsletter-form {
            display: flex;
            margin-top: 20px;
            position: relative;
        }

        .newsletter-input {
            flex: 1;
            padding: 12px 15px;
            background-color: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(212, 167, 106, 0.3);
            border-radius: 30px 0 0 30px;
            color: var(--beige);
            border-right: none;
            font-size: 18px;
            font-family: 'Caveat', cursive;
        }

        .newsletter-input:focus {
            outline: none;
            background-color: rgba(255, 255, 255, 0.15);
            border-color: var(--primary-color);
        }

        .newsletter-input::placeholder {
            color: rgba(245, 230, 211, 0.6);
            font-family: 'Caveat', cursive;
        }

        .newsletter-btn {
            background-color: var(--primary-color);
            color: var(--dark-brown);
            border: 1px solid var(--primary-color);
            padding: 0 20px;
            border-radius: 0 30px 30px 0;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
            font-size: 20px;
            font-family: 'Caveat', cursive;
        }

        .newsletter-btn:hover {
            background-color: var(--accent-color);
            border-color: var(--accent-color);
            color: var(--cream-color);
        }

        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(212, 167, 106, 0.2);
            color: var(--beige);
            font-size: 18px;
            opacity: 0.8;
        }

        /* Notification */
        .notification {
            position: fixed;
            top: 100px;
            right: 20px;
            padding: 15px 25px;
            border-radius: 5px;
            font-weight: 600;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
            opacity: 0;
            transform: translateX(100px);
            transition: all 0.3s ease;
            z-index: 9999;
            max-width: 300px;
            pointer-events: none;
            font-family: 'Caveat', cursive;
            font-size: 20px;
        }

        .notification.show {
            opacity: 1;
            transform: translateX(0);
        }

        .notification.success {
            background-color: var(--success-color);
            color: white;
        }

        .notification.error {
            background-color: var(--error-color);
            color: white;
        }

        .notification.info {
            background-color: var(--primary-color);
            color: var(--dark-brown);
        }

        /* Floating animation */
        .floating-item {
            position: fixed;
            width: 40px;
            height: 40px;
            background: linear-gradient(45deg, var(--primary-color), var(--accent-color));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 9999;
            pointer-events: none;
            box-shadow: 0 2px 15px rgba(212, 167, 106, 0.5);
            transition: transform 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            font-size: 18px;
        }

        .floating-item i {
            color: var(--dark-brown);
        }

        .cart-icon.animate {
            animation: cartBounce 0.5s ease;
        }

        @keyframes cartBounce {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.3); }
        }

        .loading-spinner {
            display: inline-block;
            width: 20px;
            height: 20px;
            border: 3px solid rgba(212, 167, 106, 0.3);
            border-radius: 50%;
            border-top-color: var(--primary-color);
            animation: spin 1s ease-in-out infinite;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(40px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .pulse-animation {
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% {
                box-shadow: 0 0 0 0 rgba(212, 167, 106, 0.4);
            }
            70% {
                box-shadow: 0 0 0 10px rgba(212, 167, 106, 0);
            }
            100% {
                box-shadow: 0 0 0 0 rgba(212, 167, 106, 0);
            }
        }

        /* ============== RESPONSIVE DESIGN ============== */
        
        /* Desktop large (1400px+) */
        @media (min-width: 1400px) {
            .container {
                padding: 0 60px;
            }
            .products-grid {
                grid-template-columns: repeat(5, 1fr);
                gap: 35px;
            }
            .price {
                font-size: 34px;
            }
        }

        /* Desktop (1200px - 1399px) */
        @media (min-width: 1200px) and (max-width: 1399px) {
            .container {
                padding: 0 40px;
            }
            .products-grid {
                grid-template-columns: repeat(4, 1fr);
                gap: 30px;
            }
            .price {
                font-size: 32px;
            }
        }

        /* Tablet (768px - 1024px) */
        @media (min-width: 768px) and (max-width: 1024px) {
            .container {
                padding: 0 30px;
            }
            
            .products-grid {
                grid-template-columns: repeat(3, 1fr);
                gap: 25px;
            }
            
            .hero h1 {
                font-size: 42px;
            }
            
            .hero p {
                font-size: 24px;
            }
            
            .hero-content {
                padding: 40px;
                margin: 0 20px;
            }
            
            .section-title h2 {
                font-size: 40px;
            }
            
            .categories-grid {
                grid-template-columns: repeat(3, 1fr);
                gap: 25px;
            }
            
            .footer-content {
                grid-template-columns: repeat(2, 1fr);
                gap: 35px;
            }
            
            .about-content {
                flex-direction: column;
                text-align: center;
                gap: 40px;
            }
            
            .about-image {
                order: -1;
                max-width: 500px;
                margin: 0 auto;
                box-shadow: 0 10px 0 var(--dark-cream);
            }
            
            .about-stats {
                justify-content: space-around;
            }
            
            .price {
                font-size: 28px;
            }
            
            .product-content h3 {
                font-size: 22px;
            }
        }

        /* Mobile (up to 767px) */
        @media (max-width: 767px) {
            body {
                font-size: 20px;
            }
            
            .container {
                padding: 0 16px;
            }
            
            /* Mobile Menu */
            nav {
                position: fixed;
                top: 0;
                left: -100%;
                width: 280px;
                height: 100vh;
                background-color: var(--beige);
                flex-direction: column;
                padding: 100px 30px 30px;
                transition: left 0.4s ease;
                box-shadow: 5px 0 15px rgba(139, 69, 19, 0.3);
                border-right: 2px solid var(--dark-cream);
                z-index: 999;
            }
            
            nav.active {
                left: 0;
            }
            
            nav ul {
                flex-direction: column;
                gap: 25px;
            }
            
            nav a {
                font-size: 24px;
            }
            
            .mobile-menu-btn {
                display: block;
            }
            
            .header-actions {
                gap: 12px;
            }
            
            /* Products grid - 1-2 columns */
            .products-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 16px;
            }
            
            /* Hero section */
            .hero {
                height: auto;
                min-height: 100vh;
                padding: 120px 0 60px;
            }
            
            .hero h1 {
                font-size: 32px;
            }
            
            .hero p {
                font-size: 20px;
            }
            
            .hero-content {
                padding: 30px 20px;
                margin: 0;
            }
            
            .btn {
                padding: 12px 25px;
                font-size: 18px;
                display: inline-block;
                margin-bottom: 10px;
                width: auto;
            }
            
            .btn-outline {
                margin-left: 10px;
            }
            
            /* Sections padding */
            section {
                padding: 60px 0;
            }
            
            .section-title {
                margin-bottom: 40px;
            }
            
            .section-title h2 {
                font-size: 32px;
            }
            
            /* Categories */
            .categories-grid {
                grid-template-columns: 1fr;
                gap: 20px;
            }
            
            .category-card {
                height: 300px;
            }
            
            /* Products */
            .product-img {
                height: 200px;
            }
            
            .product-content h3 {
                font-size: 18px;
                min-height: auto;
            }
            
            .product-description {
                font-size: 14px;
                min-height: auto;
                margin-bottom: 10px;
            }
            
            .price {
                font-size: 24px;
            }
            
            .old-price {
                font-size: 14px;
            }
            
            .product-actions {
                gap: 8px;
            }
            
            .add-to-cart, .view-details {
                width: 34px;
                height: 34px;
                font-size: 14px;
            }
            
            /* Filters */
            .products-filter {
                gap: 10px;
                margin-bottom: 30px;
            }
            
            .filter-btn {
                padding: 8px 18px;
                font-size: 18px;
            }
            
            /* About */
            .about-content {
                flex-direction: column;
                gap: 30px;
            }
            
            .about-text h2 {
                font-size: 32px;
                text-align: center;
            }
            
            .about-text p {
                font-size: 18px;
                text-align: center;
            }
            
            .about-stats {
                flex-direction: column;
                gap: 25px;
            }
            
            .about-image {
                order: -1;
                max-width: 100%;
                box-shadow: 0 8px 0 var(--dark-cream);
            }
            
            /* Footer */
            .footer-content {
                grid-template-columns: 1fr;
                gap: 35px;
            }
            
            .footer-column {
                text-align: center;
            }
            
            .footer-column h3:after {
                left: 50%;
                transform: translateX(-50%);
            }
            
            .social-links {
                justify-content: center;
            }
            
            .newsletter-form {
                max-width: 300px;
                margin: 20px auto 0;
            }
            
            /* Cart modal */
            .cart-modal {
                max-width: 100%;
            }
            
            /* Search */
            .search-expanded {
                position: fixed;
                top: 70px;
                left: 16px;
                right: 16px;
                width: auto;
                z-index: 1002;
            }
            
            .search-toggle {
                width: 40px;
                height: 40px;
                font-size: 16px;
            }
            
            .theme-toggle {
                width: 44px;
                height: 24px;
            }
            
            .theme-toggle-handle {
                width: 16px;
                height: 16px;
            }
            
            .theme-toggle.active .theme-toggle-handle {
                transform: translateX(20px);
            }
            
            .logo {
                font-size: 26px;
            }
            
            .logo-text {
                display: inline-block;
            }
            
            .cart-icon {
                font-size: 22px;
            }
            
            .cart-count {
                font-size: 12px;
                width: 18px;
                height: 18px;
                top: -6px;
                right: -6px;
            }
            
            .notification {
                top: 80px;
                right: 10px;
                left: 10px;
                max-width: none;
                font-size: 16px;
                text-align: center;
            }
        }

        /* Small mobile (up to 480px) */
        @media (max-width: 480px) {
            .products-grid {
                grid-template-columns: 1fr;
                gap: 20px;
            }
            
            .hero h1 {
                font-size: 28px;
            }
            
            .hero p {
                font-size: 18px;
            }
            
            .hero-content {
                padding: 25px 16px;
            }
            
            .btn, .btn-outline {
                display: block;
                width: 100%;
                margin: 10px 0;
                text-align: center;
            }
            
            .btn-outline {
                margin-left: 0;
            }
            
            .price {
                font-size: 26px;
            }
            
            .product-price {
                flex-direction: column;
                align-items: flex-start;
                gap: 10px;
            }
            
            .product-actions {
                width: 100%;
                justify-content: flex-end;
            }
            
            .logo {
                font-size: 22px;
            }
            
            .header-actions {
                gap: 8px;
            }
            
            .theme-toggle {
                width: 40px;
                height: 22px;
            }
            
            .theme-toggle-handle {
                width: 14px;
                height: 14px;
                left: 2px;
                top: 2px;
            }
            
            .theme-toggle.active .theme-toggle-handle {
                transform: translateX(18px);
            }
            
            .search-toggle {
                width: 36px;
                height: 36px;
                font-size: 14px;
            }
        }

        /* Dark theme starry background */
        .starry-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
            opacity: 0;
            transition: opacity 0.5s ease;
        }

        body.dark-theme .starry-bg {
            opacity: 1;
        }

        .star {
            position: absolute;
            background-color: white;
            border-radius: 50%;
            animation: twinkle var(--duration) ease-in-out infinite;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.3; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.2); }
        }

        .hidden {
            display: none !important;
        }
    </style>
</head>
<body>
    <!-- Фон с мерцающими звездами -->
    <div class="starry-bg" id="starryBg"></div>
    
    <!-- Header -->
    <header id="header">
        <div class="container">
            <div class="header-content">
                <a href="#home" class="logo">
                    <i class="fas fa-crown"></i>
                    <span class="logo-text">LuxeStyle</span>
                </a>
                
                <nav id="nav">
                    <ul>
                        <li><a href="#home" class="nav-link" data-translate="nav.home">Главная</a></li>
                        <li><a href="#categories" class="nav-link" data-translate="nav.categories">Категории</a></li>
                        <li><a href="#products" class="nav-link" data-translate="nav.products">Товары</a></li>
                        <li><a href="#about" class="nav-link" data-translate="nav.about">О нас</a></li>
                        <li><a href="#contact" class="nav-link" data-translate="nav.contact">Контакты</a></li>
                    </ul>
                </nav>
                
                <div class="header-actions">
                    <div class="compact-search" id="compactSearch">
                        <button class="search-toggle" id="searchToggle" title="Поиск">
                            <i class="fas fa-search"></i>
                        </button>
                        <div class="search-expanded" id="searchExpanded">
                            <div class="search-input-wrapper">
                                <input type="text" class="search-input" id="searchInput" placeholder="Поиск товаров...">
                                <button class="search-submit" id="searchSubmit">
                                    <i class="fas fa-search"></i>
                                </button>
                            </div>
                            <div class="search-results" id="searchResults"></div>
                        </div>
                    </div>
                    
                    <div class="theme-toggle" id="themeToggle" title="Переключить тему">
                        <i class="fas fa-sun"></i>
                        <i class="fas fa-moon"></i>
                        <div class="theme-toggle-handle"></div>
                    </div>
                    
                    <div class="language-selector" id="languageSelector">
                        <div class="language-flag" id="currentFlag">
                            <img src="https://flagcdn.com/w40/ru.png" alt="Русский">
                        </div>
                        <span id="currentLanguage">РУ</span>
                        <div class="language-dropdown">
                            <div class="language-option" data-lang="ru">
                                <div class="language-flag">
                                    <img src="https://flagcdn.com/w40/ru.png" alt="Русский">
                                </div>
                                <span>Русский</span>
                            </div>
                            <div class="language-option" data-lang="en">
                                <div class="language-flag">
                                    <img src="https://flagcdn.com/w40/gb.png" alt="English">
                                </div>
                                <span>English</span>
                            </div>
                            <div class="language-option" data-lang="kz">
                                <div class="language-flag">
                                    <img src="https://flagcdn.com/w40/kz.png" alt="Қазақша">
                                </div>
                                <span>Қазақша</span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="cart-icon" id="cartIcon">
                        <i class="fas fa-shopping-bag"></i>
                        <span class="cart-count" id="cartCount">0</span>
                    </div>
                    
                    <button class="mobile-menu-btn" id="mobileMenuBtn">
                        <i class="fas fa-bars"></i>
                    </button>
                </div>
            </div>
        </div>
        <div class="search-overlay" id="searchOverlay"></div>
    </header>

    <!-- Cart Modal -->
    <div class="modal-overlay" id="modalOverlay"></div>
    <div class="cart-modal" id="cartModal">
        <div class="cart-header">
            <h3 data-translate="cart.title">Корзина</h3>
            <button class="close-cart" id="closeCartBtn">
                <i class="fas fa-times"></i>
            </button>
        </div>
        
        <div class="cart-items" id="cartItemsContainer">
            <!-- Cart items will be rendered here -->
        </div>
        
        <div class="cart-footer" id="cartFooter">
            <div class="cart-total">
                <span data-translate="cart.total">Итого:</span>
                <span class="total-amount" id="cartTotalPrice">0 ₽</span>
            </div>
            <button class="checkout-btn" id="checkoutBtn" data-translate="cart.checkout">Оформить заказ</button>
        </div>
    </div>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content">
                <h1 data-translate="hero.title">Эксклюзивные брендовые вещи для истинных ценителей</h1>
                <p data-translate="hero.subtitle">Откройте для себя мир роскоши и стиля с нашей коллекцией премиальных брендов. Качество, которое говорят само за себя.</p>
                <div>
                    <a href="#products" class="btn pulse-animation" data-translate="hero.collection_btn">Коллекция</a>
                    <a href="#about" class="btn btn-outline" data-translate="hero.about_btn">О нас</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Categories Section -->
    <section class="categories" id="categories">
        <div class="container">
            <div class="section-title">
                <h2 data-translate="categories.title">Категории</h2>
            </div>
            
            <div class="categories-grid">
                <div class="category-card" data-category="clothing">
                    <div class="category-img">
                        <img src="https://images.unsplash.com/photo-1591047139829-d91aecb6caea?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Одежда">
                    </div>
                    <div class="category-content">
                        <h3 data-translate="categories.clothing">Одежда</h3>
                        <p data-translate="categories.clothing_desc">Эксклюзивная одежда от мировых брендов</p>
                    </div>
                </div>
                
                <div class="category-card" data-category="shoes">
                    <div class="category-img">
                        <img src="https://images.unsplash.com/photo-1543163521-1bf539c55dd2?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Обувь">
                    </div>
                    <div class="category-content">
                        <h3 data-translate="categories.shoes">Обувь</h3>
                        <p data-translate="categories.shoes_desc">Коллекция премиальной обуви</p>
                    </div>
                </div>
                
                <div class="category-card" data-category="accessories">
                    <div class="category-img">
                        <img src="https://images.unsplash.com/photo-1599643478518-a784e5dc4c8f?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Аксессуары">
                    </div>
                    <div class="category-content">
                        <h3 data-translate="categories.accessories">Аксессуары</h3>
                        <p data-translate="categories.accessories_desc">Роскошные аксессуары для завершения образа</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Products Section -->
    <section class="products" id="products">
        <div class="container">
            <div class="section-title">
                <h2 data-translate="products.title">Популярные товары</h2>
            </div>
            
            <div class="products-filter">
                <button class="filter-btn active" data-filter="all" data-translate="products.all">Все товары</button>
                <button class="filter-btn" data-filter="clothing" data-translate="categories.clothing">Одежда</button>
                <button class="filter-btn" data-filter="shoes" data-translate="categories.shoes">Обувь</button>
                <button class="filter-btn" data-filter="accessories" data-translate="categories.accessories">Аксессуары</button>
            </div>
            
            <div class="products-grid" id="productsGrid">
                <!-- Товары будут загружены через JavaScript -->
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section class="about" id="about">
        <div class="container">
            <div class="about-content">
                <div class="about-text">
                    <h2 data-translate="about.title">О LuxeStyle</h2>
                    <p data-translate="about.desc1">Мы — эксклюзивный ритейлер люксовых брендов, предлагающий тщательно отобранную коллекцию премиальных товаров для ценителей настоящего качества и стиля.</p>
                    <p data-translate="about.desc2">Наша миссия — предоставить доступ к самым востребованным и редким предметам роскоши, сочетающим в себе безупречный дизайн, высочайшее качество и статусность.</p>
                    
                    <div class="about-stats">
                        <div class="stat-item">
                            <span class="stat-number">2010</span>
                            <span class="stat-label" data-translate="about.year">Год основания</span>
                        </div>
                        <div class="stat-item">
                            <span class="stat-number">50+</span>
                            <span class="stat-label" data-translate="about.brands">Брендов</span>
                        </div>
                        <div class="stat-item">
                            <span class="stat-number">25k+</span>
                            <span class="stat-label" data-translate="about.clients">Довольных клиентов</span>
                        </div>
                    </div>
                </div>
                
                <div class="about-image">
                    <img src="https://images.unsplash.com/photo-1445205170230-053b83016050?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="О нашем магазине">
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contact">
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3 data-translate="footer.about_title">О компании</h3>
                    <p data-translate="footer.about_desc">Эксклюзивные брендовые вещи для истинных ценителей роскоши и стиля.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-pinterest-p"></i></a>
                    </div>
                </div>
                
                <div class="footer-column">
                    <h3 data-translate="footer.categories_title">Категории</h3>
                    <ul class="footer-links">
                        <li><a href="#categories" data-translate="categories.clothing">Одежда</a></li>
                        <li><a href="#categories" data-translate="categories.shoes">Обувь</a></li>
                        <li><a href="#categories" data-translate="categories.accessories">Аксессуары</a></li>
                        <li><a href="#products" data-translate="footer.new_collection">Новая коллекция</a></li>
                        <li><a href="#products" data-translate="footer.sale">Распродажа</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3 data-translate="footer.info_title">Информация</h3>
                    <ul class="footer-links">
                        <li><a href="#about" data-translate="nav.about">О нас</a></li>
                        <li><a href="#" data-translate="footer.delivery">Доставка и оплата</a></li>
                        <li><a href="#" data-translate="footer.returns">Возврат и обмен</a></li>
                        <li><a href="#" data-translate="footer.privacy">Политика конфиденциальности</a></li>
                        <li><a href="#contact" data-translate="nav.contact">Контакты</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3 data-translate="footer.newsletter_title">Новостная рассылка</h3>
                    <p data-translate="footer.newsletter_desc">Подпишитесь на рассылку и получите скидку 10% на первый заказ.</p>
                    <form class="newsletter-form" id="newsletterForm">
                        <input type="email" class="newsletter-input" id="newsletterInput" placeholder="Ваш email" required>
                        <button type="submit" class="newsletter-btn">
                            <i class="fas fa-paper-plane"></i>
                        </button>
                    </form>
                </div>
            </div>
            
            <div class="copyright">
                <p>&copy; 2023 LuxeStyle. <span data-translate="footer.rights">Все права защищены.</span></p>
            </div>
        </div>
    </footer>

    <script>
        // ============== ГЛОБАЛЬНЫЕ ПЕРЕМЕННЫЕ ==============
        let currentLang = 'ru';
        let currentFilter = 'all';
        let cart = JSON.parse(localStorage.getItem('luxestyle_cart')) || [];
        let products = [];
        let isDarkTheme = localStorage.getItem('luxestyle_dark_theme') === 'true';
        let searchTimeout = null;

        // ============== ДАННЫЕ ТОВАРОВ (цены от 5000 до 10000 руб.) ==============
        const productsData = [
            { id: 1, name: { ru: "Кожаная куртка премиум-класса", en: "Premium Leather Jacket", kz: "Премиум былған кожа куртка" }, category: "clothing", price: 8900, image: "https://primovello.ru/upload/phpthumb/13/28eb40578103936682746c3e48c30fa8.webp", badge: "New", description: { ru: "Итальянская кожа, ручная работа", en: "Italian leather, handmade", kz: "Итальян кожасы, қолдан жасалған" } },
            { id: 2, name: { ru: "Кашемировое пальто", en: "Cashmere Coat", kz: "Кашемир пальто" }, category: "clothing", price: 12500, image: "https://st.aestatic.net/items-img/R/F/2/N/A698e03202c994d77963cb55cc22e685b3.jpeg_960x960.jpg", badge: "Luxury", description: { ru: "100% кашемир, ограниченная серия", en: "100% cashmere, limited edition", kz: "100% кашемир, шектеулі басылым" } },
            { id: 3, name: { ru: "Дизайнерское вечернее платье", en: "Designer Evening Dress", kz: "Дизайнерлік кешкі көйлек" }, category: "clothing", price: 18500, image: "https://i.pinimg.com/originals/cf/dc/4e/cfdc4e7119a954b5134961e9c53c87c8.jpg", badge: "Exclusive", description: { ru: "Ручная вышивка, эксклюзивный дизайн", en: "Hand embroidery, exclusive design", kz: "Қолдан кестеленген, эксклюзивті дизайн" } },
            { id: 4, name: { ru: "Брендовая рубашка", en: "Branded Shirt", kz: "Брендтік жейде" }, category: "clothing", price: 6900, image: "https://n.cdn.cdek.shopping/images/shopping/64VkVYwOk7hz03dR.jpg?v=1", badge: "Sale", oldPrice: 9900, description: { ru: "Хлопок премиум качества, итальянский пошив", en: "Premium cotton, Italian tailoring", kz: "Премиум мақта, итальяндық тігін" } },
            { id: 5, name: { ru: "Дизайнерские кроссовки", en: "Designer Sneakers", kz: "Дизайнерлік кросовкалар" }, category: "shoes", price: 7500, image: "https://ir.ozone.ru/s3/multimedia-1/c600/6705766117.jpg", badge: "Хит", description: { ru: "Эксклюзивная коллекция", en: "Exclusive collection", kz: "Эксклюзивті жинақ" } },
            { id: 6, name: { ru: "Кожаные туфли ручной работы", en: "Handmade Leather Shoes", kz: "Қолдан жасалған былған кожа туфли" }, category: "shoes", price: 8500, image: "https://avatars.mds.yandex.net/i?id=7ed11f0327e5fb840693e3e1ce8998b4_sr-3688950-images-thumbs&n=13", badge: "Handmade", description: { ru: "Ручная работа, натуральная кожа", en: "Handmade, genuine leather", kz: "Қолдан жасалған, нағыз кожа" } },
            { id: 7, name: { ru: "Зимние ботинки из нубука", en: "Winter Nubuck Boots", kz: "Қысқы нубук етік" }, category: "shoes", price: 9200, image: "https://static.insales-cdn.com/images/products/1/1109/138077269/lg-001.jpg", badge: "Winter", description: { ru: "Водонепроницаемые, утепленные", en: "Waterproof, insulated", kz: "Су өткізбейтін, жылы" } },
            { id: 8, name: { ru: "Классические оксфорды", en: "Classic Oxfords", kz: "Классикалық оксфордтар" }, category: "shoes", price: 9900, image: "https://cdn-sh1.vigbo.com/shops/119009/products/13673558/images/3-6ef45b54b04624037e8fe8db5bb8f74d.jpg", badge: "Classic", description: { ru: "Английский стиль, премиум кожа", en: "English style, premium leather", kz: "Ағылшын стилі, премиум кожа" } },
            { id: 9, name: { ru: "Швейцарские часы", en: "Swiss Watch", kz: "Швейцариялық сағат" }, category: "accessories", price: 5800, image: "https://avatars.mds.yandex.net/i?id=2c421457220dc1e7aab26d65f5656851_l-5209742-images-thumbs&n=13", badge: "VIP", vip: true, description: { ru: "Автоматический механизм", en: "Automatic movement", kz: "Автоматты механизм" } },
            { id: 10, name: { ru: "Дизайнерская кожаная сумка", en: "Designer Leather Bag", kz: "Дизайнерлік былған кожа сөмке" }, category: "accessories", price: 11200, image: "https://i.pinimg.com/originals/67/5a/59/675a598b33e74527f4d8110a354080fb.jpg", badge: "Sale", oldPrice: 14500, description: { ru: "Ручная работа, натуральная кожа", en: "Handmade, genuine leather", kz: "Қолдан жасалған, нағыз кожа" } },
            { id: 11, name: { ru: "Золотые запонки", en: "Gold Cufflinks", kz: "Алтын манжет түймелері" }, category: "accessories", price: 4800, image: "https://avatars.mds.yandex.net/i?id=68c934408b0e5a4753734e7087d383d7_l-10752576-images-thumbs&n=13", badge: "New", description: { ru: "18-каратное золото", en: "18-karat gold", kz: "18 карат алтын" } },
            { id: 12, name: { ru: "Дизайнерский кожаный ремень", en: "Designer Leather Belt", kz: "Дизайнерлік былған кожа белбеу" }, category: "accessories", price: 3900, image: "https://img.joomcdn.net/3570a0f6db84bbeac03fa9a36a55b6b5fcbaa72f_original.jpeg", badge: "Premium", description: { ru: "Натуральная кожа", en: "Genuine leather", kz: "Нағыз кожа" } },
            { id: 13, name: { ru: "Шерстяной блейзер", en: "Wool Blazer", kz: "Жүн блейзер" }, category: "clothing", price: 6800, image: "https://avatars.mds.yandex.net/i?id=affe3ede110aa9222ee58509a02317ef2f0e3b1b-5869570-images-thumbs&n=13", badge: "New", description: { ru: "Шерсть мериноса", en: "Merino wool", kz: "Мерино жүні" } },
            { id: 14, name: { ru: "Шелковое платье", en: "Silk Dress", kz: "Жібек көйлек" }, category: "clothing", price: 9500, image: "https://avatars.mds.yandex.net/i?id=5aa291879f3ada160d8e8cb91c55d1255bd30733-5133916-images-thumbs&n=13", badge: "Luxury", description: { ru: "100% натуральный шелк", en: "100% natural silk", kz: "100% табиғи жібек" } },
            { id: 15, name: { ru: "Кожаные штаны", en: "Leather Pants", kz: "Былған кожа шалбар" }, category: "clothing", price: 7500, image: "https://avatars.mds.yandex.net/i?id=f6c133850977e7b5823ac1beb9133c49e81fa5d0-4385982-images-thumbs&n=13", badge: "Sale", oldPrice: 9500, description: { ru: "Мягкая кожа", en: "Soft leather", kz: "Жұмсақ кожа" } },
            { id: 16, name: { ru: "Кашемировый свитер", en: "Cashmere Sweater", kz: "Кашемир свитер" }, category: "clothing", price: 5500, image: "https://avatars.mds.yandex.net/i?id=7efa45f36a90062258668d63321a39a62577dc84-12154389-images-thumbs&n=13", badge: "Хит", description: { ru: "Невероятно мягкий", en: "Incredibly soft", kz: "Өте жұмсақ" } },
            { id: 17, name: { ru: "Кожаные лоферы", en: "Leather Loafers", kz: "Былған кожа лоферлер" }, category: "shoes", price: 6500, image: "https://avatars.mds.yandex.net/i?id=9650be67ea17d3fe72918999826d1f9e67d91b4c-4219872-images-thumbs&n=13", badge: "Classic", description: { ru: "Комфорт на весь день", en: "All-day comfort", kz: "Күні бойы ыңғайлылық" } },
            { id: 18, name: { ru: "Спортивные кроссовки", en: "Sports Sneakers", kz: "Спорттық кросовкалар" }, category: "shoes", price: 5200, image: "https://avatars.mds.yandex.net/i?id=e53882dafcf7d50425e88aecd6abe5bf827c51c7-5887670-images-thumbs&n=13", badge: "Sport", description: { ru: "Технологичная подошва", en: "Technological sole", kz: "Технологиялық табан" } },
            { id: 19, name: { ru: "Сапоги на каблуке", en: "Heeled Boots", kz: "Өкшелі етік" }, category: "shoes", price: 8800, image: "https://avatars.mds.yandex.net/i?id=599b382bf4a86f7ab98360c0ca1fca29e57256b7-4517378-images-thumbs&n=13", badge: "Fashion", description: { ru: "Стильные, удобные", en: "Stylish, comfortable", kz: "Стильді, ыңғайлы" } },
            { id: 20, name: { ru: "Кроссовки для бега", en: "Running Sneakers", kz: "Жүгіру кросовкалары" }, category: "shoes", price: 4600, image: "https://avatars.mds.yandex.net/i?id=7e94ab4d9e92a3c442aa5bc8e2aed0fbfaf1c2fd-12146892-images-thumbs&n=13", badge: "Sale", oldPrice: 6500, description: { ru: "Амортизация", en: "Cushioning", kz: "Амортизация" } },
            { id: 21, name: { ru: "Солнечные очки", en: "Sunglasses", kz: "Күннен қорғайтын көзілдірік" }, category: "accessories", price: 3200, image: "https://avatars.mds.yandex.net/i?id=1363f2896e16c2f192cee3e125ac167e-4575620-images-thumbs&n=13", badge: "New", description: { ru: "UV защита", en: "UV protection", kz: "UV қорғаныс" } },
            { id: 22, name: { ru: "Кожаный бумажник", en: "Leather Wallet", kz: "Былған кожа әмиян" }, category: "accessories", price: 2500, image: "https://avatars.mds.yandex.net/i?id=e3df1907290f8abb0c0b7ade3973a3c2bbf28c6e-5147471-images-thumbs&n=13", badge: "Premium", description: { ru: "Натуральная кожа", en: "Genuine leather", kz: "Нағыз кожа" } },
            { id: 23, name: { ru: "Шелковый шарф", en: "Silk Scarf", kz: "Жібек шарф" }, category: "accessories", price: 4200, image: "https://avatars.mds.yandex.net/i?id=2a4089059da56db826cf41a38c02440d3f87fc45-5693960-images-thumbs&n=13", badge: "Luxury", description: { ru: "Итальянский шелк", en: "Italian silk", kz: "Итальян жібегі" } },
            { id: 24, name: { ru: "Ювелирное колье", en: "Jewelry Necklace", kz: "Зергерлік алқа" }, category: "accessories", price: 7800, image: "https://avatars.mds.yandex.net/i?id=ba49fe7ec3ceb383b61e21bd963683084ce7b428-4259532-images-thumbs&n=13", badge: "Exclusive", description: { ru: "Серебро с позолотой", en: "Silver with gold plating", kz: "Алтынмен қапталған күміс" } }
        ];

        // ============== ТЕКСТЫ ДЛЯ ПЕРЕВОДА ==============
        const translations = {
            ru: {
                "nav.home": "Главная", "nav.categories": "Категории", "nav.products": "Товары", "nav.about": "О нас", "nav.contact": "Контакты",
                "hero.title": "Эксклюзивные брендовые вещи для истинных ценителей",
                "hero.subtitle": "Откройте для себя мир роскоши и стиля с нашей коллекцией премиальных брендов. Качество, которое говорят само за себя.",
                "hero.collection_btn": "Коллекция", "hero.about_btn": "О нас",
                "categories.title": "Категории", "categories.clothing": "Одежда", "categories.clothing_desc": "Эксклюзивная одежда от мировых брендов",
                "categories.shoes": "Обувь", "categories.shoes_desc": "Коллекция премиальной обуви",
                "categories.accessories": "Аксессуары", "categories.accessories_desc": "Роскошные аксессуары",
                "products.title": "Популярные товары", "products.all": "Все товары",
                "cart.title": "Корзина", "cart.empty": "Ваша корзина пуста", "cart.empty_desc": "Добавьте товары из каталога",
                "cart.total": "Итого:", "cart.checkout": "Оформить заказ", "cart.item_added": "Товар добавлен в корзину",
                "about.title": "О LuxeStyle", "about.desc1": "Мы — эксклюзивный ритейлер люксовых брендов.", "about.desc2": "Наша миссия — предоставить доступ к самым востребованным предметам роскоши.",
                "about.year": "Год основания", "about.brands": "Брендов", "about.clients": "Довольных клиентов",
                "footer.about_title": "О компании", "footer.about_desc": "Эксклюзивные брендовые вещи для истинных ценителей.",
                "footer.categories_title": "Категории", "footer.new_collection": "Новая коллекция", "footer.sale": "Распродажа",
                "footer.info_title": "Информация", "footer.delivery": "Доставка и оплата", "footer.returns": "Возврат и обмен",
                "footer.privacy": "Политика конфиденциальности", "footer.newsletter_title": "Новостная рассылка",
                "footer.newsletter_desc": "Подпишитесь на рассылку и получите скидку 10%", "footer.rights": "Все права защищены.",
                "product.view": "Посмотреть детали", "product.add_to_cart": "Добавить в корзину",
                "notification.success": "Успешно!", "notification.error": "Ошибка!", "notification.subscribed": "Вы подписались на рассылку!",
                "notification.invalid_email": "Введите корректный email"
            },
            en: {
                "nav.home": "Home", "nav.categories": "Categories", "nav.products": "Products", "nav.about": "About", "nav.contact": "Contact",
                "hero.title": "Exclusive Branded Items for True Connoisseurs",
                "hero.subtitle": "Discover the world of luxury and style with our collection of premium brands.",
                "hero.collection_btn": "Collection", "hero.about_btn": "About",
                "categories.title": "Categories", "categories.clothing": "Clothing", "categories.clothing_desc": "Exclusive clothing from world brands",
                "categories.shoes": "Shoes", "categories.shoes_desc": "Collection of premium footwear",
                "categories.accessories": "Accessories", "categories.accessories_desc": "Luxurious accessories",
                "products.title": "Popular Products", "products.all": "All Products",
                "cart.title": "Shopping Cart", "cart.empty": "Your cart is empty", "cart.empty_desc": "Add items from the catalog",
                "cart.total": "Total:", "cart.checkout": "Checkout", "cart.item_added": "Item added to cart",
                "about.title": "About LuxeStyle", "about.desc1": "We are an exclusive retailer of luxury brands.", "about.desc2": "Our mission is to provide access to the most sought-after luxury items.",
                "about.year": "Year founded", "about.brands": "Brands", "about.clients": "Satisfied clients",
                "footer.about_title": "About Company", "footer.about_desc": "Exclusive branded items for true connoisseurs.",
                "footer.categories_title": "Categories", "footer.new_collection": "New Collection", "footer.sale": "Sale",
                "footer.info_title": "Information", "footer.delivery": "Delivery & Payment", "footer.returns": "Returns & Exchange",
                "footer.privacy": "Privacy Policy", "footer.newsletter_title": "Newsletter",
                "footer.newsletter_desc": "Subscribe and get 10% off", "footer.rights": "All rights reserved.",
                "product.view": "View details", "product.add_to_cart": "Add to Cart",
                "notification.success": "Success!", "notification.error": "Error!", "notification.subscribed": "You have subscribed!",
                "notification.invalid_email": "Enter a valid email"
            },
            kz: {
                "nav.home": "Басты", "nav.categories": "Санаттар", "nav.products": "Тауарлар", "nav.about": "Біз туралы", "nav.contact": "Байланыс",
                "hero.title": "Нағыз талғампаздарға арналған эксклюзивті брендтік заттар",
                "hero.subtitle": "Біздің премиум брендтер жинағымен сән мен сәнділік әлемін ашыңыз.",
                "hero.collection_btn": "Жинақ", "hero.about_btn": "Біз туралы",
                "categories.title": "Санаттар", "categories.clothing": "Киім", "categories.clothing_desc": "Әлемдік брендтердің эксклюзивті киімдері",
                "categories.shoes": "Аяқ киім", "categories.shoes_desc": "Премиум аяқ киімдер жинағы",
                "categories.accessories": "Аксессуарлар", "categories.accessories_desc": "Сәнді аксессуарлар",
                "products.title": "Танымал тауарлар", "products.all": "Барлық тауарлар",
                "cart.title": "Себет", "cart.empty": "Сіздің себетіңіз бос", "cart.empty_desc": "Каталогтан тауарлар қосыңыз",
                "cart.total": "Барлығы:", "cart.checkout": "Тапсырысты рәсімдеу", "cart.item_added": "Тауар себетке қосылды",
                "about.title": "LuxeStyle туралы", "about.desc1": "Біз - люкс брендтердің эксклюзивті дистрибьюторымыз.", "about.desc2": "Біздің миссиямыз - сирек люкс заттарға қол жеткізу.",
                "about.year": "Құрылған жылы", "about.brands": "Брендтер", "about.clients": "Қанағаттанған клиенттер",
                "footer.about_title": "Компания туралы", "footer.about_desc": "Нағыз сәнділік пен сән талғампаздарына арналған эксклюзивті брендтік заттар.",
                "footer.categories_title": "Санаттар", "footer.new_collection": "Жаңа жинақ", "footer.sale": "Сатылым",
                "footer.info_title": "Ақпарат", "footer.delivery": "Жеткізу және төлем", "footer.returns": "Қайтару және алмасу",
                "footer.privacy": "Құпиялылық саясаты", "footer.newsletter_title": "Жаңалықтар тарату",
                "footer.newsletter_desc": "Жазылыңыз және 10% жеңілдік алыңыз", "footer.rights": "Барлық құқықтар қорғалған.",
                "product.view": "Толығырақ қарау", "product.add_to_cart": "Себетке қосу",
                "notification.success": "Сәтті!", "notification.error": "Қате!", "notification.subscribed": "Сіз жазылдыңыз!",
                "notification.invalid_email": "Дұрыс email енгізіңіз"
            }
        };

        // ============== ФУНКЦИИ ==============
        function formatPrice(price) {
            const formats = { 'en': { symbol: '$', multiplier: 0.012 }, 'kz': { symbol: '₸', multiplier: 5.5 }, 'ru': { symbol: '₽', multiplier: 1 } };
            const format = formats[currentLang] || formats.ru;
            const formattedPrice = Math.round(price * format.multiplier).toLocaleString();
            return `${formattedPrice} ${format.symbol}`;
        }

        function getTranslation(key) { return translations[currentLang]?.[key] || key; }

        function updateAllTexts() {
            document.querySelectorAll('[data-translate]').forEach(el => {
                const key = el.getAttribute('data-translate');
                if (el.tagName === 'INPUT') el.placeholder = getTranslation(key);
                else el.textContent = getTranslation(key);
            });
        }

        function updateLanguageUI(lang) {
            const flags = { 'ru': { src: 'https://flagcdn.com/w40/ru.png', text: 'РУ' }, 'en': { src: 'https://flagcdn.com/w40/gb.png', text: 'EN' }, 'kz': { src: 'https://flagcdn.com/w40/kz.png', text: 'ҚАЗ' } };
            if (flags[lang]) {
                document.querySelector('#currentFlag img').src = flags[lang].src;
                document.getElementById('currentLanguage').textContent = flags[lang].text;
            }
        }

        function setLanguage(lang) {
            if (!translations[lang]) return;
            currentLang = lang;
            localStorage.setItem('luxestyle_lang', lang);
            updateLanguageUI(lang);
            updateAllTexts();
            renderProducts(currentFilter);
            if (document.getElementById('cartModal').classList.contains('active')) renderCartItems();
            document.getElementById('languageSelector')?.classList.remove('active');
            showNotification(getTranslation('notification.success') + ' Язык изменен', 'success');
        }

        function saveCartToStorage() { localStorage.setItem('luxestyle_cart', JSON.stringify(cart)); }
        
        function updateCartCount() {
            const count = cart.reduce((total, item) => total + item.quantity, 0);
            document.getElementById('cartCount').textContent = count;
        }

        function showNotification(message, type = 'info') {
            const old = document.querySelectorAll('.notification');
            old.forEach(n => n.remove());
            const notification = document.createElement('div');
            notification.className = `notification ${type}`;
            notification.textContent = message;
            document.body.appendChild(notification);
            setTimeout(() => notification.classList.add('show'), 10);
            setTimeout(() => { notification.classList.remove('show'); setTimeout(() => notification.remove(), 300); }, 3000);
        }

        function addToCart(productId, buttonElement = null) {
            const product = products.find(p => p.id === productId);
            if (!product) return;
            const existing = cart.find(item => item.id === productId);
            if (existing) existing.quantity += 1;
            else cart.push({ id: product.id, name: product.name[currentLang] || product.name.ru, price: product.price, image: product.image, quantity: 1 });
            saveCartToStorage();
            updateCartCount();
            if (document.getElementById('cartModal').classList.contains('active')) renderCartItems();
            showNotification(getTranslation('cart.item_added'), 'success');
        }

        function removeFromCart(productId) {
            cart = cart.filter(item => item.id !== productId);
            saveCartToStorage();
            updateCartCount();
            renderCartItems();
            if (cart.length === 0) showNotification(getTranslation('cart.empty'), 'info');
            else showNotification('Товар удален', 'info');
        }

        function updateCartItemQuantity(productId, change) {
            const item = cart.find(i => i.id === productId);
            if (item) {
                item.quantity += change;
                if (item.quantity < 1) removeFromCart(productId);
                else { saveCartToStorage(); renderCartItems(); updateCartCount(); }
            }
        }

        function renderCartItems() {
            const container = document.getElementById('cartItemsContainer');
            const footer = document.getElementById('cartFooter');
            if (!container) return;
            if (cart.length === 0) {
                container.innerHTML = `<div class="cart-empty"><i class="fas fa-shopping-bag"></i><h4>${getTranslation('cart.empty')}</h4><p>${getTranslation('cart.empty_desc')}</p></div>`;
                footer.style.display = 'none';
                return;
            }
            footer.style.display = 'block';
            let total = 0;
            container.innerHTML = cart.map(item => {
                total += item.price * item.quantity;
                return `<div class="cart-item" data-id="${item.id}">
                    <div class="cart-item-img"><img src="${item.image}" alt="${item.name}"></div>
                    <div class="cart-item-details">
                        <div class="cart-item-title">${item.name}</div>
                        <div class="cart-item-price">${formatPrice(item.price)}</div>
                        <div class="cart-item-controls">
                            <button class="quantity-btn decrease" data-id="${item.id}">-</button>
                            <span class="cart-item-quantity">${item.quantity}</span>
                            <button class="quantity-btn increase" data-id="${item.id}">+</button>
                            <button class="remove-item" data-id="${item.id}"><i class="fas fa-trash"></i></button>
                        </div>
                    </div>
                </div>`;
            }).join('');
            document.getElementById('cartTotalPrice').textContent = formatPrice(total);
            document.querySelectorAll('.increase').forEach(btn => btn.addEventListener('click', () => updateCartItemQuantity(parseInt(btn.dataset.id), 1)));
            document.querySelectorAll('.decrease').forEach(btn => btn.addEventListener('click', () => updateCartItemQuantity(parseInt(btn.dataset.id), -1)));
            document.querySelectorAll('.remove-item').forEach(btn => btn.addEventListener('click', () => removeFromCart(parseInt(btn.dataset.id))));
        }

        function checkout() {
            if (cart.length === 0) { showNotification(getTranslation('cart.empty'), 'error'); return; }
            showNotification(getTranslation('notification.success') + ' ' + getTranslation('cart.thank_you') || 'Спасибо за заказ!', 'success');
            cart = [];
            saveCartToStorage();
            updateCartCount();
            renderCartItems();
            setTimeout(() => closeCart(), 1500);
        }

        function openCart() { document.getElementById('cartModal').classList.add('active'); document.getElementById('modalOverlay').classList.add('active'); document.body.style.overflow = 'hidden'; renderCartItems(); }
        function closeCart() { document.getElementById('cartModal').classList.remove('active'); document.getElementById('modalOverlay').classList.remove('active'); document.body.style.overflow = 'auto'; }

        function renderProducts(filter = 'all') {
            const grid = document.getElementById('productsGrid');
            if (!grid) return;
            currentFilter = filter;
            const filtered = filter === 'all' ? products : products.filter(p => p.category === filter);
            if (filtered.length === 0) {
                grid.innerHTML = `<div style="text-align:center;padding:40px;grid-column:1/-1;"><i class="fas fa-box-open" style="font-size:60px;"></i><h3>Товары не найдены</h3></div>`;
                return;
            }
            grid.innerHTML = filtered.map(p => `
                <div class="product-card ${p.vip ? 'vip-product' : ''}" data-id="${p.id}">
                    ${p.badge ? `<div class="${p.badge === 'VIP' ? 'vip-badge' : 'product-badge'}">${p.badge}</div>` : ''}
                    <div class="product-img"><img src="${p.image}" alt="${p.name[currentLang] || p.name.ru}" loading="lazy"></div>
                    <div class="product-content">
                        <h3>${p.name[currentLang] || p.name.ru}</h3>
                        <div class="product-description">${p.description[currentLang] || p.description.ru}</div>
                        <div class="product-price">
                            <div>${p.oldPrice ? `<span class="old-price">${formatPrice(p.oldPrice)}</span>` : ''}<span class="price">${formatPrice(p.price)}</span></div>
                            <div class="product-actions">
                                <button class="view-details" data-id="${p.id}" title="${getTranslation('product.view')}"><i class="fas fa-eye"></i></button>
                                <button class="add-to-cart" data-id="${p.id}" title="${getTranslation('product.add_to_cart')}"><i class="fas fa-shopping-cart"></i></button>
                            </div>
                        </div>
                    </div>
                </div>
            `).join('');
            document.querySelectorAll('.add-to-cart').forEach(btn => btn.addEventListener('click', (e) => { e.stopPropagation(); addToCart(parseInt(btn.dataset.id), btn); }));
            document.querySelectorAll('.view-details').forEach(btn => btn.addEventListener('click', (e) => { e.stopPropagation(); const p = products.find(x => x.id === parseInt(btn.dataset.id)); if(p) showProductModal(p); }));
        }

        function showProductModal(product) {
            const modal = document.createElement('div');
            modal.className = 'cart-modal';
            modal.style.maxWidth = '500px';
            modal.innerHTML = `
                <div class="cart-header"><h3>${getTranslation('product.view')}</h3><button class="close-cart"><i class="fas fa-times"></i></button></div>
                <div style="padding:20px 30px;text-align:center;">
                    <img src="${product.image}" style="width:100%;max-width:300px;border-radius:10px;margin-bottom:20px;">
                    <h3>${product.name[currentLang] || product.name.ru}</h3>
                    <p style="margin:15px 0;color:var(--light-brown);">${product.description[currentLang] || product.description.ru}</p>
                    <div style="font-size:36px;font-weight:800;color:var(--accent-color);margin:20px 0;">${formatPrice(product.price)}</div>
                    <button class="btn" onclick="addToCart(${product.id}); closeCart();" style="background:var(--accent-color);">${getTranslation('product.add_to_cart')}</button>
                </div>
            `;
            document.body.appendChild(modal);
            document.getElementById('modalOverlay').classList.add('active');
            modal.classList.add('active');
            const close = () => { modal.classList.remove('active'); setTimeout(() => { modal.remove(); document.getElementById('modalOverlay').classList.remove('active'); }, 400); };
            modal.querySelector('.close-cart').addEventListener('click', close);
            document.getElementById('modalOverlay').addEventListener('click', close);
        }

        function toggleTheme() {
            isDarkTheme = !isDarkTheme;
            localStorage.setItem('luxestyle_dark_theme', isDarkTheme);
            if (isDarkTheme) { document.body.classList.add('dark-theme'); document.getElementById('themeToggle').classList.add('active'); createStars(); }
            else { document.body.classList.remove('dark-theme'); document.getElementById('themeToggle').classList.remove('active'); }
        }

        function createStars() {
            const starryBg = document.getElementById('starryBg');
            starryBg.innerHTML = '';
            if (!isDarkTheme) return;
            for (let i = 0; i < 120; i++) {
                const star = document.createElement('div');
                star.className = 'star';
                star.style.cssText = `width:${Math.random()*3+1}px;height:${Math.random()*3+1}px;left:${Math.random()*100}vw;top:${Math.random()*100}vh;animation-duration:${Math.random()*5+3}s;animation-delay:${Math.random()*5}s;opacity:${Math.random()*0.5+0.2}`;
                starryBg.appendChild(star);
            }
        }

        function initTheme() {
            if (isDarkTheme) { document.body.classList.add('dark-theme'); document.getElementById('themeToggle').classList.add('active'); createStars(); }
            else { document.body.classList.remove('dark-theme'); document.getElementById('themeToggle').classList.remove('active'); }
        }

        function searchProducts(query) {
            if (!query.trim()) { document.getElementById('searchResults').innerHTML = ''; document.getElementById('searchResults').classList.remove('active'); return; }
            const term = query.toLowerCase();
            const results = products.filter(p => (p.name[currentLang] || p.name.ru).toLowerCase().includes(term) || (p.description[currentLang] || p.description.ru).toLowerCase().includes(term));
            const resultsDiv = document.getElementById('searchResults');
            if (results.length) {
                resultsDiv.innerHTML = results.slice(0,5).map(p => `
                    <div class="search-result-item" data-id="${p.id}">
                        <div class="search-result-img"><img src="${p.image}"></div>
                        <div class="search-result-info"><div class="search-result-name">${p.name[currentLang] || p.name.ru}</div><div class="search-result-price">${formatPrice(p.price)}</div></div>
                    </div>
                `).join('');
                resultsDiv.classList.add('active');
                document.querySelectorAll('.search-result-item').forEach(item => item.addEventListener('click', () => {
                    const pid = parseInt(item.dataset.id);
                    const prod = products.find(p => p.id === pid);
                    if(prod) { closeSearch(); document.getElementById('products').scrollIntoView({behavior:'smooth',block:'start'}); document.querySelectorAll('.filter-btn').forEach(btn => { btn.classList.remove('active'); if(btn.dataset.filter === prod.category) btn.classList.add('active'); }); renderProducts(prod.category); }
                }));
            } else { resultsDiv.innerHTML = `<div class="search-no-results"><p>По запросу "${query}" ничего не найдено</p></div>`; resultsDiv.classList.add('active'); }
        }

        function toggleSearch() { const exp = document.getElementById('searchExpanded'); exp.classList.toggle('active'); document.getElementById('searchOverlay').style.display = exp.classList.contains('active') ? 'block' : 'none'; if(exp.classList.contains('active')) document.getElementById('searchInput').focus(); }
        function closeSearch() { document.getElementById('searchExpanded').classList.remove('active'); document.getElementById('searchOverlay').style.display = 'none'; document.getElementById('searchResults').innerHTML = ''; document.getElementById('searchResults').classList.remove('active'); }

        // ============== ИНИЦИАЛИЗАЦИЯ ==============
        document.addEventListener('DOMContentLoaded', () => {
            products = productsData;
            const savedLang = localStorage.getItem('luxestyle_lang');
            if (savedLang && translations[savedLang]) currentLang = savedLang;
            initTheme();
            updateLanguageUI(currentLang);
            updateAllTexts();
            renderProducts();
            updateCartCount();
            
            document.getElementById('themeToggle').addEventListener('click', toggleTheme);
            document.getElementById('searchToggle').addEventListener('click', toggleSearch);
            document.getElementById('searchOverlay').addEventListener('click', closeSearch);
            document.getElementById('searchSubmit').addEventListener('click', () => searchProducts(document.getElementById('searchInput').value));
            document.getElementById('searchInput').addEventListener('input', (e) => { clearTimeout(searchTimeout); searchTimeout = setTimeout(() => searchProducts(e.target.value), 300); });
            document.querySelectorAll('.filter-btn').forEach(btn => btn.addEventListener('click', function() { document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active')); this.classList.add('active'); renderProducts(this.dataset.filter); }));
            document.getElementById('cartIcon').addEventListener('click', openCart);
            document.getElementById('closeCartBtn').addEventListener('click', closeCart);
            document.getElementById('modalOverlay').addEventListener('click', closeCart);
            document.getElementById('checkoutBtn').addEventListener('click', checkout);
            document.getElementById('mobileMenuBtn').addEventListener('click', () => { document.getElementById('nav').classList.add('active'); document.body.style.overflow = 'hidden'; });
            document.querySelectorAll('.nav-link').forEach(link => link.addEventListener('click', () => { document.getElementById('nav').classList.remove('active'); document.body.style.overflow = 'auto'; }));
            document.querySelectorAll('.category-card').forEach(card => card.addEventListener('click', function() { const cat = this.dataset.category; document.querySelectorAll('.filter-btn').forEach(btn => { btn.classList.remove('active'); if(btn.dataset.filter === cat) btn.classList.add('active'); }); document.getElementById('products').scrollIntoView({behavior:'smooth'}); renderProducts(cat); }));
            document.getElementById('newsletterForm').addEventListener('submit', (e) => { e.preventDefault(); const input = document.getElementById('newsletterInput'); if(!input.value.trim() || !/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(input.value)) { showNotification(getTranslation('notification.invalid_email'), 'error'); return; } showNotification(getTranslation('notification.subscribed'), 'success'); input.value = ''; });
            document.querySelectorAll('.language-option').forEach(opt => opt.addEventListener('click', () => setLanguage(opt.dataset.lang)));
            document.getElementById('languageSelector').addEventListener('click', (e) => { e.stopPropagation(); document.getElementById('languageSelector').classList.toggle('active'); });
            document.addEventListener('click', (e) => { if(!e.target.closest('.language-selector')) document.getElementById('languageSelector')?.classList.remove('active'); if(!e.target.closest('#nav') && !e.target.closest('#mobileMenuBtn') && document.getElementById('nav').classList.contains('active')) { document.getElementById('nav').classList.remove('active'); document.body.style.overflow = 'auto'; } });
            window.addEventListener('scroll', () => { document.getElementById('header').classList.toggle('scrolled', window.scrollY > 100); });
            document.querySelectorAll('a[href^="#"]').forEach(anchor => anchor.addEventListener('click', function(e) { const target = document.querySelector(this.getAttribute('href')); if(target) { e.preventDefault(); document.getElementById('nav').classList.remove('active'); document.body.style.overflow = 'auto'; window.scrollTo({top: target.offsetTop - 80, behavior: 'smooth'}); } }));
            document.addEventListener('keydown', (e) => { if(e.key === 'Escape') { closeCart(); document.getElementById('nav').classList.remove('active'); document.body.style.overflow = 'auto'; closeSearch(); } });
        });
        
        window.addToCart = addToCart;
        window.closeCart = closeCart;
    </script>
</body>
</html>
