<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LuxeStyle — премиальная мода</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400..700&family=Pacifico&family=Caveat:wght@400..700&display=swap" rel="stylesheet">
    <style>
        /* ===== ЧИСТЫЙ, ПРОФЕССИОНАЛЬНЫЙ ДИЗАЙН ===== */
        :root {
            --primary: #D4A76A;
            --secondary: #8B4513;
            --accent: #FF6B35;
            --cream: #FFF8E7;
            --brown-dark: #5C4033;
            --brown-light: #A67B5B;
            --beige: #F5E6D3;
            --cream-dark: #E8D8B6;
            --white: #FFFFFF;
            --black: #2C1810;
            --success: #4CAF50;
            --error: #f44336;
            --gray: #999;
            --dark-bg: #1a1a1a;
            --dark-card: #2d2d2d;
            --dark-text: #e0e0e0;
            --dark-border: #444;
            --shadow-sm: 0 2px 8px rgba(0,0,0,0.05);
            --shadow-md: 0 4px 12px rgba(0,0,0,0.1);
            --transition: all 0.25s ease;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: 'Caveat', cursive;
            font-size: 22px;
            background-color: var(--cream);
            color: var(--brown-dark);
            line-height: 1.4;
            transition: background-color 0.3s, color 0.3s;
            opacity: 0;
            animation: reveal 0.5s forwards;
        }
        @keyframes reveal { to { opacity: 1; } }

        h1, h2, h3, h4 {
            font-family: 'Dancing Script', cursive;
            font-weight: 600;
            color: var(--secondary);
        }

        a { text-decoration: none; color: inherit; transition: var(--transition); }
        button { font-family: 'Caveat', cursive; font-size: 22px; cursor: pointer; border: none; background: none; }

        .container {
            width: 100%;
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* ===== ЗАГРУЗОЧНЫЙ ЭКРАН (без кнопки) ===== */
        #loader {
            position: fixed;
            inset: 0;
            background: linear-gradient(135deg, #2C1810, #5C4033, #8B4513);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            transition: opacity 0.8s, visibility 0.8s;
        }
        #loader.hidden { opacity: 0; visibility: hidden; pointer-events: none; }
        .loader-content { text-align: center; max-width: 800px; padding: 40px; position: relative; }
        .logo-container { position: relative; margin-bottom: 40px; }
        .logo-glow {
            position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);
            width: 300px; height: 300px;
            background: radial-gradient(circle, rgba(212,167,106,0.3) 0%, rgba(212,167,106,0.1) 50%, transparent 70%);
            border-radius: 50%;
            animation: pulseGlow 3s infinite;
        }
        .main-title {
            font-family: 'Pacifico', cursive; font-size: 90px;
            background: linear-gradient(45deg, #D4A76A, #FFD700, #D4A76A);
            -webkit-background-clip: text; background-clip: text;
            -webkit-text-fill-color: transparent;
            background-size: 200% auto;
            animation: titleReveal 1.5s ease forwards 0.5s, goldShine 3s infinite 2s;
            transform: translateY(30px); opacity: 0;
        }
        @keyframes titleReveal { to { opacity: 1; transform: translateY(0); } }
        @keyframes goldShine { 0% { background-position: 0% 50%; } 50% { background-position: 100% 50%; } 100% { background-position: 0% 50%; } }
        @keyframes pulseGlow { 0%,100% { transform: translate(-50%,-50%) scale(1); opacity: 0.5; } 50% { transform: translate(-50%,-50%) scale(1.2); opacity: 0.8; } }

        .subtitle {
            font-family: 'Dancing Script', cursive; font-size: 48px;
            color: var(--cream); margin-bottom: 60px;
            opacity: 0; transform: translateY(30px);
            animation: subtitleReveal 1.5s ease forwards 1.2s;
        }
        @keyframes subtitleReveal { to { opacity: 1; transform: translateY(0); } }

        .loader-stats {
            display: flex; justify-content: center; gap: 50px; margin-top: 50px;
            opacity: 0; animation: statsReveal 1s ease forwards 2s;
        }
        @keyframes statsReveal { to { opacity: 1; } }
        .stat-number {
            font-family: 'Caveat', cursive; font-size: 42px; font-weight: 700;
            color: var(--primary); display: block; margin-bottom: 5px;
        }
        .stat-label { font-size: 24px; color: var(--beige); opacity: 0.9; }

        .progress-container {
            width: 300px; height: 6px; background: rgba(255,255,255,0.1);
            border-radius: 3px; margin: 40px auto 0; overflow: hidden;
            opacity: 0; animation: progressReveal 0.8s ease forwards 1.5s;
        }
        @keyframes progressReveal { to { opacity: 1; } }
        .progress-bar {
            height: 100%; width: 0%;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            position: relative; overflow: hidden;
        }
        .progress-bar::after {
            content: ''; position: absolute; top: 0; left: 0; right: 0; bottom: 0;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.4), transparent);
            animation: shimmer 2s infinite;
        }
        @keyframes shimmer { 0% { transform: translateX(-100%); } 100% { transform: translateX(100%); } }

        .loader-icons { position: absolute; inset: 0; pointer-events: none; }
        .floating-icon {
            position: absolute; font-size: 24px; color: rgba(212,167,106,0.6);
            opacity: 0; animation: floatAround 20s linear infinite;
        }
        @keyframes floatAround {
            0% { transform: translate(0,0) rotate(0deg); opacity: 0; }
            10% { opacity: 0.7; }
            90% { opacity: 0.7; }
            100% { transform: translate(var(--tx,100px), var(--ty,-100px)) rotate(360deg); opacity: 0; }
        }

        /* ===== ТЁМНАЯ ТЕМА ===== */
        body.dark-theme {
            --cream: var(--dark-bg);
            --beige: var(--dark-card);
            --cream-dark: var(--dark-border);
            --brown-dark: var(--dark-text);
            --brown-light: #a0a0a0;
            --white: #2d2d2d;
            --black: #e0e0e0;
            background-color: var(--dark-bg);
        }
        .starry-bg {
            position: fixed; inset: 0; pointer-events: none; z-index: -1; opacity: 0;
            transition: opacity 0.5s;
        }
        body.dark-theme .starry-bg { opacity: 1; }
        .star {
            position: absolute; background: white; border-radius: 50%;
            animation: twinkle var(--duration) infinite;
        }
        @keyframes twinkle { 0%,100%{ opacity:0.3; transform:scale(1); } 50%{ opacity:1; transform:scale(1.2); } }

        /* ===== ХЕДЕР ===== */
        header {
            background: var(--cream); position: fixed; width: 100%; z-index: 1000;
            padding: 15px 0; box-shadow: var(--shadow-sm); border-bottom: 1px solid var(--cream-dark);
            transition: var(--transition);
        }
        header.scrolled {
            padding: 10px 0; background: rgba(255,248,231,0.95);
            box-shadow: var(--shadow-md);
        }
        body.dark-theme header { background: var(--dark-card); border-bottom-color: var(--dark-border); }
        body.dark-theme header.scrolled { background: rgba(45,45,45,0.95); }
        .header-content { display: flex; justify-content: space-between; align-items: center; }

        .logo {
            font-family: 'Pacifico', cursive; font-size: 32px; color: var(--primary);
            display: flex; align-items: center; gap: 10px;
        }

        nav ul { display: flex; list-style: none; gap: 30px; }
        nav a {
            font-weight: 600; font-size: 24px; padding: 5px 0;
            position: relative; color: var(--secondary);
        }
        nav a::after {
            content: ''; position: absolute; bottom: 0; left: 0;
            width: 0; height: 2px; background: var(--primary);
            transition: width 0.3s;
        }
        nav a:hover::after { width: 100%; }
        nav a:hover { color: var(--primary); }

        .header-actions { display: flex; gap: 15px; align-items: center; }

        /* компактный поиск */
        .compact-search { position: relative; }
        .search-toggle {
            width: 45px; height: 45px; background: var(--beige);
            border: 1px solid var(--cream-dark); border-radius: 50%;
            display: flex; align-items: center; justify-content: center;
            cursor: pointer; color: var(--secondary); transition: var(--transition);
        }
        .search-toggle:hover { background: var(--primary); border-color: var(--primary); color: var(--brown-dark); transform: scale(1.05); }
        .search-expanded {
            position: absolute; top: 100%; right: 0; margin-top: 10px;
            background: var(--cream); border: 1px solid var(--cream-dark);
            border-radius: 8px; padding: 15px; width: 300px;
            box-shadow: var(--shadow-md); display: none; z-index: 1001;
        }
        .search-expanded.active { display: block; animation: fadeInDown 0.3s; }
        @keyframes fadeInDown { from { opacity:0; transform:translateY(-10px); } to { opacity:1; transform:translateY(0); } }
        .search-input-wrapper { position: relative; margin-bottom: 10px; }
        .search-input {
            width: 100%; padding: 10px 40px 10px 15px;
            background: var(--beige); border: 1px solid var(--cream-dark);
            border-radius: 25px; font-family: 'Caveat', cursive; font-size: 18px;
            color: var(--brown-dark); outline: none;
        }
        .search-input:focus { border-color: var(--primary); background: var(--cream); }
        .search-submit {
            position: absolute; right: 5px; top: 50%; transform: translateY(-50%);
            width: 30px; height: 30px; background: var(--primary);
            border: none; border-radius: 50%; color: var(--brown-dark);
            cursor: pointer; transition: var(--transition);
        }
        .search-submit:hover { background: var(--accent); color: var(--cream); transform: translateY(-50%) scale(1.1); }
        .search-results {
            max-height: 300px; overflow-y: auto; border-top: 1px solid var(--cream-dark);
            padding-top: 10px; display: none;
        }
        .search-results.active { display: block; }
        .search-result-item {
            display: flex; padding: 8px; align-items: center;
            border-bottom: 1px solid var(--cream-dark); cursor: pointer;
            border-radius: 4px; transition: var(--transition);
        }
        .search-result-item:hover { background: var(--beige); transform: translateX(5px); }
        .search-result-img { width: 50px; height: 50px; border-radius: 4px; overflow: hidden; margin-right: 10px; flex-shrink: 0; border: 1px solid var(--cream-dark); }
        .search-result-img img { width: 100%; height: 100%; object-fit: cover; }
        .search-result-info { flex: 1; }
        .search-result-name { font-weight: 600; font-size: 16px; margin-bottom: 3px; color: var(--secondary); white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
        .search-result-price { color: var(--primary); font-weight: 600; font-size: 14px; }
        .search-no-results { padding: 10px; text-align: center; color: var(--brown-light); font-size: 16px; }
        .search-overlay { position: fixed; inset: 0; background: transparent; z-index: 1000; display: none; }

        /* переключатель темы */
        .theme-toggle {
            width: 50px; height: 26px; background: var(--beige);
            border-radius: 13px; position: relative; cursor: pointer;
            border: 1px solid var(--cream-dark); transition: var(--transition);
        }
        .theme-toggle.active { background: var(--primary); border-color: var(--primary); }
        .theme-toggle-handle {
            position: absolute; left: 3px; top: 3px; width: 18px; height: 18px;
            background: var(--white); border-radius: 50%; transition: transform 0.3s;
        }
        .theme-toggle.active .theme-toggle-handle { transform: translateX(24px); }
        .theme-toggle i { position: absolute; top: 50%; transform: translateY(-50%); font-size: 12px; color: var(--brown-dark); }
        .theme-toggle .fa-sun { left: 6px; }
        .theme-toggle .fa-moon { right: 6px; }

        /* язык */
        .language-selector {
            position: relative; display: flex; align-items: center; gap: 5px;
            cursor: pointer; font-weight: 600; color: var(--secondary);
            padding: 5px; border-radius: 4px; font-size: 20px;
        }
        .language-flag { width: 30px; height: 20px; border-radius: 2px; overflow: hidden; border: 1px solid var(--cream-dark); display: flex; align-items: center; justify-content: center; }
        .language-flag img { width: 100%; height: 100%; object-fit: cover; }
        .language-dropdown {
            position: absolute; top: 100%; right: 0; margin-top: 5px;
            background: var(--beige); border-radius: 4px; min-width: 120px;
            box-shadow: var(--shadow-md); opacity: 0; visibility: hidden;
            transform: translateY(-10px); transition: var(--transition);
            border: 1px solid var(--cream-dark); z-index: 10;
        }
        .language-selector.active .language-dropdown { opacity: 1; visibility: visible; transform: translateY(0); }
        .language-option { display: flex; align-items: center; gap: 10px; padding: 10px; transition: var(--transition); cursor: pointer; }
        .language-option:hover { background: rgba(212,167,106,0.2); }

        .cart-icon { position: relative; font-size: 24px; cursor: pointer; color: var(--secondary); transition: var(--transition); }
        .cart-icon:hover { color: var(--primary); }
        .cart-count {
            position: absolute; top: -8px; right: -8px;
            background: var(--accent); color: var(--cream);
            font-size: 14px; width: 20px; height: 20px;
            border-radius: 50%; display: flex; align-items: center; justify-content: center;
            font-weight: 700;
        }
        .mobile-menu-btn { display: none; font-size: 28px; cursor: pointer; color: var(--primary); background: none; border: none; padding: 5px; }

        /* HERO */
        .hero {
            height: 100vh; display: flex; align-items: center;
            background: linear-gradient(rgba(255,248,231,0.9), rgba(255,248,231,0.8)), url('https://images.unsplash.com/photo-1490481651871-ab68de25d43d?w=2070');
            background-size: cover; background-position: center;
        }
        body.dark-theme .hero {
            background: linear-gradient(rgba(26,26,26,0.9), rgba(26,26,26,0.8)), url('https://images.unsplash.com/photo-1490481651871-ab68de25d43d?w=2070');
        }
        .hero-content {
            max-width: 750px; background: rgba(255,255,255,0.9); padding: 50px;
            border-radius: 12px; box-shadow: var(--shadow-md); border: 1px solid var(--cream-dark);
            animation: fadeInUp 1s;
        }
        body.dark-theme .hero-content { background: rgba(45,45,45,0.9); border-color: var(--dark-border); }
        .hero h1 { font-size: 56px; margin-bottom: 20px; }
        .hero p { font-size: 26px; margin-bottom: 30px; color: var(--brown-dark); }

        .btn {
            display: inline-block; background: var(--primary); color: var(--brown-dark);
            padding: 12px 30px; font-weight: 600; border-radius: 30px;
            border: 1px solid var(--primary); transition: var(--transition);
            cursor: pointer; font-size: 22px;
        }
        .btn:hover { background: transparent; color: var(--primary); transform: translateY(-2px); box-shadow: var(--shadow-sm); }
        .btn-outline { background: transparent; color: var(--primary); margin-left: 15px; }
        .btn-outline:hover { background: var(--primary); color: var(--brown-dark); }

        /* ЗАГОЛОВКИ */
        .section-title { text-align: center; margin-bottom: 50px; }
        .section-title h2 {
            font-size: 46px; display: inline-block; position: relative;
            background: linear-gradient(45deg, var(--secondary), var(--primary));
            -webkit-background-clip: text; background-clip: text; -webkit-text-fill-color: transparent;
        }
        .section-title h2::after {
            content: ''; position: absolute; width: 80px; height: 2px;
            background: var(--primary); bottom: -15px; left: 50%; transform: translateX(-50%);
        }

        section { padding: 80px 0; }

        /* КАТЕГОРИИ */
        .categories { background: var(--beige); }
        .categories-grid {
            display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 30px;
        }
        .category-card {
            background: var(--cream); border-radius: 8px; overflow: hidden;
            border: 1px solid var(--cream-dark); box-shadow: var(--shadow-sm);
            transition: var(--transition); cursor: pointer; height: 350px;
        }
        .category-card:hover { transform: translateY(-8px); box-shadow: var(--shadow-md); border-color: var(--primary); }
        .category-img { height: 70%; overflow: hidden; }
        .category-img img { width: 100%; height: 100%; object-fit: cover; transition: transform 0.6s; }
        .category-card:hover .category-img img { transform: scale(1.1); }
        .category-content { padding: 20px; height: 30%; display: flex; flex-direction: column; justify-content: center; background: var(--cream); }
        .category-content h3 { font-size: 26px; margin-bottom: 5px; }
        .category-content p { color: var(--brown-light); font-size: 18px; }

        /* ТОВАРЫ */
        .products { background: var(--cream); }
        .products-filter {
            display: flex; justify-content: center; flex-wrap: wrap;
            gap: 5px; margin-bottom: 40px; border-bottom: 1px solid var(--cream-dark);
            padding-bottom: 0;
        }
        .filter-btn {
            background: transparent; color: var(--brown-dark); border: none;
            padding: 8px 20px; cursor: pointer; font-weight: 600; font-size: 22px;
            border-bottom: 2px solid transparent; margin-bottom: -1px; transition: var(--transition);
        }
        .filter-btn.active, .filter-btn:hover { background: transparent; color: var(--primary); border-bottom-color: var(--primary); }
        @media (max-width:576px) {
            .products-filter { flex-wrap: nowrap; overflow-x: auto; justify-content: flex-start; padding-bottom: 5px; }
            .filter-btn { white-space: nowrap; }
        }

        .products-grid {
            display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 30px;
        }
        .product-card {
            background: var(--beige); border-radius: 8px; overflow: hidden;
            border: 1px solid var(--cream-dark); box-shadow: var(--shadow-sm);
            transition: var(--transition); position: relative;
        }
        .product-card:hover { transform: translateY(-5px); box-shadow: var(--shadow-md); border-color: var(--primary); }
        .product-badge {
            position: absolute; top: 12px; left: 12px;
            background: var(--accent); color: var(--cream); padding: 4px 10px;
            border-radius: 20px; font-weight: 600; font-size: 16px; z-index: 2;
        }
        .vip-badge {
            position: absolute; top: 12px; right: 12px;
            background: var(--primary); color: var(--brown-dark); padding: 4px 10px;
            border-radius: 20px; font-weight: 600; font-size: 16px; z-index: 2;
            box-shadow: 0 0 8px var(--primary);
        }
        .product-img { height: 250px; overflow: hidden; }
        .product-img img { width: 100%; height: 100%; object-fit: cover; transition: transform 0.5s; }
        .product-card:hover .product-img img { transform: scale(1.05); }
        .product-content { padding: 20px; background: var(--cream); }
        .product-content h3 { font-size: 24px; margin-bottom: 8px; }
        .product-description { font-size: 18px; color: var(--brown-light); margin-bottom: 12px; }
        .product-price {
            display: flex; align-items: center; justify-content: space-between;
            margin-top: 10px;
        }
        .price { font-size: 26px; font-weight: 700; color: var(--primary); }
        .old-price { text-decoration: line-through; color: var(--gray); font-size: 20px; margin-right: 5px; }
        .product-actions { display: flex; gap: 8px; }
        .add-to-cart, .view-details {
            width: 40px; height: 40px; border-radius: 50%;
            background: var(--primary); color: var(--brown-dark);
            display: flex; align-items: center; justify-content: center;
            cursor: pointer; transition: var(--transition); border: 1px solid var(--primary);
        }
        .add-to-cart:hover { background: var(--accent); border-color: var(--accent); color: var(--cream); transform: scale(1.1); }
        .view-details { background: transparent; color: var(--primary); }
        .view-details:hover { background: var(--primary); color: var(--brown-dark); transform: scale(1.1); }

        /* КОРЗИНА */
        .modal-overlay {
            position: fixed; inset: 0; background: rgba(44,24,16,0.7);
            z-index: 1500; opacity: 0; visibility: hidden; transition: var(--transition);
            backdrop-filter: blur(3px);
        }
        .modal-overlay.active { opacity: 1; visibility: visible; }
        .cart-modal {
            position: fixed; top: 0; right: -100%; width: 100%; max-width: 450px;
            height: 100%; background: var(--beige); z-index: 2000;
            transition: right 0.4s cubic-bezier(0.25,0.46,0.45,0.94);
            box-shadow: -5px 0 20px rgba(0,0,0,0.2); display: flex; flex-direction: column;
            border-left: 1px solid var(--cream-dark);
        }
        .cart-modal.active { right: 0; }
        .cart-header {
            display: flex; justify-content: space-between; align-items: center;
            padding: 20px 30px; border-bottom: 1px solid var(--cream-dark); background: var(--cream);
        }
        .cart-header h3 { font-size: 28px; }
        .close-cart { font-size: 26px; cursor: pointer; color: var(--primary); transition: var(--transition); background: none; border: none; }
        .close-cart:hover { transform: rotate(90deg); color: var(--accent); }
        .cart-items { flex: 1; overflow-y: auto; padding: 20px 30px; }
        .cart-item {
            display: flex; padding: 15px 0; border-bottom: 1px solid var(--cream-dark);
            align-items: center; transition: var(--transition);
        }
        .cart-item.removing { animation: removeItem 0.3s forwards; }
        @keyframes removeItem { 0% { opacity:1; transform:translateX(0); } 100% { opacity:0; transform:translateX(100px); } }
        .cart-item-img { width: 80px; height: 80px; border-radius: 4px; overflow: hidden; margin-right: 15px; flex-shrink: 0; border: 1px solid var(--cream-dark); }
        .cart-item-img img { width: 100%; height: 100%; object-fit: cover; }
        .cart-item-details { flex: 1; }
        .cart-item-title { font-weight: 600; margin-bottom: 5px; font-size: 20px; }
        .cart-item-price { color: var(--primary); font-weight: 700; font-size: 22px; }
        .cart-item-controls { display: flex; align-items: center; margin-top: 10px; }
        .quantity-btn {
            width: 30px; height: 30px; background: var(--cream);
            border: 1px solid var(--cream-dark); border-radius: 4px;
            cursor: pointer; display: flex; align-items: center; justify-content: center;
            font-weight: 700; transition: var(--transition);
        }
        .quantity-btn:hover { background: var(--primary); border-color: var(--primary); }
        .cart-item-quantity { margin: 0 10px; font-weight: 600; min-width: 20px; text-align: center; }
        .remove-item {
            margin-left: 15px; color: var(--error); cursor: pointer;
            transition: var(--transition); background: none; border: none;
            font-size: 20px; width: 35px; height: 35px; border-radius: 50%;
            display: flex; align-items: center; justify-content: center;
        }
        .remove-item:hover { background: rgba(244,67,54,0.1); transform: scale(1.2); }
        .cart-footer {
            padding: 20px 30px; border-top: 1px solid var(--cream-dark);
            background: var(--cream);
        }
        .cart-total { display: flex; justify-content: space-between; margin-bottom: 20px; font-size: 22px; font-weight: 600; }
        .total-amount { color: var(--primary); font-size: 26px; }
        .checkout-btn {
            width: 100%; padding: 12px; background: var(--primary); color: var(--brown-dark);
            border: 1px solid var(--primary); border-radius: 6px; font-weight: 700;
            font-size: 22px; cursor: pointer; transition: var(--transition);
        }
        .checkout-btn:hover { background: var(--accent); border-color: var(--accent); color: var(--cream); transform: translateY(-2px); }
        .cart-empty { text-align: center; padding: 60px 20px; }
        .cart-empty i { font-size: 70px; color: var(--cream-dark); margin-bottom: 20px; opacity: 0.5; }
        .cart-empty h4 { color: var(--secondary); margin-bottom: 10px; font-size: 26px; }
        .cart-empty p { color: var(--brown-light); font-size: 20px; }

        /* О НАС */
        .about { background: var(--beige); }
        .about-content { display: flex; align-items: center; gap: 50px; }
        .about-text { flex: 1; }
        .about-text h2 { font-size: 46px; margin-bottom: 20px; }
        .about-text p { margin-bottom: 15px; font-size: 22px; }
        .about-stats { display: flex; justify-content: space-between; margin-top: 30px; }
        .about-stats .stat-number { font-size: 40px; color: var(--primary); }
        .about-image {
            flex: 1; border-radius: 8px; overflow: hidden;
            box-shadow: 0 10px 0 var(--cream-dark); border: 1px solid var(--cream-dark);
        }
        .about-image img { width: 100%; display: block; transition: transform 0.5s; }
        .about-image:hover img { transform: scale(1.05); }

        /* ФУТЕР */
        footer {
            background: var(--brown-dark); color: var(--beige);
            padding: 60px 0 30px;
        }
        .footer-content {
            display: grid; grid-template-columns: repeat(4,1fr); gap: 40px;
            margin-bottom: 40px;
        }
        .footer-column h3 {
            font-size: 26px; margin-bottom: 20px; padding-bottom: 10px;
            border-bottom: 2px solid var(--primary); display: inline-block;
            color: var(--primary);
        }
        .footer-column p { margin-bottom: 15px; opacity: 0.9; font-size: 20px; }
        .social-links { display: flex; gap: 15px; margin-top: 15px; }
        .social-links a {
            width: 40px; height: 40px; border-radius: 50%;
            background: rgba(255,255,255,0.1); display: flex;
            align-items: center; justify-content: center;
            transition: var(--transition); color: var(--beige);
        }
        .social-links a:hover { background: var(--primary); color: var(--brown-dark); transform: translateY(-3px); }
        .footer-links { list-style: none; }
        .footer-links li { margin-bottom: 10px; }
        .footer-links a { color: var(--beige); opacity: 0.9; font-size: 20px; transition: var(--transition); }
        .footer-links a:hover { color: var(--primary); padding-left: 5px; opacity: 1; }
        .newsletter-form { display: flex; margin-top: 15px; }
        .newsletter-input {
            flex: 1; padding: 10px 15px; background: rgba(255,255,255,0.1);
            border: 1px solid rgba(212,167,106,0.3); border-radius: 30px 0 0 30px;
            color: var(--beige); border-right: none; font-size: 18px;
        }
        .newsletter-input:focus { outline: none; border-color: var(--primary); }
        .newsletter-btn {
            background: var(--primary); color: var(--brown-dark);
            border: 1px solid var(--primary); padding: 0 20px;
            border-radius: 0 30px 30px 0; cursor: pointer; font-weight: 600;
            transition: var(--transition); font-size: 20px;
        }
        .newsletter-btn:hover { background: var(--accent); border-color: var(--accent); color: var(--cream); }
        .copyright { text-align: center; padding-top: 30px; border-top: 1px solid rgba(212,167,106,0.2); font-size: 18px; opacity: 0.8; }

        /* УВЕДОМЛЕНИЯ */
        .notification {
            position: fixed; top: 100px; right: 20px;
            padding: 12px 24px; border-radius: 6px; font-weight: 600;
            box-shadow: var(--shadow-md); z-index: 9999; max-width: 300px;
            font-size: 20px; background: var(--primary); color: var(--brown-dark);
            opacity: 0; transform: translateX(100px); transition: all 0.3s;
        }
        .notification.show { opacity: 1; transform: translateX(0); }
        .notification.success { background: var(--success); color: white; }
        .notification.error { background: var(--error); color: white; }

        /* АНИМАЦИИ */
        .floating-item {
            position: fixed; width: 40px; height: 40px;
            background: linear-gradient(45deg, var(--primary), var(--accent));
            border-radius: 50%; display: flex; align-items: center; justify-content: center;
            z-index: 9999; pointer-events: none; box-shadow: 0 2px 10px rgba(212,167,106,0.5);
            transition: transform 0.6s cubic-bezier(0.175,0.885,0.32,1.275);
        }
        .cart-icon.animate { animation: cartBounce 0.5s; }
        @keyframes cartBounce { 0%,100%{ transform:scale(1); } 50%{ transform:scale(1.3); } }
        .loading-spinner {
            display: inline-block; width: 20px; height: 20px;
            border: 3px solid rgba(212,167,106,0.3); border-radius: 50%;
            border-top-color: var(--primary); animation: spin 1s infinite;
        }
        @keyframes spin { to { transform: rotate(360deg); } }

        /* АДАПТИВНОСТЬ */
        @media (max-width:1200px) {
            .footer-content { grid-template-columns: repeat(2,1fr); }
            .about-content { gap: 40px; }
            .main-title { font-size: 70px; }
        }
        @media (max-width:992px) {
            .hero h1 { font-size: 46px; }
            .about-content { flex-direction: column; text-align: center; }
            .about-image { order: -1; box-shadow: 0 10px 0 var(--cream-dark); }
            .about-stats { justify-content: space-around; }
            .main-title { font-size: 60px; }
            .subtitle { font-size: 32px; }
        }
        @media (max-width:768px) {
            nav {
                position: fixed; top: 0; left: -100%; width: 280px; height: 100vh;
                background: var(--beige); flex-direction: column; padding: 100px 30px 30px;
                transition: left 0.4s; box-shadow: 2px 0 15px rgba(0,0,0,0.1);
                border-right: 1px solid var(--cream-dark); z-index: 999;
            }
            nav.active { left: 0; }
            nav ul { flex-direction: column; gap: 20px; }
            .mobile-menu-btn { display: block; }
            .hero h1 { font-size: 36px; }
            .hero p { font-size: 22px; }
            .hero-content { padding: 30px; margin: 0 15px; }
            .section-title h2 { font-size: 34px; }
            .cart-modal { max-width: 100%; }
            .search-expanded { position: fixed; top: 80px; left: 20px; right: 20px; width: auto; }
            .main-title { font-size: 48px; }
            .subtitle { font-size: 28px; }
            .loader-stats { flex-direction: column; gap: 20px; }
            .logo-glow { width: 200px; height: 200px; }
        }
        @media (max-width:576px) {
            .btn { display: block; width: 100%; margin-bottom: 10px; }
            .btn-outline { margin-left: 0; }
            .categories-grid, .products-grid { grid-template-columns: 1fr; }
            .footer-content { grid-template-columns: 1fr; }
            .about-stats { flex-direction: column; gap: 20px; }
            .notification { top: 80px; right: 10px; left: 10px; max-width: none; }
            .main-title { font-size: 40px; }
            .subtitle { font-size: 24px; }
            .progress-container { width: 250px; }
        }
    </style>
</head>
<body>
    <!-- ЗАГРУЗОЧНЫЙ ЭКРАН (без кнопки) -->
    <div id="loader">
        <div class="loader-content">
            <div class="logo-container"><div class="logo-glow"></div><h1 class="main-title">LuxeStyle</h1></div>
            <h2 class="subtitle">Лучший магазин в мире по брендовым вещам</h2>
            <div class="loader-stats">
                <div class="stat-item"><span class="stat-number" id="statBrands">0+</span><span class="stat-label">Брендов</span></div>
                <div class="stat-item"><span class="stat-number" id="statProducts">0</span><span class="stat-label">Товаров</span></div>
                <div class="stat-item"><span class="stat-number" id="statYears">0</span><span class="stat-label">Лет на рынке</span></div>
            </div>
            <div class="progress-container"><div class="progress-bar" id="progressBar"></div></div>
            <div class="loader-icons" id="loaderIcons"></div>
        </div>
    </div>

    <!-- ЗВЁЗДЫ ДЛЯ ТЁМНОЙ ТЕМЫ -->
    <div class="starry-bg" id="starryBg"></div>
    <div class="confetti-container" id="confettiContainer"></div>

    <!-- ШАПКА -->
    <header id="header">
        <div class="container">
            <div class="header-content">
                <a href="#home" class="logo"><i class="fas fa-crown"></i><span>LuxeStyle</span></a>
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
                        <button class="search-toggle" id="searchToggle"><i class="fas fa-search"></i></button>
                        <div class="search-expanded" id="searchExpanded">
                            <div class="search-input-wrapper">
                                <input type="text" class="search-input" id="searchInput" placeholder="Поиск товаров...">
                                <button class="search-submit" id="searchSubmit"><i class="fas fa-search"></i></button>
                            </div>
                            <div class="search-results" id="searchResults"></div>
                        </div>
                    </div>
                    <div class="theme-toggle" id="themeToggle"><i class="fas fa-sun"></i><i class="fas fa-moon"></i><div class="theme-toggle-handle"></div></div>
                    <div class="language-selector" id="languageSelector">
                        <div class="language-flag" id="currentFlag"><img src="https://flagcdn.com/w40/ru.png" alt="Русский"></div>
                        <span id="currentLanguage">РУ</span>
                        <div class="language-dropdown">
                            <div class="language-option" data-lang="ru"><div class="language-flag"><img src="https://flagcdn.com/w40/ru.png" alt="Русский"></div><span>Русский</span></div>
                            <div class="language-option" data-lang="en"><div class="language-flag"><img src="https://flagcdn.com/w40/gb.png" alt="English"></div><span>English</span></div>
                            <div class="language-option" data-lang="kz"><div class="language-flag"><img src="https://flagcdn.com/w40/kz.png" alt="Қазақша"></div><span>Қазақша</span></div>
                        </div>
                    </div>
                    <div class="cart-icon" id="cartIcon"><i class="fas fa-shopping-bag"></i><span class="cart-count" id="cartCount">0</span></div>
                    <button class="mobile-menu-btn" id="mobileMenuBtn"><i class="fas fa-bars"></i></button>
                </div>
            </div>
        </div>
        <div class="search-overlay" id="searchOverlay"></div>
    </header>

    <!-- МОДАЛКА КОРЗИНЫ -->
    <div class="modal-overlay" id="modalOverlay"></div>
    <div class="cart-modal" id="cartModal">
        <div class="cart-header"><h3 data-translate="cart.title">Корзина</h3><button class="close-cart" id="closeCartBtn"><i class="fas fa-times"></i></button></div>
        <div class="cart-items" id="cartItemsContainer"></div>
        <div class="cart-footer" id="cartFooter">
            <div class="cart-total"><span data-translate="cart.total">Итого:</span><span class="total-amount" id="cartTotalPrice">0 ₽</span></div>
            <button class="checkout-btn" id="checkoutBtn" data-translate="cart.checkout">Оформить заказ</button>
        </div>
    </div>

    <!-- HERO -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content">
                <h1 data-translate="hero.title">Эксклюзивные брендовые вещи для истинных ценителей</h1>
                <p data-translate="hero.subtitle">Откройте для себя мир роскоши и стиля с нашей коллекцией премиальных брендов.</p>
                <div><a href="#products" class="btn pulse-animation" data-translate="hero.collection_btn">Коллекция</a><a href="#about" class="btn btn-outline" data-translate="hero.about_btn">О нас</a></div>
            </div>
        </div>
    </section>

    <!-- КАТЕГОРИИ -->
    <section class="categories" id="categories">
        <div class="container">
            <div class="section-title"><h2 data-translate="categories.title">Категории</h2></div>
            <div class="categories-grid">
                <div class="category-card" data-category="clothing"><div class="category-img"><img src="https://images.unsplash.com/photo-1591047139829-d91aecb6caea?w=800" alt="Одежда"></div><div class="category-content"><h3 data-translate="categories.clothing">Одежда</h3><p data-translate="categories.clothing_desc">Эксклюзивная одежда от мировых брендов</p></div></div>
                <div class="category-card" data-category="shoes"><div class="category-img"><img src="https://images.unsplash.com/photo-1543163521-1bf539c55dd2?w=800" alt="Обувь"></div><div class="category-content"><h3 data-translate="categories.shoes">Обувь</h3><p data-translate="categories.shoes_desc">Коллекция премиальной обуви</p></div></div>
                <div class="category-card" data-category="accessories"><div class="category-img"><img src="https://images.unsplash.com/photo-1599643478518-a784e5dc4c8f?w=800" alt="Аксессуары"></div><div class="category-content"><h3 data-translate="categories.accessories">Аксессуары</h3><p data-translate="categories.accessories_desc">Роскошные аксессуары для завершения образа</p></div></div>
            </div>
        </div>
    </section>

    <!-- ТОВАРЫ + ВКЛАДКИ -->
    <section class="products" id="products">
        <div class="container">
            <div class="section-title"><h2 data-translate="products.title">Популярные товары</h2></div>
            <div class="products-filter">
                <button class="filter-btn active" data-filter="all" data-translate="products.all">Все товары</button>
                <button class="filter-btn" data-filter="clothing" data-translate="categories.clothing">Одежда</button>
                <button class="filter-btn" data-filter="shoes" data-translate="categories.shoes">Обувь</button>
                <button class="filter-btn" data-filter="accessories" data-translate="categories.accessories">Аксессуары</button>
                <button class="filter-btn" data-filter="sale" data-translate="products.sale">🔥 Акции</button>
            </div>
            <div class="products-grid" id="productsGrid"></div>
        </div>
    </section>

    <!-- О НАС -->
    <section class="about" id="about">
        <div class="container">
            <div class="about-content">
                <div class="about-text">
                    <h2 data-translate="about.title">О LuxeStyle</h2>
                    <p data-translate="about.desc1">Мы — эксклюзивный ритейлер люксовых брендов, предлагающий тщательно отобранную коллекцию премиальных товаров для ценителей настоящего качества и стиля.</p>
                    <p data-translate="about.desc2">Наша миссия — предоставить доступ к самым востребованным и редким предметам роскоши.</p>
                    <div class="about-stats">
                        <div class="stat-item"><span class="stat-number">2010</span><span class="stat-label" data-translate="about.year">Год основания</span></div>
                        <div class="stat-item"><span class="stat-number">50+</span><span class="stat-label" data-translate="about.brands">Брендов</span></div>
                        <div class="stat-item"><span class="stat-number">25k+</span><span class="stat-label" data-translate="about.clients">Довольных клиентов</span></div>
                    </div>
                </div>
                <div class="about-image"><img src="https://images.unsplash.com/photo-1445205170230-053b83016050?w=800" alt="О магазине"></div>
            </div>
        </div>
    </section>

    <!-- ФУТЕР -->
    <footer id="contact">
        <div class="container">
            <div class="footer-content">
                <div class="footer-column"><h3 data-translate="footer.about_title">О компании</h3><p data-translate="footer.about_desc">Эксклюзивные брендовые вещи для истинных ценителей.</p><div class="social-links"><a href="#"><i class="fab fa-instagram"></i></a><a href="#"><i class="fab fa-facebook-f"></i></a><a href="#"><i class="fab fa-twitter"></i></a><a href="#"><i class="fab fa-pinterest-p"></i></a></div></div>
                <div class="footer-column"><h3 data-translate="footer.categories_title">Категории</h3><ul class="footer-links"><li><a href="#categories" data-translate="categories.clothing">Одежда</a></li><li><a href="#categories" data-translate="categories.shoes">Обувь</a></li><li><a href="#categories" data-translate="categories.accessories">Аксессуары</a></li><li><a href="#products" data-translate="footer.new_collection">Новая коллекция</a></li><li><a href="#products" data-translate="footer.sale">Распродажа</a></li></ul></div>
                <div class="footer-column"><h3 data-translate="footer.info_title">Информация</h3><ul class="footer-links"><li><a href="#about" data-translate="nav.about">О нас</a></li><li><a href="#" data-translate="footer.delivery">Доставка</a></li><li><a href="#" data-translate="footer.returns">Возврат</a></li><li><a href="#" data-translate="footer.privacy">Конфиденциальность</a></li><li><a href="#contact" data-translate="nav.contact">Контакты</a></li></ul></div>
                <div class="footer-column"><h3 data-translate="footer.newsletter_title">Подписка</h3><p data-translate="footer.newsletter_desc">Скидка 10% на первый заказ.</p><form class="newsletter-form" id="newsletterForm"><input type="email" class="newsletter-input" id="newsletterInput" placeholder="Ваш email" required><button type="submit" class="newsletter-btn"><i class="fas fa-paper-plane"></i></button></form></div>
            </div>
            <div class="copyright"><p>&copy; 2023 LuxeStyle. <span data-translate="footer.rights">Все права защищены.</span></p></div>
        </div>
    </footer>

    <script>
        (function() {
            // ========== ПЕРЕВОДЫ ==========
            const translations = {
                ru: {
                    "nav.home": "Главная",
                    "nav.categories": "Категории",
                    "nav.products": "Товары",
                    "nav.about": "О нас",
                    "nav.contact": "Контакты",
                    "hero.title": "Эксклюзивные брендовые вещи для истинных ценителей",
                    "hero.subtitle": "Откройте для себя мир роскоши и стиля с нашей коллекцией премиальных брендов. Качество, которое говорят само за себя.",
                    "hero.collection_btn": "Коллекция",
                    "hero.about_btn": "О нас",
                    "categories.title": "Категории",
                    "categories.clothing": "Одежда",
                    "categories.clothing_desc": "Эксклюзивная одежда от мировых брендов",
                    "categories.shoes": "Обувь",
                    "categories.shoes_desc": "Коллекция премиальной обуви",
                    "categories.accessories": "Аксессуары",
                    "categories.accessories_desc": "Роскошные аксессуары для завершения образа",
                    "products.title": "Популярные товары",
                    "products.all": "Все товары",
                    "products.sale": "🔥 Акции",
                    "cart.title": "Корзина",
                    "cart.empty": "Ваша корзина пуста",
                    "cart.empty_desc": "Добавьте товары из каталога",
                    "cart.total": "Итого:",
                    "cart.checkout": "Оформить заказ",
                    "cart.remove": "Удалить",
                    "cart.confirm_remove": "Удалить товар из корзины?",
                    "cart.thank_you": "Спасибо за заказ! Ваш заказ успешно оформлен.",
                    "cart.item_added": "Товар добавлен в корзину",
                    "about.title": "О LuxeStyle",
                    "about.desc1": "Мы — эксклюзивный ритейлер люксовых брендов, предлагающий тщательно отобранную коллекцию премиальных товаров для ценителей настоящего качества и стиля.",
                    "about.desc2": "Наша миссия — предоставить доступ к самым востребованным и редким предметам роскоши, сочетающим в себе безупречный дизайн, высочайшее качество и статусность.",
                    "about.year": "Год основания",
                    "about.brands": "Брендов",
                    "about.clients": "Довольных клиентов",
                    "footer.about_title": "О компании",
                    "footer.about_desc": "Эксклюзивные брендовые вещи для истинных ценителей роскоши и стиля.",
                    "footer.categories_title": "Категории",
                    "footer.new_collection": "Новая коллекция",
                    "footer.sale": "Распродажа",
                    "footer.info_title": "Информация",
                    "footer.delivery": "Доставка и оплата",
                    "footer.returns": "Возврат и обмен",
                    "footer.privacy": "Политика конфиденциальности",
                    "footer.newsletter_title": "Новостная рассылка",
                    "footer.newsletter_desc": "Подпишитесь на рассылку и получите скидку 10% на первый заказ.",
                    "footer.rights": "Все права защищены.",
                    "product.view": "Посмотреть детали",
                    "product.add_to_cart": "Добавить в корзину",
                    "notification.success": "Успешно!",
                    "notification.error": "Ошибка!",
                    "notification.subscribed": "Вы успешно подписались на рассылку!",
                    "notification.invalid_email": "Пожалуйста, введите корректный email",
                    "newsletter.placeholder": "Ваш email",
                    "search.placeholder": "Поиск товаров..."
                },
                en: {
                    "nav.home": "Home",
                    "nav.categories": "Categories",
                    "nav.products": "Products",
                    "nav.about": "About",
                    "nav.contact": "Contact",
                    "hero.title": "Exclusive Branded Items for True Connoisseurs",
                    "hero.subtitle": "Discover the world of luxury and style with our collection of premium brands. Quality that speaks for itself.",
                    "hero.collection_btn": "Collection",
                    "hero.about_btn": "About",
                    "categories.title": "Categories",
                    "categories.clothing": "Clothing",
                    "categories.clothing_desc": "Exclusive clothing from world brands",
                    "categories.shoes": "Shoes",
                    "categories.shoes_desc": "Collection of premium footwear",
                    "categories.accessories": "Accessories",
                    "categories.accessories_desc": "Luxurious accessories to complete your look",
                    "products.title": "Popular Products",
                    "products.all": "All Products",
                    "products.sale": "🔥 Sale",
                    "cart.title": "Shopping Cart",
                    "cart.empty": "Your cart is empty",
                    "cart.empty_desc": "Add items from the catalog",
                    "cart.total": "Total:",
                    "cart.checkout": "Checkout",
                    "cart.remove": "Remove",
                    "cart.confirm_remove": "Remove item from cart?",
                    "cart.thank_you": "Thank you for your order! Your order has been successfully placed.",
                    "cart.item_added": "Item added to cart",
                    "about.title": "About LuxeStyle",
                    "about.desc1": "We are an exclusive retailer of luxury brands, offering a carefully selected collection of premium goods for connoisseurs of true quality and style.",
                    "about.desc2": "Our mission is to provide access to the most sought-after and rare luxury items that combine impeccable design, highest quality and status.",
                    "about.year": "Year founded",
                    "about.brands": "Brands",
                    "about.clients": "Satisfied clients",
                    "footer.about_title": "About Company",
                    "footer.about_desc": "Exclusive branded items for true connoisseurs of luxury and style.",
                    "footer.categories_title": "Categories",
                    "footer.new_collection": "New Collection",
                    "footer.sale": "Sale",
                    "footer.info_title": "Information",
                    "footer.delivery": "Delivery & Payment",
                    "footer.returns": "Returns & Exchange",
                    "footer.privacy": "Privacy Policy",
                    "footer.newsletter_title": "Newsletter",
                    "footer.newsletter_desc": "Subscribe to our newsletter and get 10% off your first order.",
                    "footer.rights": "All rights reserved.",
                    "product.view": "View details",
                    "product.add_to_cart": "Add to Cart",
                    "notification.success": "Success!",
                    "notification.error": "Error!",
                    "notification.subscribed": "You have successfully subscribed to the newsletter!",
                    "notification.invalid_email": "Please enter a valid email",
                    "newsletter.placeholder": "Your email",
                    "search.placeholder": "Search products..."
                },
                kz: {
                    "nav.home": "Басты",
                    "nav.categories": "Санаттар",
                    "nav.products": "Тауарлар",
                    "nav.about": "Біз туралы",
                    "nav.contact": "Байланыс",
                    "hero.title": "Нағыз талғампаздарға арналған эксклюзивті брендтік заттар",
                    "hero.subtitle": "Біздің премиум брендтер жинағымен сән мен сәнділік әлемін ашыңыз. Өзі сөйлейтін сапа.",
                    "hero.collection_btn": "Жинақ",
                    "hero.about_btn": "Біз туралы",
                    "categories.title": "Санаттар",
                    "categories.clothing": "Киім",
                    "categories.clothing_desc": "Әлемдік брендтердің эксклюзивті киімдері",
                    "categories.shoes": "Аяқ киім",
                    "categories.shoes_desc": "Премиум аяқ киімдер жинағы",
                    "categories.accessories": "Аксессуарлар",
                    "categories.accessories_desc": "Сіздің сәулетіңізді аяқтайтын сәнді аксессуарлар",
                    "products.title": "Танымал тауарлар",
                    "products.all": "Барлық тауарлар",
                    "products.sale": "🔥 Акциялар",
                    "cart.title": "Себет",
                    "cart.empty": "Сіздің себетіңіз бос",
                    "cart.empty_desc": "Каталогтан тауарлар қосыңыз",
                    "cart.total": "Барлығы:",
                    "cart.checkout": "Тапсырысты рәсімдеу",
                    "cart.remove": "Жою",
                    "cart.confirm_remove": "Тауарды себеттен жойғыңыз келе ме?",
                    "cart.thank_you": "Тапсырысыңыз үшін рахмет! Сіздің тапсырысыңыз сәтті рәсімделді.",
                    "cart.item_added": "Тауар себетке қосылды",
                    "about.title": "LuxeStyle туралы",
                    "about.desc1": "Біз - нағыз сапа мен сән талғампаздарына арналған премиум тауарлардың мұқият таңдалған жинағын ұсынатын люкс брендтердің эксклюзивті дистрибьюторымыз.",
                    "about.desc2": "Біздің миссиямыз - мінсіз дизайн, жоғары сапа және мәртебесін біріктіретін ең сұранысты және сирек люкс заттарға қол жеткізу.",
                    "about.year": "Құрылған жылы",
                    "about.brands": "Брендтер",
                    "about.clients": "Қанағаттанған клиенттер",
                    "footer.about_title": "Компания туралы",
                    "footer.about_desc": "Нағыз сәнділік пен сән талғампаздарына арналған эксклюзивті брендтік заттар.",
                    "footer.categories_title": "Санаттар",
                    "footer.new_collection": "Жаңа жинақ",
                    "footer.sale": "Сатылым",
                    "footer.info_title": "Ақпарат",
                    "footer.delivery": "Жеткізу және төлем",
                    "footer.returns": "Қайтару және алмасу",
                    "footer.privacy": "Құпиялылық саясаты",
                    "footer.newsletter_title": "Жаңалықтар тарату",
                    "footer.newsletter_desc": "Жаңалықтар тарату тізіміне жазылыңыз және бірінші тапсырысыңыздан 10% жеңілдік алыңыз.",
                    "footer.rights": "Барлық құқықтар қорғалған.",
                    "product.view": "Толығырақ қарау",
                    "product.add_to_cart": "Себетке қосу",
                    "notification.success": "Сәтті!",
                    "notification.error": "Қате!",
                    "notification.subscribed": "Сіз жаңалықтар тарату тізіміне сәтті жазылдыңыз!",
                    "notification.invalid_email": "Дұрыс email енгізіңіз",
                    "newsletter.placeholder": "Сіздің email",
                    "search.placeholder": "Тауарларды іздеу..."
                }
            };

            // ========== ВСЕ 36 ТОВАРОВ С АКЦИЯМИ И КОММЕНТАРИЯМИ ==========
            const productsData = [
                { id:1, name:{ru:"Кожаная куртка премиум-класса", en:"Premium Leather Jacket", kz:"Премиум былған кожа куртка"}, category:"clothing", price:89999, oldPrice:119999, badge:"Sale", image:"https://primovello.ru/upload/phpthumb/13/28eb40578103936682746c3e48c30fa8.webp", description:{ru:"Итальянская кожа, ручная работа", en:"Italian leather, handmade", kz:"Итальян кожасы, қолдан жасалған"}, comments:[ {user:"Анна", text:"Отличное качество, села идеально!"}, {user:"Михаил", text:"Дорого, но стоит каждой копейки."} ] },
                { id:2, name:{ru:"Кашемировое пальто", en:"Cashmere Coat", kz:"Кашемир пальто"}, category:"clothing", price:125000, image:"https://st.aestatic.net/items-img/R/F/2/N/A698e03202c994d77963cb55cc22e685b3.jpeg_960x960.jpg", badge:"Luxury", description:{ru:"100% кашемир, ограниченная серия", en:"100% cashmere, limited edition", kz:"100% кашемир, шектеулі басылым"}, comments:[ {user:"Елена", text:"Очень теплое и элегантное."} ] },
                { id:3, name:{ru:"Дизайнерское вечернее платье", en:"Designer Evening Dress", kz:"Дизайнерлік кешкі көйлек"}, category:"clothing", price:185000, oldPrice:225000, badge:"Sale", image:"https://i.pinimg.com/originals/cf/dc/4e/cfdc4e7119a954b5134961e9c53c87c8.jpg", description:{ru:"Ручная вышивка, эксклюзивный дизайн", en:"Hand embroidery, exclusive design", kz:"Қолдан кестеленген, эксклюзивті дизайн"}, comments:[{user:"Ольга", text:"Шикарное платье, все подруги спрашивали где купила."}] },
                { id:4, name:{ru:"Брендовая рубашка", en:"Branded Shirt", kz:"Брендтік жейде"}, category:"clothing", price:24999, oldPrice:34999, badge:"Sale", image:"https://n.cdn.cdek.shopping/images/shopping/64VkVYwOk7hz03dR.jpg?v=1", description:{ru:"Хлопок премиум качества, итальянский пошив", en:"Premium cotton, Italian tailoring", kz:"Премиум мақта, итальяндық тігін"}, comments:[] },
                { id:5, name:{ru:"Дизайнерские кроссовки Limited Edition", en:"Designer Sneakers Limited Edition", kz:"Дизайнерлік кросовкалар шектеулі басылым"}, category:"shoes", price:74500, oldPrice:89500, badge:"Sale", image:"https://ir.ozone.ru/s3/multimedia-1/c600/6705766117.jpg", description:{ru:"Эксклюзивная коллекция, ограниченный тираж", en:"Exclusive collection, limited circulation", kz:"Эксклюзивті жинақ, шектеулі тираж"}, comments:[{user:"Денис", text:"Очень удобные, качество огонь!"}] },
                { id:6, name:{ru:"Кожаные туфли ручной работы", en:"Handmade Leather Shoes", kz:"Қолдан жасалған былған кожа туфли"}, category:"shoes", price:65000, image:"https://avatars.mds.yandex.net/i?id=7ed11f0327e5fb840693e3e1ce8998b4_sr-3688950-images-thumbs&n=13", badge:"Handmade", description:{ru:"Ручная работа, натуральная кожа", en:"Handmade, genuine leather", kz:"Қолдан жасалған, нағыз кожа"}, comments:[] },
                { id:7, name:{ru:"Зимние ботинки из нубука", en:"Winter Nubuck Boots", kz:"Қысқы нубук етік"}, category:"shoes", price:52000, oldPrice:62000, badge:"Sale", image:"https://static.insales-cdn.com/images/products/1/1109/138077269/lg-001.jpg", description:{ru:"Водонепроницаемые, утепленные", en:"Waterproof, insulated", kz:"Су өткізбейтін, жылы"}, comments:[{user:"Игорь", text:"В -25 не замерз, супер!"}] },
                { id:8, name:{ru:"Классические оксфорды", en:"Classic Oxfords", kz:"Классикалық оксфордтар"}, category:"shoes", price:89000, image:"https://cdn-sh1.vigbo.com/shops/119009/products/13673558/images/3-6ef45b54b04624037e8fe8db5bb8f74d.jpg", badge:"Classic", description:{ru:"Английский стиль, премиум кожа", en:"English style, premium leather", kz:"Ағылшын стилі, премиум кожа"}, comments:[] },
                { id:9, name:{ru:"Швейцарские часы с золотым браслетом", en:"Swiss Watch with Gold Bracelet", kz:"Алтын білезікпен швейцариялық сағат"}, category:"accessories", price:325000, oldPrice:390000, badge:"VIP", vip:true, image:"https://avatars.mds.yandex.net/i?id=2c421457220dc1e7aab26d65f5656851_l-5209742-images-thumbs&n=13", description:{ru:"Автоматический механизм, сапфировое стекло", en:"Automatic movement, sapphire crystal", kz:"Автоматты механизм, сапфир шыны"}, comments:[{user:"Артем", text:"Шикарные часы, все знакомые завидуют."}] },
                { id:10, name:{ru:"Дизайнерская кожаная сумка", en:"Designer Leather Bag", kz:"Дизайнерлік былған кожа сөмке"}, category:"accessories", price:112000, oldPrice:145000, badge:"Sale", image:"https://i.pinimg.com/originals/67/5a/59/675a598b33e74527f4d8110a354080fb.jpg", description:{ru:"Ручная работа, натуральная кожа, золотая фурнитура", en:"Handmade, genuine leather, gold hardware", kz:"Қолдан жасалған, нағыз кожа, алтын фурнитура"}, comments:[] },
                { id:11, name:{ru:"Золотые запонки с бриллиантами", en:"Gold Cufflinks with Diamonds", kz:"Алмастары бар алтын манжет түймелері"}, category:"accessories", price:78000, image:"https://avatars.mds.yandex.net/i?id=68c934408b0e5a4753734e7087d383d7_l-10752576-images-thumbs&n=13", badge:"New", description:{ru:"18-каратное золото, бриллианты 0.5 карат", en:"18-karat gold, 0.5 carat diamonds", kz:"18 карат алтын, 0.5 карат алмас"}, comments:[] },
                { id:12, name:{ru:"Дизайнерский кожаный ремень", en:"Designer Leather Belt", kz:"Дизайнерлік былған кожа белбеу"}, category:"accessories", price:18900, oldPrice:24000, badge:"Sale", image:"https://img.joomcdn.net/3570a0f6db84bbeac03fa9a36a55b6b5fcbaa72f_original.jpeg", description:{ru:"Натуральная кожа, позолоченная пряжка", en:"Genuine leather, gold-plated buckle", kz:"Нағыз кожа, алтынмен қапталған ілгек"}, comments:[{user:"Павел", text:"Отличный ремень, пряжка тяжёлая, качественная."}] },
                { id:13, name:{ru:"Шерстяной блейзер", en:"Wool Blazer", kz:"Жүн блейзер"}, category:"clothing", price:68000, image:"https://avatars.mds.yandex.net/i?id=affe3ede110aa9222ee58509a02317ef2f0e3b1b-5869570-images-thumbs&n=13", badge:"New", description:{ru:"Шерсть мериноса, классический крой", en:"Merino wool, classic cut", kz:"Мерино жүні, классикалық кесу"}, comments:[] },
                { id:14, name:{ru:"Шелковое платье", en:"Silk Dress", kz:"Жібек көйлек"}, category:"clothing", price:95000, oldPrice:115000, badge:"Sale", image:"https://avatars.mds.yandex.net/i?id=5aa291879f3ada160d8e8cb91c55d1255bd30733-5133916-images-thumbs&n=13", description:{ru:"100% натуральный шелк, ручная роспись", en:"100% natural silk, hand-painted", kz:"100% табиғи жібек, қолмен боялған"}, comments:[{user:"Светлана", text:"Потрясающее платье, очень нежное."}] },
                { id:15, name:{ru:"Кожаные штаны", en:"Leather Pants", kz:"Былған кожа шалбар"}, category:"clothing", price:75000, oldPrice:85000, badge:"Sale", image:"https://avatars.mds.yandex.net/i?id=f6c133850977e7b5823ac1beb9133c49e81fa5d0-4385982-images-thumbs&n=13", description:{ru:"Мягкая кожа, идеальная посадка", en:"Soft leather, perfect fit", kz:"Жұмсақ кожа, тамаша сәйкестік"}, comments:[] },
                { id:16, name:{ru:"Кашемировый свитер", en:"Cashmere Sweater", kz:"Кашемир свитер"}, category:"clothing", price:45000, image:"https://avatars.mds.yandex.net/i?id=7efa45f36a90062258668d63321a39a62577dc84-12154389-images-thumbs&n=13", badge:"Хит", description:{ru:"Невероятно мягкий, сохраняет тепло", en:"Incredibly soft, retains heat", kz:"Өте жұмсақ, жылуды сақтайды"}, comments:[{user:"Алексей", text:"Очень тёплый, но не колется."}] },
                { id:17, name:{ru:"Кожаные лоферы", en:"Leather Loafers", kz:"Былған кожа лоферлер"}, category:"shoes", price:55000, image:"https://avatars.mds.yandex.net/i?id=9650be67ea17d3fe72918999826d1f9e67d91b4c-4219872-images-thumbs&n=13", badge:"Classic", description:{ru:"Комфорт на весь день, премиум кожа", en:"All-day comfort, premium leather", kz:"Күні бойы ыңғайлылық, премиум кожа"}, comments:[] },
                { id:18, name:{ru:"Спортивные кроссовки", en:"Sports Sneakers", kz:"Спорттық кросовкалар"}, category:"shoes", price:42000, oldPrice:50000, badge:"Sale", image:"https://avatars.mds.yandex.net/i?id=e53882dafcf7d50425e88aecd6abe5bf827c51c7-5887670-images-thumbs&n=13", description:{ru:"Технологичная подошва, дышащий материал", en:"Technological sole, breathable material", kz:"Технологиялық табан, тыныс алатын материал"}, comments:[] },
                { id:19, name:{ru:"Сапоги на каблуке", en:"Heeled Boots", kz:"Өкшелі етік"}, category:"shoes", price:78000, image:"https://avatars.mds.yandex.net/i?id=599b382bf4a86f7ab98360c0ca1fca29e57256b7-4517378-images-thumbs&n=13", badge:"Fashion", description:{ru:"Стильные, удобные, модный фасон", en:"Stylish, comfortable, fashionable design", kz:"Стильді, ыңғайлы, сәнді дизайн"}, comments:[{user:"Ксения", text:"На каблуке можно ходить целый день."}] },
                { id:20, name:{ru:"Кроссовки для бега", en:"Running Sneakers", kz:"Жүгіру кросовкалары"}, category:"shoes", price:36000, oldPrice:45000, badge:"Sale", image:"https://avatars.mds.yandex.net/i?id=7e94ab4d9e92a3c442aa5bc8e2aed0fbfaf1c2fd-12146892-images-thumbs&n=13", description:{ru:"Амортизация, поддержка стопы", en:"Cushioning, foot support", kz:"Амортизация, аяқты қолдау"}, comments:[] },
                { id:21, name:{ru:"Солнечные очки", en:"Sunglasses", kz:"Күннен қорғайтын көзілдірік"}, category:"accessories", price:32000, image:"https://avatars.mds.yandex.net/i?id=1363f2896e16c2f192cee3e125ac167e-4575620-images-thumbs&n=13", badge:"New", description:{ru:"UV защита, стильная оправа", en:"UV protection, stylish frame", kz:"UV қорғаныс, стильді рама"}, comments:[] },
                { id:22, name:{ru:"Кожаный бумажник", en:"Leather Wallet", kz:"Былған кожа әмиян"}, category:"accessories", price:15000, oldPrice:20000, badge:"Sale", image:"https://avatars.mds.yandex.net/i?id=e3df1907290f8abb0c0b7ade3973a3c2bbf28c6e-5147471-images-thumbs&n=13", description:{ru:"Вместительный, натуральная кожа", en:"Spacious, genuine leather", kz:"Сыйымды, нағыз кожа"}, comments:[] },
                { id:23, name:{ru:"Шелковый шарф", en:"Silk Scarf", kz:"Жібек шарф"}, category:"accessories", price:22000, image:"https://avatars.mds.yandex.net/i?id=2a4089059da56db826cf41a38c02440d3f87fc45-5693960-images-thumbs&n=13", badge:"Luxury", description:{ru:"Ручная роспись, итальянский шелк", en:"Hand-painted, Italian silk", kz:"Қолмен боялған, итальян жібегі"}, comments:[{user:"Марина", text:"Очень красивый, нежный."}] },
                { id:24, name:{ru:"Ювелирное колье", en:"Jewelry Necklace", kz:"Зергерлік алқа"}, category:"accessories", price:98000, image:"https://avatars.mds.yandex.net/i?id=ba49fe7ec3ceb383b61e21bd963683084ce7b428-4259532-images-thumbs&n=13", badge:"Exclusive", description:{ru:"Серебро с позолотой, натуральные камни", en:"Silver with gold plating, natural stones", kz:"Алтынмен қапталған күміс, табиғи тастар"}, comments:[] },
                { id:25, name:{ru:"Кожаный жилет с мехом", en:"Leather Vest with Fur", kz:"Былған кожа мехпен жилет"}, category:"clothing", price:125000, image:"https://avatars.mds.yandex.net/i?id=bf9ba6cc0d17161bb53a1606ff4fe071822237ac-5232580-images-thumbs&n=13", badge:"VIP", vip:true, description:{ru:"Натуральный мех, ручная отделка", en:"Natural fur, handmade finishing", kz:"Табиғи мех, қолмен өңделген"}, comments:[{user:"Владимир", text:"Стильно, тепло, все спрашивают где взял."}] },
                { id:26, name:{ru:"Шёлковый халат", en:"Silk Robe", kz:"Жібек халат"}, category:"clothing", price:68000, image:"https://avatars.mds.yandex.net/i?id=6fc21753887b4c0a23fa006462bd27e6b2666d8d-9211032-images-thumbs&n=13", badge:"Luxury", description:{ru:"100% натуральный шёлк, вышивка золотом", en:"100% natural silk, gold embroidery", kz:"100% табиғи жібек, алтынмен кесте"}, comments:[] },
                { id:27, name:{ru:"Кожаные перчатки", en:"Leather Gloves", kz:"Былған кожа қолғап"}, category:"clothing", price:32000, oldPrice:40000, badge:"Sale", image:"https://avatars.mds.yandex.net/i?id=d0697f08f61463be3dfb3bee0b1b155a85caeca6-5287696-images-thumbs&n=13", description:{ru:"Мягкая кожа, подкладка из кашемира", en:"Soft leather, cashmere lining", kz:"Жұмсақ кожа, кашемир астары"}, comments:[] },
                { id:28, name:{ru:"Вельветовый пиджак", en:"Velvet Blazer", kz:"Вельвет пиджак"}, category:"clothing", price:85000, image:"https://avatars.mds.yandex.net/i?id=be42a59545b3c35b6256843205985eb4ee33e615-5239905-images-thumbs&n=13", badge:"New", description:{ru:"Итальянский вельвет, классический крой", en:"Italian velvet, classic cut", kz:"Итальян вельветі, классикалық кесу"}, comments:[] },
                { id:29, name:{ru:"Ботинки Chelsea", en:"Chelsea Boots", kz:"Челси етік"}, category:"shoes", price:92000, image:"https://avatars.mds.yandex.net/i?id=7b0d81dbf4cc5fcf484af994df37eb7505bf22a7-4306555-images-thumbs&n=13", badge:"VIP", vip:true, description:{ru:"Английская кожа, резиновая подошва", en:"English leather, rubber sole", kz:"Ағылшын кожасы, резина табан"}, comments:[{user:"Роман", text:"Лучшие ботинки, что у меня были."}] },
                { id:30, name:{ru:"Кроссовки из замши", en:"Suede Sneakers", kz:"Замша кросовкалар"}, category:"shoes", price:58000, oldPrice:72000, badge:"Sale", image:"https://avatars.mds.yandex.net/i?id=9b2661750e0bb4e46e3a8c98543ac28ac413e808-5024048-images-thumbs&n=13", description:{ru:"Итальянская замша, кожаная подкладка", en:"Italian suede, leather lining", kz:"Итальян замшасы, былған кожа астары"}, comments:[] },
                { id:31, name:{ru:"Лодочки на шпильке", en:"Stiletto Pumps", kz:"Шпилькадағы лодочка"}, category:"shoes", price:68000, image:"https://avatars.mds.yandex.net/i?id=3d47006cc9173c84cb32410679795c885dc7b968-4575491-images-thumbs&n=13", badge:"Fashion", description:{ru:"Высота каблука 10 см, кожа премиум", en:"10 cm heel, premium leather", kz:"Өкше биіктігі 10 см, премиум кожа"}, comments:[] },
                { id:32, name:{ru:"Спортивные тапочки", en:"Sports Slippers", kz:"Спорттық тақия"}, category:"shoes", price:25000, image:"https://avatars.mds.yandex.net/i?id=ad7391ff447dd5fcba453a9064563001e2fa840d-8210080-images-thumbs&n=13", badge:"Comfort", description:{ru:"Памящая форма, антибактериальная стелька", en:"Memory foam, antibacterial insole", kz:"Еске сақтау көбігі, антибактериялық табан"}, comments:[] },
                { id:33, name:{ru:"Золотое кольцо с сапфиром", en:"Gold Ring with Sapphire", kz:"Сапфирмен алтын сақина"}, category:"accessories", price:185000, image:"https://avatars.mds.yandex.net/i?id=b0ed31128c4ed7a7c7171666e1654d3de0489d0c-12475132-images-thumbs&n=13", badge:"VIP", vip:true, description:{ru:"18-каратное золото, натуральный сапфир", en:"18-karat gold, natural sapphire", kz:"18 карат алтын, табиғи сапфир"}, comments:[{user:"Екатерина", text:"Колечко просто сказка, очень нежное."}] },
                { id:34, name:{ru:"Кожаный клатч", en:"Leather Clutch", kz:"Былған кожа клатч"}, category:"accessories", price:45000, image:"https://avatars.mds.yandex.net/i?id=512e30ee9df791651e36cb8f8fd79596f3235c1c-7662942-images-thumbs&n=13", badge:"New", description:{ru:"Вечерняя сумка, цепочка на плечо", en:"Evening bag, shoulder chain", kz:"Кешкі сөмке, иық тізбегі"}, comments:[] },
                { id:35, name:{ru:"Шелковый галстук", en:"Silk Tie", kz:"Жібек галстук"}, category:"accessories", price:18000, image:"https://avatars.mds.yandex.net/i?id=5617bac3dd1839c49460f5afabe1485f8e89111e-12145584-images-thumbs&n=13", badge:"Classic", description:{ru:"Ручная роспись, итальянский шелк", en:"Hand-painted, Italian silk", kz:"Қолмен боялған, итальян жібегі"}, comments:[] },
                { id:36, name:{ru:"Дизайнерские очки", en:"Designer Glasses", kz:"Дизайнерлік көзілдірік"}, category:"accessories", price:42000, oldPrice:52000, badge:"Sale", image:"https://avatars.mds.yandex.net/i?id=c203b4248bc5ebc1aa2cd3f738c1b0a6aa5cd12d-5234452-images-thumbs&n=13", description:{ru:"Ацетат целлюлозы, поляризованные линзы", en:"Cellulose acetate, polarized lenses", kz:"Целлюлоза ацетаты, поляризацияланған линзалар"}, comments:[] }
            ];

            let currentLang = localStorage.getItem('luxestyle_lang') || 'ru';
            let currentFilter = 'all';
            let cart = JSON.parse(localStorage.getItem('luxestyle_cart')) || [];
            let products = productsData;
            let isDarkTheme = localStorage.getItem('luxestyle_dark_theme') === 'true';
            let searchTimeout = null;

            // ========== ЗАГРУЗОЧНЫЙ ЭКРАН ==========
            function initLoader() {
                createFloatingIcons();
                animateStats();
                animateProgressBar();
            }
            function createFloatingIcons() {
                const icons = ['fa-crown','fa-gem','fa-star','fa-heart','fa-shopping-bag','fa-gift','fa-ring','fa-coins'];
                const loaderIcons = document.getElementById('loaderIcons');
                for (let i=0; i<20; i++) {
                    const icon = document.createElement('i');
                    icon.className = `floating-icon fas ${icons[Math.floor(Math.random()*icons.length)]}`;
                    icon.style.left = Math.random()*100 + '%';
                    icon.style.top = Math.random()*100 + '%';
                    icon.style.setProperty('--tx', (Math.random()-0.5)*200 + 'px');
                    icon.style.setProperty('--ty', (Math.random()-0.5)*200 + 'px');
                    icon.style.animationDelay = Math.random()*5 + 's';
                    icon.style.fontSize = (Math.random()*20+15) + 'px';
                    icon.style.color = `rgba(212,167,106,${Math.random()*0.5+0.3})`;
                    loaderIcons.appendChild(icon);
                }
            }
            function animateStats() {
                let b=0, p=0, y=0;
                const brands = document.getElementById('statBrands');
                const prods = document.getElementById('statProducts');
                const years = document.getElementById('statYears');
                const bi = setInterval(()=>{ brands.textContent = (++b)+'+'; if(b>=50) clearInterval(bi); },30);
                const pi = setInterval(()=>{ prods.textContent = (p+=2); if(p>=36) clearInterval(pi); },20);
                const yi = setInterval(()=>{ years.textContent = ++y; if(y>=13) clearInterval(yi); },70);
            }
            function animateProgressBar() {
                const bar = document.getElementById('progressBar');
                let progress = 0;
                const interval = setInterval(() => {
                    progress += 1;
                    bar.style.width = progress + '%';
                    if (progress >= 100) {
                        clearInterval(interval);
                        document.getElementById('loader').classList.add('hidden');
                        createConfetti();
                        setTimeout(() => showNotification('Добро пожаловать в LuxeStyle!', 'info'), 500);
                    }
                }, 25);
            }
            function createConfetti() {
                const cont = document.getElementById('confettiContainer');
                cont.innerHTML = '';
                const colors = ['#FF6B35','#D4A76A','#FFD700','#4CAF50','#2196F3','#9C27B0','#FF4081','#00BCD4'];
                for (let i=0; i<150; i++) {
                    const c = document.createElement('div');
                    c.className = 'confetti';
                    const color = colors[Math.floor(Math.random()*colors.length)];
                    const size = Math.random()*10+5;
                    c.style.backgroundColor = color;
                    c.style.width = size + 'px';
                    c.style.height = (Math.random()>0.5?size:size/2) + 'px';
                    c.style.borderRadius = Math.random()>0.5?'50%':'2px';
                    c.style.left = Math.random()*100 + 'vw';
                    c.style.animation = `fall ${Math.random()*3+2}s ease-in ${Math.random()*2}s forwards`;
                    cont.appendChild(c);
                    setTimeout(() => c.remove(), 5000);
                }
            }
            function showNotification(msg, type='info') {
                document.querySelectorAll('.notification').forEach(n => n.remove());
                const n = document.createElement('div');
                n.className = `notification ${type}`;
                n.textContent = msg;
                n.style.cssText = `position:fixed;top:100px;right:20px;padding:12px 24px;border-radius:6px;font-weight:600;box-shadow:var(--shadow-md);z-index:9999;max-width:300px;font-size:20px;background:${type==='success'?'var(--success)':type==='error'?'var(--error)':'var(--primary)'};color:${type==='info'?'var(--brown-dark)':'white'};opacity:0;transform:translateX(100px);transition:all 0.3s;`;
                document.body.appendChild(n);
                setTimeout(()=>{ n.style.opacity='1'; n.style.transform='translateX(0)'; },10);
                setTimeout(()=>{ n.style.opacity='0'; n.style.transform='translateX(100px)'; setTimeout(()=>n.remove(),300); },3000);
            }

            // ========== ТЕМА ==========
            function initTheme() {
                if (isDarkTheme) { document.body.classList.add('dark-theme'); document.getElementById('themeToggle').classList.add('active'); createStars(); }
            }
            function toggleTheme() {
                isDarkTheme = !isDarkTheme;
                localStorage.setItem('luxestyle_dark_theme', isDarkTheme);
                document.body.classList.toggle('dark-theme', isDarkTheme);
                document.getElementById('themeToggle').classList.toggle('active', isDarkTheme);
                if (isDarkTheme) createStars();
                showNotification(isDarkTheme?'Темная тема включена':'Светлая тема включена', 'info');
            }
            function createStars() {
                if (!isDarkTheme) return;
                const bg = document.getElementById('starryBg');
                bg.innerHTML = '';
                for (let i=0; i<150; i++) {
                    const s = document.createElement('div');
                    s.className = 'star';
                    s.style.width = (Math.random()*3+1)+'px';
                    s.style.height = s.style.width;
                    s.style.left = Math.random()*100+'vw';
                    s.style.top = Math.random()*100+'vh';
                    s.style.opacity = Math.random()*0.5+0.2;
                    s.style.setProperty('--duration', (Math.random()*5+3)+'s');
                    s.style.animationDelay = Math.random()*5+'s';
                    bg.appendChild(s);
                }
            }

            // ========== ЯЗЫК ==========
            function setLanguage(lang) {
                if (!translations[lang]) return;
                currentLang = lang;
                localStorage.setItem('luxestyle_lang', lang);
                updateLanguageUI(lang);
                updateAllTexts();
                renderProducts(currentFilter);
                if (document.getElementById('cartModal').classList.contains('active')) renderCartItems();
                document.getElementById('languageSelector').classList.remove('active');
                showNotification('Язык изменен', 'success');
            }
            function updateLanguageUI(lang) {
                const flag = { ru:{src:'https://flagcdn.com/w40/ru.png',text:'РУ'}, en:{src:'https://flagcdn.com/w40/gb.png',text:'EN'}, kz:{src:'https://flagcdn.com/w40/kz.png',text:'ҚАЗ'} }[lang];
                if (flag) {
                    document.getElementById('currentFlag').querySelector('img').src = flag.src;
                    document.getElementById('currentLanguage').textContent = flag.text;
                }
            }
            function updateAllTexts() {
                document.querySelectorAll('[data-translate]').forEach(el => {
                    const key = el.dataset.translate;
                    if (translations[currentLang] && translations[currentLang][key]) {
                        if (el.tagName === 'INPUT') el.placeholder = translations[currentLang][key];
                        else el.textContent = translations[currentLang][key];
                    }
                });
            }
            function getTranslation(key) { return translations[currentLang]?.[key] || key; }

            // ========== ФОРМАТ ЦЕН ==========
            function formatPrice(price) {
                const mult = { en:1/70, kz:5, ru:1 }[currentLang] || 1;
                const symbol = { en:'$', kz:'₸', ru:'₽' }[currentLang] || '₽';
                return Math.round(price * mult).toLocaleString() + ' ' + symbol;
            }

            // ========== РЕНДЕР ТОВАРОВ ==========
            function renderProducts(filter = 'all') {
                currentFilter = filter;
                const grid = document.getElementById('productsGrid');
                let filtered = products;
                if (filter === 'sale') filtered = products.filter(p => p.oldPrice);
                else if (filter !== 'all') filtered = products.filter(p => p.category === filter);

                grid.innerHTML = '';
                if (!filtered.length) {
                    grid.innerHTML = '<div style="text-align:center;padding:40px;color:var(--brown-light);"><i class="fas fa-box-open" style="font-size:60px;"></i><h3>Товары не найдены</h3></div>';
                    return;
                }

                filtered.forEach(p => {
                    const card = document.createElement('div');
                    card.className = `product-card ${p.vip ? 'vip-product' : ''}`;
                    card.dataset.id = p.id;
                    card.innerHTML = `
                        ${p.badge ? `<div class="${p.badge==='VIP'?'vip-badge':'product-badge'}">${p.badge}</div>` : ''}
                        <div class="product-img"><img src="${p.image}" alt="${p.name[currentLang]}" loading="lazy"></div>
                        <div class="product-content">
                            <h3>${p.name[currentLang]}</h3>
                            <div class="product-description">${p.description[currentLang]}</div>
                            <div class="product-price">
                                <div>${p.oldPrice ? `<span class="old-price">${formatPrice(p.oldPrice)}</span>` : ''}<span class="price">${formatPrice(p.price)}</span></div>
                                <div class="product-actions">
                                    <button class="view-details" data-id="${p.id}" title="${getTranslation('product.view')}"><i class="fas fa-eye"></i></button>
                                    <button class="add-to-cart" data-id="${p.id}" title="${getTranslation('product.add_to_cart')}"><i class="fas fa-shopping-cart"></i></button>
                                </div>
                            </div>
                        </div>
                    `;
                    grid.appendChild(card);
                });
                attachProductEvents();
            }

            function attachProductEvents() {
                document.querySelectorAll('.add-to-cart').forEach(btn => {
                    btn.addEventListener('click', e => {
                        e.stopPropagation();
                        const id = parseInt(btn.dataset.id);
                        addToCart(id, btn);
                    });
                });
                document.querySelectorAll('.view-details').forEach(btn => {
                    btn.addEventListener('click', e => {
                        e.stopPropagation();
                        const id = parseInt(btn.dataset.id);
                        showProductModal(id);
                    });
                });
            }

            // ========== МОДАЛКА ТОВАРА С КОММЕНТАРИЯМИ ==========
            function showProductModal(productId) {
                const product = products.find(p => p.id === productId);
                if (!product) return;

                const commentsHTML = product.comments && product.comments.length 
                    ? product.comments.map(c => `<div style="border-bottom:1px solid var(--cream-dark); padding:10px 0;"><strong>${c.user}</strong><p style="margin-top:5px; font-size:18px;">${c.text}</p></div>`).join('')
                    : '<p style="color:var(--brown-light);">Пока нет отзывов. Будьте первым!</p>';

                const modalContent = `
                    <div style="text-align:center; margin-bottom:20px;">
                        <img src="${product.image}" alt="${product.name[currentLang]}" style="width:100%; max-width:300px; border-radius:8px; margin-bottom:15px;">
                        <h3 style="color:var(--secondary);">${product.name[currentLang]}</h3>
                        <p style="color:var(--brown-light); margin-bottom:10px;">${product.description[currentLang]}</p>
                        <div style="font-size:24px; font-weight:bold; color:var(--primary); margin-bottom:10px;">
                            ${formatPrice(product.price)}
                            ${product.oldPrice ? `<br><span style="font-size:16px; text-decoration:line-through; color:var(--gray);">${formatPrice(product.oldPrice)}</span>` : ''}
                        </div>
                        <button class="btn" onclick="addToCart(${product.id}); closeProductModal();" style="margin-bottom:20px;">${getTranslation('product.add_to_cart')}</button>
                    </div>
                    <div style="border-top:1px solid var(--cream-dark); padding-top:20px;">
                        <h4 style="margin-bottom:15px;">⭐ Отзывы</h4>
                        <div style="max-height:250px; overflow-y:auto; padding-right:10px;">${commentsHTML}</div>
                        <div style="margin-top:20px;">
                            <input type="text" id="commentName" placeholder="Ваше имя" style="width:100%; padding:8px; margin-bottom:10px; border:1px solid var(--cream-dark); border-radius:4px;">
                            <textarea id="commentText" placeholder="Ваш комментарий" rows="2" style="width:100%; padding:8px; border:1px solid var(--cream-dark); border-radius:4px;"></textarea>
                            <button class="btn" style="margin-top:10px;" onclick="addComment(${product.id})">Отправить</button>
                        </div>
                    </div>
                `;

                const modal = document.createElement('div');
                modal.className = 'cart-modal';
                modal.style.maxWidth = '500px';
                modal.innerHTML = `<div class="cart-header"><h3>${product.name[currentLang]}</h3><button class="close-cart" id="closeProductModal"><i class="fas fa-times"></i></button></div><div style="padding:20px; overflow-y:auto;">${modalContent}</div>`;
                document.body.appendChild(modal);
                document.getElementById('modalOverlay').classList.add('active');
                modal.classList.add('active');
                const close = () => { modal.classList.remove('active'); setTimeout(() => { modal.remove(); document.getElementById('modalOverlay').classList.remove('active'); }, 400); };
                modal.querySelector('#closeProductModal').addEventListener('click', close);
                document.getElementById('modalOverlay').addEventListener('click', close);
                window.closeProductModal = close;
                window.addComment = function(pid) {
                    const name = document.getElementById('commentName').value.trim();
                    const text = document.getElementById('commentText').value.trim();
                    if (!name || !text) { showNotification('Заполните все поля', 'error'); return; }
                    const prod = products.find(p => p.id === pid);
                    if (prod) {
                        prod.comments = prod.comments || [];
                        prod.comments.push({ user: name, text });
                        showNotification('Комментарий добавлен (демо)', 'success');
                        close();
                        setTimeout(() => showProductModal(pid), 300);
                    }
                };
            }

            // ========== КОРЗИНА ==========
            function addToCart(id, btn) {
                const product = products.find(p => p.id === id);
                if (!product) return;
                if (btn) animateAddToCart(id, btn);
                const idx = cart.findIndex(i => i.id === id);
                if (idx > -1) cart[idx].quantity++;
                else cart.push({ id: product.id, name: product.name[currentLang], price: product.price, image: product.image, quantity: 1 });
                saveCart();
                updateCartCount();
                if (document.getElementById('cartModal').classList.contains('active')) renderCartItems();
                showNotification(getTranslation('cart.item_added'), 'success');
            }
            function animateAddToCart(id, btn) {
                const rect = btn.getBoundingClientRect();
                const cartIcon = document.getElementById('cartIcon');
                const cartRect = cartIcon.getBoundingClientRect();
                const floating = document.createElement('div');
                floating.className = 'floating-item';
                floating.innerHTML = '<i class="fas fa-shopping-cart"></i>';
                floating.style.left = rect.left + rect.width/2 - 20 + 'px';
                floating.style.top = rect.top + rect.height/2 - 20 + 'px';
                document.body.appendChild(floating);
                requestAnimationFrame(() => {
                    floating.style.transform = `translate(${cartRect.left - rect.left}px, ${cartRect.top - rect.top}px) scale(0.5)`;
                    floating.style.opacity = '0.7';
                });
                setTimeout(() => {
                    floating.remove();
                    cartIcon.classList.add('animate');
                    setTimeout(() => cartIcon.classList.remove('animate'), 500);
                }, 600);
            }
            function saveCart() { localStorage.setItem('luxestyle_cart', JSON.stringify(cart)); }
            function updateCartCount() { document.getElementById('cartCount').textContent = cart.reduce((s,i)=>s+i.quantity,0); }
            function renderCartItems() {
                const container = document.getElementById('cartItemsContainer');
                const footer = document.getElementById('cartFooter');
                if (!cart.length) {
                    container.innerHTML = `<div class="cart-empty"><i class="fas fa-shopping-bag"></i><h4 data-translate="cart.empty">${getTranslation('cart.empty')}</h4><p data-translate="cart.empty_desc">${getTranslation('cart.empty_desc')}</p></div>`;
                    footer.style.display = 'none';
                    return;
                }
                footer.style.display = 'block';
                let html = '', total = 0;
                cart.forEach(item => {
                    total += item.price * item.quantity;
                    html += `
                        <div class="cart-item" data-id="${item.id}">
                            <div class="cart-item-img"><img src="${item.image}" alt="${item.name}"></div>
                            <div class="cart-item-details">
                                <div class="cart-item-title">${item.name}</div>
                                <div class="cart-item-price">${formatPrice(item.price)}</div>
                                <div class="cart-item-controls">
                                    <button class="quantity-btn decrease" data-id="${item.id}">-</button>
                                    <span class="cart-item-quantity">${item.quantity}</span>
                                    <button class="quantity-btn increase" data-id="${item.id}">+</button>
                                    <button class="remove-item" data-id="${item.id}" title="${getTranslation('cart.remove')}"><i class="fas fa-trash"></i></button>
                                </div>
                            </div>
                        </div>
                    `;
                });
                container.innerHTML = html;
                document.getElementById('cartTotalPrice').textContent = formatPrice(total);
                attachCartEvents();
            }
            function attachCartEvents() {
                document.querySelectorAll('.increase').forEach(btn => {
                    btn.addEventListener('click', () => updateCartItemQuantity(parseInt(btn.dataset.id), 1));
                });
                document.querySelectorAll('.decrease').forEach(btn => {
                    btn.addEventListener('click', () => updateCartItemQuantity(parseInt(btn.dataset.id), -1));
                });
                document.querySelectorAll('.remove-item').forEach(btn => {
                    btn.addEventListener('click', () => removeFromCart(parseInt(btn.dataset.id)));
                });
            }
            function updateCartItemQuantity(id, delta) {
                const idx = cart.findIndex(i => i.id === id);
                if (idx === -1) return;
                cart[idx].quantity += delta;
                if (cart[idx].quantity < 1) removeFromCart(id);
                else { saveCart(); updateCartCount(); renderCartItems(); }
            }
            function removeFromCart(id) {
                const el = document.querySelector(`.cart-item[data-id="${id}"]`);
                if (el) el.classList.add('removing');
                setTimeout(() => {
                    cart = cart.filter(i => i.id !== id);
                    saveCart();
                    updateCartCount();
                    renderCartItems();
                    if (!cart.length) showNotification(getTranslation('cart.empty'), 'info');
                }, 300);
            }
            function checkout() {
                if (!cart.length) { showNotification(getTranslation('cart.empty'), 'error'); return; }
                createConfetti();
                showNotification(getTranslation('cart.thank_you'), 'success');
                cart = [];
                saveCart();
                updateCartCount();
                renderCartItems();
                setTimeout(closeCart, 1500);
            }
            function openCart() { document.getElementById('cartModal').classList.add('active'); document.getElementById('modalOverlay').classList.add('active'); document.body.style.overflow = 'hidden'; renderCartItems(); }
            function closeCart() { document.getElementById('cartModal').classList.remove('active'); document.getElementById('modalOverlay').classList.remove('active'); document.body.style.overflow = 'auto'; }

            // ========== ПОИСК ==========
            function toggleSearch() {
                const exp = document.getElementById('searchExpanded');
                const ov = document.getElementById('searchOverlay');
                exp.classList.toggle('active');
                ov.style.display = exp.classList.contains('active') ? 'block' : 'none';
                if (exp.classList.contains('active')) document.getElementById('searchInput').focus();
            }
            function closeSearch() {
                document.getElementById('searchExpanded').classList.remove('active');
                document.getElementById('searchOverlay').style.display = 'none';
                clearSearchResults();
            }
            function clearSearchResults() {
                document.getElementById('searchResults').innerHTML = '';
                document.getElementById('searchResults').classList.remove('active');
            }
            function searchProducts(query) {
                if (!query.trim()) { clearSearchResults(); return; }
                const term = query.toLowerCase();
                const results = products.filter(p => 
                    p.name[currentLang].toLowerCase().includes(term) || 
                    p.description[currentLang].toLowerCase().includes(term)
                );
                displaySearchResults(results, query);
            }
            function displaySearchResults(results, query) {
                const cont = document.getElementById('searchResults');
                cont.innerHTML = results.length ? results.slice(0,5).map(p => `
                    <div class="search-result-item" data-id="${p.id}">
                        <div class="search-result-img"><img src="${p.image}" alt="${p.name[currentLang]}"></div>
                        <div class="search-result-info"><div class="search-result-name">${p.name[currentLang]}</div><div class="search-result-price">${formatPrice(p.price)}</div></div>
                    </div>
                `).join('') : `<div class="search-no-results"><p>По запросу "${query}" ничего не найдено</p></div>`;
                cont.classList.add('active');
                document.querySelectorAll('.search-result-item').forEach(el => {
                    el.addEventListener('click', () => {
                        const id = parseInt(el.dataset.id);
                        const p = products.find(p => p.id === id);
                        closeSearch();
                        window.scrollTo({ top: document.getElementById('products').offsetTop - 80, behavior:'smooth' });
                        document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
                        document.querySelector(`.filter-btn[data-filter="${p.category}"]`)?.classList.add('active');
                        renderProducts(p.category);
                    });
                });
            }
            function performSearch() {
                const q = document.getElementById('searchInput').value.trim();
                q ? searchProducts(q) : clearSearchResults();
            }

            // ========== ИНИЦИАЛИЗАЦИЯ ==========
            document.addEventListener('DOMContentLoaded', () => {
                initLoader();
                if (localStorage.getItem('luxestyle_lang') && translations[localStorage.getItem('luxestyle_lang')]) 
                    currentLang = localStorage.getItem('luxestyle_lang');
                initTheme();
                updateLanguageUI(currentLang);
                updateAllTexts();
                renderProducts();
                updateCartCount();
                attachEventListeners();
            });

            function attachEventListeners() {
                document.getElementById('themeToggle').addEventListener('click', toggleTheme);
                document.getElementById('searchToggle').addEventListener('click', toggleSearch);
                document.getElementById('searchSubmit').addEventListener('click', performSearch);
                document.getElementById('searchOverlay').addEventListener('click', closeSearch);
                document.getElementById('searchInput').addEventListener('input', function() {
                    clearTimeout(searchTimeout);
                    searchTimeout = setTimeout(() => searchProducts(this.value), 300);
                });
                document.getElementById('searchInput').addEventListener('keypress', e => { if (e.key === 'Enter') { e.preventDefault(); performSearch(); } });
                document.getElementById('languageSelector').addEventListener('click', function(e) { e.stopPropagation(); this.classList.toggle('active'); });
                document.addEventListener('click', e => { if (!e.target.closest('.language-selector')) document.getElementById('languageSelector').classList.remove('active'); });
                document.querySelectorAll('.language-option').forEach(opt => opt.addEventListener('click', function(e) { e.stopPropagation(); setLanguage(this.dataset.lang); }));

                document.querySelectorAll('.filter-btn').forEach(btn => {
                    btn.addEventListener('click', function() {
                        document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
                        this.classList.add('active');
                        renderProducts(this.dataset.filter);
                    });
                });

                document.getElementById('cartIcon').addEventListener('click', openCart);
                document.getElementById('closeCartBtn').addEventListener('click', closeCart);
                document.getElementById('modalOverlay').addEventListener('click', closeCart);
                document.getElementById('checkoutBtn').addEventListener('click', checkout);

                document.getElementById('mobileMenuBtn').addEventListener('click', () => { document.getElementById('nav').classList.add('active'); document.body.style.overflow = 'hidden'; });
                document.querySelectorAll('.nav-link').forEach(l => l.addEventListener('click', () => { document.getElementById('nav').classList.remove('active'); document.body.style.overflow = 'auto'; }));
                document.addEventListener('click', e => {
                    const nav = document.getElementById('nav');
                    if (nav.classList.contains('active') && !e.target.closest('#nav') && !e.target.closest('#mobileMenuBtn')) {
                        nav.classList.remove('active'); document.body.style.overflow = 'auto';
                    }
                });

                document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                    anchor.addEventListener('click', function(e) {
                        const target = document.querySelector(this.getAttribute('href'));
                        if (target) { e.preventDefault(); window.scrollTo({ top: target.offsetTop - 80, behavior: 'smooth' }); }
                    });
                });

                document.getElementById('newsletterForm').addEventListener('submit', function(e) {
                    e.preventDefault();
                    const input = document.getElementById('newsletterInput');
                    if (!input.value.trim() || !/^\S+@\S+\.\S+$/.test(input.value)) {
                        showNotification(getTranslation('notification.invalid_email'), 'error'); return;
                    }
                    showNotification(getTranslation('notification.subscribed'), 'success');
                    input.value = '';
                });

                window.addEventListener('scroll', () => {
                    document.getElementById('header').classList.toggle('scrolled', window.scrollY > 100);
                });

                document.querySelectorAll('.category-card').forEach(card => {
                    card.addEventListener('click', function() {
                        const cat = this.dataset.category;
                        document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
                        document.querySelector(`.filter-btn[data-filter="${cat}"]`)?.classList.add('active');
                        window.scrollTo({ top: document.getElementById('products').offsetTop - 80, behavior: 'smooth' });
                        renderProducts(cat);
                    });
                });

                document.addEventListener('keydown', e => { if (e.key === 'Escape') { closeCart(); document.getElementById('nav').classList.remove('active'); document.body.style.overflow = 'auto'; closeSearch(); } });
            }

            window.addToCart = addToCart;
            window.closeCart = closeCart;
        })();
    </script>
</body>
</html>
