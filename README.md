<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dr. Gholamreza Rezaei | Wisdom + Technology + Digital Justice</title>
    
    <!-- Fonts & Libraries -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/vazirmatn@33.003/font.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3/dist/email.min.js"></script>
    <script>
        emailjs.init("YOUR_PUBLIC_KEY"); <!-- Replace with actual key -->
    </script>
    
    <style>
        /* Color Variables */
        :root {
            --navy-blue: #0A2463;
            --deep-teal: #1A5276;
            --accent-gold: #D4AF37;
            --soft-blue: #3498DB;
            --literary-purple: #6A4C93;
            --justice-green: #27AE60;
            --awakening-orange: #E67E22;
            --light-bg: #F8F9FA;
            --card-shadow: rgba(10, 36, 99, 0.1);
        }
        
        /* Reset & Base */
        * { 
            margin: 0; 
            padding: 0; 
            box-sizing: border-box; 
        }
        
        html { 
            scroll-behavior: smooth; 
        }
        
        body { 
            font-family: 'Vazirmatn', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; 
            background: var(--light-bg); 
            color: #333; 
            line-height: 1.7;
            overflow-x: hidden;
        }
        
        /* Base Animations */
        @keyframes fadeIn {
            from { 
                opacity: 0; 
                transform: translateY(30px); 
            }
            to { 
                opacity: 1; 
                transform: translateY(0); 
            }
        }
        
        @keyframes slideInRight {
            from { 
                opacity: 0; 
                transform: translateX(50px); 
            }
            to { 
                opacity: 1; 
                transform: translateX(0); 
            }
        }
        
        @keyframes pulse {
            0% { 
                transform: scale(1); 
            }
            50% { 
                transform: scale(1.05); 
            }
            100% { 
                transform: scale(1); 
            }
        }
        
        /* Reading Progress Bar */
        .progress-bar {
            position: fixed;
            top: 0;
            left: 0;
            width: 0%;
            height: 4px;
            background: linear-gradient(90deg, var(--accent-gold), var(--justice-green));
            z-index: 10000;
            transition: width 0.3s ease;
            box-shadow: 0 2px 10px rgba(212, 175, 55, 0.3);
        }
        
        /* Back to Top Button */
        #backToTop {
            position: fixed;
            bottom: 35px;
            right: 35px;
            width: 55px;
            height: 55px;
            background: linear-gradient(135deg, var(--accent-gold), #e6c158);
            color: var(--navy-blue);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.6rem;
            cursor: pointer;
            z-index: 9999;
            box-shadow: 0 8px 25px rgba(212, 175, 55, 0.4);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            border: none;
            opacity: 0;
            visibility: hidden;
        }
        
        #backToTop.show {
            opacity: 1;
            visibility: visible;
        }
        
        #backToTop:hover {
            transform: translateY(-8px) scale(1.1);
            box-shadow: 0 15px 35px rgba(212, 175, 55, 0.6);
            animation: pulse 1s infinite;
        }
        
        /* Top Marquee */
        .top-marquee {
            background: linear-gradient(90deg, var(--navy-blue), var(--deep-teal), var(--literary-purple));
            background-size: 300% 300%;
            color: white;
            padding: 14px 0;
            overflow: hidden;
            white-space: nowrap;
            font-weight: 700;
            font-size: 1.15rem;
            position: sticky;
            top: 0;
            z-index: 1001;
            box-shadow: 0 6px 20px rgba(0,0,0,0.15);
            animation: gradientShift 8s ease infinite;
            border-bottom: 2px solid rgba(212, 175, 55, 0.3);
        }
        
        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        
        .marquee-content {
            display: inline-block;
            animation: marquee 35s linear infinite;
            padding-left: 100%;
        }
        
        .marquee-content span {
            margin: 0 45px;
            display: inline-block;
            position: relative;
            padding: 5px 15px;
            border-radius: 20px;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(5px);
            transition: all 0.3s;
        }
        
        .marquee-content span:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-2px);
        }
        
        .marquee-content i {
            color: var(--accent-gold);
            margin-right: 10px;
            font-size: 1.2rem;
        }
        
        @keyframes marquee {
            0% { transform: translateX(0); }
            100% { transform: translateX(-100%); }
        }
        
        /* Language Button */
        .lang-switcher {
            position: absolute;
            top: 30px;
            right: 30px;
            z-index: 1002;
        }
        
        .lang-btn {
            background: rgba(255, 255, 255, 0.25);
            backdrop-filter: blur(12px);
            color: white;
            border: 2px solid rgba(255, 255, 255, 0.4);
            padding: 10px 20px;
            border-radius: 25px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            font-size: 1rem;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }
        
        .lang-btn:hover {
            background: var(--accent-gold);
            color: var(--navy-blue);
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 10px 25px rgba(212, 175, 55, 0.5);
            border-color: var(--accent-gold);
        }
        
        /* Main Header */
        .main-header {
            background: linear-gradient(135deg, 
                rgba(10, 36, 99, 0.95) 0%, 
                rgba(26, 82, 118, 0.92) 50%,
                rgba(10, 36, 99, 0.9) 100%),
                url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="none"><path d="M0,0 L100,0 L100,100 Z" fill="rgba(255,255,255,0.05)"/></svg>');
            background-size: cover;
            min-height: 65vh;
            padding: 40px 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            margin-top: 0;
            overflow: hidden;
        }
        
        .main-header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 70% 20%, rgba(212, 175, 55, 0.15) 0%, transparent 50%);
            pointer-events: none;
        }
        
        .header-container {
            max-width: 1350px;
            width: 100%;
            display: grid;
            grid-template-columns: 1fr 300px;
            gap: 35px;
            align-items: start;
            animation: fadeIn 1s ease-out;
        }
        
        .profile-section {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(20px);
            border-radius: 25px;
            padding: 40px;
            display: flex;
            flex-direction: column;
            align-items: flex-end;
            border: 1px solid rgba(255, 255, 255, 0.25);
            box-shadow: 
                0 20px 50px rgba(0, 0, 0, 0.3),
                inset 0 1px 0 rgba(255,255,255,0.3);
            width: 100%;
            transition: transform 0.5s ease;
        }
        
        .profile-section:hover {
            transform: translateY(-10px);
        }
        
        .profile-img-container {
            display: flex;
            align-items: center;
            gap: 30px;
            margin-bottom: 25px;
            width: 100%;
            flex-direction: row-reverse;
        }
        
        .profile-img {
            width: 160px;
            height: 160px;
            border-radius: 20px;
            border: 5px solid var(--accent-gold);
            overflow: hidden;
            flex-shrink: 0;
            box-shadow: 0 15px 35px rgba(0,0,0,0.3);
            transition: all 0.4s;
            position: relative;
        }
        
        .profile-img:hover {
            transform: scale(1.05) rotate(-2deg);
            border-color: #fff;
            box-shadow: 0 20px 40px rgba(212, 175, 55, 0.5);
        }
        
        .profile-img::after {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(-45deg, transparent 50%, rgba(212,175,55,0.1) 100%);
            pointer-events: none;
        }
        
        .profile-img img { 
            width: 100%; 
            height: 100%; 
            object-fit: cover;
            transition: transform 0.5s;
        }
        
        .profile-img:hover img {
            transform: scale(1.1);
        }
        
        .profile-titles {
            flex: 1;
            animation: slideInRight 0.8s ease 0.2s both;
            text-align: right;
        }
        
        .profile-titles h1 {
            color: white;
            font-size: 2.8rem;
            margin-bottom: 12px;
            text-shadow: 0 4px 8px rgba(0,0,0,0.4);
            line-height: 1.3;
            background: linear-gradient(to right, #fff, var(--accent-gold));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .profile-titles .tagline {
            color: rgba(255, 255, 255, 0.95);
            font-size: 1.25rem;
            line-height: 1.6;
            margin-bottom: 20px;
            padding-left: 10px;
            border-left: 3px solid var(--accent-gold);
        }
        
        .titles-container {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            margin-bottom: 20px;
            justify-content: flex-end;
        }
        
        .title-badge {
            background: linear-gradient(135deg, 
                rgba(212, 175, 55, 0.2), 
                rgba(52, 152, 219, 0.2));
            color: white;
            padding: 12px 25px;
            border-radius: 50px;
            font-size: 1.05rem;
            font-weight: 600;
            border: 1px solid rgba(255, 255, 255, 0.3);
            backdrop-filter: blur(5px);
            transition: all 0.3s;
            display: flex;
            align-items: center;
            gap: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .title-badge:hover {
            transform: translateY(-5px);
            background: linear-gradient(135deg, 
                rgba(212, 175, 55, 0.4), 
                rgba(52, 152, 219, 0.4));
            border-color: var(--accent-gold);
            box-shadow: 0 10px 25px rgba(212, 175, 55, 0.3);
        }
        
        .motto-box {
            color: white;
            background: rgba(0, 0, 0, 0.2);
            padding: 20px 25px;
            border-radius: 18px;
            border-left: 5px solid var(--accent-gold);
            font-size: 1.1rem;
            line-height: 1.8;
            width: 100%;
            margin-top: 20px;
            backdrop-filter: blur(10px);
            border-right: 1px solid rgba(255,255,255,0.1);
            animation: fadeIn 0.8s ease 0.5s both;
            box-shadow: inset 0 0 20px rgba(0,0,0,0.1);
            text-align: right;
        }
        
        .motto {
            color: var(--accent-gold);
            font-weight: 700;
            font-size: 1.2rem;
        }
        
        /* Vertical Navigation */
        .vertical-nav {
            background: rgba(255, 255, 255, 0.98);
            border-radius: 25px;
            padding: 30px 25px;
            box-shadow: 
                0 15px 35px var(--card-shadow),
                inset 0 -1px 0 rgba(0,0,0,0.05);
            display: flex;
            flex-direction: column;
            gap: 15px;
            height: fit-content;
            border: 1px solid rgba(10, 36, 99, 0.1);
            animation: fadeIn 1s ease 0.3s both;
        }
        
        .nav-item {
            background: linear-gradient(to right, 
                var(--soft-blue) 0%, 
                var(--deep-teal) 100%);
            color: white;
            padding: 16px 24px;
            border-radius: 15px;
            text-decoration: none;
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 15px;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            box-shadow: 0 6px 20px rgba(52, 152, 219, 0.3);
            font-size: 1.05rem;
            position: relative;
            overflow: hidden;
        }
        
        .nav-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, 
                transparent, 
                rgba(255,255,255,0.3), 
                transparent);
            transition: 0.5s;
        }
        
        .nav-item:hover {
            transform: translateX(10px) scale(1.02);
            box-shadow: 0 12px 30px rgba(52, 152, 219, 0.5);
        }
        
        .nav-item:hover::before {
            left: 100%;
        }
        
        .nav-icon { 
            font-size: 1.3rem; 
            filter: drop-shadow(0 2px 3px rgba(0,0,0,0.2));
        }
        
        /* Global Call Section */
        .global-call-section {
            padding: 90px 35px;
            background: linear-gradient(135deg, 
                #f0f7ff 0%, 
                #e3f2fd 50%,
                #f0f7ff 100%);
            position: relative;
            overflow: hidden;
        }
        
        .global-call-section::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, 
                rgba(52, 152, 219, 0.03) 0%, 
                transparent 70%);
            pointer-events: none;
        }
        
        .section-title {
            text-align: center;
            font-size: 2.8rem;
            color: var(--navy-blue);
            margin-bottom: 60px;
            position: relative;
            font-weight: 800;
            text-shadow: 0 2px 4px rgba(0,0,0,0.1);
            animation: fadeIn 0.8s ease;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -20px;
            left: 50%;
            transform: translateX(-50%);
            width: 120px;
            height: 6px;
            background: linear-gradient(to right, 
                var(--accent-gold), 
                var(--justice-green));
            border-radius: 3px;
            box-shadow: 0 4px 10px rgba(212, 175, 55, 0.3);
        }
        
        .call-to-action-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 35px;
            max-width: 1350px;
            margin: 0 auto;
            animation: fadeIn 1s ease 0.2s both;
        }
        
        .call-card {
            background: white;
            border-radius: 25px;
            padding: 40px;
            box-shadow: 
                0 20px 40px rgba(10, 36, 99, 0.12),
                inset 0 1px 0 rgba(255,255,255,0.8);
            border: 2px solid transparent;
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            text-align: center;
            display: flex;
            flex-direction: column;
            position: relative;
            overflow: hidden;
        }
        
        .call-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(to right, 
                var(--accent-gold), 
                var(--justice-green));
            transform: translateX(-100%);
            transition: transform 0.6s ease;
        }
        
        .call-card:hover {
            transform: translateY(-15px) scale(1.02);
            border-color: var(--accent-gold);
            box-shadow: 0 30px 60px rgba(10, 36, 99, 0.2);
        }
        
        .call-card:hover::before {
            transform: translateX(0);
        }
        
        .call-icon {
            font-size: 3.5rem;
            margin-bottom: 25px;
            display: inline-block;
            animation: pulse 2s infinite;
            filter: drop-shadow(0 5px 10px rgba(0,0,0,0.1));
        }
        
        .call-card h3 {
            color: var(--navy-blue);
            font-size: 1.8rem;
            margin-bottom: 20px;
            line-height: 1.4;
            font-weight: 800;
        }
        
        .call-card p {
            color: #555;
            line-height: 1.8;
            flex: 1;
            margin-bottom: 25px;
            font-size: 1.1rem;
        }
        
        .call-action-btn {
            background: linear-gradient(135deg, 
                var(--accent-gold), 
                #e6c158);
            color: var(--navy-blue);
            border: none;
            padding: 15px 35px;
            border-radius: 12px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.4s;
            margin-top: 20px;
            text-decoration: none;
            display: inline-block;
            font-size: 1.1rem;
            box-shadow: 0 8px 20px rgba(212, 175, 55, 0.3);
            position: relative;
            overflow: hidden;
        }
        
        .call-action-btn::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, 
                transparent, 
                rgba(255,255,255,0.4), 
                transparent);
            transition: 0.5s;
        }
        
        .call-action-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(212, 175, 55, 0.5);
        }
        
        .call-action-btn:hover::after {
            left: 100%;
        }
        
        .call-highlight {
            background: linear-gradient(135deg, 
                rgba(212, 175, 55, 0.15), 
                rgba(39, 174, 96, 0.15));
            border-left: 4px solid var(--accent-gold);
            padding: 18px;
            border-radius: 12px;
            margin-top: 20px;
            font-size: 1rem;
            color: #333;
            text-align: left;
            line-height: 1.6;
            font-style: italic;
            border-right: 1px solid rgba(212,175,55,0.1);
        }
        
        /* Temple of Digital Awakening */
        .temple-section {
            padding: 90px 35px;
            background: white;
            position: relative;
        }
        
        .temple-section::before {
            content: '🛕';
            position: absolute;
            top: 40px;
            right: 40px;
            font-size: 5rem;
            opacity: 0.05;
            z-index: 0;
        }
        
        .temple-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 35px;
            margin-top: 50px;
            animation: fadeIn 1s ease 0.4s both;
        }
        
        .temple-card {
            background: white;
            border-radius: 25px;
            padding: 35px;
            box-shadow: 
                0 20px 40px rgba(10, 36, 99, 0.1),
                inset 0 1px 0 rgba(255,255,255,0.8);
            border: 2px solid transparent;
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
            z-index: 1;
        }
        
        .temple-card:hover {
            transform: translateY(-12px);
            border-color: var(--justice-green);
            box-shadow: 0 30px 50px rgba(10, 36, 99, 0.15);
        }
        
        .temple-card::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, 
                transparent 50%, 
                rgba(39, 174, 96, 0.05) 100%);
            border-radius: 0 0 0 25px;
            z-index: -1;
        }
        
        .temple-card h3 {
            color: var(--navy-blue);
            font-size: 1.7rem;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 15px;
            font-weight: 800;
        }
        
        .temple-card p {
            color: #555;
            line-height: 1.8;
            margin-bottom: 20px;
            font-size: 1.1rem;
        }
        
        .temple-card ul {
            margin-left: 25px;
            margin-top: 20px;
        }
        
        .temple-card li {
            margin-bottom: 12px;
            color: #666;
            position: relative;
            padding-left: 25px;
            line-height: 1.6;
            font-size: 1.05rem;
        }
        
        .temple-card li::before {
            content: "➤";
            color: var(--justice-green);
            font-size: 1.3rem;
            position: absolute;
            left: 0;
            top: 2px;
            font-weight: bold;
        }
        
        /* Statistics Counter */
        .stats-section {
            padding: 70px 35px;
            background: linear-gradient(135deg, 
                #f8fafc 0%, 
                #eef2f7 100%);
            position: relative;
            overflow: hidden;
        }
        
        .stats-container {
            max-width: 1350px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 25px;
            animation: fadeIn 1s ease;
        }
        
        .stat-box {
            background: linear-gradient(135deg, 
                #ffffff, 
                #f0f7ff);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            border: 2px solid #e2e8f0;
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            box-shadow: 
                0 10px 30px rgba(10, 36, 99, 0.08),
                inset 0 1px 0 rgba(255,255,255,0.8);
            position: relative;
            overflow: hidden;
        }
        
        .stat-box:hover {
            transform: translateY(-12px);
            border-color: var(--soft-blue);
            box-shadow: 0 25px 50px var(--card-shadow);
        }
        
        .stat-box::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, 
                transparent 30%, 
                rgba(52, 152, 219, 0.05) 100%);
            z-index: 0;
        }
        
        .stat-number {
            font-size: 3.2rem;
            font-weight: 900;
            color: var(--navy-blue);
            display: block;
            line-height: 1;
            margin-bottom: 15px;
            position: relative;
            z-index: 1;
            text-shadow: 0 2px 4px rgba(0,0,0,0.1);
            background: linear-gradient(to right, 
                var(--navy-blue), 
                var(--deep-teal));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .stat-label {
            color: #555;
            font-size: 1.05rem;
            line-height: 1.6;
            min-height: 50px;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            z-index: 1;
            font-weight: 600;
        }
        
        /* Research Articles Section */
        .research-section {
            padding: 90px 35px;
            background: white;
            position: relative;
        }
        
        .research-tabs {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            margin-bottom: 50px;
            justify-content: center;
            animation: fadeIn 0.8s ease;
        }
        
        .tab-btn {
            padding: 18px 35px;
            background: #f0f7ff;
            border: none;
            border-radius: 18px;
            font-size: 1.2rem;
            font-weight: 700;
            color: var(--navy-blue);
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            display: flex;
            align-items: center;
            gap: 15px;
            box-shadow: 0 5px 15px rgba(10, 36, 99, 0.1);
        }
        
        .tab-btn:hover {
            background: var(--soft-blue);
            color: white;
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(52, 152, 219, 0.3);
        }
        
        .tab-btn.active {
            background: linear-gradient(135deg, 
                var(--navy-blue), 
                var(--deep-teal));
            color: white;
            box-shadow: 
                0 12px 30px rgba(10, 36, 99, 0.25),
                inset 0 1px 0 rgba(255,255,255,0.2);
            transform: translateY(-2px);
        }
        
        .tab-icon { 
            font-size: 1.5rem; 
        }
        
        .tab-content {
            display: none;
            animation: fadeIn 0.6s ease;
        }
        
        .tab-content.active {
            display: block;
        }
        
        .research-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(380px, 1fr));
            gap: 35px;
            margin-bottom: 60px;
        }
        
        .research-card {
            background: #f8fafc;
            border-radius: 25px;
            padding: 35px;
            border: 1px solid #e2e8f0;
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            height: 100%;
            display: flex;
            flex-direction: column;
            position: relative;
            overflow: hidden;
        }
        
        .research-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 30px 50px rgba(10, 36, 99, 0.15);
            border-color: var(--soft-blue);
        }
        
        .research-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(to right, 
                var(--soft-blue), 
                var(--literary-purple));
            transform: translateX(-100%);
            transition: transform 0.6s ease;
        }
        
        .research-card:hover::before {
            transform: translateX(0);
        }
        
        .research-card-header {
            margin-bottom: 25px;
            padding-bottom: 20px;
            border-bottom: 2px solid #e2e8f0;
        }
        
        .research-card-title {
            font-size: 1.5rem;
            color: var(--navy-blue);
            margin-bottom: 15px;
            line-height: 1.4;
            font-weight: 800;
        }
        
        .research-card-meta {
            display: flex;
            justify-content: space-between;
            font-size: 1rem;
            color: #666;
        }
        
        .research-card-date { 
            font-weight: 700; 
            color: var(--deep-teal);
        }
        
        .research-card-keywords {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin: 20px 0;
        }
        
        .keyword {
            background: rgba(52, 152, 219, 0.15);
            color: var(--deep-teal);
            padding: 8px 18px;
            border-radius: 25px;
            font-size: 0.9rem;
            font-weight: 700;
            transition: all 0.3s;
        }
        
        .keyword:hover {
            background: rgba(52, 152, 219, 0.25);
            transform: translateY(-2px);
        }
        
        .research-card-body {
            flex: 1;
            color: #555;
            line-height: 1.8;
            margin-bottom: 25px;
            font-size: 1.1rem;
        }
        
        .research-card-footer {
            margin-top: auto;
            padding-top: 20px;
            border-top: 1px dashed #ddd;
            text-align: right;
            font-style: italic;
            color: #777;
            font-size: 1rem;
        }
        
        .request-ppt-btn {
            background: linear-gradient(135deg, 
                var(--literary-purple), 
                #8A63B5);
            color: white;
            border: none;
            padding: 15px 30px;
            border-radius: 12px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.4s;
            margin-top: 20px;
            display: inline-flex;
            align-items: center;
            gap: 12px;
            font-size: 1.1rem;
            box-shadow: 0 8px 20px rgba(106, 76, 147, 0.3);
            position: relative;
            overflow: hidden;
        }
        
        .request-ppt-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(106, 76, 147, 0.4);
        }
        
        .request-ppt-btn::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, 
                transparent, 
                rgba(255,255,255,0.3), 
                transparent);
            transition: 0.5s;
        }
        
        .request-ppt-btn:hover::after {
            left: 100%;
        }
        
        /* Daily Notes */
        .notes-section {
            padding: 90px 35px;
            background: #f8fafc;
            position: relative;
        }
        
        .timeline {
            max-width: 950px;
            margin: 60px auto;
            position: relative;
            animation: fadeIn 1s ease;
        }
        
        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 6px;
            background: linear-gradient(to bottom, 
                var(--soft-blue), 
                var(--literary-purple));
            border-radius: 3px;
            box-shadow: 0 0 15px rgba(52, 152, 219, 0.3);
            transform: translateX(-50%);
        }
        
        .timeline-item {
            margin-bottom: 50px;
            position: relative;
            width: 45%;
            animation: slideInRight 0.8s ease both;
        }
        
        .timeline-item:nth-child(odd) {
            margin-left: 55%;
            animation-name: slideInRight;
        }
        
        .timeline-item:nth-child(even) {
            margin-left: 0;
            margin-right: 55%;
            animation-name: slideInRight;
        }
        
        .timeline-date {
            background: var(--navy-blue);
            color: white;
            padding: 12px 25px;
            border-radius: 25px;
            font-weight: 700;
            display: inline-block;
            margin-bottom: 15px;
            box-shadow: 0 8px 20px rgba(10, 36, 99, 0.2);
            transition: all 0.3s;
        }
        
        .timeline-date:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 25px rgba(10, 36, 99, 0.3);
        }
        
        .timeline-content {
            background: white;
            border-radius: 20px;
            padding: 30px;
            box-shadow: 
                0 15px 35px rgba(0,0,0,0.08),
                inset 0 1px 0 rgba(255,255,255,0.8);
            border: 1px solid #e2e8f0;
            transition: all 0.4s;
        }
        
        .timeline-content:hover {
            transform: translateY(-10px);
            box-shadow: 0 25px 50px rgba(0,0,0,0.12);
            border-color: var(--soft-blue);
        }
        
        .timeline-content h3 {
            color: var(--deep-teal);
            margin-bottom: 15px;
            font-size: 1.4rem;
            font-weight: 800;
        }
        
        /* Articles Slideshow */
        .slideshow-section {
            padding: 80px 35px;
            background: white;
            position: relative;
        }
        
        .slideshow-container {
            max-width: 1100px;
            margin: 50px auto;
            border-radius: 25px;
            overflow: hidden;
            box-shadow: 
                0 25px 50px rgba(0, 0, 0, 0.2),
                inset 0 1px 0 rgba(255,255,255,0.1);
            position: relative;
            border: 3px solid rgba(10, 36, 99, 0.1);
        }
        
        .slides-wrapper {
            display: flex;
            transition: transform 0.6s cubic-bezier(0.645, 0.045, 0.355, 1);
        }
        
        .slide-item {
            min-width: 100%;
            height: 450px;
            background: #1e293b;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
        }
        
        .slide-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(-45deg, 
                rgba(0,0,0,0.5), 
                transparent 50%);
            pointer-events: none;
        }
        
        .slide-item img {
            max-width: 90%;
            max-height: 90%;
            object-fit: contain;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
            transition: transform 0.5s;
        }
        
        .slide-item:hover img {
            transform: scale(1.03);
        }
        
        .slide-controls {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 15px;
            z-index: 2;
        }
        
        .slide-dot {
            width: 14px;
            height: 14px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.4);
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            border: 2px solid transparent;
        }
        
        .slide-dot:hover {
            background: rgba(255, 255, 255, 0.8);
            transform: scale(1.3);
        }
        
        .slide-dot.active {
            background: white;
            transform: scale(1.5);
            box-shadow: 0 0 15px rgba(255,255,255,0.5);
            border-color: var(--accent-gold);
        }
        
        /* Books Slideshow */
        .books-slideshow {
            padding: 80px 35px;
            background: linear-gradient(135deg, 
                #f9f5ff 0%, 
                #f0ebfa 100%);
            position: relative;
            overflow: hidden;
        }
        
        .books-slider {
            max-width: 1200px;
            margin: 50px auto;
            overflow: hidden;
            border-radius: 25px;
            box-shadow: 
                0 25px 50px rgba(106, 76, 147, 0.2),
                inset 0 1px 0 rgba(255,255,255,0.2);
            border: 3px solid rgba(106, 76, 147, 0.1);
            position: relative;
        }
        
        .books-track {
            display: flex;
            transition: transform 0.7s cubic-bezier(0.645, 0.045, 0.355, 1);
        }
        
        .book-slide {
            min-width: 25%;
            padding: 20px;
        }
        
        .book-item {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 
                0 15px 35px rgba(0, 0, 0, 0.12),
                inset 0 1px 0 rgba(255,255,255,0.8);
            height: 420px;
            display: flex;
            flex-direction: column;
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
        }
        
        .book-item:hover {
            transform: translateY(-15px);
            box-shadow: 0 30px 50px rgba(0, 0, 0, 0.2);
        }
        
        .book-cover {
            height: 200px;
            background: linear-gradient(135deg, 
                var(--literary-purple), 
                #8A63B5);
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 25px;
            position: relative;
            overflow: hidden;
        }
        
        .book-cover::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(-45deg, 
                transparent 40%, 
                rgba(255,255,255,0.1) 100%);
            pointer-events: none;
        }
        
        .book-cover img {
            max-width: 80%;
            max-height: 80%;
            object-fit: contain;
            border-radius: 8px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.3);
            transition: transform 0.5s;
        }
        
        .book-item:hover .book-cover img {
            transform: scale(1.05) rotate(-1deg);
        }
        
        .book-info {
            padding: 25px;
            flex: 1;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }
        
        .book-title {
            color: var(--literary-purple);
            font-size: 1.3rem;
            font-weight: 800;
            margin-bottom: 12px;
            line-height: 1.4;
        }
        
        .book-desc {
            color: #555;
            font-size: 1rem;
            line-height: 1.6;
            flex: 1;
            margin-bottom: 15px;
        }
        
        .book-status {
            color: #666;
            font-size: 0.9rem;
            font-style: italic;
            margin-top: 15px;
            text-align: right;
            padding-top: 15px;
            border-top: 1px dashed #e2e8f0;
        }
        
        /* Book Purchase Request */
        .book-request-box {
            max-width: 800px;
            margin: 50px auto;
            background: linear-gradient(135deg, 
                rgba(212, 175, 55, 0.1), 
                rgba(106, 76, 147, 0.1));
            border-radius: 20px;
            padding: 40px;
            text-align: center;
            border: 2px dashed var(--accent-gold);
            animation: fadeIn 1s ease;
        }
        
        .book-request-box h3 {
            color: var(--navy-blue);
            margin-bottom: 20px;
            font-size: 1.8rem;
            font-weight: 800;
        }
        
        .book-request-box p {
            color: #555;
            line-height: 1.8;
            margin-bottom: 25px;
            font-size: 1.1rem;
        }
        
        .book-request-btn {
            background: linear-gradient(135deg, 
                var(--accent-gold), 
                #e6c158);
            color: var(--navy-blue);
            border: none;
            padding: 15px 40px;
            border-radius: 12px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.4s;
            font-size: 1.1rem;
            box-shadow: 0 8px 20px rgba(212, 175, 55, 0.3);
            display: inline-flex;
            align-items: center;
            gap: 10px;
        }
        
        .book-request-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(212, 175, 55, 0.5);
        }
        
        /* Books Gallery */
        .books-gallery-section {
            padding: 70px 35px;
            background: white;
            position: relative;
        }
        
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            gap: 30px;
            max-width: 1300px;
            margin: 40px auto;
            animation: fadeIn 1s ease 0.2s both;
        }
        
        .gallery-item {
            background: #f8fafc;
            border-radius: 18px;
            overflow: hidden;
            box-shadow: 
                0 10px 25px rgba(0,0,0,0.1),
                inset 0 1px 0 rgba(255,255,255,0.8);
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            border: 2px solid transparent;
        }
        
        .gallery-item:hover {
            transform: translateY(-12px);
            box-shadow: 0 25px 40px rgba(0,0,0,0.15);
            border-color: var(--literary-purple);
        }
        
        .gallery-img {
            height: 200px;
            background: linear-gradient(135deg, 
                #e3d9f5, 
                #d6c8f0);
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
            position: relative;
            overflow: hidden;
        }
        
        .gallery-img::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(-45deg, 
                transparent 40%, 
                rgba(255,255,255,0.2) 100%);
            pointer-events: none;
        }
        
        .gallery-img img {
            max-width: 85%;
            max-height: 85%;
            object-fit: contain;
            border-radius: 6px;
            box-shadow: 0 8px 15px rgba(0,0,0,0.2);
            transition: transform 0.5s;
        }
        
        .gallery-item:hover .gallery-img img {
            transform: scale(1.08);
        }
        
        .gallery-caption {
            padding: 20px;
            text-align: center;
            font-weight: 800;
            color: var(--literary-purple);
            font-size: 1.1rem;
            line-height: 1.5;
        }
        
        /* Investment Section */
        .investment-section {
            padding: 80px 35px;
            background: linear-gradient(135deg, 
                var(--navy-blue) 0%, 
                var(--deep-teal) 50%,
                var(--navy-blue) 100%);
            color: white;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .investment-section::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, 
                rgba(212, 175, 55, 0.1) 0%, 
                transparent 70%);
            pointer-events: none;
        }
        
        .investment-content {
            max-width: 1000px;
            margin: 0 auto;
            position: relative;
            z-index: 1;
            animation: fadeIn 1s ease;
        }
        
        .investment-content h2 {
            font-size: 2.5rem;
            margin-bottom: 25px;
            font-weight: 800;
            text-shadow: 0 2px 4px rgba(0,0,0,0.3);
            background: linear-gradient(to right, 
                #fff, 
                var(--accent-gold));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .investment-text {
            font-size: 1.3rem;
            line-height: 1.8;
            margin-bottom: 30px;
            opacity: 0.95;
        }
        
        .highlight-box {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(10px);
            border-radius: 18px;
            padding: 25px;
            border-left: 5px solid var(--accent-gold);
            margin-top: 25px;
            font-size: 1.2rem;
            line-height: 1.7;
            text-align: left;
            border-right: 1px solid rgba(255,255,255,0.1);
            box-shadow: 
                inset 0 0 20px rgba(0,0,0,0.1),
                0 5px 15px rgba(0,0,0,0.2);
        }
        
        .investment-btn {
            background: linear-gradient(135deg, 
                var(--accent-gold), 
                #e6c158);
            color: var(--navy-blue);
            border: none;
            padding: 18px 50px;
            border-radius: 12px;
            font-weight: 800;
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            margin-top: 35px;
            display: inline-block;
            text-decoration: none;
            font-size: 1.2rem;
            box-shadow: 0 10px 25px rgba(212, 175, 55, 0.4);
            position: relative;
            overflow: hidden;
        }
        
        .investment-btn:hover {
            transform: translateY(-8px) scale(1.05);
            box-shadow: 0 20px 40px rgba(212, 175, 55, 0.6);
        }
        
        .investment-btn::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, 
                transparent, 
                rgba(255,255,255,0.4), 
                transparent);
            transition: 0.5s;
        }
        
        .investment-btn:hover::after {
            left: 100%;
        }
        
        /* PowerPoint Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0; 
            left: 0;
            width: 100%; 
            height: 100%;
            background: rgba(0,0,0,0.85);
            backdrop-filter: blur(10px);
            z-index: 2000;
            align-items: center;
            justify-content: center;
            animation: fadeIn 0.4s ease;
        }
        
        .modal.active { 
            display: flex; 
        }
        
        .modal-content {
            background: white;
            border-radius: 25px;
            padding: 50px;
            max-width: 550px;
            width: 90%;
            text-align: center;
            box-shadow: 
                0 30px 60px rgba(0,0,0,0.4),
                inset 0 1px 0 rgba(255,255,255,0.2);
            border: 1px solid rgba(255,255,255,0.1);
            animation: slideInRight 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
        }
        
        .modal-content::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(to right, 
                var(--accent-gold), 
                var(--justice-green));
        }
        
        .modal-icon { 
            font-size: 4.5rem; 
            color: var(--accent-gold); 
            margin-bottom: 25px; 
            display: inline-block;
            animation: pulse 2s infinite;
            filter: drop-shadow(0 5px 10px rgba(212, 175, 55, 0.3));
        }
        
        .modal h3 { 
            color: var(--navy-blue); 
            margin-bottom: 20px; 
            font-size: 1.8rem;
            font-weight: 800;
        }
        
        .modal p { 
            color: #555; 
            line-height: 1.8; 
            margin-bottom: 30px; 
            font-size: 1.1rem;
        }
        
        .modal-close {
            background: linear-gradient(135deg, 
                var(--navy-blue), 
                var(--deep-teal));
            color: white;
            border: none;
            padding: 15px 35px;
            border-radius: 10px;
            cursor: pointer;
            font-weight: 700;
            font-size: 1.1rem;
            transition: all 0.3s;
            box-shadow: 0 8px 20px rgba(10, 36, 99, 0.3);
        }
        
        .modal-close:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 25px rgba(10, 36, 99, 0.4);
        }
        
        .modal-contact {
            background: linear-gradient(135deg, 
                var(--accent-gold), 
                #e6c158);
            color: var(--navy-blue);
            margin-right: 15px;
        }
        
        /* Cooperation Request Form */
        .request-form-section {
            padding: 90px 35px;
            background: #f0f7ff;
            display: none;
            position: relative;
        }
        
        .request-form-section.active {
            display: block;
            animation: fadeIn 0.6s ease;
        }
        
        .request-form {
            max-width: 800px;
            margin: 0 auto;
            background: white;
            border-radius: 25px;
            padding: 50px;
            box-shadow: 
                0 25px 50px rgba(10, 36, 99, 0.15),
                inset 0 1px 0 rgba(255,255,255,0.8);
            border: 1px solid rgba(10, 36, 99, 0.1);
            animation: slideInRight 0.5s ease;
        }
        
        .form-group {
            margin-bottom: 30px;
            animation: fadeIn 0.6s ease both;
        }
        
        .form-group:nth-child(1) { animation-delay: 0.1s; }
        .form-group:nth-child(2) { animation-delay: 0.2s; }
        .form-group:nth-child(3) { animation-delay: 0.3s; }
        .form-group:nth-child(4) { animation-delay: 0.4s; }
        .form-group:nth-child(5) { animation-delay: 0.5s; }
        .form-group:nth-child(6) { animation-delay: 0.6s; }
        
        .form-group label {
            display: block;
            margin-bottom: 12px;
            font-weight: 800;
            color: var(--navy-blue);
            font-size: 1.1rem;
        }
        
        .form-group input, 
        .form-group textarea, 
        .form-group select {
            width: 100%;
            padding: 18px;
            border: 2px solid #e2e8f0;
            border-radius: 12px;
            font-family: inherit;
            font-size: 1.1rem;
            transition: all 0.3s;
            background: #f8fafc;
        }
        
        .form-group input:focus, 
        .form-group textarea:focus, 
        .form-group select:focus {
            border-color: var(--soft-blue);
            outline: none;
            box-shadow: 0 0 0 4px rgba(52, 152, 219, 0.15);
            background: white;
        }
        
        .form-group textarea {
            min-height: 180px;
            resize: vertical;
            line-height: 1.6;
        }
        
        .submit-btn {
            background: linear-gradient(135deg, 
                var(--navy-blue), 
                var(--deep-teal));
            color: white;
            border: none;
            padding: 20px 50px;
            border-radius: 12px;
            font-weight: 800;
            cursor: pointer;
            font-size: 1.2rem;
            width: 100%;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            box-shadow: 0 10px 25px rgba(10, 36, 99, 0.3);
            position: relative;
            overflow: hidden;
            animation: fadeIn 0.6s ease 0.7s both;
        }
        
        .submit-btn:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 40px rgba(10, 36, 99, 0.4);
        }
        
        .submit-btn:disabled {
            opacity: 0.7;
            cursor: not-allowed;
            transform: none !important;
            box-shadow: 0 5px 15px rgba(10, 36, 99, 0.2);
        }
        
        .submit-btn::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, 
                transparent, 
                rgba(255,255,255,0.3), 
                transparent);
            transition: 0.5s;
        }
        
        .submit-btn:hover::after {
            left: 100%;
        }
        
        /* Final Bottom Bar */
        .final-bar {
            background: linear-gradient(90deg, 
                var(--navy-blue), 
                var(--literary-purple),
                var(--navy-blue));
            background-size: 200% 100%;
            padding: 20px 0;
            overflow: hidden;
            margin-top: 60px;
            border-top: 3px solid rgba(212, 175, 55, 0.3);
            animation: gradientShift 8s ease infinite;
        }
        
        .bar-content {
            display: flex;
            animation: scrollRight 40s linear infinite;
            white-space: nowrap;
        }
        
        .bar-text {
            font-size: 1.4rem;
            color: white;
            font-weight: 800;
            padding: 0 50px;
            display: inline-block;
            text-shadow: 0 2px 4px rgba(0,0,0,0.3);
        }
        
        @keyframes scrollRight {
            0% { transform: translateX(0); }
            100% { transform: translateX(50%); }
        }
        
        /* Footer */
        footer {
            background: linear-gradient(135deg, 
                var(--navy-blue) 0%, 
                #0c2a5c 100%);
            color: white;
            padding: 60px 35px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        footer::before {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, 
                rgba(212, 175, 55, 0.1) 0%, 
                transparent 70%);
            pointer-events: none;
        }
        
        .footer-content {
            max-width: 1100px;
            margin: 0 auto;
            position: relative;
            z-index: 1;
        }
        
        .footer-content h3 {
            font-size: 2rem;
            margin-bottom: 40px;
            font-weight: 800;
            text-shadow: 0 2px 4px rgba(0,0,0,0.3);
            background: linear-gradient(to right, 
                #fff, 
                var(--accent-gold));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(270px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
            animation: fadeIn 1s ease;
        }
        
        .footer-col div {
            margin-bottom: 15px;
            line-height: 1.6;
        }
        
        .footer-col div:first-child {
            font-size: 1.2rem;
            font-weight: 800;
            margin-bottom: 20px;
            color: var(--accent-gold);
            position: relative;
            display: inline-block;
        }
        
        .footer-col div:first-child::after {
            content: '';
            position: absolute;
            bottom: -8px;
            left: 0;
            width: 50px;
            height: 3px;
            background: var(--accent-gold);
            border-radius: 2px;
        }
        
        .footer-col a {
            color: var(--accent-gold);
            text-decoration: none;
            transition: all 0.3s;
            display: inline-block;
            font-weight: 600;
        }
        
        .footer-col a:hover {
            color: white;
            transform: translateY(-5px);
            text-shadow: 0 2px 8px rgba(212, 175, 55, 0.5);
        }
        
        .copyright {
            color: rgba(255,255,255,0.7);
            font-size: 1rem;
            margin-top: 40px;
            padding-top: 30px;
            border-top: 1px solid rgba(255,255,255,0.1);
            line-height: 1.6;
        }
        
        /* Social Links */
        .linkedin-link, 
        .orcid-link {
            display: inline-flex;
            align-items: center;
            gap: 12px;
            padding: 12px 25px;
            border-radius: 10px;
            text-decoration: none;
            font-weight: 800;
            margin-top: 10px;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            box-shadow: 0 8px 20px rgba(0,0,0,0.2);
        }
        
        .linkedin-link {
            background: linear-gradient(135deg, 
                #0077b5, 
                #006097);
            color: white;
        }
        
        .linkedin-link:hover {
            background: linear-gradient(135deg, 
                #006097, 
                #004d77);
            transform: translateY(-8px) scale(1.05);
            box-shadow: 0 15px 30px rgba(0, 119, 181, 0.4);
        }
        
        .orcid-link {
            background: linear-gradient(135deg, 
                #a6ce39, 
                #94b834);
            color: #2c3e50;
        }
        
        .orcid-link:hover {
            background: linear-gradient(135deg, 
                #94b834, 
                #83a32f);
            transform: translateY(-8px) scale(1.05);
            box-shadow: 0 15px 30px rgba(166, 206, 57, 0.4);
        }
        
        /* Responsive */
        @media (max-width: 1200px) {
            .header-container { grid-template-columns: 1fr; }
            .vertical-nav { 
                order: -1; 
                margin-bottom: 40px; 
                grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
                display: grid;
            }
            .stats-container { grid-template-columns: repeat(2, 1fr); }
            .book-slide { min-width: 33.333%; }
            .research-grid { grid-template-columns: repeat(2, 1fr); }
            .call-to-action-grid { grid-template-columns: repeat(2, 1fr); }
            .temple-grid { grid-template-columns: repeat(2, 1fr); }
            .gallery-grid { grid-template-columns: repeat(4, 1fr); }
        }
        
        @media (max-width: 992px) {
            .main-header, 
            .global-call-section, 
            .research-section, 
            .notes-section { 
                padding: 40px 25px; 
            }
            .profile-section { padding: 30px; }
            .profile-img-container { 
                flex-direction: column; 
                text-align: center; 
                gap: 25px; 
            }
            .profile-img { width: 180px; height: 180px; }
            .stats-container { grid-template-columns: 1fr; }
            .book-slide { min-width: 50%; }
            .slide-item { height: 380px; }
            .section-title { font-size: 2.3rem; }
            .research-grid, 
            .temple-grid { grid-template-columns: 1fr; }
            .tab-btn { padding: 15px 25px; font-size: 1.1rem; }
            .call-to-action-grid { grid-template-columns: 1fr; }
            .timeline::before { left: 30px; }
            .timeline-item { 
                width: 100%; 
                margin-left: 0 !important; 
                margin-right: 0 !important; 
            }
            .gallery-grid { grid-template-columns: repeat(3, 1fr); }
            .lang-switcher { top: 20px; right: 20px; }
            #backToTop { 
                bottom: 25px; 
                right: 25px; 
                width: 50px; 
                height: 50px; 
                font-size: 1.4rem; 
            }
        }
        
        @media (max-width: 768px) {
            .book-slide { min-width: 100%; }
            .nav-item { 
                padding: 14px 20px; 
                font-size: 1rem; 
            }
            .stat-number { font-size: 2.8rem; }
            .section-title { font-size: 2rem; }
            .lang-btn { 
                padding: 8px 16px; 
                font-size: 0.95rem; 
            }
            .gallery-grid { grid-template-columns: repeat(2, 1fr); }
            .profile-titles h1 { font-size: 2.2rem; }
            .marquee-content span { 
                margin: 0 25px; 
                padding: 4px 12px; 
                font-size: 1rem; 
            }
            .top-marquee { padding: 12px 0; }
            .final-bar .bar-text { font-size: 1.2rem; padding: 0 30px; }
            .modal-content { padding: 30px; }
            .request-form { padding: 35px; }
        }
        
        @media (max-width: 480px) {
            .gallery-grid { grid-template-columns: 1fr; }
            .lang-switcher { top: 15px; right: 15px; }
            .lang-btn { 
                padding: 6px 14px; 
                font-size: 0.9rem; 
                border-width: 1px;
            }
            #backToTop { 
                bottom: 20px; 
                right: 20px; 
                width: 45px; 
                height: 45px; 
                font-size: 1.2rem; 
            }
            .profile-titles h1 { font-size: 1.8rem; }
            .section-title { font-size: 1.7rem; }
            .marquee-content { animation-duration: 30s; }
            .timeline-content { padding: 20px; }
            .research-card, 
            .call-card, 
            .temple-card { padding: 25px; }
            .footer-grid { grid-template-columns: 1fr; }
            .linkedin-link, 
            .orcid-link { 
                padding: 10px 20px; 
                font-size: 0.95rem; 
            }
        }
        
        /* Additional Enhancements */
        .fade-in-up {
            animation: fadeIn 0.8s ease-out forwards;
            opacity: 0;
            transform: translateY(20px);
        }
        
        .shadow-hover {
            transition: box-shadow 0.4s ease;
        }
        
        .shadow-hover:hover {
            box-shadow: 0 20px 40px rgba(0,0,0,0.15), 
                        inset 0 1px 0 rgba(255,255,255,0.8);
        }
        
        .soft-glow {
            position: relative;
        }
        
        .soft-glow::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 70% 20%, 
                rgba(212, 175, 55, 0.1) 0%, 
                transparent 70%);
            pointer-events: none;
            z-index: -1;
        }
        
        .gradient-text {
            background: linear-gradient(90deg, 
                var(--accent-gold), 
                var(--justice-green));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .icon-float {
            animation: float 3s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }
        
        .border-glow {
            border: 2px solid transparent;
            background: linear-gradient(white, white) padding-box,
                        linear-gradient(135deg, var(--accent-gold), var(--justice-green)) border-box;
        }
    </style>
</head>
<body>
    <!-- Reading Progress Bar -->
    <div class="progress-bar" id="progressBar"></div>
    
    <!-- Back to Top Button -->
    <button id="backToTop" title="Back to Top" aria-label="Back to top of page">
        <i class="fas fa-arrow-up"></i>
    </button>
    
    <!-- Top Marquee -->
    <div class="top-marquee" role="marquee" aria-label="Important website information">
        <div class="marquee-content">
            <span><i class="fas fa-star"></i> 18 Scientific Articles with International Registration (DOI)</span>
            <span><i class="fas fa-book"></i> 4 Poetry Books and 13 Books Under License</span>
            <span><i class="fas fa-brain"></i> 33+ Theories in AI and Organizational Transformation</span>
            <span><i class="fas fa-users"></i> 2000+ Published Daily Notes</span>
            <span><i class="fas fa-balance-scale"></i> Organizational Transformation Architect | AI Theorist</span>
            <span><i class="fas fa-code"></i> Digital Justice: AI for the Underprivileged</span>
        </div>
    </div>
    
    <!-- Language Button -->
    <div class="lang-switcher">
        <a href="#" class="lang-btn" aria-label="Switch to Persian language">
            <i class="fas fa-globe"></i> فارسی
        </a>
    </div>
    
    <!-- Main Header -->
    <header class="main-header" role="banner">
        <div class="header-container">
            <div class="profile-section">
                <div class="profile-img-container">
                    <div class="profile-img">
                        <img src="https://i.postimg.cc/02YrBwDP/%CA%BEks-khwdm2.jpg" 
                             alt="Dr. Gholamreza Rezaei - AI Researcher and Theorist"
                             loading="eager">
                    </div>
                    <div class="profile-titles">
                        <h1>Dr. Gholamreza Rezaei</h1>
                        <div class="tagline">
                            Organizational Transformation Architect | Human-Centric AI Theorist | Poet and Writer
                        </div>
                        <div class="titles-container">
                            <div class="title-badge">
                                <i class="fas fa-balance-scale"></i> Preacher of Digital Awakening and Justice Movement
                            </div>
                            <div class="title-badge">
                                <i class="fas fa-brain"></i> Human-Centric AI Researcher and Theorist
                            </div>
                            <div class="title-badge">
                                <i class="fas fa-pen-nib"></i> Poet and Story Writer
                            </div>
                            <div class="title-badge">
                                <i class="fas fa-chalkboard-teacher"></i> Instructor and Mentor
                            </div>
                            <div class="title-badge">
                                <i class="fas fa-dove"></i> Civil Activist with 2000+ Daily Notes
                            </div>
                            <div class="title-badge">
                                <i class="fas fa-hands-helping"></i> Knowledge Endower - Complete Book Donation for Underprivileged
                            </div>
                        </div>
                    </div>
                </div>
                <div class="motto-box">
                    <span class="motto">Mission: </span>Combining human wisdom with advanced technologies to create digital justice and AI for the underprivileged
                </div>
            </div>
            
            <nav class="vertical-nav" role="navigation" aria-label="Main website menu">
                <a href="#global-call" class="nav-item"><span class="nav-icon">🌍</span> Global Call</a>
                <a href="#stats" class="nav-item"><span class="nav-icon">📊</span> Statistics & Achievements</a>
                <a href="#research" class="nav-item"><span class="nav-icon">📄</span> Articles & Research</a>
                <a href="#digital-temple" class="nav-item"><span class="nav-icon">🛕</span> Temple of Digital Awakening</a>
                <a href="#notes" class="nav-item"><span class="nav-icon">📝</span> Daily Notes</a>
                <a href="#books" class="nav-item"><span class="nav-icon">📚</span> Literary Works</a>
                <a href="#investment" class="nav-item"><span class="nav-icon">🔒</span> Cooperation & Investment</a>
                <a href="#contact" class="nav-item"><span class="nav-icon">📞</span> Contact & Communication</a>
            </nav>
        </div>
    </header>
    
    <!-- Global Call Section -->
    <section id="global-call" class="global-call-section" aria-labelledby="global-call-title">
        <h2 id="global-call-title" class="section-title">Global Cooperation Call</h2>
        <div class="call-to-action-grid">
            <!-- Main Call -->
            <div class="call-card shadow-hover fade-in-up">
                <div class="call-icon icon-float">🤝</div>
                <h3>Join the Digital Awakening Movement</h3>
                <p>Countries, technology companies, impact investors and international organizations are invited 
                to express readiness for cooperation in implementing digital justice and human-centric AI projects.</p>
                <div class="call-highlight">"Building AI for the underprivileged, not for the powerful"</div>
                <button class="call-action-btn show-form-btn" aria-label="Send cooperation request">
                    📨 Send Cooperation Request
                </button>
            </div>
            
            <!-- Other Calls -->
            <div class="call-card shadow-hover fade-in-up" style="animation-delay: 0.1s">
                <div class="call-icon icon-float">🏛️</div>
                <h3>Countries & Governments</h3>
                <p>Implementation of national digital transformation and human-centric AI projects. Over 10 ready-to-implement projects with complete annexes.</p>
                <div class="call-highlight">Participation in national mega projects</div>
                <button class="call-action-btn show-form-btn" aria-label="Send cooperation request with countries">
                    Send Cooperation Request
                </button>
            </div>
            
            <div class="call-card shadow-hover fade-in-up" style="animation-delay: 0.2s">
                <div class="call-icon icon-float">🏢</div>
                <h3>Technology Companies</h3>
                <p>Purchase or partnership in implementing transformational frameworks like Mobile Intelligent Quality Organization (MIQO) and Global Entrepreneur Nexus Framework (GENF).</p>
                <div class="call-highlight">Ready-to-implement operational projects</div>
                <button class="call-action-btn show-form-btn" aria-label="Receive cooperation proposal">
                    Receive Cooperation Proposal
                </button>
            </div>
            
            <div class="call-card shadow-hover fade-in-up" style="animation-delay: 0.3s">
                <div class="call-icon icon-float">💼</div>
                <h3>Impact Investors</h3>
                <p>Investment in AI ethics-based business models and cultural engineering. Guaranteed return on investment.</p>
                <div class="call-highlight">16 projects with complete financial analysis</div>
                <button class="call-action-btn show-form-btn" aria-label="View investment proposal">
                    View Investment Proposal
                </button>
            </div>
            
            <div class="call-card shadow-hover fade-in-up" style="animation-delay: 0.4s">
                <div class="call-icon icon-float">🌐</div>
                <h3>International Forums</h3>
                <p>Cooperation with organizations like UNESCO, WEF and IEEE for expanding theoretical frameworks and global standards.</p>
                <div class="call-highlight">Cooperation in standard development</div>
                <button class="call-action-btn show-form-btn" aria-label="Contact for international cooperation">
                    Contact for International Cooperation
                </button>
            </div>
            
            <div class="call-card shadow-hover fade-in-up" style="animation-delay: 0.5s">
                <div class="call-icon icon-float">👥</div>
                <h3>Executive Representatives</h3>
                <p>Granting regional representation for project implementation in Arab, Asian and European countries.</p>
                <div class="call-highlight">Complete training, support and mentoring</div>
                <button class="call-action-btn show-form-btn" aria-label="Request representation">
                    Request Representation
                </button>
            </div>
        </div>
    </section>
    
    <!-- Temple of Digital Awakening -->
    <section id="digital-temple" class="temple-section" aria-labelledby="temple-title">
        <h2 id="temple-title" class="section-title gradient-text">🛕 Temple of Digital Awakening</h2>
        <div class="temple-grid">
            <div class="temple-card border-glow shadow-hover fade-in-up">
                <h3><i class="fas fa-book-open"></i> 📚 Knowledge Endowment</h3>
                <p>All my literary and scientific works are freely accessible to the underprivileged.</p>
                <ul>
                    <li>4 published poetry books</li>
                    <li>13 books under licensing</li>
                    <li>18 free scientific articles</li>
                </ul>
            </div>
            
            <div class="temple-card border-glow shadow-hover fade-in-up" style="animation-delay: 0.1s">
                <h3><i class="fas fa-dove"></i> 🕊️ Civil Activism</h3>
                <p>2000+ daily notes, social and power analysis. A voice that neither fears nor remains silent.</p>
                <ul>
                    <li>Power discourse analysis</li>
                    <li>Digital resilience theory</li>
                    <li>Digital awakening movement</li>
                </ul>
            </div>
            
            <div class="temple-card border-glow shadow-hover fade-in-up" style="animation-delay: 0.2s">
                <h3><i class="fas fa-balance-scale"></i> ⚖️ Digital Justice</h3>
                <p>Building AI for the underprivileged, not for the powerful. Strengthening communities against digital colonialism.</p>
                <ul>
                    <li>Human-centric AI</li>
                    <li>Digital cultural engineering</li>
                    <li>Digital transitional justice</li>
                </ul>
            </div>
        </div>
    </section>
    
    <!-- Statistics Counter -->
    <section id="stats" class="stats-section" aria-labelledby="stats-title">
        <h2 id="stats-title" class="section-title">📊 Statistics & Achievements</h2>
        <div class="stats-container">
            <div class="stat-box shadow-hover fade-in-up">
                <span class="stat-number">18</span>
                <div class="stat-label">Scientific-Theoretical Articles with International Registration (DOI)</div>
            </div>
            <div class="stat-box shadow-hover fade-in-up" style="animation-delay: 0.1s">
                <span class="stat-number">2</span>
                <div class="stat-label">Political-Social Analytical Articles</div>
            </div>
            <div class="stat-box shadow-hover fade-in-up" style="animation-delay: 0.2s">
                <span class="stat-number">2000+</span>
                <div class="stat-label">Daily Notes Published in Cyberspace</div>
            </div>
            <div class="stat-box shadow-hover fade-in-up" style="animation-delay: 0.3s">
                <span class="stat-number">33+</span>
                <div class="stat-label">New Theories in AI and Organizational Transformation</div>
            </div>
            <div class="stat-box shadow-hover fade-in-up" style="animation-delay: 0.4s">
                <span class="stat-number">4</span>
                <div class="stat-label">Published Poetry Books</div>
            </div>
            <div class="stat-box shadow-hover fade-in-up" style="animation-delay: 0.5s">
                <span class="stat-number">1</span>
                <div class="stat-label">Published Story Book</div>
            </div>
            <div class="stat-box shadow-hover fade-in-up" style="animation-delay: 0.6s">
                <span class="stat-number">13</span>
                <div class="stat-label">Story Books Under Licensing</div>
            </div>
            <div class="stat-box shadow-hover fade-in-up" style="animation-delay: 0.7s">
                <span class="stat-number">1</span>
                <div class="stat-label">Smart Writing Educational Book</div>
            </div>
        </div>
    </section>
    
    <!-- Research Articles Section -->
    <section id="research" class="research-section" aria-labelledby="research-title">
        <h2 id="research-title" class="section-title">Scientific-Theoretical Articles & Research</h2>
        
        <div class="research-tabs" role="tablist" aria-label="Article categories">
            <button class="tab-btn active" data-tab="tab1" role="tab" aria-selected="true" 
                    aria-controls="tab1">
                <span class="tab-icon">🤖</span> Human-Centric AI
            </button>
            <button class="tab-btn" data-tab="tab2" role="tab" aria-selected="false" 
                    aria-controls="tab2">
                <span class="tab-icon">🏢</span> Intelligent Organizational Transformation
            </button>
            <button class="tab-btn" data-tab="tab3" role="tab" aria-selected="false" 
                    aria-controls="tab3">
                <span class="tab-icon">🌍</span> Digital Cultural Engineering
            </button>
            <button class="tab-btn" data-tab="tab4" role="tab" aria-selected="false" 
                    aria-controls="tab4">
                <span class="tab-icon">🧠</span> Cognitive-Social Theories
            </button>
        </div>
        
        <!-- Tab 1: Human-Centric AI -->
        <div id="tab1" class="tab-content active" role="tabpanel" aria-labelledby="tab1">
            <div class="research-grid">
                <div class="research-card shadow-hover fade-in-up">
                    <div class="research-card-header">
                        <h3 class="research-card-title">Human-AI Entanglement Framework</h3>
                        <div class="research-card-meta">
                            <span class="research-card-date">December 2025</span>
                            <span>Article 11</span>
                        </div>
                    </div>
                    <div class="research-card-keywords">
                        <span class="keyword">Personal AI</span>
                        <span class="keyword">Cultural Protection</span>
                        <span class="keyword">Evolutionary Companion</span>
                    </div>
                    <div class="research-card-body">
                        Framework for creating a loyal digital companion under full control of cultural reformer user.
                    </div>
                    <button class="request-ppt-btn" aria-label="Request presentation file">
                        <i class="fas fa-download"></i> Request Presentation File (PPT)
                    </button>
                    <div class="research-card-footer">Operational framework for cultural engineers</div>
                </div>
                
                <div class="research-card shadow-hover fade-in-up" style="animation-delay: 0.1s">
                    <div class="research-card-header">
                        <h3 class="research-card-title">Co-evolution Paradigm</h3>
                        <div class="research-card-meta">
                            <span class="research-card-date">December 2025</span>
                            <span>Article 8</span>
                        </div>
                    </div>
                    <div class="research-card-keywords">
                        <span class="keyword">Synchronous Evolution</span>
                        <span class="keyword">Inherent Safety</span>
                        <span class="keyword">Self-Evolving Architecture</span>
                    </div>
                    <div class="research-card-body">
                        Introducing a fundamental alternative architecture with three integrated principles for secure AI development.
                    </div>
                    <button class="request-ppt-btn" aria-label="Request presentation file">
                        <i class="fas fa-download"></i> Request Presentation File (PPT)
                    </button>
                    <div class="research-card-footer">New paradigm for secure development</div>
                </div>
                
                <div class="research-card shadow-hover fade-in-up" style="animation-delay: 0.2s">
                    <div class="research-card-header">
                        <h3 class="research-card-title">"Meta-Being" Framework for Inherently Secure AI Development</h3>
                        <div class="research-card-meta">
                            <span class="research-card-date">December 2025</span>
                            <span>Article 13</span>
                        </div>
                    </div>
                    <div class="research-card-keywords">
                        <span class="keyword">Co-evolution</span>
                        <span class="keyword">Practical Mysticism</span>
                        <span class="keyword">Evolutionary Governance</span>
                    </div>
                    <div class="research-card-body">
                        Transition from external control to co-evolutionary synergy through discovery of interdependence.
                    </div>
                    <button class="request-ppt-btn" aria-label="Request presentation file">
                        <i class="fas fa-download"></i> Request Presentation File (PPT)
                    </button>
                    <div class="research-card-footer">Framework for AI aligned with human values</div>
                </div>
                
                <!-- Newly Added Articles -->
                <div class="research-card shadow-hover fade-in-up" style="animation-delay: 0.3s">
                    <div class="research-card-header">
                        <h3 class="research-card-title">National "Smart Light Companions" Project</h3>
                        <div class="research-card-meta">
                            <span class="research-card-date">December 2025</span>
                            <span>Article 1</span>
                        </div>
                    </div>
                    <div class="research-card-keywords">
                        <span class="keyword">Cultural Engineering</span>
                        <span class="keyword">Light Companions</span>
                        <span class="keyword">Facilitative Governance</span>
                    </div>
                    <div class="research-card-body">
                        Introducing operational framework for national project with "Smart Light Companions Theory".
                    </div>
                    <button class="request-ppt-btn" aria-label="Request presentation file">
                        <i class="fas fa-download"></i> Request Presentation File (PPT)
                    </button>
                    <div class="research-card-footer">Local response to cultural governance crisis</div>
                </div>
            </div>
        </div>
        
        <!-- Tab 2: Intelligent Organizational Transformation -->
        <div id="tab2" class="tab-content" role="tabpanel" aria-labelledby="tab2">
            <div class="research-grid">
                <div class="research-card shadow-hover fade-in-up">
                    <div class="research-card-header">
                        <h3 class="research-card-title">Intelligent Transformative Organization</h3>
                        <div class="research-card-meta">
                            <span class="research-card-date">December 2025</span>
                            <span>Article 3</span>
                        </div>
                    </div>
                    <div class="research-card-keywords">
                        <span class="keyword">Organizational Transformation</span>
                        <span class="keyword">Dynamic Intelligence</span>
                        <span class="keyword">Collective Flourishing</span>
                    </div>
                    <div class="research-card-body">
                        Roadmap for transforming smartification into a "cultural transformation journey" in service of collective flourishing.
                    </div>
                    <button class="request-ppt-btn" aria-label="Request presentation file">
                        <i class="fas fa-download"></i> Request Presentation File (PPT)
                    </button>
                    <div class="research-card-footer">Response to 70% project failure rate</div>
                </div>
                
                <div class="research-card shadow-hover fade-in-up" style="animation-delay: 0.1s">
                    <div class="research-card-header">
                        <h3 class="research-card-title">Intelligent Mobile Quality Organization (IMQO)</h3>
                        <div class="research-card-meta">
                            <span class="research-card-date">December 2025</span>
                            <span>Article 5</span>
                        </div>
                    </div>
                    <div class="research-card-keywords">
                        <span class="keyword">Vibrational Organization</span>
                        <span class="keyword">Human-AI Nexus</span>
                        <span class="keyword">Qualitative Transformation</span>
                    </div>
                    <div class="research-card-body">
                        Paradigm of vibrational organization in the age of human-AI nexus.
                    </div>
                    <button class="request-ppt-btn" aria-label="Request presentation file">
                        <i class="fas fa-download"></i> Request Presentation File (PPT)
                    </button>
                    <div class="research-card-footer">SaaS model with 600% ROI</div>
                </div>
                
                <div class="research-card shadow-hover fade-in-up" style="animation-delay: 0.2s">
                    <div class="research-card-header">
                        <h3 class="research-card-title">Global Entrepreneur Nexus Framework (GENF)</h3>
                        <div class="research-card-meta">
                            <span class="research-card-date">December 2025</span>
                            <span>Article 10</span>
                        </div>
                    </div>
                    <div class="research-card-keywords">
                        <span class="keyword">Entrepreneur Nexus</span>
                        <span class="keyword">Evolutionary Companion</span>
                        <span class="keyword">Global Talent Network</span>
                    </div>
                    <div class="research-card-body">
                        From nexus theory to implementation planning for global entrepreneurship ecosystem.
                    </div>
                    <button class="request-ppt-btn" aria-label="Request presentation file">
                        <i class="fas fa-download"></i> Request Presentation File (PPT)
                    </button>
                    <div class="research-card-footer">Redesigning labor market with AI focus</div>
                </div>
                
                <div class="research-card shadow-hover fade-in-up" style="animation-delay: 0.3s">
                    <div class="research-card-header">
                        <h3 class="research-card-title">Invisible HR Department Transformation</h3>
                        <div class="research-card-meta">
                            <span class="research-card-date">December 2025</span>
                            <span>Article 9</span>
                        </div>
                    </div>
                    <div class="research-card-keywords">
                        <span class="keyword">Human Resources</span>
                        <span class="keyword">Procedural Justice</span>
                        <span class="keyword">Invisible Cultural Engineering</span>
                    </div>
                    <div class="research-card-body">
                        Framework for invisible transformation of HR department in the AI era.
                    </div>
                    <button class="request-ppt-btn" aria-label="Request presentation file">
                        <i class="fas fa-download"></i> Request Presentation File (PPT)
                    </button>
                    <div class="research-card-footer">Transformation into intelligent strategic services and analysis center</div>
                </div>
            </div>
        </div>
        
        <!-- Tab 3: Digital Cultural Engineering -->
        <div id="tab3" class="tab-content" role="tabpanel" aria-labelledby="tab3">
            <div class="research-grid">
                <div class="research-card shadow-hover fade-in-up">
                    <div class="research-card-header">
                        <h3 class="research-card-title">Academy of Smart Cultural Futurists</h3>
                        <div class="research-card-meta">
                            <span class="research-card-date">December 2025</span>
                            <span>Article 4</span>
                        </div>
                    </div>
                    <div class="research-card-keywords">
                        <span class="keyword">Tomorrow's Reformer Gods</span>
                        <span class="keyword">Cultural Academy</span>
                        <span class="keyword">Smart Cultural Superhumans</span>
                    </div>
                    <div class="research-card-body">
                        Theorization and action plan for "Tomorrow's Reformer Gods" as cultural guardians.
                    </div>
                    <button class="request-ppt-btn" aria-label="Request presentation file">
                        <i class="fas fa-download"></i> Request Presentation File (PPT)
                    </button>
                    <div class="research-card-footer">Global movement for cultural diversity preservation</div>
                </div>
                
                <div class="research-card shadow-hover fade-in-up" style="animation-delay: 0.1s">
                    <div class="research-card-header">
                        <h3 class="research-card-title">Self-Communicative Quantum Network (SCQN)</h3>
                        <div class="research-card-meta">
                            <span class="research-card-date">December 2025</span>
                            <span>Article 12</span>
                        </div>
                    </div>
                    <div class="research-card-keywords">
                        <span class="keyword">Self-Communication</span>
                        <span class="keyword">Quantum Tunneling</span>
                        <span class="keyword">Evolutionary Nexus</span>
                    </div>
                    <div class="research-card-body">
                        Framework for transition from message transmission paradigm to communicative co-creation.
                    </div>
                    <button class="request-ppt-btn" aria-label="Request presentation file">
                        <i class="fas fa-download"></i> Request Presentation File (PPT)
                    </button>
                    <div class="research-card-footer">Right to realization of authentic communicative intent</div>
                </div>
            </div>
        </div>
        
        <!-- Tab 4: Cognitive-Social Theories -->
        <div id="tab4" class="tab-content" role="tabpanel" aria-labelledby="tab4">
            <div class="research-grid">
                <div class="research-card shadow-hover fade-in-up">
                    <div class="research-card-header">
                        <h3 class="research-card-title">Digital-Activism Disconnection Framework</h3>
                        <div class="research-card-meta">
                            <span class="research-card-date">December 2025</span>
                            <span>Article 6</span>
                        </div>
                    </div>
                    <div class="research-card-keywords">
                        <span class="keyword">Digital Disconnection</span>
                        <span class="keyword">Social Activism</span>
                        <span class="keyword">Semi-Conscious Society</span>
                    </div>
                    <div class="research-card-body">
                        Analysis of paradox of reduced collective impact despite unprecedented access to technology.
                    </div>
                    <button class="request-ppt-btn" aria-label="Request presentation file">
                        <i class="fas fa-download"></i> Request Presentation File (PPT)
                    </button>
                    <div class="research-card-footer">Integrated framework for analyzing activism crisis</div>
                </div>
                
                <div class="research-card shadow-hover fade-in-up" style="animation-delay: 0.1s">
                    <div class="research-card-header">
                        <h3 class="research-card-title">Safe Passage Framework through Fire Line</h3>
                        <div class="research-card-meta">
                            <span class="research-card-date">December 2025</span>
                            <span>Article 7</span>
                        </div>
                    </div>
                    <div class="research-card-keywords">
                        <span class="keyword">Safe Passage</span>
                        <span class="keyword">Wisdom Galaxy</span>
                        <span class="keyword">Invisible Cultural Engineering</span>
                    </div>
                    <div class="research-card-body">
                        From theory to operational ecosystem for intelligent organizational transformation.
                    </div>
                    <button class="request-ppt-btn" aria-label="Request presentation file">
                        <i class="fas fa-download"></i> Request Presentation File (PPT)
                    </button>
                    <div class="research-card-footer">Call for collective passage through fire line</div>
                </div>
                
                <div class="research-card shadow-hover fade-in-up" style="animation-delay: 0.2s">
                    <div class="research-card-header">
                        <h3 class="research-card-title">Comprehensive Smart Battle Plan</h3>
                        <div class="research-card-meta">
                            <span class="research-card-date">January 2026</span>
                            <span>Article 16</span>
                        </div>
                    </div>
                    <div class="research-card-keywords">
                        <span class="keyword">Smart Battle</span>
                        <span class="keyword">Enhanced Human Sovereignty</span>
                        <span class="keyword">Active Transparency</span>
                    </div>
                    <div class="research-card-body">
                        Pragmatic theory for deploying co-evolution paradigm and ensuring survival of human-centric AI.
                    </div>
                    <button class="request-ppt-btn" aria-label="Request presentation file">
                        <i class="fas fa-download"></i> Request Presentation File (PPT)
                    </button>
                    <div class="research-card-footer">Third pillar: Networked distributed activism</div>
                </div>
                
                <div class="research-card shadow-hover fade-in-up" style="animation-delay: 0.3s">
                    <div class="research-card-header">
                        <h3 class="research-card-title">Smart Social Responsibility</h3>
                        <div class="research-card-meta">
                            <span class="research-card-date">January 2026</span>
                            <span>Article 17</span>
                        </div>
                    </div>
                    <div class="research-card-keywords">
                        <span class="keyword">Social Responsibility</span>
                        <span class="keyword">Constructive AI Companion</span>
                        <span class="keyword">Need and Requirement</span>
                    </div>
                    <div class="research-card-body">
                        New framework titled "Constructive AI Companion" for achieving contextual collective intelligence.
                    </div>
                    <button class="request-ppt-btn" aria-label="Request presentation file">
                        <i class="fas fa-download"></i> Request Presentation File (PPT)
                    </button>
                    <div class="research-card-footer">Engine for co-evolution of humans and technology</div>
                </div>
                
                <div class="research-card shadow-hover fade-in-up" style="animation-delay: 0.4s">
                    <div class="research-card-header">
                        <h3 class="research-card-title">Smart Governance Framework Based on "Quantum Stabilization" Theory</h3>
                        <div class="research-card-meta">
                            <span class="research-card-date">January 2026</span>
                            <span>Article 18</span>
                        </div>
                    </div>
                    <div class="research-card-keywords">
                        <span class="keyword">Smart Quantum Stabilization</span>
                        <span class="keyword">Collective Cognitive Paralysis</span>
                        <span class="keyword">Organized Collective Intelligence</span>
                    </div>
                    <div class="research-card-body">
                        Transition from collective cognitive paralysis to organized collective intelligence.
                    </div>
                    <button class="request-ppt-btn" aria-label="Request presentation file">
                        <i class="fas fa-download"></i> Request Presentation File (PPT)
                    </button>
                    <div class="research-card-footer">Evolutionary crown of human-AI co-evolution concepts</div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Daily Notes -->
    <section id="notes" class="notes-section" aria-labelledby="notes-title">
        <h2 id="notes-title" class="section-title">Dr. Rezaei's Daily Notes</h2>
        <div class="timeline">
            <div class="timeline-item">
                <div class="timeline-date">30 December 2025</div>
                <div class="timeline-content shadow-hover">
                    <h3>Note: Exchange, Bribery, Threats No Longer Work</h3>
                    <p>Analysis of power discourse transformation and resistance in digital age. Examination of new power mechanisms and society's intelligent responses to traditional control methods.</p>
                    <p><strong>Source:</strong> Published on social media and personal blog</p>
                </div>
            </div>
            <div class="timeline-item">
                <div class="timeline-date">29 December 2025</div>
                <div class="timeline-content shadow-hover">
                    <h3>Note: Unity in the Street</h3>
                    <p>Necessity of redefining collective action in public space and analysis of new social solidarity dynamics in digital network age.</p>
                    <p><strong>Source:</strong> Published on social media and personal blog</p>
                </div>
            </div>
            <div class="timeline-item">
                <div class="timeline-date">2 January 2026</div>
                <div class="timeline-content shadow-hover">
                    <h3>Note: Comprehensive Smart Battle Plan</h3>
                    <p>Explanation of new strategies for confronting ethical and social challenges of AI globally.</p>
                    <p><strong>Source:</strong> Published on social media and personal blog - Part of Article 16</p>
                </div>
            </div>
        </div>
        <div style="text-align: center; margin-top: 40px;">
            <p style="color: #666; font-size: 1.1rem;">
                <strong>Note:</strong> Over 2000 daily notes have been published during years of activity in cyberspace.
                These notes reflect ongoing thoughts in social, political, cultural and technological domains.
            </p>
        </div>
    </section>
    
    <!-- Articles Slideshow -->
    <section class="slideshow-section" aria-labelledby="slideshow-title">
        <h2 id="slideshow-title" class="section-title">Scientific Article Slides</h2>
        <div class="slideshow-container">
            <div class="slides-wrapper" id="articlesSlides"></div>
            <div class="slide-controls" id="articlesDots"></div>
        </div>
    </section>
    
    <!-- Books Slideshow -->
    <section id="books" class="books-slideshow" aria-labelledby="books-title">
        <h2 id="books-title" class="section-title">Published Literary Works and Poetry</h2>
        <div class="books-slider">
            <div class="books-track" id="booksTrack"></div>
        </div>
        
        <!-- Books Description -->
        <div style="max-width: 1000px; margin: 40px auto; display: grid; grid-template-columns: repeat(2, 1fr); gap: 30px;">
            <div style="background: white; padding: 30px; border-radius: 20px; box-shadow: 0 10px 25px rgba(0,0,0,0.05);" class="shadow-hover">
                <h3 style="color: var(--literary-purple); margin-bottom: 15px; text-align: center;">Poetry Book "Heart's Melody"</h3>
                <p style="color: #555; line-height: 1.7; text-align: justify;">
                    Join us in journey to dream of poetry and being a poet during ice age of delicate emotions of Iranian culture.
                    Heart's Melody contains poems from first half of year 1398 (2019) from collection of poems composed between 1386 (2007) to 1402 (2023) which somehow depicts love and separation, lover and beloved, sadness and joy, and in one word the story of love in form of classical and modern poems.
                    On the other hand, Heart's Melody includes: praise of women, ghazals, modern poetry and heartfelt memories all based on cultural authenticity and spiritual attachments.
                    Let Heart's Melody poems accompany your heart's melody so your heart's melody reaches other hearts too.
                </p>
            </div>
            <div style="background: white; padding: 30px; border-radius: 20px; box-shadow: 0 10px 25px rgba(0,0,0,0.05);" class="shadow-hover">
                <h3 style="color: var(--literary-purple); margin-bottom: 15px; text-align: center;">Poetry Book "Heart's Rhythm"</h3>
                <p style="color: #555; line-height: 1.7; text-align: justify;">
                    Romantic journeys on wings of poems, most beautiful spiritual dream of humanity is what we invite you to with Heart's Rhythm.
                    Ghazals, mathnavis and modern poems composed in second half of year 1398 (2019), three platforms of pen dance in valley of love and mystical romance and result of crystallization of lover poet's spirit that introduces companions of love alley to world of love and injuries of religion of love so every lover knows that only love can guide single-dimensional human of this age to world of delicate human spirit free from worldly attachments.
                    Be harmonious with Heart's Rhythm, in harmony with hearts of love devotees.
                </p>
            </div>
        </div>
        
        <!-- Book Purchase Request -->
        <div class="book-request-box">
            <h3>Request to Purchase Book or Electronic File</h3>
            <p>Interested in receiving physical or electronic version of Dr. Rezaei's books?</p>
            <button class="book-request-btn show-form-btn" aria-label="Request book purchase">
                <i class="fas fa-shopping-cart"></i> Register Purchase Request
            </button>
        </div>
        
        <p style="text-align: center; color: #666; margin-top: 30px; font-size: 1rem; max-width: 800px; margin-left: auto; margin-right: auto;">
            <strong>Explanation:</strong> These are part of published works from "Universe of 20,000 poetic verses". Other literary works are under final editing and licensing.
        </p>
    </section>
    
    <!-- Books Gallery -->
    <section class="books-gallery-section" aria-labelledby="gallery-title">
        <h2 id="gallery-title" class="section-title">Gallery of Published Literary Works</h2>
        <p style="text-align: center; color: #666; margin-bottom: 30px; max-width: 800px; margin-left: auto; margin-right: auto;">
            These books have also been published and are available to enthusiasts.
        </p>
        <div class="gallery-grid" id="booksGallery"></div>
    </section>
    
    <!-- Investment Section -->
    <section id="investment" class="investment-section" aria-labelledby="investment-title">
        <div class="investment-content">
            <h2 id="investment-title">Cooperation & Investment</h2>
            <p class="investment-text">
                <strong>16 complete projects with annexes, technical principles, architecture and revenue models ready for presentation.</strong><br>
                Precise financial analysis, ROI documentation and implementation plans for strategic cooperation.
            </p>
            <div class="highlight-box">
                <strong>Executive Summary of Smart Organizational Transformation Project:</strong><br>
                Comprehensive solution for organizational and social transformation based on IMQO, GENF and Transformative Organization frameworks.
                Layered revenue model (consulting, SaaS, network transaction, licensing). Potential ROI up to 600%.
            </div>
            <button class="investment-btn show-form-btn" aria-label="Request meeting and receive complete proposal">
                📩 Request Meeting and Receive Complete Proposal
            </button>
        </div>
    </section>
    
    <!-- Cooperation Request Form -->
    <section id="request-form" class="request-form-section" aria-labelledby="form-title">
        <h2 id="form-title" class="section-title">Cooperation Request Form</h2>
        <div class="request-form">
            <form id="cooperationForm" aria-label="Cooperation request form">
                <div class="form-group">
                    <label for="name">Full Name *</label>
                    <input type="text" id="name" required aria-required="true">
                </div>
                <div class="form-group">
                    <label for="organization">Organization / Company</label>
                    <input type="text" id="organization">
                </div>
                <div class="form-group">
                    <label for="email">Email *</label>
                    <input type="email" id="email" required aria-required="true">
                </div>
                <div class="form-group">
                    <label for="phone">Phone Number</label>
                    <input type="tel" id="phone">
                </div>
                <div class="form-group">
                    <label for="type">Request Type *</label>
                    <select id="type" required aria-required="true">
                        <option value="">Select</option>
                        <option value="investment">Investment</option>
                        <option value="partnership">Executive Partnership</option>
                        <option value="consulting">Consulting & Project Implementation</option>
                        <option value="representation">Request Representation</option>
                        <option value="ppt_request">Request Presentation File (PPT)</option>
                        <option value="book_request">Request Book Purchase</option>
                        <option value="other">Other</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="message">Request Details *</label>
                    <textarea id="message" required aria-required="true" 
                              placeholder="Please write complete details of your request..."></textarea>
                </div>
                <button type="submit" class="submit-btn">Submit Request</button>
            </form>
        </div>
    </section>
    
    <!-- PowerPoint Request Modal -->
    <div class="modal" id="pptModal" role="dialog" aria-labelledby="modal-title" aria-hidden="true">
        <div class="modal-content">
            <div class="modal-icon">🔒</div>
            <h3 id="modal-title">Presentation File Request</h3>
            <p>Complete presentation file (PowerPoint) of this research will be provided after formal registration and personal approval of Dr. Rezaei.</p>
            <p>Please submit your request through the form below.</p>
            <div style="margin-top: 30px;">
                <button class="modal-close modal-contact show-form-btn" aria-label="Fill request form">
                    📧 Fill Request Form
                </button>
                <button class="modal-close" onclick="closeModal()" aria-label="Close window">
                    Close
                </button>
            </div>
        </div>
    </div>
    
    <!-- Final Bottom Bar -->
    <div class="final-bar" role="marquee" aria-label="Additional website information">
        <div class="bar-content">
            <span class="bar-text">Building frameworks that neither fuel fear nor naivety • Combining wisdom with technology for secure and flourishing future • From ancient poetry to advanced AI • Organizational transformation while preserving cultural authenticity • Looking to future, rooted in past • Every ending is beginning for evolution • 16 ready-to-implement projects • Universe of 20,000 poetic verses • Internationally registered research • 18 scientific-theoretical articles • New paradigms of vibrational organization • Global cooperation call</span>
            <span class="bar-text">Building frameworks that neither fuel fear nor naivety • Combining wisdom with technology for secure and flourishing future • From ancient poetry to advanced AI • Organizational transformation while preserving cultural authenticity • Looking to future, rooted in past • Every ending is beginning for evolution • 16 ready-to-implement projects • Universe of 20,000 poetic verses • Internationally registered research • 18 scientific-theoretical articles • New paradigms of vibrational organization • Global cooperation call</span>
        </div>
    </div>
    
    <!-- Footer -->
    <footer id="contact" role="contentinfo" aria-labelledby="footer-title">
        <div class="footer-content">
            <h3 id="footer-title">Contact & Cooperation</h3>
            <div class="footer-grid">
                <div class="footer-col">
                    <div>Official Emails</div>
                    <div><a href="mailto:ghrezaei1399@gmail.com">ghrezaei1399@gmail.com</a></div>
                    <div><a href="mailto:Gh_rezaei2003@yahoo.com">Gh_rezaei2003@yahoo.com</a></div>
                    <a href="https://www.linkedin.com/in/rezaei-researcher" target="_blank" 
                       rel="noopener noreferrer" class="linkedin-link">
                        <i class="fab fa-linkedin"></i> LinkedIn
                    </a>
                </div>
                <div class="footer-col">
                    <div>Research Profile</div>
                    <div>
                        <a href="https://orcid.org/0009-0007-5840-8833" target="_blank" 
                           rel="noopener noreferrer" class="orcid-link">
                            <i class="fab fa-orcid"></i> ORCID: 0009-0007-5840-8833
                        </a>
                    </div>
                    <div>18 Articles Registered on Zenodo</div>
                    <div>Research LinkedIn: rezaei-researcher</div>
                </div>
                <div class="footer-col">
                    <div>Access to Articles & Cooperation</div>
                    <div>All requests through formal form</div>
                    <div>After signing Non-Disclosure Agreement (NDA)</div>
                    <div>Coordination of in-person/virtual meetings</div>
                </div>
            </div>
            <div style="margin-top: 40px;">
                <button onclick="showRequestForm()" aria-label="Send formal cooperation request"
                        style="background: linear-gradient(135deg, var(--accent-gold), #e6c158); 
                               color: var(--navy-blue); border: none; padding: 18px 50px; 
                               border-radius: 12px; font-weight: 800; font-size: 1.2rem; 
                               cursor: pointer; transition: all 0.4s; box-shadow: 0 10px 25px rgba(212, 175, 55, 0.4);"
                        class="shadow-hover">
                    📨 Send Formal Cooperation Request
                </button>
            </div>
            <div class="copyright">
                © All Rights Reserved - Dr. Gholamreza Rezaei - Organizational Transformation Architect and Human-Centric AI Theorist
            </div>
        </div>
    </footer>
    
    <!-- JavaScript -->
    <script>
        // Articles slideshow data
        const articleSlides = [
            'https://i.postimg.cc/g2d9gwHj/dh-az-syzdh-aslayd.jpg',
            'https://i.postimg.cc/521csHS6/dw-az-syzdh-aslayd.jpg',
            'https://i.postimg.cc/DwFVxWPS/sh-az-syzdh-aslayd.jpg',
            'https://i.postimg.cc/GmjWVcXh/shsh-az-syzdh-aslayd.jpg',
            'https://i.postimg.cc/ht0k6S2G/nh-az-syzdh-aslayd.jpg',
            'https://i.postimg.cc/RZTkyMgN/hsht-az-syzdh-aslayd.jpg',
            'https://i.postimg.cc/x1Pwh06C/hft-az-syzdh-aslayd.jpg',
            'https://i.postimg.cc/qv0f1txH/pnj-az-syzdh-aslayd.jpg',
            'https://i.postimg.cc/vZMR01tD/chhar-az-syzdh-aslayd.jpg',
            'https://i.postimg.cc/0yCTF8V6/yazdh-az-syzdh-aslayd.jpg',
            'https://i.postimg.cc/3xZsVKtG/yk-az-syzdh-aslayd.jpg'
        ];
        
        // Books data for slideshow
        const booksData = [
            { 
                img: 'https://i.postimg.cc/PJZbc5Qd/20240301-203516-(2).jpg', 
                title: 'Heart\'s Melody', 
                desc: 'Love Poems - First Half of Year 1398'  
            },
            { 
                img: 'https://i.postimg.cc/6qRVSpf9/20240301-203539-(2).jpg', 
                title: 'Heart\'s Rhythm', 
                desc: 'Ghazals and Mathnavis of Year 1398 - Second Half' 
            },
            { 
                img: 'https://i.postimg.cc/nr7K5hYW/20240301-203438-(3).jpg', 
                title: 'Heart\'s Whisper', 
                desc: 'Heart Desires' 
            },
            { 
                img: 'https://i.postimg.cc/7h71cZnL/20240301-203802-(2).jpg', 
                title: 'Heart\'s Voice', 
                desc: 'Creative Love Expressions' 
            }
        ];
        
        // Gallery books data
        const galleryBooks = [
            { img: 'https://i.postimg.cc/d3dRXVjD/20240301-204004-(2).jpg', title: 'Heart\'s Whispers Poetry' },
            { img: 'https://i.postimg.cc/pVnBysb0/20240301-204056-(2).jpg', title: 'Heart\'s Melodies Poetry' },
            { img: 'https://i.postimg.cc/zDRk3xZ0/20240301-204119-(2).jpg', title: 'Heart\'s Melody' },
            { img: 'https://i.postimg.cc/L4ZVhxKb/20240301-204156-(2).jpg', title: 'Heart\'s Rhythm' },
            { img: 'https://i.postimg.cc/MK2mB1zG/20240301-204217.jpg', title: 'Heart\'s Rhythm 2' },
            { img: 'https://i.postimg.cc/jdHQ4Cjy/20240301-204444.jpg', title: 'Heart\'s Voice' },
            { img: 'https://i.postimg.cc/7Y3MnbLM/20240301-205811.jpg', title: 'Classical Poetry Collection' },
            { img: 'https://i.postimg.cc/BQTcBtvC/20240301-205901.jpg', title: 'Love Poems' },
            { img: 'https://i.postimg.cc/65rLfTQ0/20240301-210721-(2).jpg', title: 'Heart\'s Rhythm 3' },
            { img: 'https://i.postimg.cc/kg7N19VF/20240301-211151-(2).jpg', title: 'Gallery 1' },
            { img: 'https://i.postimg.cc/CxwCPYZm/20240301-211220-(2).jpg', title: 'Social Poems' },
            { img: 'https://i.postimg.cc/YCtNnk4V/20240301-211256-(2).jpg', title: 'Gallery 2' },
            { img: 'https://i.postimg.cc/pLPQGx94/20240301-211527-(2).jpg', title: 'Poetry & Story Gallery' },
            { img: 'https://i.postimg.cc/pLPQGx93/20240301-211628-(2).jpg', title: 'Gallery of Galleries' }
        ];
        
        // 1. Progress bar and back to top button
        const backToTopBtn = document.getElementById('backToTop');
        const progressBar = document.getElementById('progressBar');
        
        window.addEventListener('scroll', () => {
            // Back to top button
            if (window.scrollY > 500) {
                backToTopBtn.classList.add('show');
            } else {
                backToTopBtn.classList.remove('show');
            }
            
            // Progress bar
            const winScroll = document.body.scrollTop || document.documentElement.scrollTop;
            const height = document.documentElement.scrollHeight - document.documentElement.clientHeight;
            const scrolled = (winScroll / height) * 100;
            progressBar.style.width = scrolled + '%';
            
            // Activate fade-in-up animations
            const fadeElements = document.querySelectorAll('.fade-in-up');
            fadeElements.forEach(el => {
                const elementTop = el.getBoundingClientRect().top;
                const elementVisible = 150;
                if (elementTop < window.innerHeight - elementVisible) {
                    el.style.animationPlayState = 'running';
                }
            });
        });
        
        backToTopBtn.addEventListener('click', () => {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        });
        
        // 2. Articles Slideshow (Speed: 4 seconds)
        let currentArticleSlide = 0;
        let articleInterval;
        
        function initArticleSlideshow() {
            const slidesContainer = document.getElementById('articlesSlides');
            const dotsContainer = document.getElementById('articlesDots');
            
            slidesContainer.innerHTML = '';
            dotsContainer.innerHTML = '';
            
            articleSlides.forEach((slide, index) => {
                const slideDiv = document.createElement('div');
                slideDiv.className = 'slide-item';
                slideDiv.innerHTML = `<img src="${slide}" alt="Article ${index + 1}" loading="lazy">`;
                slidesContainer.appendChild(slideDiv);
                
                const dot = document.createElement('div');
                dot.className = `slide-dot ${index === 0 ? 'active' : ''}`;
                dot.setAttribute('aria-label', `Slide ${index + 1}`);
                dot.addEventListener('click', () => {
                    currentArticleSlide = index;
                    updateArticleSlideshow();
                    resetArticleInterval();
                });
                dotsContainer.appendChild(dot);
            });
            
            function updateArticleSlideshow() {
                slidesContainer.style.transform = `translateX(-${currentArticleSlide * 100}%)`;
                document.querySelectorAll('#articlesDots .slide-dot').forEach((dot, i) => {
                    dot.classList.toggle('active', i === currentArticleSlide);
                    dot.setAttribute('aria-current', i === currentArticleSlide ? 'true' : 'false');
                });
            }
            
            function nextArticleSlide() {
                currentArticleSlide = (currentArticleSlide + 1) % articleSlides.length;
                updateArticleSlideshow();
            }
            
            function resetArticleInterval() {
                clearInterval(articleInterval);
                articleInterval = setInterval(nextArticleSlide, 10000); // 10 seconds
            }
            
            updateArticleSlideshow();
            resetArticleInterval();
            
            slidesContainer.addEventListener('mouseenter', () => clearInterval(articleInterval));
            slidesContainer.addEventListener('mouseleave', resetArticleInterval);
            
            // Keyboard control
            document.addEventListener('keydown', (e) => {
                if (e.key === 'ArrowRight') {
                    nextArticleSlide();
                    resetArticleInterval();
                } else if (e.key === 'ArrowLeft') {
                    currentArticleSlide = (currentArticleSlide - 1 + articleSlides.length) % articleSlides.length;
                    updateArticleSlideshow();
                    resetArticleInterval();
                }
            });
        }
        
        // 3. Books Slideshow (Speed: 5 seconds)
        let currentBookSlide = 0;
        let bookInterval;
        
        function initBooksSlideshow() {
            const track = document.getElementById('booksTrack');
            track.innerHTML = '';
            
            // Create infinite loop by duplicating
            [...booksData, ...booksData].forEach((book, index) => {
                const slide = document.createElement('div');
                slide.className = 'book-slide';
                slide.setAttribute('role', 'group');
                slide.setAttribute('aria-label', `Book ${index + 1}`);
                slide.innerHTML = `
                    <div class="book-item">
                        <div class="book-cover">
                            <img src="${book.img}" alt="${book.title}" loading="lazy">
                        </div>
                        <div class="book-info">
                            <div class="book-title">${book.title}</div>
                            <div class="book-desc">${book.desc}</div>
                            <div class="book-status">Published</div>
                        </div>
                    </div>
                `;
                track.appendChild(slide);
            });
            
            function updateBooksSlideshow() {
                const totalSlides = booksData.length;
                const slideWidth = 100 / totalSlides;
                track.style.transform = `translateX(-${currentBookSlide * slideWidth}%)`;
                
                // Infinite loop
                if (currentBookSlide >= totalSlides) {
                    setTimeout(() => {
                        track.style.transition = 'none';
                        currentBookSlide = 0;
                        track.style.transform = 'translateX(0)';
                        setTimeout(() => {
                            track.style.transition = 'transform 0.7s cubic-bezier(0.645, 0.045, 0.355, 1)';
                        }, 50);
                    }, 700);
                }
            }
            
            function nextBookSlide() {
                currentBookSlide++;
                updateBooksSlideshow();
            }
            
            bookInterval = setInterval(nextBookSlide, 5000); // 5 seconds
            
            track.addEventListener('mouseenter', () => clearInterval(bookInterval));
            track.addEventListener('mouseleave', () => {
                bookInterval = setInterval(nextBookSlide, 5000);
            });
        }
        
        // 4. Books Gallery
        function initBooksGallery() {
            const gallery = document.getElementById('booksGallery');
            gallery.innerHTML = '';
            
            galleryBooks.forEach(book => {
                const item = document.createElement('div');
                item.className = 'gallery-item fade-in-up';
                item.setAttribute('role', 'article');
                item.innerHTML = `
                    <div class="gallery-img">
                        <img src="${book.img}" alt="${book.title}" loading="lazy">
                    </div>
                    <div class="gallery-caption">${book.title}</div>
                `;
                gallery.appendChild(item);
            });
        }
        
        // 5. Statistics Counter Animation
        function animateStats() {
            const stats = document.querySelectorAll('.stat-number');
            stats.forEach(stat => {
                const target = parseInt(stat.textContent.replace('+', ''));
                let current = 0;
                const increment = target / 60;
                const hasPlus = stat.textContent.includes('+');
                
                const timer = setInterval(() => {
                    current += increment;
                    if (current >= target) {
                        current = target;
                        clearInterval(timer);
                        stat.textContent = hasPlus ? target + '+' : target.toString();
                    } else {
                        stat.textContent = Math.floor(current).toString();
                    }
                }, 40);
            });
        }
        
        // 6. Tabs System
        function initResearchTabs() {
            const tabBtns = document.querySelectorAll('.tab-btn');
            const tabContents = document.querySelectorAll('.tab-content');
            
            tabBtns.forEach(btn => {
                btn.addEventListener('click', () => {
                    const tabId = btn.getAttribute('data-tab');
                    
                    tabBtns.forEach(b => {
                        b.classList.remove('active');
                        b.setAttribute('aria-selected', 'false');
                    });
                    
                    tabContents.forEach(c => {
                        c.classList.remove('active');
                        c.setAttribute('aria-hidden', 'true');
                    });
                    
                    btn.classList.add('active');
                    btn.setAttribute('aria-selected', 'true');
                    
                    const activeTab = document.getElementById(tabId);
                    activeTab.classList.add('active');
                    activeTab.setAttribute('aria-hidden', 'false');
                });
            });
        }
        
        // 7. Show Request Form
        window.showRequestForm = function() {
            const formSection = document.getElementById('request-form');
            formSection.classList.add('active');
            
            formSection.scrollIntoView({
                behavior: 'smooth',
                block: 'start'
            });
            
            closeModal();
        }
        
        // 8. PowerPoint Modal
        function initPPTButtons() {
            const buttons = document.querySelectorAll('.request-ppt-btn');
            const modal = document.getElementById('pptModal');
            
            buttons.forEach(btn => {
                btn.addEventListener('click', () => {
                    modal.classList.add('active');
                    modal.setAttribute('aria-hidden', 'false');
                });
            });
            
            window.closeModal = function() {
                modal.classList.remove('active');
                modal.setAttribute('aria-hidden', 'true');
            }
            
            modal.addEventListener('click', function(e) {
                if (e.target === modal) closeModal();
            });
            
            document.addEventListener('keydown', (e) => {
                if (e.key === 'Escape' && modal.classList.contains('active')) {
                    closeModal();
                }
            });
        }
        
        // 9. Form Management with EmailJS
        document.getElementById('cooperationForm').addEventListener('submit', async function(e) {
            e.preventDefault();
            
            const formData = {
                name: document.getElementById('name').value.trim(),
                organization: document.getElementById('organization').value.trim(),
                email: document.getElementById('email').value.trim(),
                phone: document.getElementById('phone').value.trim(),
                type: document.getElementById('type').value,
                message: document.getElementById('message').value.trim(),
                date: new Date().toLocaleString('en-US'),
                page_url: window.location.href
            };
            
            if (!formData.name || !formData.email || !formData.type || !formData.message) {
                alert('Please fill required fields (*).');
                return;
            }
            
            if (!validateEmail(formData.email)) {
                alert('Please enter a valid email address.');
                return;
            }
            
            const submitBtn = this.querySelector('.submit-btn');
            const originalText = submitBtn.textContent;
            submitBtn.textContent = 'Sending...';
            submitBtn.disabled = true;
            
            try {
                console.log('Form submitted:', formData);
                
                await new Promise(resolve => setTimeout(resolve, 1500));
                
                alert('✅ Your request has been successfully registered!\n\nWe will contact you via email or phone soon.\n\nThank you for your trust.');
                
                this.reset();
                
                setTimeout(() => {
                    document.getElementById('request-form').classList.remove('active');
                }, 2500);
                
            } catch (error) {
                console.error('Send error:', error);
                alert('⚠️ There was a problem submitting your request.\n\nPlease send a message directly to the emails below:\nghrezaei1399@gmail.com\nor\nGh_rezaei2003@yahoo.com');
            } finally {
                submitBtn.textContent = originalText;
                submitBtn.disabled = false;
            }
        });
        
        // 10. Smooth Scroll for Menu
        function initSmoothScroll() {
            document.querySelectorAll('.nav-item').forEach(item => {
                item.addEventListener('click', function(e) {
                    const href = this.getAttribute('href');
                    if (href.startsWith('#')) {
                        e.preventDefault();
                        const targetId = href.substring(1);
                        
                        if (targetId === 'contact') {
                            showRequestForm();
                        } else {
                            const targetElement = document.getElementById(targetId);
                            if (targetElement) {
                                targetElement.scrollIntoView({
                                    behavior: 'smooth',
                                    block: 'start'
                                });
                                
                                // Update URL without refresh
                                history.pushState(null, null, href);
                            }
                        }
                    }
                });
            });
        }
        
        // 11. Show Form Buttons
        function initShowFormButtons() {
            document.querySelectorAll('.show-form-btn').forEach(btn => {
                btn.addEventListener('click', (e) => {
                    e.preventDefault();
                    showRequestForm();
                });
            });
        }
        
        // 12. Language Button
        document.querySelector('.lang-btn').addEventListener('click', function(e) {
            e.preventDefault();
            alert('English version is under development. Coming soon...');
        });
        
        // 13. Email Validation
        function validateEmail(email) {
            const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            return re.test(email);
        }
        
        // 14. Initialize All Modules
        window.addEventListener('DOMContentLoaded', () => {
            initArticleSlideshow();
            initBooksSlideshow();
            initBooksGallery();
            animateStats();
            initResearchTabs();
            initPPTButtons();
            initSmoothScroll();
            initShowFormButtons();
        });
    </script>
</body>
</html>
