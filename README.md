<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Novary Agency - Jasa Pembuatan Website Profesional</title>
    <link href="https://cdn.jsdelivr.net/npm/remixicon@3.5.0/fonts/remixicon.css" rel="stylesheet">
    <style>
        /* ===== CSS VARIABLES ===== */
        :root {
            --bg-primary: #0a0a0f;
            --bg-secondary: #12121a;
            --bg-card: #1a1a24;
            --text-primary: #ffffff;
            --text-secondary: #a0a0b0;
            --neon-blue: #00d4ff;
            --neon-blue-glow: rgba(0, 212, 255, 0.3);
            --neon-orange: #ff6b35;
            --neon-orange-glow: rgba(255, 107, 53, 0.3);
            --gradient-blue: linear-gradient(135deg, #00d4ff 0%, #0099cc 100%);
            --gradient-orange: linear-gradient(135deg, #ff6b35 0%, #ff8c5a 100%);
            --border-color: rgba(255, 255, 255, 0.08);
            --transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }

        /* ===== RESET & BASE ===== */
        *, *::before, *::after {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            background: var(--bg-primary);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* ===== UTILITY CLASSES ===== */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 24px;
        }

        .section-title {
            font-size: clamp(1.8rem, 4vw, 2.5rem);
            font-weight: 700;
            margin-bottom: 16px;
            letter-spacing: -0.02em;
        }

        .section-subtitle {
            color: var(--text-secondary);
            font-size: 1.1rem;
            max-width: 600px;
        }

        .highlight {
            color: var(--neon-blue);
        }

        .highlight-orange {
            color: var(--neon-orange);
        }

        /* ===== BUTTONS ===== */
        .btn {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 14px 28px;
            border-radius: 50px;
            font-weight: 600;
            font-size: 0.95rem;
            text-decoration: none;
            transition: var(--transition);
            border: none;
            cursor: pointer;
        }

        .btn-primary {
            background: var(--gradient-blue);
            color: var(--bg-primary);
            box-shadow: 0 4px 20px var(--neon-blue-glow);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 30px var(--neon-blue-glow);
        }

        .btn-secondary {
            background: transparent;
            color: var(--text-primary);
            border: 1px solid var(--border-color);
        }

        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.05);
            border-color: var(--neon-blue);
        }

        .btn-orange {
            background: var(--gradient-orange);
            color: white;
            box-shadow: 0 4px 20px var(--neon-orange-glow);
        }

        .btn-orange:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 30px var(--neon-orange-glow);
        }

        /* ===== NAVIGATION ===== */
        nav {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
            padding: 20px 0;
            transition: var(--transition);
        }

        nav.scrolled {
            background: rgba(10, 10, 15, 0.95);
            backdrop-filter: blur(20px);
            padding: 12px 0;
            border-bottom: 1px solid var(--border-color);
        }

        .nav-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .logo-icon {
            width: 40px;
            height: 40px;
            background: var(--gradient-blue);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            color: var(--bg-primary);
        }

        .logo span {
            background: var(--gradient-blue);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-links {
            display: flex;
            gap: 32px;
            list-style: none;
        }

        .nav-links a {
            color: var(--text-secondary);
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -4px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--neon-blue);
            transition: var(--transition);
        }

        .nav-links a:hover {
            color: var(--text-primary);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-cta {
            padding: 10px 20px;
            font-size: 0.9rem;
        }

        .mobile-toggle {
            display: none;
            flex-direction: column;
            gap: 5px;
            cursor: pointer;
            padding: 8px;
        }

        .mobile-toggle span {
            width: 24px;
            height: 2px;
            background: var(--text-primary);
            transition: var(--transition);
        }

        /* ===== HERO SECTION ===== */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
            padding: 120px 0 80px;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -20%;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, var(--neon-blue-glow) 0%, transparent 70%);
            filter: blur(80px);
            animation: pulse 8s ease-in-out infinite;
        }

        .hero::after {
            content: '';
            position: absolute;
            bottom: -30%;
            left: -10%;
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, var(--neon-orange-glow) 0%, transparent 70%);
            filter: blur(100px);
            animation: pulse 10s ease-in-out infinite reverse;
        }

        @keyframes pulse {
            0%, 100% { opacity: 0.5; transform: scale(1); }
            50% { opacity: 0.8; transform: scale(1.1); }
        }

        .hero-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 80px;
            align-items: center;
            position: relative;
            z-index: 1;
        }

        .hero-content {
            animation: fadeInUp 1s ease;
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

        .hero-badge {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 8px 16px;
            background: rgba(0, 212, 255, 0.1);
            border: 1px solid rgba(0, 212, 255, 0.2);
            border-radius: 50px;
            font-size: 0.85rem;
            color: var(--neon-blue);
            margin-bottom: 24px;
        }

        .hero-badge i {
            font-size: 1rem;
        }

        .hero h1 {
            font-size: clamp(2.5rem, 5vw, 3.5rem);
            font-weight: 800;
            line-height: 1.1;
            margin-bottom: 20px;
            letter-spacing: -0.03em;
        }

        .hero h1 .gradient-text {
            background: var(--gradient-blue);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero p {
            font-size: 1.2rem;
            color: var(--text-secondary);
            margin-bottom: 32px;
            max-width: 500px;
        }

        .hero-buttons {
            display: flex;
            gap: 16px;
            flex-wrap: wrap;
        }

        .hero-stats {
            display: flex;
            gap: 40px;
            margin-top: 48px;
            padding-top: 32px;
            border-top: 1px solid var(--border-color);
        }

        .stat {
            text-align: center;
        }

        .stat-number {
            font-size: 2rem;
            font-weight: 700;
            color: var(--neon-blue);
        }

        .stat-label {
            font-size: 0.85rem;
            color: var(--text-secondary);
            margin-top: 4px;
        }

        .hero-visual {
            position: relative;
            animation: fadeInUp 1s ease 0.3s both;
        }

        .hero-image-wrapper {
            position: relative;
            width: 100%;
            aspect-ratio: 1;
            max-width: 500px;
            margin: 0 auto;
        }

        .hero-browser {
            background: var(--bg-card);
            border-radius: 16px;
            overflow: hidden;
            border: 1px solid var(--border-color);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5);
        }

        .browser-header {
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 12px 16px;
            background: var(--bg-secondary);
            border-bottom: 1px solid var(--border-color);
        }

        .browser-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
        }

        .browser-dot.red { background: #ff5f57; }
        .browser-dot.yellow { background: #febc2e; }
        .browser-dot.green { background: #28c840; }

        .browser-content {
            padding: 24px;
            min-height: 280px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }

        .browser-placeholder {
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            gap: 16px;
        }

        .placeholder-box {
            background: linear-gradient(135deg, rgba(0, 212, 255, 0.1) 0%, rgba(0, 212, 255, 0.05) 100%);
            border: 1px solid rgba(0, 212, 255, 0.2);
            border-radius: 8px;
        }

        .placeholder-box.hero-main {
            height: 70px;
        }

        .placeholder-row {
            display: flex;
            gap: 16px;
        }

        .placeholder-box.small {
            flex: 1;
            height: 50px;
        }

        .floating-elements {
            position: absolute;
            top: -20px;
            right: -30px;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(5deg); }
        }

        .floating-card {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 14px 18px;
            backdrop-filter: blur(10px);
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 12px;
        }

        .floating-card i {
            font-size: 1.3rem;
            color: var(--neon-blue);
        }

        .floating-card span {
            font-size: 0.8rem;
            font-weight: 600;
            white-space: nowrap;
        }

        /* ===== SERVICES SECTION ===== */
        .services {
            padding: 120px 0;
            position: relative;
        }

        .services::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 800px;
            height: 800px;
            background: radial-gradient(circle, var(--neon-blue-glow) 0%, transparent 70%);
            filter: blur(120px);
            opacity: 0.3;
        }

        .services-header {
            text-align: center;
            margin-bottom: 64px;
            position: relative;
            z-index: 1;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 24px;
            position: relative;
            z-index: 1;
        }

        .service-card {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: 20px;
            padding: 32px;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }

        .service-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: var(--gradient-blue);
            transform: scaleX(0);
            transform-origin: left;
            transition: var(--transition);
        }

        .service-card:hover {
            transform: translateY(-8px);
            border-color: rgba(0, 212, 255, 0.3);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }

        .service-card:hover::before {
            transform: scaleX(1);
        }

        .service-icon {
            width: 60px;
            height: 60px;
            background: rgba(0, 212, 255, 0.1);
            border-radius: 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 20px;
            font-size: 1.5rem;
            color: var(--neon-blue);
            transition: var(--transition);
        }

        .service-card:hover .service-icon {
            background: var(--gradient-blue);
            color: var(--bg-primary);
        }

        .service-card h3 {
            font-size: 1.25rem;
            font-weight: 600;
            margin-bottom: 12px;
        }

        .service-card p {
            color: var(--text-secondary);
            font-size: 0.95rem;
            line-height: 1.7;
        }

        /* ===== BONUS SECTION ===== */
        .bonus {
            padding: 100px 0;
        }

        .bonus-card {
            background: linear-gradient(135deg, var(--bg-card) 0%, var(--bg-secondary) 100%);
            border: 1px solid var(--border-color);
            border-radius: 24px;
            padding: 60px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .bonus-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: radial-gradient(circle at top right, var(--neon-orange-glow) 0%, transparent 50%);
            opacity: 0.5;
        }

        .bonus-content {
            position: relative;
            z-index: 1;
        }

        .bonus-icon {
            font-size: 4rem;
            color: var(--neon-orange);
            margin-bottom: 24px;
            display: inline-block;
            animation: bounce 2s ease-in-out infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .bonus-badge {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 8px 16px;
            background: rgba(255, 107, 53, 0.1);
            border: 1px solid rgba(255, 107, 53, 0.3);
            border-radius: 50px;
            font-size: 0.85rem;
            color: var(--neon-orange);
            margin-bottom: 20px;
        }

                .bonus-title {
            font-size: clamp(2rem, 4vw, 3rem);
            font-weight: 800;
            margin-bottom: 16px;
            line-height: 1.2;
        }

        .bonus-title .highlight-orange {
            background: var(--gradient-orange);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .bonus-description {
            color: var(--text-secondary);
            font-size: 1.1rem;
            max-width: 500px;
            margin: 0 auto 32px;
        }

        /* ===== ADVANTAGES SECTION ===== */
        .advantages {
            padding: 120px 0;
            background: var(--bg-secondary);
        }

        .advantages-grid {
            display: grid;
            grid-template-columns: repeat(5, 1fr);
            gap: 24px;
        }

        .advantage-card {
            text-align: center;
            padding: 32px 20px;
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: 16px;
            transition: var(--transition);
        }

        .advantage-card:hover {
            transform: translateY(-5px);
            border-color: var(--neon-blue);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .advantage-icon {
            width: 70px;
            height: 70px;
            background: rgba(0, 212, 255, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 1.8rem;
            color: var(--neon-blue);
            transition: var(--transition);
        }

        .advantage-card:hover .advantage-icon {
            background: var(--gradient-blue);
            color: var(--bg-primary);
        }

        .advantage-card h3 {
            font-size: 1rem;
            font-weight: 600;
            margin-bottom: 8px;
        }

        .advantage-card p {
            font-size: 0.85rem;
            color: var(--text-secondary);
        }

        /* ===== QUOTE SECTION ===== */
        .quote {
            padding: 100px 0;
            text-align: center;
            position: relative;
        }

        .quote::before {
            content: '"';
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 20rem;
            font-family: Georgia, serif;
            color: rgba(0, 212, 255, 0.05);
            line-height: 1;
        }

        .quote-content {
            position: relative;
            z-index: 1;
        }

        .quote blockquote {
            font-size: clamp(1.5rem, 3vw, 2.2rem);
            font-weight: 600;
            font-style: italic;
            max-width: 800px;
            margin: 0 auto 24px;
            line-height: 1.4;
        }

        .quote-author {
            display: inline-flex;
            align-items: center;
            gap: 12px;
            color: var(--text-secondary);
        }

        .quote-author::before {
            content: '';
            width: 40px;
            height: 2px;
            background: var(--neon-blue);
        }

        /* ===== TESTIMONIALS SECTION ===== */
        .testimonials {
            padding: 120px 0;
            background: var(--bg-secondary);
        }

        .testimonials-header {
            text-align: center;
            margin-bottom: 64px;
        }

        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 32px;
        }

        .testimonial-card {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: 20px;
            padding: 32px;
            transition: var(--transition);
            position: relative;
        }

        .testimonial-card:hover {
            transform: translateY(-5px);
            border-color: rgba(0, 212, 255, 0.3);
        }

        .testimonial-rating {
            display: flex;
            gap: 4px;
            margin-bottom: 16px;
        }

        .testimonial-rating i {
            color: #ffc107;
            font-size: 1.1rem;
        }

        .testimonial-text {
            font-size: 1rem;
            line-height: 1.8;
            color: var(--text-secondary);
            margin-bottom: 24px;
        }

        .testimonial-author {
            display: flex;
            align-items: center;
            gap: 16px;
        }

        .testimonial-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: var(--gradient-blue);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            font-size: 1.2rem;
            color: var(--bg-primary);
        }

        .testimonial-info h4 {
            font-size: 1rem;
            font-weight: 600;
            margin-bottom: 4px;
        }

        .testimonial-info p {
            font-size: 0.85rem;
            color: var(--text-secondary);
        }

        .testimonial-badge {
            position: absolute;
            top: 20px;
            right: 20px;
            padding: 6px 12px;
            background: rgba(0, 212, 255, 0.1);
            border-radius: 20px;
            font-size: 0.75rem;
            color: var(--neon-blue);
        }

        /* ===== CTA SECTION ===== */
        .cta {
            padding: 120px 0;
        }

        .cta-card {
            background: linear-gradient(135deg, var(--bg-card) 0%, var(--bg-secondary) 100%);
            border: 1px solid var(--border-color);
            border-radius: 24px;
            padding: 80px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .cta-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: radial-gradient(circle at center, var(--neon-blue-glow) 0%, transparent 60%);
            opacity: 0.3;
        }

        .cta-content {
            position: relative;
            z-index: 1;
        }

        .cta h2 {
            font-size: clamp(2rem, 4vw, 2.8rem);
            font-weight: 700;
            margin-bottom: 16px;
        }

        .cta p {
            color: var(--text-secondary);
            font-size: 1.1rem;
            max-width: 500px;
            margin: 0 auto 32px;
        }

        .cta-buttons {
            display: flex;
            justify-content: center;
            gap: 16px;
            flex-wrap: wrap;
        }

        /* ===== FOOTER ===== */
        footer {
            background: var(--bg-secondary);
            padding: 60px 0 30px;
            border-top: 1px solid var(--border-color);
        }

        .footer-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 24px;
        }

        .footer-brand {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .footer-brand .logo-icon {
            width: 36px;
            height: 36px;
            font-size: 1rem;
        }

        .footer-brand h3 {
            font-size: 1.2rem;
            font-weight: 700;
        }

        .footer-social {
            display: flex;
            gap: 16px;
        }

        .footer-social a {
            width: 44px;
            height: 44px;
            border-radius: 12px;
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text-secondary);
            font-size: 1.2rem;
            transition: var(--transition);
        }

        .footer-social a:hover {
            background: var(--gradient-blue);
            border-color: transparent;
            color: var(--bg-primary);
        }

        .footer-bottom {
            margin-top: 40px;
            padding-top: 24px;
            border-top: 1px solid var(--border-color);
            text-align: center;
        }

        .footer-bottom p {
            color: var(--text-secondary);
            font-size: 0.9rem;
        }

        /* ===== SCROLL ANIMATIONS ===== */
        .reveal {
            opacity: 0;
            transform: translateY(40px);
            transition: all 0.8s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* ===== MOBILE MENU ===== */
        .mobile-menu {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(10, 10, 15, 0.98);
            backdrop-filter: blur(20px);
            z-index: 999;
            padding: 100px 24px 40px;
            flex-direction: column;
            gap: 24px;
        }

        .mobile-menu.active {
            display: flex;
        }

        .mobile-menu a {
            font-size: 1.5rem;
            font-weight: 600;
            color: var(--text-primary);
            text-decoration: none;
            padding: 16px 0;
            border-bottom: 1px solid var(--border-color);
        }

        .mobile-menu .btn {
            margin-top: 24px;
            justify-content: center;
        }

        /* ===== RESPONSIVE ===== */
        @media (max-width: 1024px) {
            .hero-grid {
                grid-template-columns: 1fr;
                gap: 60px;
                text-align: center;
            }

            .hero-content {
                order: 1;
            }

            .hero-visual {
                order: 2;
            }

            .hero p {
                margin: 0 auto 32px;
            }

            .hero-buttons {
                justify-content: center;
            }

            .hero-stats {
                justify-content: center;
            }

            .hero-image-wrapper {
                max-width: 400px;
            }

            .services-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .advantages-grid {
                grid-template-columns: repeat(3, 1fr);
            }

            .testimonials-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .testimonials-grid .testimonial-card:last-child {
                grid-column: span 2;
                max-width: 50%;
                margin: 0 auto;
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .nav-cta {
                display: none;
            }

            .mobile-toggle {
                display: flex;
            }

            .hero {
                padding: 100px 0 60px;
                min-height: auto;
            }

            .hero h1 {
                font-size: 2.2rem;
            }

            .hero p {
                font-size: 1rem;
            }

            .hero-stats {
                flex-direction: column;
                gap: 24px;
            }

            .hero-image-wrapper {
                max-width: 300px;
            }

            .floating-elements {
                display: none;
            }

            .services-grid {
                grid-template-columns: 1fr;
            }

            .advantages-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 16px;
            }

            .advantage-card {
                padding: 24px 16px;
            }

            .advantage-icon {
                width: 60px;
                height: 60px;
                font-size: 1.5rem;
            }

            .bonus-card {
                padding: 40px 24px;
            }

            .bonus-icon {
                font-size: 3rem;
            }

            .testimonials-grid {
                grid-template-columns: 1fr;
            }

            .testimonials-grid .testimonial-card:last-child {
                grid-column: span 1;
                max-width: 100%;
            }

            .cta-card {
                padding: 50px 24px;
            }

            .footer-content {
                flex-direction: column;
                text-align: center;
            }

            .footer-brand {
                flex-direction: column;
            }
        }

        @media (max-width: 480px) {
            .hero-buttons {
                flex-direction: column;
            }

            .hero-buttons .btn {
                width: 100%;
                justify-content: center;
            }

            .advantages-grid {
                grid-template-columns: 1fr;
            }

            .cta-buttons {
                flex-direction: column;
            }

            .cta-buttons .btn {
                width: 100%;
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <!-- NAVIGATION -->
    <nav id="navbar">
        <div class="container nav-content">
            <a href="#" class="logo">
                <div class="logo-icon">
                    <i class="ri-global-line"></i>
                </div>
                <span>Novary Agency</span>
            </a>
            <ul class="nav-links">
                <li><a href="#services">Layanan</a></li>
                <li><a href="#advantages">Keunggulan</a></li>
                <li><a href="#testimonials">Testimoni</a></li>
                <li><a href="#contact">Kontak</a></li>
            </ul>
            <a href="https://wa.me/6281234567890" class="btn btn-primary nav-cta">
                <i class="ri-whatsapp-line"></i> Chat WhatsApp
            </a>
            <div class="mobile-toggle" id="mobileToggle">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <!-- MOBILE MENU -->
    <div class="mobile-menu" id="mobileMenu">
        <a href="#services" onclick="closeMobileMenu()">Layanan</a>
        <a href="#advantages" onclick="closeMobileMenu()">Keunggulan</a>
        <a href="#testimonials" onclick="closeMobileMenu()">Testimoni</a>
        <a href="#contact" onclick="closeMobileMenu()">Kontak</a>
        <a href="https://wa.me/6281234567890" class="btn btn-primary">
            <i class="ri-whatsapp-line"></i> Chat WhatsApp
        </a>
    </div>

    <!-- HERO SECTION -->
    <section class="hero">
        <div class="container">
            <div class="hero-grid">
                <div class="hero-content">
                    <div class="hero-badge">
                        <i class="ri-sparkling-line"></i>
                        Jasa Website Profesional
                    </div>
                    <h1>
                        Website Modern Untuk<br>
                        <span class="gradient-text">Bisnis & Personal Branding</span>
                    </h1>
                    <p>Jasa pembuatan website profesional dengan desain modern, responsif, dan performa cepat. Mulai dari 100K saja!</p>
                    <div class="hero-buttons">
                        <a href="https://wa.me/6281234567890" class="btn btn-primary">
                            <i class="ri-whatsapp-line"></i> Chat WhatsApp
                        </a>
                        <a href="#portfolio" class="btn btn-secondary">
                            <i class="ri-eye-line"></i> Lihat Portfolio
                        </a>
                    </div>
                    <div class="hero-stats">
                        <div class="stat">
                            <div class="stat-number">150+</div>
                            <div class="stat-label">Project Selesai</div>
                        </div>
                        <div class="stat">
                            <div class="stat-number">100%</div>
                            <div class="stat-label">Client Puas</div>
                        </div>
                        <div class="stat">
                            <div class="stat-number">24/7</div>
                            <div class="stat-label">Support</div>
                        </div>
                    </div>
                </div>
                <div class="hero-visual">
                    <div class="hero-image-wrapper">
                        <div class="floating-elements">
                            <div class="floating-card">
                                <i class="ri-rocket-line"></i>
                                <span>Loading Fast</span>
                            </div>
                            <div class="floating-card">
                                <i class="ri-smartphone-line"></i>
                                <span>Mobile Friendly</span>
                            </div>
                        </div>
                        <div class="hero-browser">
                            <div class="browser-header">
                                <div class="browser-dot red"></div>
                                <div class="browser-dot yellow"></div>
                                <div class="browser-dot green"></div>
                            </div>
                            <div class="browser-content">
                                <div class="browser-placeholder">
                                    <div class="placeholder-box hero-main"></div>
                                    <div class="placeholder-row">
                                        <div class="placeholder-box small"></div>
                                        <div class="placeholder-box small"></div>
                                    </div>
                                    <div class="placeholder-row">
                                        <div class="placeholder-box small"></div>
                                        <div class="placeholder-box small"></div>
                                        <div class="placeholder-box small"></div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- SERVICES SECTION -->
    <section class="services" id
