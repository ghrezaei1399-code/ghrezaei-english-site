<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dr. Gholamreza Rezaei | Wisdom + Technology</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --navy-blue: #0A2463;
            --deep-teal: #1A5276;
            --accent-gold: #D4AF37;
            --soft-blue: #3498DB;
            --literary-purple: #6A4C93;
            --light-bg: #F8F9FA;
            --card-shadow: rgba(10, 36, 99, 0.1);
        }
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Inter', 'Segoe UI', sans-serif; background: var(--light-bg); color: #333; }
        
        /* Language button - optimized position */
        .lang-switcher {
            position: fixed;
            top: 25px;
            right: 25px;
            z-index: 999999;
            background: rgba(10, 36, 99, 0.9);
            padding: 5px;
            border-radius: 30px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.4);
            backdrop-filter: blur(10px);
            border: 2px solid #D4AF37;
        }
        .lang-btn {
            background: #D4AF37;
            color: #0A2463;
            padding: 10px 20px;
            border-radius: 25px;
            font-weight: bold;
            text-decoration: none;
            display: inline-block;
            transition: all 0.3s;
            font-size: 0.95rem;
        }
        .lang-btn:hover {
            background: #0A2463;
            color: #D4AF37;
            transform: scale(1.05);
            box-shadow: 0 0 15px rgba(212, 175, 55, 0.5);
        }
        
        /* Main header */
        .main-header {
            background: linear-gradient(135deg, var(--navy-blue), var(--deep-teal));
            min-height: 50vh;
            padding: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
        }
        .header-container {
            max-width: 1300px;
            width: 100%;
            display: grid;
            grid-template-columns: 1fr 280px;
            gap: 30px;
            align-items: start;
        }
        .profile-section {
            background: rgba(255, 255, 255, 0.12);
            backdrop-filter: blur(12px);
            border-radius: 20px;
            padding: 30px;
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            border: 1px solid rgba(255, 255, 255, 0.18);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
        }
        .profile-img-container {
            display: flex;
            align-items: center;
            gap: 25px;
            margin-bottom: 20px;
            width: 100%;
        }
        .profile-img {
            width: 140px;
            height: 140px;
            border-radius: 15px;
            border: 4px solid var(--accent-gold);
            overflow: hidden;
            flex-shrink: 0;
        }
        .profile-img img { width: 100%; height: 100%; object-fit: cover; }
        .profile-titles {
            flex: 1;
        }
        .profile-titles h1 {
            color: white;
            font-size: 2.2rem;
            margin-bottom: 8px;
        }
        .profile-titles .tagline {
            color: rgba(255, 255, 255, 0.9);
            font-size: 1.1rem;
            line-height: 1.5;
        }
        .motto-box {
            color: white;
            background: rgba(0, 0, 0, 0.15);
            padding: 15px 20px;
            border-radius: 15px;
            border-left: 4px solid var(--accent-gold);
            font-size: 1rem;
            line-height: 1.6;
            width: 100%;
        }
        .motto {
            color: var(--accent-gold);
            font-weight: 600;
        }
        
        /* Vertical navigation */
        .vertical-nav {
            background: rgba(255, 255, 255, 0.98);
            border-radius: 20px;
            padding: 25px 20px;
            box-shadow: 0 12px 25px var(--card-shadow);
            display: flex;
            flex-direction: column;
            gap: 12px;
            height: fit-content;
        }
        .nav-item {
            background: linear-gradient(to right, var(--soft-blue), var(--deep-teal));
            color: white;
            padding: 14px 20px;
            border-radius: 12px;
            text-decoration: none;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 10px;
            transition: all 0.3s;
            box-shadow: 0 4px 10px rgba(52, 152, 219, 0.2);
            font-size: 0.95rem;
        }
        .nav-item:hover {
            transform: translateX(5px);
            box-shadow: 0 8px 18px rgba(52, 152, 219, 0.4);
        }
        .nav-icon { font-size: 1.1rem; }
        
        /* Global call section */
        .global-call-section {
            padding: 80px 30px;
            background: linear-gradient(135deg, #f0f7ff, #e3f2fd);
        }
        .section-title {
            text-align: center;
            font-size: 2.5rem;
            color: var(--navy-blue);
            margin-bottom: 50px;
        }
        .call-to-action-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            max-width: 1300px;
            margin: 0 auto;
        }
        .call-card {
            background: white;
            border-radius: 20px;
            padding: 35px;
            box-shadow: 0 15px 35px rgba(10, 36, 99, 0.1);
            border: 2px solid transparent;
            transition: all 0.4s;
            text-align: center;
            display: flex;
            flex-direction: column;
        }
        .call-card:hover {
            transform: translateY(-10px);
            border-color: var(--accent-gold);
            box-shadow: 0 25px 50px rgba(10, 36, 99, 0.15);
        }
        .call-icon {
            font-size: 3rem;
            margin-bottom: 20px;
        }
        .call-card h3 {
            color: var(--navy-blue);
            font-size: 1.6rem;
            margin-bottom: 15px;
        }
        .call-card p {
            color: #555;
            line-height: 1.7;
            flex: 1;
            margin-bottom: 20px;
        }
        .call-highlight {
            background: rgba(212, 175, 55, 0.1);
            border-left: 4px solid var(--accent-gold);
            padding: 15px;
            border-radius: 10px;
            margin-top: 15px;
            font-size: 0.95rem;
            color: #333;
            text-align: left;
        }
        
        /* Stats counter */
        .stats-section {
            padding: 50px 30px;
            background: white;
        }
        .stats-container {
            max-width: 1300px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 20px;
        }
        .stat-box {
            background: linear-gradient(135deg, #ffffff, #f0f7ff);
            border-radius: 18px;
            padding: 25px;
            text-align: center;
            border: 2px solid #e2e8f0;
            transition: all 0.4s;
            box-shadow: 0 8px 20px rgba(10, 36, 99, 0.05);
        }
        .stat-box:hover {
            transform: translateY(-8px);
            border-color: var(--soft-blue);
            box-shadow: 0 15px 30px var(--card-shadow);
        }
        .stat-number {
            font-size: 2.8rem;
            font-weight: 800;
            color: var(--navy-blue);
            display: block;
            line-height: 1;
            margin-bottom: 10px;
        }
        .stat-label {
            color: #555;
            font-size: 0.95rem;
            line-height: 1.5;
            min-height: 45px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        /* Research articles section */
        .research-section {
            padding: 80px 30px;
            background: white;
        }
        .research-tabs {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 40px;
            justify-content: center;
        }
        .tab-btn {
            padding: 15px 30px;
            background: #f0f7ff;
            border: none;
            border-radius: 15px;
            font-size: 1.1rem;
            font-weight: 600;
            color: var(--navy-blue);
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        .tab-btn:hover {
            background: var(--soft-blue);
            color: white;
        }
        .tab-btn.active {
            background: linear-gradient(135deg, var(--navy-blue), var(--deep-teal));
            color: white;
            box-shadow: 0 8px 20px rgba(10, 36, 99, 0.2);
        }
        .tab-icon { font-size: 1.3rem; }
        .tab-content {
            display: none;
            animation: fadeIn 0.5s ease;
        }
        .tab-content.active {
            display: block;
        }
        .research-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }
        .research-card {
            background: #f8fafc;
            border-radius: 20px;
            padding: 30px;
            border: 1px solid #e2e8f0;
            transition: all 0.4s;
            height: 100%;
            display: flex;
            flex-direction: column;
        }
        .research-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(10, 36, 99, 0.1);
            border-color: var(--soft-blue);
        }
        .research-card-header {
            margin-bottom: 20px;
            padding-bottom: 15px;
            border-bottom: 2px solid #e2e8f0;
        }
        .research-card-title {
            font-size: 1.4rem;
            color: var(--navy-blue);
            margin-bottom: 10px;
            line-height: 1.4;
        }
        .research-card-meta {
            display: flex;
            justify-content: space-between;
            font-size: 0.9rem;
            color: #666;
        }
        .research-card-date { font-weight: 600; }
        .research-card-keywords {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin: 15px 0;
        }
        .keyword {
            background: rgba(52, 152, 219, 0.1);
            color: var(--deep-teal);
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
        }
        .research-card-body {
            flex: 1;
            color: #555;
            line-height: 1.7;
            margin-bottom: 20px;
        }
        .research-card-footer {
            margin-top: auto;
            padding-top: 15px;
            border-top: 1px dashed #ddd;
            text-align: right;
            font-style: italic;
            color: #777;
            font-size: 0.9rem;
        }
        .request-ppt-btn {
            background: linear-gradient(135deg, var(--literary-purple), #8A63B5);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 10px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            margin-top: 15px;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }
        .request-ppt-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(106, 76, 147, 0.3);
        }
        
        /* Daily notes */
        .notes-section {
            padding: 80px 30px;
            background: #f8fafc;
        }
        .timeline {
            max-width: 900px;
            margin: 50px auto;
            position: relative;
        }
        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 4px;
            background: linear-gradient(to bottom, var(--soft-blue), var(--literary-purple));
            border-radius: 2px;
        }
        .timeline-item {
            margin-bottom: 40px;
            position: relative;
            width: 45%;
        }
        .timeline-item:nth-child(odd) {
            margin-left: 55%;
        }
        .timeline-item:nth-child(even) {
            margin-left: 0;
            margin-right: 55%;
        }
        .timeline-date {
            background: var(--navy-blue);
            color: white;
            padding: 8px 20px;
            border-radius: 20px;
            font-weight: 600;
            display: inline-block;
            margin-bottom: 10px;
        }
        .timeline-content {
            background: white;
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.05);
            border: 1px solid #e2e8f0;
        }
        .timeline-content h3 {
            color: var(--deep-teal);
            margin-bottom: 10px;
        }
        
        /* Article slideshow */
        .slideshow-section {
            padding: 70px 30px;
            background: white;
        }
        .slideshow-container {
            max-width: 1000px;
            margin: 40px auto;
            border-radius: 22px;
            overflow: hidden;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.18);
            position: relative;
        }
        .slides-wrapper {
            display: flex;
            transition: transform 0.4s ease;
            direction: ltr;
        }
        .slide-item {
            min-width: 100%;
            height: 400px;
            background: #1e293b;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .slide-item img {
            max-width: 85%;
            max-height: 85%;
            object-fit: contain;
            border-radius: 8px;
        }
        .slide-controls {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 10px;
        }
        .slide-dot {
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.5);
            cursor: pointer;
            transition: all 0.3s;
        }
        .slide-dot.active {
            background: white;
            transform: scale(1.3);
        }
        
        /* Books slideshow */
        .books-slideshow {
            padding: 70px 30px;
            background: linear-gradient(135deg, #f9f5ff, #f0ebfa);
        }
        .books-slider {
            max-width: 1100px;
            margin: 40px auto;
            overflow: hidden;
            border-radius: 22px;
            box-shadow: 0 20px 40px rgba(106, 76, 147, 0.18);
        }
        .books-track {
            display: flex;
            transition: transform 0.5s ease;
            direction: ltr;
        }
        .book-slide {
            min-width: 25%;
            padding: 15px;
        }
        .book-item {
            background: white;
            border-radius: 18px;
            overflow: hidden;
            box-shadow: 0 12px 25px rgba(0, 0, 0, 0.1);
            height: 320px;
            display: flex;
            flex-direction: column;
        }
        .book-cover {
            height: 180px;
            background: var(--literary-purple);
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }
        .book-cover img {
            max-width: 75%;
            max-height: 75%;
            object-fit: contain;
            border-radius: 5px;
        }
        .book-info {
            padding: 20px;
            flex: 1;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }
        .book-title {
            color: var(--literary-purple);
            font-size: 1.2rem;
            font-weight: 700;
            margin-bottom: 8px;
        }
        .book-desc {
            color: #555;
            font-size: 0.9rem;
            line-height: 1.5;
        }
        .book-status {
            color: #666;
            font-size: 0.85rem;
            font-style: italic;
            margin-top: 10px;
            text-align: right;
        }
        
        /* Investment section */
        .investment-section {
            padding: 70px 30px;
            background: linear-gradient(135deg, var(--navy-blue), var(--deep-teal));
            color: white;
            text-align: center;
        }
        .investment-content {
            max-width: 900px;
            margin: 0 auto;
        }
        .investment-content h2 {
            font-size: 2.3rem;
            margin-bottom: 20px;
        }
        .investment-text {
            font-size: 1.2rem;
            line-height: 1.7;
            margin-bottom: 25px;
            opacity: 0.95;
        }
        .highlight-box {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 20px;
            border-left: 4px solid var(--accent-gold);
            margin-top: 20px;
            font-size: 1.1rem;
        }
        
        /* PowerPoint modal */
        .modal {
            display: none;
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background: rgba(0,0,0,0.7);
            z-index: 2000;
            align-items: center;
            justify-content: center;
        }
        .modal.active { display: flex; }
        .modal-content {
            background: white;
            border-radius: 20px;
            padding: 40px;
            max-width: 500px;
            width: 90%;
            text-align: center;
            box-shadow: 0 25px 50px rgba(0,0,0,0.3);
        }
        .modal-icon { font-size: 4rem; color: var(--accent-gold); margin-bottom: 20px; }
        .modal h3 { color: var(--navy-blue); margin-bottom: 15px; }
        .modal p { color: #555; line-height: 1.7; margin-bottom: 25px; }
        .modal-close {
            background: var(--navy-blue);
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 10px;
            cursor: pointer;
            font-weight: 600;
        }
        .modal-contact {
            background: var(--accent-gold);
            color: var(--navy-blue);
            margin-left: 10px;
        }
        
        /* Admin panel (hidden) */
        .admin-panel-section {
            padding: 50px 30px;
            background: #f0f7ff;
            display: none;
        }
        .admin-panel {
            max-width: 800px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 20px 40px rgba(10, 36, 99, 0.1);
        }
        .admin-form input, .admin-form textarea, .admin-form select {
            width: 100%;
            padding: 15px;
            margin-bottom: 20px;
            border: 2px solid #e2e8f0;
            border-radius: 10px;
            font-family: inherit;
            font-size: 1rem;
        }
        .admin-form textarea { min-height: 150px; resize: vertical; }
        .admin-submit {
            background: linear-gradient(135deg, var(--navy-blue), var(--deep-teal));
            color: white;
            border: none;
            padding: 15px 40px;
            border-radius: 10px;
            font-weight: 600;
            cursor: pointer;
            font-size: 1.1rem;
        }
        
        /* Final bar */
        .final-bar {
            background: linear-gradient(90deg, var(--navy-blue), var(--literary-purple));
            padding: 18px 0;
            overflow: hidden;
            margin-top: 50px;
        }
        .bar-content {
            display: flex;
            animation: scrollRight 35s linear infinite;
            white-space: nowrap;
        }
        .bar-text {
            font-size: 1.3rem;
            color: white;
            font-weight: 600;
            padding: 0 40px;
            display: inline-block;
        }
        @keyframes scrollRight {
            0% { transform: translateX(0); }
            100% { transform: translateX(50%); }
        }
        
        /* Footer */
        footer {
            background: var(--navy-blue);
            color: white;
            padding: 50px 30px;
            text-align: center;
        }
        .footer-content {
            max-width: 1000px;
            margin: 0 auto;
        }
        .footer-content h3 {
            font-size: 1.8rem;
            margin-bottom: 35px;
        }
        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
            margin-bottom: 40px;
        }
        .footer-col div:first-child {
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: 12px;
        }
        .copyright {
            color: rgba(255,255,255,0.7);
            font-size: 0.9rem;
            margin-top: 30px;
            padding-top: 20px;
            border-top: 1px solid rgba(255,255,255,0.1);
        }
        
        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        /* Responsive */
        @media (max-width: 1100px) {
            .header-container { grid-template-columns: 1fr; }
            .vertical-nav { order: -1; margin-bottom: 30px; }
            .stats-container { grid-template-columns: repeat(2, 1fr); }
            .book-slide { min-width: 33.333%; }
            .research-grid { grid-template-columns: repeat(2, 1fr); }
            .call-to-action-grid { grid-template-columns: repeat(2, 1fr); }
        }
        @media (max-width: 768px) {
            .main-header, .global-call-section, .research-section, .notes-section { padding: 30px 20px; }
            .profile-section { padding: 25px; }
            .profile-img-container { flex-direction: column; text-align: center; gap: 20px; }
            .profile-img { width: 160px; height: 160px; }
            .stats-container { grid-template-columns: 1fr; }
            .book-slide { min-width: 50%; }
            .slide-item { height: 320px; }
            .section-title { font-size: 2rem; }
            .research-grid { grid-template-columns: 1fr; }
            .tab-btn { padding: 12px 20px; font-size: 1rem; }
            .call-to-action-grid { grid-template-columns: 1fr; }
            .timeline::before { left: 30px; }
            .timeline-item { width: 100%; margin-left: 0 !important; margin-right: 0 !important; }
        }
        @media (max-width: 480px) {
            .book-slide { min-width: 100%; }
            .nav-item { padding: 12px 16px; font-size: 0.9rem; }
            .stat-number { font-size: 2.3rem; }
            .section-title { font-size: 1.8rem; }
            .lang-switcher { 
                top: 15px; 
                right: 15px; 
                padding: 3px;
            }
            .lang-btn { 
                padding: 8px 16px; 
                font-size: 0.9rem; 
            }
        }
    </style>
</head>
<body>
    <!-- Language button -->
    <div class="lang-switcher">
       <a href="https://ghrezaei1399-code.github.io/ghrezaei1399.github.io/" class="lang-btn">فارسی</a>
    </div>
    
    <!-- Main header -->
    <header class="main-header">
        <div class="header-container">
            <div class="profile-section">
                <div class="profile-img-container">
                    <div class="profile-img">
                        <img src="https://i.postimg.cc/02YrBwDP/%CA%BEks-khwdm2.jpg" alt="Dr. Rezaei">
                    </div>
                    <div class="profile-titles">
                        <h1>Dr. Gholamreza Rezaei</h1>
                        <div class="tagline">
                            Organizational Transformation Architect | AI Theorist | Poet and Writer
                        </div>
                    </div>
                </div>
                <div class="motto-box">
                    <span class="motto">Motto: </span>Combining human wisdom with advanced technology for a secure and prosperous tomorrow
                </div>
            </div>
            
            <nav class="vertical-nav">
                <a href="#global-call" class="nav-item"><span class="nav-icon">🌍</span> Global Call</a>
                <a href="#stats" class="nav-item"><span class="nav-icon">📊</span> Statistics & Achievements</a>
                <a href="#research" class="nav-item"><span class="nav-icon">📄</span> Research Papers</a>
                <a href="#notes" class="nav-item"><span class="nav-icon">📝</span> Daily Notes</a>
                <a href="#books" class="nav-item"><span class="nav-icon">📚</span> Literary Works</a>
                <a href="#investment" class="nav-item"><span class="nav-icon">🔒</span> Collaboration & Investment</a>
                <a href="#contact" class="nav-item"><span class="nav-icon">📞</span> Contact</a>
            </nav>
        </div>
    </header>
    
    <!-- Global call section -->
    <section id="global-call" class="global-call-section">
        <h2 class="section-title">Global Collaboration Call</h2>
        <div class="call-to-action-grid">
            <div class="call-card">
                <div class="call-icon">🏛️</div>
                <h3>Nations & Governments</h3>
                <p>Implementation of national digital transformation and human-centric AI plans. Over 10 ready-to-execute projects with complete annexes.</p>
                <div class="call-highlight">Participation in national mega-projects</div>
            </div>
            <div class="call-card">
                <div class="call-icon">🏢</div>
                <h3>Technology Companies</h3>
                <p>Purchase or partnership in implementing transformational frameworks like Mobile Quality Organization (IMQO) and Global Entrepreneurial Nexus (GENF).</p>
                <div class="call-highlight">Operational plans ready for implementation</div>
            </div>
            <div class="call-card">
                <div class="call-icon">🤝</div>
                <h3>Impact Investors</h3>
                <p>Investment in ethical AI-based business models and cultural engineering. Guaranteed return on investment.</p>
                <div class="call-highlight">16 projects with complete financial analysis</div>
            </div>
            <div class="call-card">
                <div class="call-icon">🌐</div>
                <h3>International Forums</h3>
                <p>Collaboration with entities like UNESCO, WEF and IEEE for expanding theoretical frameworks and global standards.</p>
                <div class="call-highlight">Collaboration in standard development</div>
            </div>
            <div class="call-card">
                <div class="call-icon">👥</div>
                <h3>Executive Representatives</h3>
                <p>Granting regional representation for project implementation in Arab, Asian and European countries.</p>
                <div class="call-highlight">Complete training, support and mentoring</div>
            </div>
        </div>
    </section>
    
    <!-- Stats counter -->
    <section id="stats" class="stats-section">
        <div class="stats-container">
            <div class="stat-box">
                <span class="stat-number">18</span>
                <div class="stat-label">Scientific-theoretical articles with international registration (DOI)</div>
            </div>
            <div class="stat-box">
                <span class="stat-number">2</span>
                <div class="stat-label">Analytical political-social articles</div>
            </div>
            <div class="stat-box">
                <span class="stat-number">33+</span>
                <div class="stat-label">New theories in AI and organizational transformation</div>
            </div>
            <div class="stat-box">
                <span class="stat-number">4</span>
                <div class="stat-label">Published poetry books</div>
            </div>
            <div class="stat-box">
                <span class="stat-number">1</span>
                <div class="stat-label">Published story book</div>
            </div>
            <div class="stat-box">
                <span class="stat-number">13</span>
                <div class="stat-label">Story books pending publication license</div>
            </div>
            <div class="stat-box">
                <span class="stat-number">1</span>
                <div class="stat-label">Smart writing book</div>
            </div>
            <div class="stat-box">
                <span class="stat-number">1</span>
                <div class="stat-label">Book in progress (Organizational Corruption)</div>
            </div>
        </div>
    </section>
    
    <!-- Research articles section -->
    <section id="research" class="research-section">
        <h2 class="section-title">Scientific-Theoretical Research Papers</h2>
        
        <div class="research-tabs">
            <button class="tab-btn active" data-tab="tab1">
                <span class="tab-icon">🤖</span> Human-Centric AI
            </button>
            <button class="tab-btn" data-tab="tab2">
                <span class="tab-icon">🏢</span> Smart Organizational Transformation
            </button>
            <button class="tab-btn" data-tab="tab3">
                <span class="tab-icon">🌍</span> Digital Cultural Engineering
            </button>
            <button class="tab-btn" data-tab="tab4">
                <span class="tab-icon">🧠</span> Cognitive-Social Theories
            </button>
        </div>
        
        <!-- Tab 1: Human-Centric AI -->
        <div id="tab1" class="tab-content active">
            <div class="research-grid">
                <div class="research-card">
                    <div class="research-card-header">
                        <h3 class="research-card-title">Human-AI Intertwining Framework</h3>
                        <div class="research-card-meta">
                            <span class="research-card-date">December 2025</span>
                            <span>Paper 11</span>
                        </div>
                    </div>
                    <div class="research-card-keywords">
                        <span class="keyword">Personal AI</span>
                        <span class="keyword">Cultural Protection</span>
                    </div>
                    <div class="research-card-body">
                        A framework for creating loyal digital assistants under complete control of cultural reformer users.
                    </div>
                    <button class="request-ppt-btn" onclick="location.href='#contact'">📥 Request Presentation File (PPT)</button>
                    <div class="research-card-footer">Operational framework for cultural engineers</div>
                </div>
                
                <div class="research-card">
                    <div class="research-card-header">
                        <h3 class="research-card-title">Co-evolution Paradigm</h3>
                        <div class="research-card-meta">
                            <span class="research-card-date">December 2025</span>
                            <span>Paper 8</span>
                        </div>
                    </div>
                    <div class="research-card-keywords">
                        <span class="keyword">Co-evolution</span>
                        <span class="keyword">Inherent Safety</span>
                    </div>
                    <div class="research-card-body">
                        Introducing a fundamental alternative architecture with three integrated principles for secure AI development.
                    </div>
                    <button class="request-ppt-btn" onclick="location.href='#contact'">📥 Request Presentation File (PPT)</button>
                    <div class="research-card-footer">New paradigm for secure development</div>
                </div>
            </div>
        </div>
        
        <!-- Tab 2: Smart Organizational Transformation -->
        <div id="tab2" class="tab-content">
            <div class="research-grid">
                <div class="research-card">
                    <div class="research-card-header">
                        <h3 class="research-card-title">Smart Transformative Organization</h3>
                        <div class="research-card-meta">
                            <span class="research-card-date">December 2025</span>
                            <span>Paper 3</span>
                        </div>
                    </div>
                    <div class="research-card-keywords">
                        <span class="keyword">Organizational Transformation</span>
                        <span class="keyword">Dynamic Intelligence</span>
                    </div>
                    <div class="research-card-body">
                        A roadmap for transforming digitalization into a "cultural transformation journey" serving collective flourishing.
                    </div>
                    <button class="request-ppt-btn" onclick="location.href='#contact'">📥 Request Presentation File (PPT)</button>
                    <div class="research-card-footer">Response to 70% project failure rate</div>
                </div>
            </div>
        </div>
        
        <!-- Tab 3: Digital Cultural Engineering -->
        <div id="tab3" class="tab-content">
            <div class="research-grid">
                <div class="research-card">
                    <div class="research-card-header">
                        <h3 class="research-card-title">National "Enlightenment Companions Smartization" Plan</h3>
                        <div class="research-card-meta">
                            <span class="research-card-date">December 2025</span>
                            <span>Paper 1</span>
                        </div>
                    </div>
                    <div class="research-card-keywords">
                        <span class="keyword">Cultural Engineering</span>
                        <span class="keyword">Enlightenment Companions</span>
                    </div>
                    <div class="research-card-body">
                        Introducing the operational framework of national plan with "Enlightenment Companions Smartization Theory".
                    </div>
                    <button class="request-ppt-btn" onclick="location.href='#contact'">📥 Request Presentation File (PPT)</button>
                    <div class="research-card-footer">Local response to cultural governance crisis</div>
                </div>
            </div>
        </div>
        
        <!-- Tab 4: Cognitive-Social Theories -->
        <div id="tab4" class="tab-content">
            <div class="research-grid">
                <div class="research-card">
                    <div class="research-card-header">
                        <h3 class="research-card-title">Digital-Activism Disconnect Theoretical Framework</h3>
                        <div class="research-card-meta">
                            <span class="research-card-date">December 2025</span>
                            <span>Paper 6</span>
                        </div>
                    </div>
                    <div class="research-card-keywords">
                        <span class="keyword">Digital Disconnect</span>
                        <span class="keyword">Social Activism</span>
                    </div>
                    <div class="research-card-body">
                        Analysis of the paradox of decreasing collective impact despite unprecedented access to technology.
                    </div>
                    <button class="request-ppt-btn" onclick="location.href='#contact'">📥 Request Presentation File (PPT)</button>
                    <div class="research-card-footer">Integrated framework for analyzing activism crisis</div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Daily notes -->
    <section id="notes" class="notes-section">
        <h2 class="section-title">Dr. Rezaei's Daily Notes</h2>
        <div class="timeline">
            <div class="timeline-item">
                <div class="timeline-date">December 30, 2025</div>
                <div class="timeline-content">
                    <h3>Daily Note: Replacement, Bribery, Threat No Longer Work</h3>
                    <p>Analysis of power discourse and resistance transformation in digital age...</p>
                </div>
            </div>
            <div class="timeline-item">
                <div class="timeline-date">December 29, 2025</div>
                <div class="timeline-content">
                    <h3>Daily Note: Unity in the Streets</h3>
                    <p>Necessity of redefining collective action in public space...</p>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Article slideshow (Images) -->
    <section class="slideshow-section">
        <h2 class="section-title">Scientific Paper Slides</h2>
        <div class="slideshow-container">
            <div class="slides-wrapper" id="articlesSlides"></div>
            <div class="slide-controls" id="articlesDots"></div>
        </div>
    </section>
    
    <!-- Books slideshow -->
    <section id="books" class="books-slideshow">
        <h2 class="section-title">Published Literary and Poetry Works</h2>
        <div class="books-slider">
            <div class="books-track" id="booksTrack"></div>
        </div>
        <p style="text-align: center; color: #666; margin-top: 30px; font-size: 1rem; max-width: 800px; margin-left: auto; margin-right: auto;">
            <strong>Note:</strong> These are part of published works from "Universe of 20,000 composed verses". Other literary works are in final editing and licensing process.
        </p>
    </section>
    
    <!-- Investment section -->
    <section id="investment" class="investment-section">
        <div class="investment-content">
            <h2>Collaboration & Investment</h2>
            <p class="investment-text">
                <strong>16 complete projects with annexes, technical principles, architecture and revenue models ready for presentation.</strong><br>
                Detailed financial analyses, ROI documentation and executive plans for strategic collaborations.
            </p>
            <div class="highlight-box">
                <strong>Note:</strong> All documents and analyses are provided only after signing NDA and personal approval.
            </div>
        </div>
    </section>
    
    <!-- Admin panel (hidden) -->
    <section id="admin-panel" class="admin-panel-section">
        <div class="admin-panel">
            <h2>Content Management Panel</h2>
            <form class="admin-form" id="adminForm">
                <input type="text" id="itemTitle" placeholder="Title (English)" required>
                <textarea id="itemContent" placeholder="Content (English)" required></textarea>
                <select id="itemType">
                    <option value="article">Article</option>
                    <option value="book">Book</option>
                    <option value="note">Daily Note</option>
                    <option value="stat">Statistic</option>
                </select>
                <input type="text" id="itemDate" placeholder="Date (Example: 2025-12-30)">
                <input type="text" id="itemKeywords" placeholder="Keywords (comma separated)">
                <button type="submit" class="admin-submit">Save & Publish</button>
            </form>
        </div>
    </section>
    
    <!-- PowerPoint request modal -->
    <div class="modal" id="pptModal">
        <div class="modal-content">
            <div class="modal-icon">🔒</div>
            <h3>Presentation File Request</h3>
            <p>The complete presentation file (PowerPoint) of this research will be provided after official request registration and personal approval of Dr. Rezaei.</p>
            <p>Please send your request through the contact section.</p>
            <div style="margin-top: 30px;">
                <button class="modal-close modal-contact" onclick="location.href='#contact'">📧 Send Request</button>
                <button class="modal-close" onclick="closeModal()">Close</button>
            </div>
        </div>
    </div>
    
    <!-- Final bar -->
    <div class="final-bar">
        <div class="bar-content">
            <span class="bar-text">Building frameworks that neither fuel fear nor naivety • Combining wisdom with technology for a secure and prosperous future • From ancient poetry to advanced artificial intelligence • Organizational transformation with cultural authenticity • Looking to the future, rooted in the past • Every ending is a beginning for evolution • 16 ready-to-execute projects • Universe of 20,000 verses • Internationally registered research • 18 scientific-theoretical articles • New paradigms of vibrational organization • Global collaboration call</span>
            <span class="bar-text">Building frameworks that neither fuel fear nor naivety • Combining wisdom with technology for a secure and prosperous future • From ancient poetry to advanced artificial intelligence • Organizational transformation with cultural authenticity • Looking to the future, rooted in the past • Every ending is a beginning for evolution • 16 ready-to-execute projects • Universe of 20,000 verses • Internationally registered research • 18 scientific-theoretical articles • New paradigms of vibrational organization • Global collaboration call</span>
        </div>
    </div>
    
    <!-- Footer -->
    <footer id="contact">
        <div class="footer-content">
            <h3>Contact & Collaboration</h3>
            <div class="footer-grid">
                <div class="footer-col">
                    <div>Official Emails</div>
                    <div>ghrezaei1399@gmail.com</div>
                    <div>Gh_rezaei2003@yahoo.com</div>
                </div>
                <div class="footer-col">
                    <div>Research Profile</div>
                    <div>ORCID: 0009-0007-5840-8833</div>
                    <div>LinkedIn: linkedin.com/in/reaei-researcher</div>
                </div>
                <div class="footer-col">
                    <div>Article Access</div>
                    <div>18 registered articles on Zenodo</div>
                    <div>With approval and official request</div>
                </div>
            </div>
            <div class="copyright">
                © All rights reserved - Dr. Gholamreza Rezaei - Design based on combination of human wisdom and advanced technology
            </div>
        </div>
    </footer>
    
    <script>
        // Article slides data (11 images)
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
        
        // Books data (18 images)
        const booksData = [
            { img: 'https://i.postimg.cc/nr7K5hYW/20240301-203438-(3).jpg', title: 'Voice of Heart', desc: 'Romantic poems 2018' },
            { img: 'https://i.postimg.cc/PJZbc5Qd/20240301-203516-(2).jpg', title: 'Heart Melody', desc: 'Ghazals and Masnavis 2018' },
            { img: 'https://i.postimg.cc/6qRVSpf9/20240301-203539-(2).jpg', title: 'Poetry Collection', desc: 'Selected classical poems' },
            { img: 'https://i.postimg.cc/7h71cZnL/20240301-203802-(2).jpg', title: 'Modern Poetry Collection', desc: 'Contemporary creations' },
            { img: 'https://i.postimg.cc/d3dRXVjD/20240301-204004-(2).jpg', title: 'Waiting for the Axis', desc: 'Innovative story' },
            { img: 'https://i.postimg.cc/pVnBysb0/20240301-204056-(2).jpg', title: 'Smart Writing', desc: 'Educational book' },
            { img: 'https://i.postimg.cc/zDRk3xZ0/20240301-204119-(2).jpg', title: 'Heart Whisper', desc: 'Mystical poems' },
            { img: 'https://i.postimg.cc/L4ZVhxKb/20240301-204156-(2).jpg', title: 'Heart Song', desc: 'Social poems' },
            { img: 'https://i.postimg.cc/MK2mB1zG/20240301-204217.jpg', title: 'Voice of Heart 2', desc: 'Selected poems' },
            { img: 'https://i.postimg.cc/jdHQ4Cjy/20240301-204444.jpg', title: 'Heart Melody 2', desc: 'New ghazals' },
            { img: 'https://i.postimg.cc/7Y3MnbLM/20240301-205811.jpg', title: 'Classic Poetry Collection', desc: 'Classical poetry recreation' },
            { img: 'https://i.postimg.cc/BQTcBtvC/20240301-205901.jpg', title: 'Short Stories', desc: 'Fictional works' },
            { img: 'https://i.postimg.cc/65rLfTQ0/20240301-210721-(2).jpg', title: 'Advanced Smart Writing', desc: 'Volume 2' },
            { img: 'https://i.postimg.cc/kg7N19VF/20240301-211151-(2).jpg', title: 'Waiting for the Axis 2', desc: 'Story continuation' },
            { img: 'https://i.postimg.cc/CxwCPYZm/20240301-211220-(2).jpg', title: 'Social Poems 2', desc: 'Society critique' },
            { img: 'https://i.postimg.cc/YCtNnk4V/20240301-211256-(2).jpg', title: 'Mysticism and AI', desc: 'Philosophical integration' },
            { img: 'https://i.postimg.cc/pLPQGx94/20240301-211527-(2).jpg', title: 'Organizational Transformation in Poetry', desc: 'New perspective' },
            { img: 'https://i.postimg.cc/pLPQGx93/20240301-211628-(2).jpg', title: 'Thousand Verses from Universe', desc: 'Selection from 20,000 verses' }
        ];
        
        // 1. Article slideshow
        let currentArticleSlide = 0;
        let articleInterval;
        function initArticleSlideshow() {
            const slidesContainer = document.getElementById('articlesSlides');
            const dotsContainer = document.getElementById('articlesDots');
            
            articleSlides.forEach((slide, index) => {
                const slideDiv = document.createElement('div');
                slideDiv.className = 'slide-item';
                slideDiv.innerHTML = `<img src="${slide}" alt="Paper ${index + 1}">`;
                slidesContainer.appendChild(slideDiv);
                
                const dot = document.createElement('div');
                dot.className = `slide-dot ${index === 0 ? 'active' : ''}`;
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
                });
            }
            
            function resetArticleInterval() {
                clearInterval(articleInterval);
                articleInterval = setInterval(() => {
                    currentArticleSlide = (currentArticleSlide + 1) % articleSlides.length;
                    updateArticleSlideshow();
                }, 3000);
            }
            
            updateArticleSlideshow();
            resetArticleInterval();
        }
        
        // 2. Books slideshow
        let currentBookSlide = 0;
        let bookInterval;
        function initBooksSlideshow() {
            const track = document.getElementById('booksTrack');
            
            // پاک کردن محتوای قبلی
            track.innerHTML = '';
            
            // فقط یک بار اضافه کن
            booksData.forEach((book, index) => {
                const slide = document.createElement('div');
                slide.className = 'book-slide';
                slide.innerHTML = `
                    <div class="book-item">
                        <div class="book-cover">
                            <img src="${book.img}" alt="${book.title}">
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
            
            // ریست اینتروال قبلی
            clearInterval(bookInterval);
            
            bookInterval = setInterval(() => {
                currentBookSlide++;
                const totalSlides = booksData.length;
                const slideWidth = 100 / 4; // 4 کتاب در هر صفحه
                
                track.style.transform = `translateX(-${currentBookSlide * slideWidth}%)`;
                
                // اگر به انتها رسید، برگرد به اول
                if (currentBookSlide >= totalSlides - 3) {
                    setTimeout(() => {
                        track.style.transition = 'none';
                        currentBookSlide = 0;
                        track.style.transform = 'translateX(0)';
                        setTimeout(() => {
                            track.style.transition = 'transform 0.5s ease';
                        }, 50);
                    }, 500);
                }
            }, 2500);
        }
        
        // 3. Stats counter
        function animateStats() {
            const stats = document.querySelectorAll('.stat-number');
            stats.forEach(stat => {
                const target = parseInt(stat.textContent);
                let current = 0;
                const increment = target / 50;
                
                const timer = setInterval(() => {
                    current += increment;
                    if (current >= target) {
                        current = target;
                        clearInterval(timer);
                    }
                    stat.textContent = Math.floor(current);
                }, 25);
            });
        }
        
        // 4. Tab system
        function initResearchTabs() {
            const tabBtns = document.querySelectorAll('.tab-btn');
            const tabContents = document.querySelectorAll('.tab-content');
            
            tabBtns.forEach(btn => {
                btn.addEventListener('click', () => {
                    const tabId = btn.getAttribute('data-tab');
                    tabBtns.forEach(b => b.classList.remove('active'));
                    tabContents.forEach(c => c.classList.remove('active'));
                    btn.classList.add('active');
                    document.getElementById(tabId).classList.add('active');
                });
            });
        }
        
        // 5. PowerPoint modal
        function initPPTButtons() {
            const modal = document.getElementById('pptModal');
            
            window.closeModal = function() {
                modal.classList.remove('active');
            }
            
            modal.addEventListener('click', function(e) {
                if (e.target === modal) closeModal();
            });
        }
        
        // 6. Smooth scroll
        function initSmoothScroll() {
            document.querySelectorAll('.nav-item').forEach(item => {
                item.addEventListener('click', function(e) {
                    e.preventDefault();
                    const targetId = this.getAttribute('href');
                    const targetElement = document.querySelector(targetId);
                    if (targetElement) {
                        targetElement.scrollIntoView({ 
                            behavior: 'smooth', 
                            block: 'start' 
                        });
                    }
                });
            });
        }
        
        // 7. Admin panel (demo)
        document.getElementById('adminForm').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Admin panel is under development. In final version, this form will save and display content.');
        });
        
        // Run all
        window.addEventListener('DOMContentLoaded', () => {
            initArticleSlideshow();
            initBooksSlideshow();
            initResearchTabs();
            initPPTButtons();
            initSmoothScroll();
            setTimeout(animateStats, 400);
        });
    </script>
</body>
</html>

