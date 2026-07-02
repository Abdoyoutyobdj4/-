<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ABDO DIGITAL HUB - خدمات رقمية بجودة عالية</title>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <style>
        :root {
            --primary: #0a0e1a;
            --secondary: #111827;
            --accent-blue: #3b82f6;
            --accent-cyan: #06b6d4;
            --accent-green: #10b981;
            --accent-yellow: #fbbf24;
            --text-light: #f3f4f6;
            --text-muted: #9ca3af;
            --glass: rgba(255, 255, 255, 0.05);
            --glass-border: rgba(255, 255, 255, 0.1);
        }
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            font-family: 'Tajawal', sans-serif;
            background: var(--primary);
            color: var(--text-light);
            overflow-x: hidden;
            line-height: 1.6;
        }
        .bg-animation {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            z-index: -1; overflow: hidden;
        }
        .bg-animation::before {
            content: ''; position: absolute; width: 600px; height: 600px;
            background: radial-gradient(circle, rgba(59, 130, 246, 0.15) 0%, transparent 70%);
            top: -200px; right: -200px; animation: float 8s ease-in-out infinite;
        }
        .bg-animation::after {
            content: ''; position: absolute; width: 500px; height: 500px;
            background: radial-gradient(circle, rgba(6, 182, 212, 0.1) 0%, transparent 70%);
            bottom: -150px; left: -150px; animation: float 10s ease-in-out infinite reverse;
        }
        @keyframes float {
            0%, 100% { transform: translate(0, 0) scale(1); }
            50% { transform: translate(30px, -30px) scale(1.1); }
        }
        .particle {
            position: fixed; width: 4px; height: 4px;
            background: var(--accent-cyan); border-radius: 50%; opacity: 0.3;
            animation: particle-float 15s linear infinite; z-index: -1;
        }
        @keyframes particle-float {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
            10% { opacity: 0.3; } 90% { opacity: 0.3; }
            100% { transform: translateY(-100vh) rotate(720deg); opacity: 0; }
        }
        header {
            position: fixed; top: 0; width: 100%; z-index: 1000;
            background: rgba(10, 14, 26, 0.9); backdrop-filter: blur(20px);
            border-bottom: 1px solid var(--glass-border); transition: all 0.3s ease;
        }
        header.scrolled {
            background: rgba(10, 14, 26, 0.98);
            box-shadow: 0 4px 30px rgba(0, 0, 0, 0.5);
        }
        .nav-container {
            max-width: 1400px; margin: 0 auto; padding: 1rem 2rem;
            display: flex; justify-content: space-between; align-items: center;
        }
        .logo { display: flex; align-items: center; gap: 12px; text-decoration: none; }
        .logo-icon {
            width: 50px; height: 50px;
            background: linear-gradient(135deg, var(--accent-blue), var(--accent-cyan));
            border-radius: 12px; display: flex; align-items: center; justify-content: center;
            font-size: 1.5rem; font-weight: 900; color: white; position: relative; overflow: hidden;
        }
        .logo-icon::after {
            content: ''; position: absolute; top: -50%; right: -50%;
            width: 100%; height: 100%; background: rgba(255,255,255,0.2);
            transform: rotate(45deg); animation: shine 3s infinite;
        }
        @keyframes shine {
            0% { transform: translateX(-100%) rotate(45deg); }
            100% { transform: translateX(200%) rotate(45deg); }
        }
        .logo-text { color: var(--text-light); }
        .logo-text h1 {
            font-size: 1.4rem; font-weight: 800;
            background: linear-gradient(135deg, var(--accent-blue), var(--accent-cyan));
            -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
        }
        .logo-text span { font-size: 0.75rem; color: var(--text-muted); display: block; margin-top: -2px; }
        .nav-links { display: flex; gap: 2rem; list-style: none; }
        .nav-links a {
            color: var(--text-muted); text-decoration: none; font-weight: 600; font-size: 0.95rem;
            transition: all 0.3s ease; position: relative;
        }
        .nav-links a:hover { color: var(--accent-cyan); }
        .nav-links a::after {
            content: ''; position: absolute; bottom: -5px; right: 0; width: 0; height: 2px;
            background: linear-gradient(90deg, var(--accent-blue), var(--accent-cyan));
            transition: width 0.3s ease;
        }
        .nav-links a:hover::after { width: 100%; }
        .mobile-menu-btn { display: none; background: none; border: none; color: var(--text-light); font-size: 1.5rem; cursor: pointer; }
        .hero {
            min-height: 100vh; display: flex; align-items: center; justify-content: center;
            padding: 8rem 2rem 4rem; position: relative; overflow: hidden;
        }
        .hero-content {
            max-width: 1400px; width: 100%; display: grid;
            grid-template-columns: 1fr 1fr; gap: 4rem; align-items: center;
        }
        .hero-text { z-index: 2; }
        .hero-badge {
            display: inline-flex; align-items: center; gap: 8px;
            background: var(--glass); border: 1px solid var(--glass-border);
            padding: 0.5rem 1.2rem; border-radius: 50px; font-size: 0.85rem;
            color: var(--accent-cyan); margin-bottom: 1.5rem; animation: fadeInUp 0.8s ease;
        }
        .hero-badge i { animation: pulse 2s infinite; }
        @keyframes pulse { 0%, 100% { opacity: 1; } 50% { opacity: 0.5; } }
        .hero h2 { font-size: 3.5rem; font-weight: 900; line-height: 1.2; margin-bottom: 1.5rem; animation: fadeInUp 0.8s ease 0.2s both; }
        .hero h2 .gradient-text {
            background: linear-gradient(135deg, var(--accent-blue), var(--accent-cyan), var(--accent-green));
            -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
        }
        .hero p { font-size: 1.15rem; color: var(--text-muted); margin-bottom: 2.5rem; max-width: 500px; animation: fadeInUp 0.8s ease 0.4s both; }
        .hero-buttons { display: flex; gap: 1rem; animation: fadeInUp 0.8s ease 0.6s both; }
        .btn {
            padding: 1rem 2.5rem; border-radius: 12px; font-weight: 700; font-size: 1rem;
            text-decoration: none; transition: all 0.3s ease; display: inline-flex;
            align-items: center; gap: 8px; cursor: pointer; border: none; font-family: 'Tajawal', sans-serif;
        }
        .btn-primary {
            background: linear-gradient(135deg, var(--accent-blue), var(--accent-cyan));
            color: white; box-shadow: 0 10px 30px rgba(59, 130, 246, 0.3);
        }
        .btn-primary:hover { transform: translateY(-3px); box-shadow: 0 15px 40px rgba(59, 130, 246, 0.4); }
        .btn-secondary {
            background: var(--glass); color: var(--text-light); border: 1px solid var(--glass-border);
        }
        .btn-secondary:hover { background: rgba(255, 255, 255, 0.1); transform: translateY(-3px); }
        .hero-stats { display: flex; gap: 2.5rem; margin-top: 3rem; animation: fadeInUp 0.8s ease 0.8s both; }
        .stat-item { text-align: center; }
        .stat-item h3 { font-size: 2rem; font-weight: 900; color: var(--accent-cyan); }
        .stat-item span { font-size: 0.85rem; color: var(--text-muted); }
        .hero-visual { position: relative; display: flex; justify-content: center; align-items: center; }
        .hero-card {
            background: var(--glass); backdrop-filter: blur(20px); border: 1px solid var(--glass-border);
            border-radius: 24px; padding: 2rem; width: 100%; max-width: 450px;
            position: relative; overflow: hidden; animation: float-card 6s ease-in-out infinite;
        }
        @keyframes float-card { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-20px); } }
        .hero-card::before {
            content: ''; position: absolute; top: -50%; right: -50%;
            width: 200%; height: 200%; background: radial-gradient(circle, rgba(59, 130, 246, 0.1) 0%, transparent 50%);
            animation: rotate 20s linear infinite;
        }
        @keyframes rotate { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }
        .hero-card-content { position: relative; z-index: 1; }
        .card-header { display: flex; align-items: center; gap: 1rem; margin-bottom: 1.5rem; }
        .card-icon {
            width: 60px; height: 60px; border-radius: 16px;
            display: flex; align-items: center; justify-content: center; font-size: 1.8rem;
        }
        .card-icon.netflix { background: linear-gradient(135deg, #e50914, #b20710); }
        .card-icon.chatgpt { background: linear-gradient(135deg, #10a37f, #0d8c6d); }
        .card-icon.canva { background: linear-gradient(135deg, #00c4cc, #7b2cbf); }
        .card-icon.iptv { background: linear-gradient(135deg, #3b82f6, #06b6d4); }
        .card-info h4 { font-size: 1.3rem; font-weight: 800; }
        .card-info span { color: var(--text-muted); font-size: 0.85rem; }
        .card-price { font-size: 2.5rem; font-weight: 900; color: var(--accent-yellow); margin: 1rem 0; }
        .card-price span { font-size: 1rem; color: var(--text-muted); font-weight: 400; }
        .card-features { list-style: none; margin-bottom: 1.5rem; }
        .card-features li { display: flex; align-items: center; gap: 8px; padding: 0.5rem 0; color: var(--text-muted); font-size: 0.9rem; }
        .card-features li i { color: var(--accent-green); font-size: 0.8rem; }
        .card-btn {
            width: 100%; padding: 1rem; border-radius: 12px; border: none;
            font-family: 'Tajawal', sans-serif; font-weight: 700; font-size: 1rem;
            cursor: pointer; transition: all 0.3s ease;
        }
        .card-btn.netflix { background: linear-gradient(135deg, #e50914, #b20710); color: white; }
        .card-btn.chatgpt { background: linear-gradient(135deg, #10a37f, #0d8c6d); color: white; }
        .card-btn.canva { background: linear-gradient(135deg, #00c4cc, #7b2cbf); color: white; }
        .card-btn.iptv { background: linear-gradient(135deg, #3b82f6, #06b6d4); color: white; }
        .card-btn:hover { transform: scale(1.02); box-shadow: 0 10px 30px rgba(0,0,0,0.3); }
        .card-slider { position: relative; height: 400px; }
        .slide-card { position: absolute; width: 100%; transition: all 0.6s ease; opacity: 0; transform: translateX(50px) scale(0.9); pointer-events: none; }
        .slide-card.active { opacity: 1; transform: translateX(0) scale(1); pointer-events: all; }
        .slide-dots { display: flex; justify-content: center; gap: 8px; margin-top: 1.5rem; }
        .dot { width: 10px; height: 10px; border-radius: 50%; background: var(--glass-border); cursor: pointer; transition: all 0.3s ease; }
        .dot.active { background: var(--accent-cyan); width: 30px; border-radius: 5px; }
        section { padding: 6rem 2rem; position: relative; }
        .section-header { text-align: center; margin-bottom: 4rem; }
        .section-header h2 { font-size: 2.5rem; font-weight: 900; margin-bottom: 1rem; }
        .section-header h2 .gradient-text {
            background: linear-gradient(135deg, var(--accent-blue), var(--accent-cyan));
            -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
        }
        .section-header p { color: var(--text-muted); font-size: 1.1rem; max-width: 600px; margin: 0 auto; }
        .section-line { width: 80px; height: 4px; background: linear-gradient(90deg, var(--accent-blue), var(--accent-cyan)); margin: 1.5rem auto 0; border-radius: 2px; }
        .services-grid {
            max-width: 1400px; margin: 0 auto; display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 2rem;
        }
        .service-card {
            background: var(--glass); backdrop-filter: blur(10px); border: 1px solid var(--glass-border);
            border-radius: 20px; padding: 2.5rem; transition: all 0.4s ease; position: relative; overflow: hidden;
        }
        .service-card::before {
            content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 4px;
            background: linear-gradient(90deg, var(--accent-blue), var(--accent-cyan));
            transform: scaleX(0); transition: transform 0.4s ease;
        }
        .service-card:hover::before { transform: scaleX(1); }
        .service-card:hover { transform: translateY(-10px); border-color: rgba(59, 130, 246, 0.3); box-shadow: 0 20px 50px rgba(0, 0, 0, 0.3); }
        .service-icon {
            width: 70px; height: 70px; border-radius: 18px;
            display: flex; align-items: center; justify-content: center;
            font-size: 2rem; margin-bottom: 1.5rem; position: relative;
        }
        .service-icon::after {
            content: ''; position: absolute; inset: -3px; border-radius: 20px; padding: 3px;
            background: linear-gradient(135deg, var(--accent-blue), var(--accent-cyan));
            -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            -webkit-mask-composite: xor; mask-composite: exclude; opacity: 0.5;
        }
        .service-card h3 { font-size: 1.4rem; font-weight: 800; margin-bottom: 0.8rem; }
        .service-card p { color: var(--text-muted); font-size: 0.95rem; margin-bottom: 1.5rem; }
        .service-price {
            display: inline-flex; align-items: baseline; gap: 4px;
            background: rgba(251, 191, 36, 0.1); padding: 0.5rem 1.2rem;
            border-radius: 50px; border: 1px solid rgba(251, 191, 36, 0.2);
        }
        .service-price .price { font-size: 1.8rem; font-weight: 900; color: var(--accent-yellow); }
        .service-price .currency { color: var(--text-muted); font-size: 0.9rem; }
        .service-features { list-style: none; margin: 1.5rem 0; }
        .service-features li { display: flex; align-items: center; gap: 10px; padding: 0.4rem 0; color: var(--text-muted); font-size: 0.9rem; }
        .service-features li i { color: var(--accent-green); font-size: 0.8rem; }
        .service-btn { width: 100%; padding: 1rem; border-radius: 12px; border: none; font-family: 'Tajawal', sans-serif; font-weight: 700; font-size: 1rem; cursor: pointer; transition: all 0.3s ease; margin-top: 1rem; }
        .pricing-grid {
            max-width: 1200px; margin: 0 auto; display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 2rem;
        }
        .pricing-card {
            background: var(--glass); backdrop-filter: blur(10px); border: 1px solid var(--glass-border);
            border-radius: 24px; padding: 2.5rem; text-align: center; transition: all 0.4s ease; position: relative;
        }
        .pricing-card.popular {
            border-color: var(--accent-yellow); transform: scale(1.05);
            box-shadow: 0 20px 50px rgba(251, 191, 36, 0.1);
        }
        .pricing-card.popular::before {
            content: 'الأكثر مبيعاً'; position: absolute; top: -12px; left: 50%; transform: translateX(-50%);
            background: linear-gradient(135deg, var(--accent-yellow), #f59e0b); color: var(--primary);
            padding: 0.3rem 1.5rem; border-radius: 50px; font-size: 0.8rem; font-weight: 800;
        }
        .pricing-card:hover { transform: translateY(-10px); border-color: rgba(59, 130, 246, 0.3); }
        .pricing-card.popular:hover { transform: translateY(-10px) scale(1.05); }
        .pricing-card .duration { font-size: 1.2rem; font-weight: 700; color: var(--text-light); margin-bottom: 0.5rem; }
        .pricing-card .price-tag { font-size: 3.5rem; font-weight: 900; color: var(--accent-yellow); margin: 1rem 0; }
        .pricing-card .price-tag span { font-size: 1rem; color: var(--text-muted); font-weight: 400; }
        .pricing-features { list-style: none; text-align: right; margin: 2rem 0; }
        .pricing-features li { padding: 0.7rem 0; border-bottom: 1px solid var(--glass-border); display: flex; align-items: center; gap: 10px; color: var(--text-muted); }
        .pricing-features li:last-child { border-bottom: none; }
        .pricing-features li i { color: var(--accent-green); }
        .devices-section { background: linear-gradient(180deg, var(--primary) 0%, rgba(17, 24, 39, 0.8) 100%); }
        .devices-grid {
            max-width: 1400px; margin: 0 auto; display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 2rem;
        }
        .device-card {
            background: var(--glass); border: 1px solid var(--glass-border);
            border-radius: 20px; padding: 2rem; text-align: center; transition: all 0.4s ease; cursor: pointer;
        }
        .device-card:hover { transform: translateY(-10px); border-color: var(--accent-blue); box-shadow: 0 20px 50px rgba(59, 130, 246, 0.2); }
        .device-card i { font-size: 3.5rem; margin-bottom: 1.5rem; background: linear-gradient(135deg, var(--accent-blue), var(--accent-cyan)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; }
        .device-card h3 { font-size: 1.3rem; font-weight: 800; margin-bottom: 0.5rem; }
        .device-card p { color: var(--text-muted); font-size: 0.9rem; }
        .trust-section { background: var(--secondary); }
        .trust-grid {
            max-width: 1200px; margin: 0 auto; display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 2rem;
        }
        .trust-card {
            background: var(--glass); border: 1px solid var(--glass-border);
            border-radius: 16px; padding: 2rem; text-align: center; transition: all 0.3s ease;
        }
        .trust-card:hover { border-color: var(--accent-green); transform: translateY(-5px); }
        .trust-card i { font-size: 2.5rem; color: var(--accent-green); margin-bottom: 1rem; }
        .trust-card h3 { font-size: 1.2rem; font-weight: 800; margin-bottom: 0.5rem; }
        .trust-card p { color: var(--text-muted); font-size: 0.9rem; }
        .payment-section { text-align: center; }
        .payment-grid {
            max-width: 800px; margin: 3rem auto 0; display: flex;
            justify-content: center; flex-wrap: wrap; gap: 1.5rem;
        }
        .payment-item {
            background: var(--glass); border: 1px solid var(--glass-border);
            border-radius: 16px; padding: 1.5rem 2rem; display: flex;
            align-items: center; gap: 1rem; transition: all 0.3s ease;
        }
        .payment-item:hover { border-color: var(--accent-cyan); transform: translateY(-5px); }
        .payment-item i { font-size: 2rem; color: var(--accent-cyan); }
        .payment-item span { font-weight: 700; font-size: 1rem; }
        .contact-section { background: linear-gradient(135deg, var(--secondary), var(--primary)); }
        .contact-grid {
            max-width: 1000px; margin: 0 auto; display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 2rem;
        }
        .contact-card {
            background: var(--glass); border: 1px solid var(--glass-border);
            border-radius: 20px; padding: 2.5rem; text-align: center;
            transition: all 0.3s ease; text-decoration: none; color: var(--text-light); display: block;
        }
        .contact-card:hover { transform: translateY(-5px); }
    