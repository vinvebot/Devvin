
Put your HTML text here<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>DEV VIN · Nomor Virtual Siap Pakai</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
    <style>
        /* ========== GLOBAL ========== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', 'Segoe UI', system-ui, sans-serif;
        }

        body {
            background: #060b14;
            color: #eef3fc;
            line-height: 1.6;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 24px;
            width: 100%;
        }

        /* ========== ANIMATED BG GLOBAL ========== */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            z-index: -1;
            background:
                radial-gradient(ellipse at 20% 50%, rgba(79, 158, 255, 0.06) 0%, transparent 60%),
                radial-gradient(ellipse at 80% 50%, rgba(79, 158, 255, 0.04) 0%, transparent 60%),
                radial-gradient(ellipse at 50% 0%, rgba(79, 158, 255, 0.03) 0%, transparent 50%);
            animation: bgPulse 8s ease-in-out infinite alternate;
        }

        @keyframes bgPulse {
            0% {
                opacity: 0.6;
                transform: scale(1);
            }
            100% {
                opacity: 1;
                transform: scale(1.05);
            }
        }

        /* ========== ANIMATED GRADIENT TEXT ========== */
        .gradient-text {
            background: linear-gradient(90deg, #4f9eff, #a78bfa, #4f9eff, #60a5fa);
            background-size: 300% 100%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientMove 4s ease-in-out infinite;
        }

        @keyframes gradientMove {
            0% {
                background-position: 0% 50%;
            }
            50% {
                background-position: 100% 50%;
            }
            100% {
                background-position: 0% 50%;
            }
        }

        /* ========== ANIMATED BORDER GLOW ========== */
        .glow-border {
            position: relative;
            border: 1px solid transparent;
            background-clip: padding-box;
        }

        .glow-border::before {
            content: '';
            position: absolute;
            inset: -2px;
            border-radius: inherit;
            padding: 2px;
            background: linear-gradient(90deg, #4f9eff, #a78bfa, #f472b6, #4f9eff);
            background-size: 300% 100%;
            -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            -webkit-mask-composite: xor;
            mask-composite: exclude;
            animation: borderSpin 4s linear infinite;
            pointer-events: none;
        }

        @keyframes borderSpin {
            0% {
                background-position: 0% 50%;
            }
            100% {
                background-position: 300% 50%;
            }
        }

        /* ========== ANIMATED BUTTONS ========== */
        .btn-animated {
            background: linear-gradient(90deg, #4f9eff, #7c3aed, #4f9eff);
            background-size: 200% 100%;
            animation: btnGradient 3s ease-in-out infinite;
            border: none;
            transition: transform 0.2s;
        }

        .btn-animated:hover {
            transform: scale(1.04);
        }

        @keyframes btnGradient {
            0% {
                background-position: 0% 50%;
            }
            50% {
                background-position: 100% 50%;
            }
            100% {
                background-position: 0% 50%;
            }
        }

        /* ========== ANIMATED CARD GLOW ========== */
        .card-glow {
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .card-glow::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(from 0deg, transparent, rgba(79, 158, 255, 0.05), transparent, rgba(167, 139, 250, 0.05), transparent);
            animation: cardRotate 10s linear infinite;
            pointer-events: none;
        }

        @keyframes cardRotate {
            0% {
                transform: rotate(0deg);
            }
            100% {
                transform: rotate(360deg);
            }
        }

        .card-glow:hover::after {
            opacity: 0.5;
        }

        .card-glow>* {
            position: relative;
            z-index: 1;
        }

        /* ========== ANIMATED SHIMMER ========== */
        .shimmer {
            position: relative;
            overflow: hidden;
        }

        .shimmer::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.03), transparent);
            animation: shimmerSlide 4s ease-in-out infinite;
            pointer-events: none;
        }

        @keyframes shimmerSlide {
            0% {
                left: -100%;
            }
            100% {
                left: 200%;
            }
        }

        /* ========== NAVBAR ========== */
        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
            border-bottom: 1px solid #1a2538;
            flex-wrap: wrap;
            gap: 16px;
            position: relative;
            z-index: 10;
        }

        .logo {
            font-size: 28px;
            font-weight: 800;
            color: #fff;
            letter-spacing: -0.5px;
            cursor: pointer;
        }

        .logo i {
            color: #4f9eff;
            margin-right: 8px;
            animation: pulse 2s ease-in-out infinite;
        }

        @keyframes pulse {
            0%,
            100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.1);
            }
        }

        .logo span {
            background: linear-gradient(90deg, #4f9eff, #a78bfa, #f472b6, #4f9eff);
            background-size: 300% 100%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientMove 3s ease-in-out infinite;
        }

        .nav-links {
            display: flex;
            gap: 20px;
            font-size: 15px;
            font-weight: 500;
            color: #a0b3cc;
            flex-wrap: wrap;
            align-items: center;
        }
        .nav-links .nav-item {
            color: #a0b3cc;
            text-decoration: none;
            cursor: pointer;
            padding: 6px 0;
            transition: 0.2s;
            border-bottom: 2px solid transparent;
        }
        .nav-links .nav-item:hover {
            color: #fff;
        }
        .nav-links .nav-item.active {
            color: #fff;
            border-bottom-color: #4f9eff;
        }

        .btn-nav {
            background: linear-gradient(90deg, #4f9eff, #7c3aed);
            background-size: 200% 100%;
            animation: btnGradient 3s ease-in-out infinite;
            color: #fff !important;
            padding: 8px 22px;
            border-radius: 30px;
            font-weight: 600;
            border: none;
            cursor: pointer;
            transition: 0.2s;
            font-size: 15px;
        }
        .btn-nav:hover {
            transform: scale(1.05);
            box-shadow: 0 4px 25px rgba(79, 158, 255, 0.4);
        }

        .user-badge {
            background: #13203a;
            padding: 6px 16px;
            border-radius: 30px;
            border: 1px solid #2a3b5a;
            font-size: 14px;
            color: #b8c7e0;
            display: flex;
            align-items: center;
            gap: 8px;
            cursor: default;
        }
        .user-badge i {
            color: #4f9eff;
        }

        /* ========== PAGE CONTAINER ========== */
        .page {
            display: none;
            animation: fadeIn 0.4s ease;
        }
        .page.active {
            display: block;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(18px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* ========== BUTTONS ========== */
        .btn-primary {
            background: linear-gradient(90deg, #4f9eff, #7c3aed, #4f9eff);
            background-size: 200% 100%;
            animation: btnGradient 3.5s ease-in-out infinite;
            border: none;
            padding: 14px 44px;
            border-radius: 40px;
            font-size: 18px;
            font-weight: 700;
            color: #fff;
            cursor: pointer;
            transition: 0.25s;
            display: inline-flex;
            align-items: center;
            gap: 12px;
            text-decoration: none;
            position: relative;
            overflow: hidden;
        }
        .btn-primary:hover {
            transform: scale(1.04);
            box-shadow: 0 8px 40px rgba(79, 158, 255, 0.45);
        }
        .btn-primary::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.1) 0%, transparent 60%);
            animation: shimmerBtn 4s ease-in-out infinite;
            pointer-events: none;
        }
        @keyframes shimmerBtn {
            0% {
                transform: translate(-30%, -30%) scale(0.5);
                opacity: 0;
            }
            50% {
                opacity: 1;
            }
            100% {
                transform: translate(30%, 30%) scale(1.5);
                opacity: 0;
            }
        }

        .btn-outline {
            background: transparent;
            border: 1.5px solid #2a3b5a;
            padding: 14px 44px;
            border-radius: 40px;
            font-size: 18px;
            font-weight: 600;
            color: #eef3fc;
            cursor: pointer;
            transition: 0.25s;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            position: relative;
        }
        .btn-outline:hover {
            border-color: #4f9eff;
            background: rgba(79, 158, 255, 0.08);
            box-shadow: 0 0 30px rgba(79, 158, 255, 0.15);
        }

        /* ========== FOOTER ========== */
        .footer {
            border-top: 1px solid #1a2538;
            padding: 30px 0 20px;
            margin-top: 40px;
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 16px;
            color: #5a6e88;
            font-size: 14px;
        }
        .footer a {
            color: #7a8ea8;
            text-decoration: none;
            margin-left: 20px;
            cursor: pointer;
        }
        .footer a:hover {
            color: #fff;
        }
        .footer .social i {
            font-size: 18px;
            margin-left: 14px;
            color: #5a6e88;
            transition: 0.2s;
            cursor: pointer;
        }
        .footer .social i:hover {
            color: #4f9eff;
            transform: scale(1.15);
        }

        /* ========== PAGE: BERANDA ========== */
        .hero {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            padding: 60px 0 50px;
            position: relative;
        }

        .hero .badge {
            background: #13203a;
            border: 1px solid #2a3b5a;
            padding: 6px 20px;
            border-radius: 40px;
            font-size: 13px;
            color: #7fa9ff;
            margin-bottom: 24px;
            display: inline-block;
            animation: pulse 2.5s ease-in-out infinite;
        }

        .hero h1 {
            font-size: 52px;
            font-weight: 800;
            line-height: 1.15;
            max-width: 800px;
        }

        .hero h1 .highlight {
            background: linear-gradient(90deg, #4f9eff, #a78bfa, #f472b6, #4f9eff);
            background-size: 300% 100%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientMove 3s ease-in-out infinite;
        }

        .hero p {
            font-size: 19px;
            color: #8fa3c0;
            max-width: 640px;
            margin: 18px 0 30px;
        }

        .hero-stats {
            display: flex;
            gap: 48px;
            flex-wrap: wrap;
            justify-content: center;
            margin-top: 10px;
        }
        .hero-stats .stat {
            text-align: center;
        }
        .hero-stats .stat .num {
            font-size: 32px;
            font-weight: 700;
            color: #fff;
            background: linear-gradient(90deg, #4f9eff, #a78bfa);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        .hero-stats .stat .label {
            font-size: 14px;
            color: #7a8ea8;
        }

        .hero-buttons {
            display: flex;
            gap: 16px;
            flex-wrap: wrap;
            justify-content: center;
            margin-top: 8px;
        }

        .section-title {
            font-size: 36px;
            font-weight: 700;
            text-align: center;
            margin: 60px 0 12px;
        }

        .section-sub {
            text-align: center;
            color: #8fa3c0;
            font-size: 17px;
            margin-bottom: 40px;
        }

        .service-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
            gap: 16px;
            margin-bottom: 20px;
        }

        .service-card {
            background: #0f1729;
            border: 1px solid #1e2a40;
            border-radius: 16px;
            padding: 18px 12px;
            text-align: center;
            transition: 0.3s;
            position: relative;
            overflow: hidden;
        }

        .service-card::before {
            content: '';
            position: absolute;
            inset: -1px;
            border-radius: 16px;
            padding: 1px;
            background: linear-gradient(90deg, transparent, rgba(79, 158, 255, 0.2), transparent);
            background-size: 200% 100%;
            -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            -webkit-mask-composite: xor;
            mask-composite: exclude;
            animation: borderSpin 4s linear infinite;
            opacity: 0;
            transition: opacity 0.4s;
            pointer-events: none;
        }

        .service-card:hover::before {
            opacity: 1;
        }

        .service-card:hover {
            border-color: #4f9eff;
            background: #131e36;
            transform: translateY(-4px);
            box-shadow: 0 8px 30px rgba(79, 158, 255, 0.12);
        }

        .service-card .icon {
            font-size: 28px;
            color: #4f9eff;
            margin-bottom: 6px;
        }
        .service-card .name {
            font-weight: 600;
            font-size: 15px;
        }
        .service-card .price {
            font-size: 13px;
            color: #7a8ea8;
            margin-top: 4px;
        }
        .service-card .price strong {
            color: #fff;
        }

        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 30px;
            margin: 40px 0 20px;
        }

        .feature-item {
            background: #0f1729;
            border: 1px solid #1e2a40;
            border-radius: 16px;
            padding: 28px 22px;
            text-align: center;
            transition: 0.3s;
            position: relative;
            overflow: hidden;
        }

        .feature-item::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            border-radius: 18px;
            background: linear-gradient(90deg, #4f9eff, #a78bfa, #f472b6, #4f9eff);
            background-size: 300% 100%;
            animation: gradientMove 4s ease-in-out infinite;
            opacity: 0;
            transition: opacity 0.4s;
            z-index: -1;
        }

        .feature-item:hover::before {
            opacity: 0.15;
        }

        .feature-item:hover {
            transform: translateY(-4px);
            border-color: #4f9eff;
            box-shadow: 0 8px 30px rgba(79, 158, 255, 0.08);
        }

        .feature-item i {
            font-size: 34px;
            color: #4f9eff;
            margin-bottom: 12px;
            animation: pulse 3s ease-in-out infinite;
        }
        .feature-item h4 {
            font-size: 18px;
            margin-bottom: 6px;
        }
        .feature-item p {
            color: #8fa3c0;
            font-size: 14px;
        }

        .pricing-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 16px;
            margin: 30px 0 20px;
        }

        .pricing-card {
            background: #0f1729;
            border: 1px solid #1e2a40;
            border-radius: 16px;
            padding: 22px 16px;
            text-align: center;
            transition: 0.3s;
            position: relative;
            overflow: hidden;
        }

        .pricing-card::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(from 0deg, transparent, rgba(79, 158, 255, 0.04), transparent, rgba(167, 139, 250, 0.04), transparent);
            animation: cardRotate 12s linear infinite;
            pointer-events: none;
            opacity: 0;
            transition: opacity 0.4s;
        }

        .pricing-card:hover::after {
            opacity: 1;
        }

        .pricing-card:hover {
            transform: translateY(-6px);
            border-color: #4f9eff;
            box-shadow: 0 8px 30px rgba(79, 158, 255, 0.12);
        }

        .pricing-card .app {
            font-weight: 600;
            font-size: 16px;
        }
        .pricing-card .harga {
            font-size: 26px;
            font-weight: 700;
            color: #4f9eff;
            margin: 6px 0;
        }
        .pricing-card .harga small {
            font-size: 14px;
            color: #7a8ea8;
            font-weight: 400;
        }
        .pricing-card .coret {
            text-decoration: line-through;
            color: #5a6e88;
            font-size: 14px;
        }

        .steps {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 30px;
            margin: 30px 0 20px;
        }

        .step {
            text-align: center;
        }

        .step .num {
            display: inline-block;
            background: #13203a;
            border: 1px solid #2a3b5a;
            border-radius: 50%;
            width: 56px;
            height: 56px;
            line-height: 56px;
            font-size: 22px;
            font-weight: 800;
            color: #4f9eff;
            margin-bottom: 12px;
            animation: pulse 3s ease-in-out infinite;
            transition: 0.3s;
        }

        .step:hover .num {
            background: #1a2a4a;
            border-color: #4f9eff;
            box-shadow: 0 0 30px rgba(79, 158, 255, 0.2);
        }

        .step h4 {
            font-size: 18px;
        }
        .step p {
            color: #8fa3c0;
            font-size: 14px;
        }

        .api-box {
            background: #0b1325;
            border: 1px solid #1e2a40;
            border-radius: 20px;
            padding: 40px 36px;
            margin: 40px 0;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            position: relative;
            overflow: hidden;
        }

        .api-box::before {
            content: '';
            position: absolute;
            inset: -1px;
            border-radius: 20px;
            padding: 1px;
            background: linear-gradient(90deg, #4f9eff, #a78bfa, #f472b6, #4f9eff);
            background-size: 300% 100%;
            -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            -webkit-mask-composite: xor;
            mask-composite: exclude;
            animation: gradientMove 4s ease-in-out infinite;
            pointer-events: none;
        }

        .api-box .left h3 {
            font-size: 26px;
        }
        .api-box .left h3 i {
            color: #4f9eff;
            animation: pulse 2s ease-in-out infinite;
        }
        .api-box .left p {
            color: #8fa3c0;
            max-width: 500px;
        }

        .api-box .code {
            background: #060b14;
            border: 1px solid #1a2538;
            border-radius: 12px;
            padding: 16px 22px;
            font-family: 'Courier New', monospace;
            font-size: 13px;
            color: #9bb3d4;
            max-width: 100%;
            overflow-x: auto;
            margin-top: 12px;
            position: relative;
        }

        .api-box .code::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(79, 158, 255, 0.05), transparent);
            animation: shimmerSlide 5s ease-in-out infinite;
            pointer-events: none;
        }

        .testi-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 24px;
            margin: 30px 0 20px;
        }

        .testi-card {
            background: #0f1729;
            border: 1px solid #1e2a40;
            border-radius: 16px;
            padding: 24px 20px;
            transition: 0.3s;
            position: relative;
            overflow: hidden;
        }

        .testi-card::before {
            content: '';
            position: absolute;
            inset: -1px;
            border-radius: 16px;
            padding: 1px;
            background: linear-gradient(90deg, transparent, rgba(79, 158, 255, 0.15), transparent);
            background-size: 200% 100%;
            -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            -webkit-mask-composite: xor;
            mask-composite: exclude;
            animation: borderSpin 5s linear infinite;
            opacity: 0;
            transition: opacity 0.4s;
            pointer-events: none;
        }

        .testi-card:hover::before {
            opacity: 1;
        }

        .testi-card:hover {
            transform: translateY(-4px);
            border-color: #4f9eff;
            box-shadow: 0 8px 30px rgba(79, 158, 255, 0.08);
        }

        .testi-card .stars {
            color: #f5b342;
            margin-bottom: 6px;
        }
        .testi-card .text {
            font-size: 15px;
            margin-bottom: 10px;
        }
        .testi-card .author {
            font-weight: 600;
            font-size: 14px;
        }
        .testi-card .role {
            font-size: 13px;
            color: #7a8ea8;
        }

        .faq-list {
            max-width: 760px;
            margin: 20px auto 40px;
        }
        .faq-item {
            border-bottom: 1px solid #1a2538;
            padding: 18px 0;
        }
        .faq-item .q {
            font-weight: 600;
            font-size: 17px;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: 0.2s;
        }
        .faq-item .q:hover {
            color: #4f9eff;
        }
        .faq-item .q i {
            color: #4f9eff;
            transition: 0.3s;
        }
        .faq-item .a {
            color: #8fa3c0;
            font-size: 15px;
            padding-top: 8px;
            display: none;
        }
        .faq-item.active .a {
            display: block;
            animation: fadeIn 0.3s ease;
        }
        .faq-item.active .q i {
            transform: rotate(180deg);
        }

        .cta-section {
            text-align: center;
            background: #0b1325;
            border: 1px solid #1e2a40;
            border-radius: 24px;
            padding: 50px 30px;
            margin: 40px 0 50px;
            position: relative;
            overflow: hidden;
        }

        .cta-section::before {
            content: '';
            position: absolute;
            inset: -1px;
            border-radius: 24px;
            padding: 1px;
            background: linear-gradient(90deg, #4f9eff, #a78bfa, #f472b6, #4f9eff);
            background-size: 300% 100%;
            -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            -webkit-mask-composite: xor;
            mask-composite: exclude;
            animation: gradientMove 5s ease-in-out infinite;
            pointer-events: none;
        }

        .cta-section h2 {
            font-size: 36px;
        }
        .cta-section p {
            color: #8fa3c0;
            margin: 12px 0 28px;
        }

        /* ========== PAGE: ORDER ========== */
        .order-container {
            max-width: 820px;
            margin: 40px auto 60px;
            background: #0f1729;
            border: 1px solid #1e2a40;
            border-radius: 24px;
            padding: 40px 48px;
            position: relative;
            overflow: hidden;
        }

        .order-container::before {
            content: '';
            position: absolute;
            inset: -1px;
            border-radius: 24px;
            padding: 1px;
            background: linear-gradient(90deg, transparent, rgba(79, 158, 255, 0.15), transparent);
            background-size: 200% 100%;
            -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            -webkit-mask-composite: xor;
            mask-composite: exclude;
            animation: borderSpin 6s linear infinite;
            pointer-events: none;
        }

        .order-container h2 {
            font-size: 32px;
            font-weight: 700;
            margin-bottom: 6px;
        }
        .order-container h2 i {
            color: #4f9eff;
            animation: pulse 2s ease-in-out infinite;
        }
        .order-container .sub {
            color: #8fa3c0;
            margin-bottom: 28px;
        }

        .form-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px 30px;
        }
        .form-group.full {
            grid-column: 1 / -1;
        }
        .form-group label {
            color: #b8c7e0;
            font-size: 13px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            display: block;
            margin-bottom: 4px;
        }
        .form-group label i {
            color: #4f9eff;
            margin-right: 6px;
            width: 18px;
        }
        .form-group input,
        .form-group select {
            background: #0f151f;
            border: 1px solid #283240;
            border-radius: 10px;
            padding: 12px 16px;
            color: #eaf0f8;
            font-size: 15px;
            outline: none;
            transition: 0.25s;
            width: 100%;
        }
        .form-group input:focus,
        .form-group select:focus {
            border-color: #4f9eff;
            box-shadow: 0 0 0 3px rgba(79, 158, 255, 0.2);
            background: #111a26;
        }
        .form-group input::placeholder {
            color: #4a5a72;
        }
        .form-group select option {
            background: #141a24;
            color: #eaf0f8;
        }

        .price-box {
            background: #0f151f;
            border-radius: 12px;
            padding: 16px 20px;
            margin: 18px 0 10px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border: 1px solid #283240;
            flex-wrap: wrap;
            gap: 10px;
            position: relative;
            overflow: hidden;
        }

        .price-box::after {
            content: '';
            position: absolute;
            inset: 0;
            background: linear-gradient(90deg, transparent, rgba(79, 158, 255, 0.04), transparent);
            background-size: 200% 100%;
            animation: shimmerSlide 5s ease-in-out infinite;
            pointer-events: none;
        }

        .price-box .label {
            color: #8895aa;
            font-size: 14px;
        }
        .price-box .label i {
            color: #4f9eff;
            margin-right: 6px;
        }
        .price-box .value {
            color: #fff;
            font-size: 24px;
            font-weight: 700;
        }
        .price-box .value span {
            background: linear-gradient(90deg, #4f9eff, #a78bfa);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .btn-order-wa {
            background: linear-gradient(90deg, #25d366, #128C7E);
            background-size: 200% 100%;
            animation: btnGradient 3s ease-in-out infinite;
            border: none;
            border-radius: 12px;
            padding: 16px 28px;
            font-size: 18px;
            font-weight: 700;
            color: #fff;
            width: 100%;
            cursor: pointer;
            transition: 0.25s;
            margin-top: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 12px;
            position: relative;
            overflow: hidden;
        }
        .btn-order-wa:hover {
            transform: scale(1.01);
            box-shadow: 0 8px 35px rgba(37, 211, 102, 0.4);
        }
        .btn-order-wa::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.15) 0%, transparent 60%);
            animation: shimmerBtn 4s ease-in-out infinite;
            pointer-events: none;
        }

        .terms {
            display: flex;
            align-items: center;
            gap: 10px;
            color: #8895aa;
            font-size: 14px;
            margin-top: 6px;
        }
        .terms input[type="checkbox"] {
            width: 18px;
            height: 18px;
            accent-color: #4f9eff;
            cursor: pointer;
        }

        .alert-info {
            background: #1a2538;
            border-left: 4px solid #25d366;
            padding: 12px 18px;
            border-radius: 8px;
            color: #b0c4de;
            font-size: 14px;
            margin: 6px 0 16px;
            display: flex;
            align-items: center;
            gap: 12px;
            position: relative;
            overflow: hidden;
        }

        .alert-info::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(37, 211, 102, 0.05), transparent);
            animation: shimmerSlide 6s ease-in-out infinite;
            pointer-events: none;
        }

        .alert-info i {
            color: #25d366;
            font-size: 18px;
            animation: pulse 2s ease-in-out infinite;
        }

        /* ========== PAGE: DASHBOARD ========== */
        .dashboard-layout {
            display: flex;
            gap: 30px;
            margin: 30px 0;
        }

        .sidebar-dash {
            width: 220px;
            flex-shrink: 0;
            background: #0b1325;
            border: 1px solid #1a2538;
            border-radius: 16px;
            padding: 20px 16px;
            display: flex;
            flex-direction: column;
            gap: 20px;
            height: fit-content;
            position: relative;
            overflow: hidden;
        }

        .sidebar-dash::before {
            content: '';
            position: absolute;
            inset: -1px;
            border-radius: 16px;
            padding: 1px;
            background: linear-gradient(90deg, transparent, rgba(79, 158, 255, 0.08), transparent);
            background-size: 200% 100%;
            -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            -webkit-mask-composite: xor;
            mask-composite: exclude;
            animation: borderSpin 8s linear infinite;
            pointer-events: none;
        }

        .sidebar-dash .user {
            display: flex;
            align-items: center;
            gap: 12px;
            padding: 8px 12px;
            background: #0f1729;
            border-radius: 12px;
            border: 1px solid #1e2a40;
        }
        .sidebar-dash .user .avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: linear-gradient(90deg, #4f9eff, #7c3aed);
            background-size: 200% 100%;
            animation: btnGradient 3s ease-in-out infinite;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            font-size: 18px;
            color: #fff;
            text-transform: uppercase;
        }
        .sidebar-dash .user .info .name {
            font-weight: 600;
            font-size: 14px;
        }
        .sidebar-dash .user .info .role {
            font-size: 12px;
            color: #7a8ea8;
        }
        .sidebar-dash .menu {
            display: flex;
            flex-direction: column;
            gap: 4px;
        }
        .sidebar-dash .menu .nav-item {
            color: #8fa3c0;
            padding: 10px 14px;
            border-radius: 10px;
            font-size: 14px;
            font-weight: 500;
            transition: 0.2s;
            display: flex;
            align-items: center;
            gap: 12px;
            cursor: pointer;
            border: none;
            background: transparent;
            width: 100%;
            text-align: left;
        }
        .sidebar-dash .menu .nav-item i {
            width: 20px;
            text-align: center;
        }
        .sidebar-dash .menu .nav-item:hover,
        .sidebar-dash .menu .nav-item.active {
            background: #13203a;
            color: #fff;
        }
        .sidebar-dash .menu .nav-item.active {
            border-left: 3px solid #4f9eff;
            background: #13203a;
        }
        .sidebar-dash .bottom {
            border-top: 1px solid #1a2538;
            padding-top: 16px;
            margin-top: auto;
        }
        .sidebar-dash .bottom .nav-item {
            color: #8fa3c0;
            padding: 10px 14px;
            border-radius: 10px;
            font-size: 14px;
            transition: 0.2s;
            display: flex;
            align-items: center;
            gap: 12px;
            cursor: pointer;
            border: none;
            background: transparent;
            width: 100%;
            text-align: left;
        }
        .sidebar-dash .bottom .nav-item:hover {
            background: #13203a;
            color: #fff;
        }

        .main-dash {
            flex: 1;
            min-width: 0;
        }
        .topbar-dash {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 16px;
            margin-bottom: 24px;
        }
        .topbar-dash h2 {
            font-size: 28px;
            font-weight: 700;
        }

        .btn-wa {
            background: #25d366;
            border: none;
            padding: 10px 22px;
            border-radius: 30px;
            font-weight: 600;
            color: #fff;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            font-size: 14px;
            transition: 0.25s;
            text-decoration: none;
            position: relative;
            overflow: hidden;
        }

        .btn-wa::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.15) 0%, transparent 60%);
            animation: shimmerBtn 5s ease-in-out infinite;
            pointer-events: none;
        }

        .btn-wa:hover {
            background: #1da851;
            transform: scale(1.04);
            box-shadow: 0 4px 25px rgba(37, 211, 102, 0.4);
        }

        .saldo-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
            gap: 16px;
            margin-bottom: 30px;
        }

        .saldo-card {
            background: #0f1729;
            border: 1px solid #1e2a40;
            border-radius: 16px;
            padding: 18px 20px;
            transition: 0.3s;
            position: relative;
            overflow: hidden;
        }

        .saldo-card::before {
            content: '';
            position: absolute;
            inset: -1px;
            border-radius: 16px;
            padding: 1px;
            background: linear-gradient(90deg, transparent, rgba(79, 158, 255, 0.08), transparent);
            background-size: 200% 100%;
            -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            -webkit-mask-composite: xor;
            mask-composite: exclude;
            animation: borderSpin 6s linear infinite;
            opacity: 0;
            transition: opacity 0.4s;
            pointer-events: none;
        }

        .saldo-card:hover::before {
            opacity: 1;
        }

        .saldo-card:hover {
            border-color: #4f9eff;
            transform: translateY(-2px);
            box-shadow: 0 4px 20px rgba(79, 158, 255, 0.06);
        }

        .saldo-card .label {
            font-size: 13px;
            color: #7a8ea8;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }
        .saldo-card .value {
            font-size: 28px;
            font-weight: 700;
            margin-top: 4px;
        }
        .saldo-card .sub {
            font-size: 13px;
            color: #4f9eff;
            margin-top: 6px;
        }
        .saldo-card .sub i {
            margin-right: 4px;
        }

        .table-wrap {
            background: #0f1729;
            border: 1px solid #1e2a40;
            border-radius: 16px;
            overflow-x: auto;
            padding: 4px 0;
            position: relative;
        }

        .table-wrap::before {
            content: '';
            position: absolute;
            inset: -1px;
            border-radius: 16px;
            padding: 1px;
            background: linear-gradient(90deg, transparent, rgba(79, 158, 255, 0.05), transparent);
            background-size: 200% 100%;
            -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            -webkit-mask-composite: xor;
            mask-composite: exclude;
            animation: borderSpin 8s linear infinite;
            pointer-events: none;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            font-size: 14px;
        }
        table th {
            text-align: left;
            padding: 14px 18px;
            color: #7a8ea8;
            font-weight: 600;
            font-size: 12px;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            border-bottom: 1px solid #1a2538;
        }
        table td {
            padding: 12px 18px;
            border-bottom: 1px solid #121b2e;
            color: #eef3fc;
        }
        table tr:last-child td {
            border-bottom: none;
        }
        table tr:hover td {
            background: rgba(79, 158, 255, 0.03);
        }

        .status {
            display: inline-block;
            padding: 4px 14px;
            border-radius: 30px;
            font-size: 12px;
            font-weight: 600;
        }
        .status.active {
            background: #0f2a1f;
            color: #4ade80;
            animation: pulse 3s ease-in-out infinite;
        }
        .status.expired {
            background: #2a1a1a;
            color: #f87171;
        }
        .status.used {
            background: #1a2538;
            color: #94a3b8;
        }

        .btn-small {
            background: transparent;
            border: 1px solid #2a3b5a;
            color: #b8c7e0;
            padding: 4px 14px;
            border-radius: 20px;
            font-size: 12px;
            cursor: pointer;
            transition: 0.25s;
        }
        .btn-small:hover {
            border-color: #4f9eff;
            color: #fff;
            background: rgba(79, 158, 255, 0.08);
            box-shadow: 0 0 20px rgba(79, 158, 255, 0.1);
        }

        .info-note {
            margin-top: 20px;
            padding: 16px 20px;
            background: #0b1325;
            border-radius: 12px;
            border: 1px solid #1a2538;
            font-size: 14px;
            color: #8fa3c0;
            display: flex;
            align-items: center;
            gap: 12px;
            position: relative;
            overflow: hidden;
        }

        .info-note::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(79, 158, 255, 0.03), transparent);
            animation: shimmerSlide 7s ease-in-out infinite;
            pointer-events: none;
        }

        .info-note i {
            color: #4f9eff;
            font-size: 18px;
            animation: pulse 2.5s ease-in-out infinite;
        }

        /* ========== PAGE: LOGIN / REGISTER ========== */
        .auth-container {
            max-width: 420px;
            margin: 50px auto 70px;
            background: #0f1729;
            border: 1px solid #1e2a40;
            border-radius: 24px;
            padding: 40px 36px;
            position: relative;
            overflow: hidden;
        }

        .auth-container::before {
            content: '';
            position: absolute;
            inset: -1px;
            border-radius: 24px;
            padding: 1px;
            background: linear-gradient(90deg, #4f9eff, #a78bfa, #f472b6, #4f9eff);
            background-size: 300% 100%;
            -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            -webkit-mask-composite: xor;
            mask-composite: exclude;
            animation: gradientMove 5s ease-in-out infinite;
            pointer-events: none;
        }

        .auth-container h2 {
            font-size: 28px;
            font-weight: 700;
            text-align: center;
            background: linear-gradient(90deg, #4f9eff, #a78bfa);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        .auth-container .sub {
            text-align: center;
            color: #8fa3c0;
            margin-bottom: 28px;
        }
        .auth-container .form-group {
            margin-bottom: 18px;
        }
        .auth-container .form-group label {
            color: #b8c7e0;
            font-size: 13px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            display: block;
            margin-bottom: 4px;
        }
        .auth-container .form-group label i {
            color: #4f9eff;
            margin-right: 6px;
        }
        .auth-container .form-group input {
            background: #0f151f;
            border: 1px solid #283240;
            border-radius: 10px;
            padding: 12px 16px;
            color: #eaf0f8;
            font-size: 15px;
            outline: none;
            transition: 0.25s;
            width: 100%;
        }
        .auth-container .form-group input:focus {
            border-color: #4f9eff;
            box-shadow: 0 0 0 3px rgba(79, 158, 255, 0.2);
            background: #111a26;
        }
        .auth-container .form-group input::placeholder {
            color: #4a5a72;
        }

        .auth-container .btn-login {
            width: 100%;
            padding: 14px;
            border: none;
            border-radius: 12px;
            background: linear-gradient(90deg, #4f9eff, #7c3aed, #4f9eff);
            background-size: 200% 100%;
            animation: btnGradient 3s ease-in-out infinite;
            color: #fff;
            font-size: 17px;
            font-weight: 700;
            cursor: pointer;
            transition: 0.25s;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 10px;
            position: relative;
            overflow: hidden;
        }
        .auth-container .btn-login:hover {
            transform: scale(1.01);
            box-shadow: 0 8px 30px rgba(79, 158, 255, 0.4);
        }
        .auth-container .extra {
            text-align: center;
            margin-top: 18px;
            color: #8fa3c0;
            font-size: 14px;
        }
        .auth-container .extra .link {
            color: #4f9eff;
            cursor: pointer;
            text-decoration: none;
            transition: 0.2s;
        }
        .auth-container .extra .link:hover {
            text-decoration: underline;
            color: #a78bfa;
        }

        /* ========== BADGE COUNT ========== */
        .badge-count {
            background: #13203a;
            padding: 4px 14px;
            border-radius: 30px;
            font-size: 14px;
            font-weight: 500;
            color: #8fa3c0;
            display: inline-block;
            border: 1px solid #1e2a40;
        }

        /* ========== RESPONSIVE ========== */
        @media (max-width: 768px) {
            .navbar {
                flex-direction: column;
                align-items: stretch;
                text-align: center;
            }
            .nav-links {
                justify-content: center;
                gap: 12px;
            }
            .hero h1 {
                font-size: 32px;
            }
            .dashboard-layout {
                flex-direction: column;
            }
            .sidebar-dash {
                width: 100%;
            }
            .order-container {
                padding: 24px 18px;
            }
            .form-grid {
                grid-template-columns: 1fr;
                gap: 14px;
            }
            .auth-container {
                padding: 28px 20px;
                margin: 30px 10px;
            }
            .section-title {
                font-size: 28px;
            }
            .api-box {
                flex-direction: column;
                align-items: stretch;
                text-align: center;
            }
            .footer {
                flex-direction: column;
                text-align: center;
            }
            .footer a {
                margin: 0 10px;
            }
        }

        @media (max-width: 480px) {
            .saldo-grid {
                grid-template-columns: 1fr;
            }
            table th,
            table td {
                padding: 8px 12px;
                font-size: 12px;
            }
            .hero-stats {
                gap: 20px;
            }
            .hero-stats .stat .num {
                font-size: 24px;
            }
        }
    </style>
</head>
<body>

    <div class="container">

        <!-- ============================================================ -->
        <!-- NAVBAR -->
        <!-- ============================================================ -->
        <nav class="navbar" id="mainNavbar">
            <div class="logo" onclick="navigateTo('beranda')">
                <i class="fas fa-shield-alt"></i>DEV<span>VIN</span>
            </div>
            <div class="nav-links" id="navLinks">
                <span class="nav-item active" data-page="beranda" onclick="navigateTo('beranda')">Beranda</span>
                <span class="nav-item" data-page="layanan" onclick="navigateTo('layanan')">Layanan</span>
                <span class="nav-item" data-page="order" onclick="navigateTo('order')">Pesan</span>
                <span class="nav-item" data-page="dashboard" onclick="navigateTo('dashboard')">Dashboard</span>
                <span class="nav-item" data-page="login" onclick="navigateTo('login')" id="loginNav">Login</span>
                <button class="btn-nav" onclick="navigateTo('register')" id="registerNav">Daftar</button>
                <span id="userBadge" style="display:none;" class="user-badge"><i class="fas fa-user-circle"></i> <span id="navbarUsername">User</span></span>
                <button class="btn-nav" onclick="logoutUser()" id="logoutNav" style="display:none; background: #dc3545;">Logout</button>
            </div>
        </nav>

        <!-- ============================================================ -->
        <!-- PAGE: BERANDA -->
        <!-- ============================================================ -->
        <div id="page-beranda" class="page active">

            <section class="hero">
                <div class="badge"><i class="fas fa-circle" style="color:#4f9eff;font-size:10px;"></i> &nbsp; 12.438 user aktif · 478 layanan</div>
                <h1>Nomor Virtual <span class="highlight">Siap Pakai</span><br />Untuk Verifikasi Apa Saja</h1>
                <p>Sewa nomor virtual untuk WhatsApp, Telegram, Shopee, Tinder &amp; 478+ aplikasi lainnya. Mulai dari Rp 1.000 — refund otomatis kalau OTP gagal.</p>
                <div class="hero-buttons">
                    <button class="btn-primary" onclick="navigateTo('order')"><i class="fas fa-rocket"></i> Mulai Sekarang</button>
                    <button class="btn-outline"><i class="fas fa-play-circle"></i> Lihat Demo</button>
                </div>
                <div class="hero-stats">
                    <div class="stat"><div class="num">76</div><div class="label">Negara</div></div>
                    <div class="stat"><div class="num">&lt;30s</div><div class="label">OTP Masuk</div></div>
                    <div class="stat"><div class="num">99,2%</div><div class="label">Success Rate</div></div>
                    <div class="stat"><div class="num">100%</div><div class="label">Refund Garansi</div></div>
                </div>
            </section>

            <!-- Layanan -->
            <h2 class="section-title">Layanan <span class="gradient-text">DEV VIN</span></h2>
            <p class="section-sub">478+ aplikasi siap verifikasi. Harga mulai Rp 1.000.</p>
            <div class="service-grid">
                <div class="service-card"><div class="icon"><i class="fab fa-whatsapp"></i></div><div class="name">WhatsApp</div><div class="price">Rp <strong>2.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fab fa-telegram"></i></div><div class="name">Telegram</div><div class="price">Rp <strong>1.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fab fa-shopify"></i></div><div class="name">Shopee</div><div class="price">Rp <strong>2.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fas fa-shopping-bag"></i></div><div class="name">Tokopedia</div><div class="price">Rp <strong>3.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fas fa-car"></i></div><div class="name">Gojek</div><div class="price">Rp <strong>5.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fas fa-utensils"></i></div><div class="name">Grab</div><div class="price">Rp <strong>3.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fab fa-tinder"></i></div><div class="name">Tinder</div><div class="price">Rp <strong>5.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fab fa-discord"></i></div><div class="name">Discord</div><div class="price">Rp <strong>2.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fab fa-spotify"></i></div><div class="name">Spotify</div><div class="price">Rp <strong>3.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fab fa-amazon"></i></div><div class="name">Amazon</div><div class="price">Rp <strong>5.000</strong></div></div>
            </div>

            <!-- Fitur -->
            <div class="features">
                <div class="feature-item"><i class="fas fa-globe-asia"></i><h4>76 Negara</h4><p>Indonesia, USA, UK, Rusia, India, Filipina, Vietnam, Thailand, Malaysia &amp; 67 lainnya.</p></div>
                <div class="feature-item"><i class="fas fa-bolt"></i><h4>OTP &lt; 30 Detik</h4><p>Sistem real-time, rata-rata SMS masuk dalam 10–30 detik.</p></div>
                <div class="feature-item"><i class="fas fa-undo-alt"></i><h4>Refund 100% Otomatis</h4><p>Kalau OTP gak masuk dalam 20 menit, saldo balik otomatis tanpa admin.</p></div>
                <div class="feature-item"><i class="fas fa-code"></i><h4>REST API Powerful</h4><p>Kompatibel SMS-Activate protocol. Cocok untuk developer &amp; reseller.</p></div>
            </div>

            <!-- Harga -->
            <h2 class="section-title">Perbandingan Harga</h2>
            <p class="section-sub">Kami konsisten 50–70% lebih murah dari pasaran.</p>
            <div class="pricing-grid">
                <div class="pricing-card"><div class="app">Telegram</div><div class="harga">Rp 1.000 <small>/nomor</small></div><div class="coret">Rp 2.000</div></div>
                <div class="pricing-card"><div class="app">WhatsApp</div><div class="harga">Rp 2.000 <small>/nomor</small></div><div class="coret">Rp 5.000</div></div>
                <div class="pricing-card"><div class="app">Shopee</div><div class="harga">Rp 2.000 <small>/nomor</small></div><div class="coret">Rp 4.000</div></div>
                <div class="pricing-card"><div class="app">Tokopedia</div><div class="harga">Rp 3.000 <small>/nomor</small></div><div class="coret">Rp 6.000</div></div>
                <div class="pricing-card"><div class="app">Gojek</div><div class="harga">Rp 5.000 <small>/nomor</small></div><div class="coret">Rp 10.000</div></div>
                <div class="pricing-card"><div class="app">Tinder</div><div class="harga">Rp 5.000 <small>/nomor</small></div><div class="coret">Rp 12.000</div></div>
            </div>

            <!-- Cara Pakai -->
            <h2 class="section-title">Cara Pakai <span class="gradient-text">3 Langkah</span></h2>
            <p class="section-sub">Dari daftar sampai dapet OTP cuma kurang dari 2 menit.</p>
            <div class="steps">
                <div class="step"><div class="num">01</div><h4>Daftar &amp; Top Up</h4><p>Bikin akun gratis pakai email atau Google. Top up saldo via QRIS — minimum Rp 10.000.</p></div>
                <div class="step"><div class="num">02</div><h4>Pilih Layanan</h4><p>Cari aplikasi (WhatsApp, Telegram, Shopee, dll) + negara yang kamu butuhin. Klik order — nomor langsung muncul.</p></div>
                <div class="step"><div class="num">03</div><h4>Terima OTP</h4><p>Pakai nomor itu di aplikasi target. OTP otomatis masuk ke dashboard DEV VIN dalam 10–30 detik. Done.</p></div>
            </div>

            <!-- API -->
            <div class="api-box">
                <div class="left">
                    <h3><i class="fas fa-code"></i> Developer API</h3>
                    <p>Integrasikan ke tools kamu sendiri. REST API kompatibel SMS-Activate protocol. Cocok untuk reseller, automation, bot Telegram, atau aplikasi internal.</p>
                    <div class="code">
                        curl -X POST "https://devvin.com/api/getNumber" \<br />
                        &nbsp; -H "X-API-Key: YOUR_API_KEY" \<br />
                        &nbsp; -d "service=wa&amp;country=6"<br />
                        # Response: { "phone": "+6281234567890", "id": "7438291", "cost": "2000" }
                    </div>
                </div>
                <button class="btn-primary" style="padding:12px 32px;font-size:15px;">Dokumentasi API <i class="fas fa-arrow-right"></i></button>
            </div>

            <!-- Testimoni -->
            <h2 class="section-title">Testimoni Real</h2>
            <p class="section-sub">12.000+ user puas dengan DEV VIN.</p>
            <div class="testi-grid">
                <div class="testi-card"><div class="stars"><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i></div><div class="text">"Bener-bener termurah. WhatsApp di sini cuma 2.000 perak — di tempat lain Rp 5.000+."</div><div class="author">Andre</div><div class="role">Reseller 100+ order/hari</div></div>
                <div class="testi-card"><div class="stars"><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i></div><div class="text">"API-nya solid. Gua pakai buat auto-register klien — uptime 99%+ selama 6 bulan."</div><div class="author">Bayu</div><div class="role">Full-stack Engineer</div></div>
                <div class="testi-card"><div class="stars"><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i></div><div class="text">"Refund auto buenarrr. Gak sampai 25 menit saldo udah balik. Gak perlu chat admin."</div><div class="author">Citra</div><div class="role">Pengguna Harian</div></div>
            </div>

            <!-- FAQ -->
            <h2 class="section-title">FAQ</h2>
            <p class="section-sub">Pertanyaan umum seputar DEV VIN.</p>
            <div class="faq-list">
                <div class="faq-item active"><div class="q">Apa itu DEV VIN? <i class="fas fa-chevron-down"></i></div><div class="a">DEV VIN adalah layanan sewa nomor virtual (nomor kosong) untuk menerima kode SMS verifikasi dari ribuan aplikasi seperti WhatsApp, Telegram, Tinder, Gojek, Shopee — dengan harga termurah mulai Rp 1.000.</div></div>
                <div class="faq-item"><div class="q">Berapa harga sewa nomor di DEV VIN? <i class="fas fa-chevron-down"></i></div><div class="a">Mulai dari Rp 1.000 untuk Telegram, Rp 2.000 untuk WhatsApp, Rp 2.000 untuk Shopee. Sampai 60–70% lebih murah dari pasaran.</div></div>
                <div class="faq-item"><div class="q">Berapa lama OTP masuk? <i class="fas fa-chevron-down"></i></div><div class="a">Rata-rata 10–30 detik. Kalau dalam 20 menit OTP belum masuk, saldo otomatis dikembalikan 100%.</div></div>
                <div class="faq-item"><div class="q">Apakah aman pakai DEV VIN? <i class="fas fa-chevron-down"></i></div><div class="a">Aman. Setiap nomor hanya digunakan untuk satu sesi verifikasi, tidak diakses orang lain, dan riwayat tidak disimpan setelah aktivasi.</div></div>
                <div class="faq-item"><div class="q">Cara top up saldo? <i class="fas fa-chevron-down"></i></div><div class="a">QRIS (BCA, Mandiri, BRI, BNI, GoPay, OVO, DANA, ShopeePay). Otomatis &amp; instan, mulai Rp 10.000.</div></div>
                <div class="faq-item"><div class="q">Apakah ada API? <i class="fas fa-chevron-down"></i></div><div class="a">Ya, REST API lengkap kompatibel SMS-Activate protocol. Cocok untuk developer &amp; reseller. Dokumentasi di /api-docs.</div></div>
            </div>

            <!-- CTA -->
            <div class="cta-section">
                <h2 class="gradient-text">Gak ada alasan nunggu.</h2>
                <p>Daftar gratis dalam 30 detik. Top up minimum Rp 10.000. Langsung pakai untuk verifikasi apa aja.</p>
                <button class="btn-primary" onclick="navigateTo('register')"><i class="fas fa-user-plus"></i> Daftar Sekarang</button>
            </div>

        </div>

        <!-- ============================================================ -->
        <!-- PAGE: LAYANAN -->
        <!-- ============================================================ -->
        <div id="page-layanan" class="page">

            <h2 class="section-title">Semua Layanan <span class="gradient-text">DEV VIN</span></h2>
            <p class="section-sub">478+ aplikasi siap verifikasi. Harga mulai Rp 1.000.</p>

            <div class="service-grid" style="max-width:900px;margin:0 auto 40px;">
                <div class="service-card"><div class="icon"><i class="fab fa-whatsapp"></i></div><div class="name">WhatsApp</div><div class="price">Rp <strong>2.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fab fa-telegram"></i></div><div class="name">Telegram</div><div class="price">Rp <strong>1.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fab fa-shopify"></i></div><div class="name">Shopee</div><div class="price">Rp <strong>2.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fas fa-shopping-bag"></i></div><div class="name">Tokopedia</div><div class="price">Rp <strong>3.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fas fa-car"></i></div><div class="name">Gojek</div><div class="price">Rp <strong>5.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fas fa-utensils"></i></div><div class="name">Grab</div><div class="price">Rp <strong>3.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fab fa-tinder"></i></div><div class="name">Tinder</div><div class="price">Rp <strong>5.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fab fa-discord"></i></div><div class="name">Discord</div><div class="price">Rp <strong>2.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fab fa-spotify"></i></div><div class="name">Spotify</div><div class="price">Rp <strong>3.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fab fa-amazon"></i></div><div class="name">Amazon</div><div class="price">Rp <strong>5.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fab fa-google"></i></div><div class="name">Google</div><div class="price">Rp <strong>2.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fab fa-facebook"></i></div><div class="name">Facebook</div><div class="price">Rp <strong>2.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fab fa-instagram"></i></div><div class="name">Instagram</div><div class="price">Rp <strong>3.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fab fa-twitter"></i></div><div class="name">Twitter X</div><div class="price">Rp <strong>2.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fab fa-line"></i></div><div class="name">Line</div><div class="price">Rp <strong>2.000</strong></div></div>
                <div class="service-card"><div class="icon"><i class="fab fa-weixin"></i></div><div class="name">WeChat</div><div class="price">Rp <strong>3.000</strong></div></div>
            </div>

            <div style="text-align:center;margin-bottom:40px;">
                <button class="btn-primary" onclick="navigateTo('order')"><i class="fas fa-rocket"></i> Pesan Sekarang</button>
            </div>

        </div>

        <!-- ============================================================ -->
        <!-- PAGE: ORDER (Mode Perbayar via WhatsApp) -->
        <!-- ============================================================ -->
        <div id="page-order" class="page">

            <div class="order-container">
                <h2><i class="fas fa-shopping-cart"></i> Pesan Nomor</h2>
                <p class="sub">Isi data di bawah, lalu kirim pesanan via WhatsApp untuk konfirmasi &amp; pembayaran.</p>

                <div class="alert-info">
                    <i class="fab fa-whatsapp"></i>
                    <span>Pesanan akan dikirim ke <strong>085250737527</strong> (admin) — Anda akan diarahkan ke chat WhatsApp.</span>
                </div>

                <form id="orderForm" onsubmit="return false;">
                    <div class="form-grid">
                        <div class="form-group">
                            <label><i class="fas fa-list"></i> Layanan</label>
                            <select id="service">
                                <option value="WhatsApp">WhatsApp OTP</option>
                                <option value="Telegram">Telegram OTP</option>
                                <option value="Shopee">Shopee OTP</option>
                                <option value="Tokopedia">Tokopedia OTP</option>
                                <option value="Gojek">Gojek OTP</option>
                                <option value="Grab">Grab OTP</option>
                                <option value="Tinder">Tinder OTP</option>
                                <option value="Discord">Discord OTP</option>
                                <option value="Spotify">Spotify OTP</option>
                                <option value="Amazon">Amazon OTP</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label><i class="fas fa-flag"></i> Negara</label>
                            <select id="country">
                                <option value="Indonesia">🇮🇩 Indonesia</option>
                                <option value="USA">🇺🇸 USA</option>
                                <option value="UK">🇬🇧 UK</option>
                                <option value="Rusia">🇷🇺 Rusia</option>
                                <option value="India">🇮🇳 India</option>
                                <option value="Filipina">🇵🇭 Filipina</option>
                                <option value="Vietnam">🇻🇳 Vietnam</option>
                                <option value="Thailand">🇹🇭 Thailand</option>
                                <option value="Malaysia">🇲🇾 Malaysia</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label><i class="fas fa-hashtag"></i> Jumlah</label>
                            <input type="number" id="qty" value="1" min="1" max="10" />
                        </div>
                        <div class="form-group">
                            <label><i class="fas fa-phone-alt"></i> HP/Email (opsional)</label>
                            <input type="text" id="contact" placeholder="Untuk notifikasi" />
                        </div>
                        <div class="form-group full">
                            <label><i class="fas fa-pen"></i> Catatan</label>
                            <input type="text" id="note" placeholder="Tambahkan keterangan jika perlu..." />
                        </div>
                    </div>

                    <div class="price-box">
                        <span class="label"><i class="fas fa-tag"></i> Total Biaya</span>
                        <span class="value">Rp <span id="totalPrice">2.000</span></span>
                    </div>

                    <div class="terms">
                        <input type="checkbox" id="agree" checked />
                        <label for="agree">Saya setuju <a href="#" style="color:#4f9eff;">syarat &amp; ketentuan</a> DEV VIN.</label>
                    </div>

                    <button type="submit" class="btn-order-wa" onclick="orderViaWA()">
                        <i class="fab fa-whatsapp"></i> Pesan via WhatsApp
                    </button>
                </form>
            </div>

        </div>

        <!-- ============================================================ -->
        <!-- PAGE: DASHBOARD -->
        <!-- ============================================================ -->
        <div id="page-dashboard" class="page">

            <div class="dashboard-layout">
                <!-- Sidebar -->
                <aside class="sidebar-dash">
                    <div class="user">
                        <div class="avatar" id="dashAvatar">D</div>
                        <div class="info">
                            <div class="name" id="dashName">User</div>
                            <div class="role">Premium Member</div>
                        </div>
                    </div>
                    <nav class="menu">
                        <button class="nav-item active" onclick="showDashPage('dashboard')"><i class="fas fa-th-large"></i> Dashboard</button>
                        <button class="nav-item" onclick="navigateTo('order')"><i class="fas fa-mobile-alt"></i> Pesan Nomor</button>
                        <button class="nav-item"><i class="fas fa-history"></i> Riwayat</button>
                        <button class="nav-item"><i class="fas fa-wallet"></i> Top Up</button>
                        <button class="nav-item"><i class="fas fa-cog"></i> Pengaturan</button>
                    </nav>
                    <div class="bottom">
                        <button class="nav-item" onclick="logoutUser()"><i class="fas fa-sign-out-alt"></i> Logout</button>
                    </div>
                </aside>

                <!-- Main Dashboard -->
                <div class="main-dash">
                    <div class="topbar-dash">
                        <h2>Dashboard</h2>
                        <button class="btn-wa" onclick="openWA()"><i class="fab fa-whatsapp"></i> Wa Admin</button>
                    </div>

                    <div class="saldo-grid">
                        <div class="saldo-card"><div class="label"><i class="fas fa-coins"></i> Saldo Tersedia</div><div class="value">Rp <span id="saldoUtama">47.500</span></div><div class="sub"><i class="fas fa-arrow-up"></i> +Rp 10.000 minggu ini</div></div>
                        <div class="saldo-card"><div class="label"><i class="fas fa-lock"></i> Saldo Hold</div><div class="value">Rp <span id="saldoHold">12.000</span></div><div class="sub"><i class="fas fa-clock"></i> 3 pesanan pending</div></div>
                        <div class="saldo-card"><div class="label"><i class="fas fa-tag"></i> Total Transaksi</div><div class="value">Rp <span id="totalTransaksi">342.800</span></div><div class="sub"><i class="fas fa-calendar-alt"></i> Sepanjang waktu</div></div>
                        <div class="saldo-card"><div class="label"><i class="fas fa-phone-alt"></i> Nomor Aktif</div><div class="value"><span id="nomorAktif">12</span></div><div class="sub"><i class="fas fa-check-circle" style="color:#4ade80;"></i> 8 siap pakai</div></div>
                    </div>

                    <div class="section-title" style="font-size:20px;margin-bottom:12px;">
                        <span><i class="fas fa-list-ul" style="color:#4f9eff;margin-right:10px;"></i> Daftar Nomor Virtual</span>
                        <span class="badge-count"><i class="fas fa-database"></i> 12 nomor</span>
                    </div>

                    <div class="table-wrap">
                        <table>
                            <thead><tr><th>No</th><th>Nomor</th><th>Layanan</th><th>Negara</th><th>Status</th><th>Harga</th><th>Aksi</th></tr></thead>
                            <tbody>
                                <tr><td>1</td><td><span style="font-family:monospace;">+62 812 3456 7890</span></td><td><i class="fab fa-whatsapp" style="color:#25d366;"></i> WhatsApp</td><td>🇮🇩 Indonesia</td><td><span class="status active">Aktif</span></td><td>Rp 2.000</td><td><button class="btn-small"><i class="fas fa-eye"></i> Detail</button></td></tr>
                                <tr><td>2</td><td><span style="font-family:monospace;">+62 812 3456 7891</span></td><td><i class="fab fa-telegram" style="color:#26a5e4;"></i> Telegram</td><td>🇮🇩 Indonesia</td><td><span class="status active">Aktif</span></td><td>Rp 1.000</td><td><button class="btn-small"><i class="fas fa-eye"></i> Detail</button></td></tr>
                                <tr><td>3</td><td><span style="font-family:monospace;">+1 212 555 0199</span></td><td><i class="fas fa-shopping-bag"></i> Shopee</td><td>🇺🇸 USA</td><td><span class="status active">Aktif</span></td><td>Rp 2.000</td><td><button class="btn-small"><i class="fas fa-eye"></i> Detail</button></td></tr>
                                <tr><td>4</td><td><span style="font-family:monospace;">+62 813 9876 5432</span></td><td><i class="fas fa-car"></i> Gojek</td><td>🇮🇩 Indonesia</td><td><span class="status expired">Kadaluarsa</span></td><td>Rp 5.000</td><td><button class="btn-small"><i class="fas fa-redo"></i> Pesan Ulang</button></td></tr>
                                <tr><td>5</td><td><span style="font-family:monospace;">+44 20 7946 0958</span></td><td><i class="fab fa-tinder"></i> Tinder</td><td>🇬🇧 UK</td><td><span class="status used">Terpakai</span></td><td>Rp 5.000</td><td><button class="btn-small"><i class="fas fa-eye"></i> Detail</button></td></tr>
                                <tr><td>6</td><td><span style="font-family:monospace;">+62 821 3344 5566</span></td><td><i class="fab fa-discord"></i> Discord</td><td>🇮🇩 Indonesia</td><td><span class="status active">Aktif</span></td><td>Rp 2.000</td><td><button class="btn-small"><i class="fas fa-eye"></i> Detail</button></td></tr>
                            </tbody>
                        </table>
                    </div>

                    <div class="info-note">
                        <i class="fas fa-info-circle"></i>
                        <span>Klik <strong>"Wa Admin"</strong> di pojok kanan atas untuk chat admin via WhatsApp.</span>
                    </div>
                </div>
            </div>

        </div>

        <!-- ============================================================ -->
        <!-- PAGE: LOGIN -->
        <!-- ============================================================ -->
        <div id="page-login" class="page">

            <div class="auth-container">
                <h2>Masuk</h2>
                <p class="sub">Login ke akun DEV VIN kamu</p>

                <form onsubmit="loginUser(event)">
                    <div class="form-group">
                        <label><i class="fas fa-envelope"></i> Email</label>
                        <input type="email" id="loginEmail" placeholder="contoh@email.com" required />
                    </div>
                    <div class="form-group">
                        <label><i class="fas fa-lock"></i> Password</label>
                        <input type="password" id="loginPass" placeholder="••••••••" required />
                    </div>
                    <button type="submit" class="btn-login"><i class="fas fa-sign-in-alt"></i> Masuk</button>
                </form>

                <div class="extra">
                    Belum punya akun? <span class="link" onclick="navigateTo('register')">Daftar sekarang</span>
                </div>
            </div>

        </div>

        <!-- ============================================================ -->
        <!-- PAGE: REGISTER -->
        <!-- ============================================================ -->
        <div id="page-register" class="page">

            <div class="auth-container">
                <h2>Daftar Akun</h2>
                <p class="sub">Gratis, cuma 30 detik</p>

                <form onsubmit="registerUser(event)">
                    <div class="form-group">
                        <label><i class="fas fa-user"></i> Nama Lengkap</label>
                        <input type="text" id="regName" placeholder="Nama kamu" required />
                    </div>
                    <div class="form-group">
                        <label><i class="fas fa-envelope"></i> Email</label>
                        <input type="email" id="regEmail" placeholder="contoh@email.com" required />
                    </div>
                    <div class="form-group">
                        <label><i class="fas fa-lock"></i> Password</label>
                        <input type="password" id="regPass" placeholder="Minimal 6 karakter" required minlength="6" />
                    </div>
                    <button type="submit" class="btn-login"><i class="fas fa-user-plus"></i> Daftar Sekarang</button>
                </form>

                <div class="extra">
                    Sudah punya akun? <span class="link" onclick="navigateTo('login')">Login di sini</span>
                </div>
            </div>

        </div>

        <!-- ============================================================ -->
        <!-- FOOTER (muncul di semua halaman) -->
        <!-- ============================================================ -->
        <div class="footer">
            <div>&copy; 2026 <strong>DEV VIN</strong> — All rights reserved.</div>
            <div>
                <span class="link" onclick="navigateTo('beranda')">Beranda</span>
                <span class="link" onclick="navigateTo('layanan')">Layanan</span>
                <span class="link" onclick="navigateTo('order')">Pesan</span>
                <span class="link" onclick="navigateTo('dashboard')">Dashboard</span>
                <span class="link" onclick="navigateTo('login')">Login</span>
                <span class="social">
                    <i class="fab fa-whatsapp"></i>
                    <i class="fab fa-telegram"></i>
                    <i class="fab fa-instagram"></i>
                    <i class="fas fa-envelope"></i>
                </span>
            </div>
        </div>

    </div>

    <!-- ============================================================ -->
    <!-- SCRIPT -->
    <!-- ============================================================ -->
    <script>
        // ========== AUTH SYSTEM (localStorage Multi-Akun) ==========

        function getUsers() {
            try {
                return JSON.parse(localStorage.getItem('devvin_users')) || [];
            } catch {
                return [];
            }
        }

        function saveUsers(users) {
            localStorage.setItem('devvin_users', JSON.stringify(users));
        }

        function getCurrentUser() {
            try {
                return JSON.parse(localStorage.getItem('devvin_current_user'));
            } catch {
                return null;
            }
        }

        function setCurrentUser(user) {
            localStorage.setItem('devvin_current_user', JSON.stringify(user));
        }

        function clearCurrentUser() {
            localStorage.removeItem('devvin_current_user');
        }

        // ========== NAVIGASI ==========
        function navigateTo(pageId) {
            // Cek auth untuk dashboard
            if (pageId === 'dashboard') {
                const user = getCurrentUser();
                if (!user) {
                    alert('Silakan login terlebih dahulu.');
                    pageId = 'login';
                }
            }

            // Sembunyikan semua page
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            const target = document.getElementById('page-' + pageId);
            if (target) target.classList.add('active');

            // Update nav links
            document.querySelectorAll('.nav-links .nav-item').forEach(item => {
                item.classList.remove('active');
                if (item.dataset.page === pageId) {
                    item.classList.add('active');
                }
            });

            // Update navbar berdasarkan auth
            updateNavbarUI();

            // Scroll ke atas
            window.scrollTo({ top: 0, behavior: 'smooth' });

            // Jika dashboard, update tampilan user
            if (pageId === 'dashboard') {
                updateDashboardUI();
            }
        }

        // ========== UPDATE NAVBAR UI ==========
        function updateNavbarUI() {
            const user = getCurrentUser();
            const loginNav = document.getElementById('loginNav');
            const registerNav = document.getElementById('registerNav');
            const logoutNav = document.getElementById('logoutNav');
            const userBadge = document.getElementById('userBadge');
            const navbarUsername = document.getElementById('navbarUsername');

            if (user) {
                loginNav.style.display = 'none';
                registerNav.style.display = 'none';
                logoutNav.style.display = 'inline-block';
                userBadge.style.display = 'inline-flex';
                navbarUsername.textContent = user.name || 'User';
            } else {
                loginNav.style.display = 'inline';
                registerNav.style.display = 'inline-block';
                logoutNav.style.display = 'none';
                userBadge.style.display = 'none';
            }
        }

        // ========== UPDATE DASHBOARD UI ==========
        function updateDashboardUI() {
            const user = getCurrentUser();
            if (user) {
                document.getElementById('dashName').textContent = user.name || 'User';
                document.getElementById('dashAvatar').textContent = (user.name || 'U').charAt(0).toUpperCase();
            }
        }

        // ========== REGISTER ==========
        function registerUser(e) {
            e.preventDefault();
            const name = document.getElementById('regName').value.trim();
            const email = document.getElementById('regEmail').value.trim();
            const password = document.getElementById('regPass').value;

            if (!name || !email || password.length < 6) {
                alert('❌ Isi semua data dengan benar (password min 6 karakter).');
                return;
            }

            let users = getUsers();
            // Cek duplikat email
            if (users.find(u => u.email === email)) {
                alert('❌ Email sudah terdaftar. Silakan login.');
                return;
            }

            const newUser = {
                id: Date.now(),
                name: name,
                email: email,
                password: password
            };

            users.push(newUser);
            saveUsers(users);
            setCurrentUser({ id: newUser.id, name: newUser.name, email: newUser.email });

            alert('✅ Pendaftaran berhasil! Selamat datang, ' + name + '!');
            updateNavbarUI();
            navigateTo('dashboard');
        }

        // ========== LOGIN ==========
        function loginUser(e) {
            e.preventDefault();
            const email = document.getElementById('loginEmail').value.trim();
            const password = document.getElementById('loginPass').value;

            if (!email || !password) {
                alert('❌ Isi email dan password.');
                return;
            }

            const users = getUsers();
            const found = users.find(u => u.email === email && u.password === password);

            if (found) {
                setCurrentUser({ id: found.id, name: found.name, email: found.email });
                alert('✅ Login berhasil! Selamat datang kembali, ' + found.name);
                updateNavbarUI();
                navigateTo('dashboard');
            } else {
                alert('❌ Email atau password salah. Belum punya akun? Daftar dulu.');
            }
        }

        // ========== LOGOUT ==========
        function logoutUser() {
            if (confirm('Yakin ingin logout?')) {
                clearCurrentUser();
                updateNavbarUI();
                navigateTo('beranda');
                alert('Anda telah logout.');
            }
        }

        // ========== DASHBOARD SUB-NAV ==========
        function showDashPage(page) {
            document.querySelectorAll('.sidebar-dash .menu .nav-item').forEach(b => b.classList.remove('active'));
            document.querySelectorAll('.sidebar-dash .menu .nav-item').forEach(b => {
                if (b.textContent.trim().toLowerCase().includes(page)) {
                    b.classList.add('active');
                }
            });
            if (page === 'order') {
                navigateTo('order');
            }
        }

        // ========== FAQ TOGGLE ==========
        document.addEventListener('click', function(e) {
            const q = e.target.closest('.faq-item .q');
            if (q) {
                q.parentElement.classList.toggle('active');
            }
        });

        // ========== ORDER ==========
        const priceMap = {
            'WhatsApp': 2000,
            'Telegram': 1000,
            'Shopee': 2000,
            'Tokopedia': 3000,
            'Gojek': 5000,
            'Grab': 3000,
            'Tinder': 5000,
            'Discord': 2000,
            'Spotify': 3000,
            'Amazon': 5000
        };

        const serviceSelect = document.getElementById('service');
        const qtyInput = document.getElementById('qty');
        const totalSpan = document.getElementById('totalPrice');

        function updateTotal() {
            const service = serviceSelect.value;
            const base = priceMap[service] || 2000;
            const qty = parseInt(qtyInput.value) || 1;
            totalSpan.textContent = (base * qty).toLocaleString('id-ID');
        }

        if (serviceSelect) {
            serviceSelect.addEventListener('change', updateTotal);
            qtyInput.addEventListener('input', updateTotal);
            updateTotal();
        }

        // ========== ORDER VIA WHATSAPP ==========
        function orderViaWA() {
            const service = serviceSelect.value;
            const country = document.getElementById('country').value;
            const qty = qtyInput.value || 1;
            const contact = document.getElementById('contact').value.trim();
            const note = document.getElementById('note').value.trim();
            const agree = document.getElementById('agree').checked;

            if (!agree) {
                alert('❌ Setujui syarat & ketentuan terlebih dahulu.');
                return;
            }

            const total = (priceMap[service] || 2000) * parseInt(qty);
            const totalFormatted = total.toLocaleString('id-ID');

            let message = `Halo admin DEV VIN, saya mau pesan nomor virtual.\n\n`;
            message += `📌 Layanan: ${service}\n`;
            message += `🌍 Negara: ${country}\n`;
            message += `🔢 Jumlah: ${qty} nomor\n`;
            message += `💰 Total: Rp ${totalFormatted}\n`;
            if (contact) message += `📱 Kontak: ${contact}\n`;
            if (note) message += `📝 Catatan: ${note}\n\n`;
            message += `Saya setuju dengan syarat & ketentuan DEV VIN.`;

            const waNumber = '6285250737527';
            const waUrl = 'https://wa.me/' + waNumber + '?text=' + encodeURIComponent(message);
            window.open(waUrl, '_blank');
        }

        // ========== WA ADMIN ==========
        function openWA() {
            const waNumber = '6285250737527';
            const msg = 'Halo admin DEV VIN, saya mau tanya...';
            window.open('https://wa.me/' + waNumber + '?text=' + encodeURIComponent(msg), '_blank');
        }

        // ========== INIT ==========
        // Cek session saat load
        const currentUser = getCurrentUser();
        if (currentUser) {
            updateNavbarUI();
            // Jika sedang di halaman login/register, pindah ke dashboard
            const activePage = document.querySelector('.page.active');
            if (activePage) {
                const id = activePage.id;
                if (id === 'page-login' || id === 'page-register') {
                    navigateTo('dashboard');
                } else {
                    // update dashboard jika sedang di dashboard
                    if (id === 'page-dashboard') {
                        updateDashboardUI();
                    }
                }
            }
        } else {
            updateNavbarUI();
            // Jika di dashboard tanpa login, arahkan ke beranda
            const activePage = document.querySelector('.page.active');
            if (activePage && activePage.id === 'page-dashboard') {
                navigateTo('beranda');
            }
        }

        console.log('DEV VIN — Multi-Akun + Harga Baru + Mode WA Aktif!');
    </script>

</body>
</html>
