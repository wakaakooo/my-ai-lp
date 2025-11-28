<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>With AI | 法人向けAI人材育成プログラム</title>
    <meta name="description" content="中小企業のAI導入を成功させる、実践型動画プログラム。たった一つの教材で組織のDXを加速させます。">
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@400;500;700&display=swap" rel="stylesheet">
    
    <style>
        /* =========================================
           Variables & Reset
           ========================================= */
        :root {
            --color-primary: #FFD43B;       /* アクセント（黄色） */
            --color-primary-hover: #eebb00; 
            --color-text-main: #111111;
            --color-text-sub: #555555;
            --color-bg-base: #F5F7FB;       /* 薄いブルーグレー */
            --color-bg-white: #FFFFFF;
            --color-bg-dark: #020617;       /* 濃紺 */
            --color-border: #E2E8F0;
            
            --font-family: "Noto Sans JP", sans-serif;
            
            --max-width: 1200px;
            --header-height: 80px;
            --radius-card: 16px;
            --radius-btn: 8px;
            
            --easing: cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
            scroll-padding-top: var(--header-height);
        }

        body {
            font-family: var(--font-family);
            color: var(--color-text-main);
            background-color: var(--color-bg-base);
            line-height: 1.7;
            -webkit-font-smoothing: antialiased;
        }

        a {
            text-decoration: none;
            color: inherit;
            transition: opacity 0.3s;
        }

        ul {
            list-style: none;
        }

        img {
            max-width: 100%;
            height: auto;
            vertical-align: bottom;
        }

        /* =========================================
           Utilities & Components
           ========================================= */
        .container {
            width: 100%;
            max-width: var(--max-width);
            margin: 0 auto;
            padding: 0 24px;
        }

        .section {
            padding: 100px 0;
        }
        
        @media (max-width: 768px) {
            .section { padding: 60px 0; }
        }

        .section--white { background-color: var(--color-bg-white); }
        .section--gray { background-color: var(--color-bg-base); }
        .section--dark { background-color: var(--color-bg-dark); color: white; }

        .section__header {
            text-align: center;
            max-width: 800px;
            margin: 0 auto 60px;
        }

        .section__title {
            font-size: 2rem; /* 32px */
            font-weight: 700;
            margin-bottom: 16px;
            line-height: 1.4;
        }
        
        .section__subtitle {
            font-size: 1.1rem;
            color: var(--color-text-sub);
        }
        
        .section--dark .section__subtitle {
            color: #cbd5e1;
        }

        /* Buttons */
        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            border-radius: var(--radius-btn);
            padding: 14px 32px;
            font-size: 1rem;
            cursor: pointer;
            transition: transform 0.2s var(--easing), box-shadow 0.2s var(--easing), background-color 0.2s;
            line-height: 1;
        }

        .btn--primary {
            background-color: var(--color-primary);
            color: var(--color-text-main);
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
        }

        .btn--primary:hover {
            background-color: var(--color-primary-hover);
            transform: scale(1.03);
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }

        .btn--text {
            background: transparent;
            text-decoration: underline;
            padding: 8px 16px;
            font-weight: 500;
            color: white; /* ヒーロー内での使用を想定 */
        }
        
        .btn--text:hover {
            opacity: 0.8;
        }

        /* Cards */
        .card {
            background: var(--color-bg-white);
            border-radius: var(--radius-card);
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05), 0 2px 4px -1px rgba(0, 0, 0, 0.03);
            padding: 32px;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .card:hover {
            transform: translateY(-4px);
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
        }

        /* Animation Utilities */
        .fade-in-up {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s var(--easing), transform 0.8s var(--easing);
        }

        .fade-in-up.is-visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* =========================================
           1. Header
           ========================================= */
        .header {
            height: var(--header-height);
            background-color: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;
            border-bottom: 1px solid var(--color-border);
        }

        .header__inner {
            display: flex;
            align-items: center;
            justify-content: space-between;
            height: 100%;
        }

        .header__logo {
            font-size: 1.5rem;
            font-weight: 700;
            letter-spacing: -0.02em;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .header__logo span {
            color: #2563EB; /* 青系で知的な印象を付加 */
        }

        .header__nav {
            display: flex;
            align-items: center;
            gap: 32px;
        }

        .header__link {
            font-size: 0.95rem;
            font-weight: 500;
            color: var(--color-text-main);
        }
        
        .header__link:hover {
            color: #2563EB;
        }

        .hamburger {
            display: none;
            flex-direction: column;
            gap: 6px;
            cursor: pointer;
            border: none;
            background: none;
        }
        
        .hamburger span {
            width: 24px;
            height: 2px;
            background-color: var(--color-text-main);
            transition: 0.3s;
        }

        @media (max-width: 900px) {
            .header__nav {
                position: fixed;
                top: var(--header-height);
                left: 0;
                width: 100%;
                height: calc(100vh - var(--header-height));
                background-color: white;
                flex-direction: column;
                padding: 40px 24px;
                gap: 24px;
                transform: translateX(100%);
                transition: transform 0.3s ease;
                border-top: 1px solid var(--color-border);
            }
            
            .header__nav.is-open {
                transform: translateX(0);
            }

            .hamburger {
                display: flex;
            }
        }

        /* =========================================
           2. Hero Section
           ========================================= */
        .hero {
            position: relative;
            padding: 160px 0 100px;
            background: linear-gradient(rgba(2, 6, 23, 0.8), rgba(2, 6, 23, 0.7)), url('https://images.unsplash.com/photo-1551434678-e076c223a692?q=80&w=2070&auto=format&fit=crop');
            background-size: cover;
            background-position: center;
            color: white;
            min-height: 80vh;
            display: flex;
            align-items: center;
        }

        .hero__container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }

        .hero__content {
            max-width: 600px;
        }

        .hero__title {
            font-size: 2.5rem;
            line-height: 1.3;
            font-weight: 700;
            margin-bottom: 24px;
        }

        .hero__description {
            font-size: 1.1rem;
            line-height: 1.8;
            margin-bottom: 40px;
            color: #e2e8f0;
        }

        .hero__actions {
            display: flex;
            flex-direction: column;
            gap: 16px;
            align-items: flex-start;
        }

        .hero__video-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(8px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: var(--radius-card);
            padding: 24px;
            display: flex;
            flex-direction: column;
            gap: 16px;
            position: relative;
            overflow: hidden;
        }

        .hero__thumbnail {
            width: 100%;
            aspect-ratio: 16/9;
            background-color: #000;
            border-radius: 8px;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .play-icon {
            width: 60px;
            height: 60px;
            background: rgba(255, 212, 59, 0.9);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: black;
            font-size: 24px;
        }

        @media (max-width: 900px) {
            .hero__container {
                grid-template-columns: 1fr;
                gap: 40px;
            }
            .hero__title { font-size: 2rem; }
            .hero { padding-top: 120px; }
        }

        /* =========================================
           3. Problem Section
           ========================================= */
        .problem__grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 32px;
        }

        .problem-card {
            text-align: center;
            padding: 40px 24px;
        }

        .problem-card__icon {
            font-size: 3rem;
            margin-bottom: 24px;
            display: inline-block;
        }

        .problem-card__title {
            font-size: 1.25rem;
            font-weight: 700;
            margin-bottom: 16px;
        }

        .problem-card__text {
            color: var(--color-text-sub);
            font-size: 0.95rem;
        }

        @media (max-width: 768px) {
            .problem__grid { grid-template-columns: 1fr; }
        }

        /* =========================================
           4. Solution Section
           ========================================= */
        .solution__container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }

        .solution__list {
            margin: 32px 0 40px;
        }

        .solution__item {
            display: flex;
            align-items: flex-start;
            gap: 16px;
            margin-bottom: 20px;
            font-size: 1.05rem;
            font-weight: 500;
        }

        .check-icon {
            color: #2563EB;
            font-weight: bold;
            flex-shrink: 0;
            margin-top: 4px;
        }

        .solution__image img {
            border-radius: var(--radius-card);
            box-shadow: 0 20px 40px -10px rgba(0, 0, 0, 0.15);
        }

        @media (max-width: 900px) {
            .solution__container { grid-template-columns: 1fr; }
            .solution__image { order: -1; }
        }

        /* =========================================
           5. Who Section
           ========================================= */
        .who__container {
            display: grid;
            grid-template-columns: 1.2fr 0.8fr;
            gap: 40px;
            align-items: center;
        }

        .who__bubbles {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .bubble {
            background: white;
            padding: 20px 24px;
            border-radius: 20px 20px 20px 0;
            box-shadow: 0 2px 8px rgba(0,0,0,0.04);
            font-weight: 500;
            position: relative;
        }

        .bubble::before {
            content: '';
            position: absolute;
            bottom: 0;
            left: -10px;
            width: 20px;
            height: 20px;
            background: white;
            border-radius: 0 0 0 20px;
            z-index: -1;
        }

        .who__image img {
            border-radius: 200px 200px 20px 20px;
            width: 100%;
            height: 400px;
            object-fit: cover;
        }

        @media (max-width: 768px) {
            .who__container { grid-template-columns: 1fr; }
            .who__image { display: none; } /* スマホでは文章優先で画像を隠す等の調整 */
        }

        /* =========================================
           6. What you get Section
           ========================================= */
        .feature__grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 32px;
        }

        .feature-card {
            border: 1px solid var(--color-border);
            position: relative;
            overflow: hidden;
        }
        
        .feature-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 4px;
            height: 100%;
            background-color: var(--color-primary);
        }

        .feature-badge {
            background-color: rgba(255, 212, 59, 0.2);
            color: #9A7D0A;
            padding: 4px 12px;
            border-radius: 100px;
            font-size: 0.8rem;
            font-weight: 700;
            display: inline-block;
            margin-bottom: 16px;
        }

        .feature-card__title {
            font-size: 1.2rem;
            font-weight: 700;
            margin-bottom: 12px;
        }

        /* =========================================
           7. Curriculum Section
           ========================================= */
        .timeline {
            max-width: 800px;
            margin: 0 auto;
        }

        .timeline__item {
            display: flex;
            gap: 24px;
            padding-bottom: 32px;
            position: relative;
        }
        
        .timeline__item:last-child { padding-bottom: 0; }
        
        .timeline__item::before {
            content: '';
            position: absolute;
            left: 19px;
            top: 40px;
            width: 2px;
            height: calc(100% - 40px);
            background-color: var(--color-border);
        }
        
        .timeline__item:last-child::before { display: none; }

        .timeline__number {
            width: 40px;
            height: 40px;
            background-color: var(--color-text-main);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            flex-shrink: 0;
            z-index: 1;
        }

        .timeline__content {
            background: white;
            padding: 20px;
            border-radius: 8px;
            width: 100%;
            box-shadow: 0 1px 3px rgba(0,0,0,0.05);
            border: 1px solid var(--color-border);
        }

        .timeline__title {
            font-weight: 700;
            font-size: 1.1rem;
            margin-bottom: 4px;
        }
        
        .timeline__desc {
            color: var(--color-text-sub);
            font-size: 0.9rem;
        }

        /* =========================================
           8. Case Section
           ========================================= */
        .case__container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }
        
        .step-flow {
            margin-bottom: 40px;
        }
        
        .step-item {
            display: flex;
            align-items: center;
            gap: 16px;
            margin-bottom: 16px;
        }
        
        .step-num {
            font-size: 0.9rem;
            font-weight: 700;
            color: #2563EB;
            background: #EFF6FF;
            padding: 4px 12px;
            border-radius: 4px;
        }
        
        .case-box {
            background: white;
            padding: 32px;
            border-radius: var(--radius-card);
            border-left: 4px solid var(--color-primary);
            margin-top: 40px;
        }

        @media (max-width: 900px) {
            .case__container { grid-template-columns: 1fr; }
        }

        /* =========================================
           9. Pricing Section
           ========================================= */
        .pricing__grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 24px;
            align-items: stretch;
        }

        .pricing-card {
            border: 1px solid var(--color-border);
            padding: 40px 24px;
            text-align: center;
            display: flex;
            flex-direction: column;
            background: white;
        }
        
        .pricing-card--recommend {
            border: 2px solid var(--color-primary);
            position: relative;
            transform: scale(1.05);
            z-index: 2;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }
        
        .recommend-badge {
            position: absolute;
            top: -12px;
            left: 50%;
            transform: translateX(-50%);
            background: var(--color-primary);
            color: black;
            font-size: 0.8rem;
            font-weight: 700;
            padding: 4px 16px;
            border-radius: 20px;
        }

        .pricing-price {
            font-size: 2.5rem;
            font-weight: 700;
            margin: 24px 0;
            color: var(--color-text-main);
        }
        
        .pricing-price span {
            font-size: 1rem;
            font-weight: 400;
            color: var(--color-text-sub);
        }

        .pricing-features {
            text-align: left;
            margin-bottom: 32px;
            flex-grow: 1;
        }
        
        .pricing-features li {
            margin-bottom: 12px;
            padding-left: 20px;
            position: relative;
            font-size: 0.95rem;
            color: var(--color-text-sub);
        }
        
        .pricing-features li::before {
            content: '•';
            position: absolute;
            left: 0;
            color: var(--color-primary);
            font-weight: bold;
        }

        @media (max-width: 900px) {
            .pricing__grid { grid-template-columns: 1fr; max-width: 500px; margin: 0 auto; gap: 40px; }
            .pricing-card--recommend { transform: scale(1); }
        }

        /* =========================================
           10. FAQ Section
           ========================================= */
        .faq__container {
            max-width: 800px;
            margin: 0 auto;
        }

        .faq-item {
            border-bottom: 1px solid var(--color-border);
        }
        
        .faq-item:first-child { border-top: 1px solid var(--color-border); }

        .faq-question {
            width: 100%;
            text-align: left;
            padding: 24px 0;
            background: none;
            border: none;
            font-size: 1.1rem;
            font-weight: 700;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: var(--color-text-main);
        }
        
        .faq-question::after {
            content: '+';
            font-size: 1.5rem;
            font-weight: 400;
            transition: transform 0.3s;
        }
        
        .faq-question.is-open::after {
            transform: rotate(45deg);
        }

        .faq-answer {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease-out;
            color: var(--color-text-sub);
        }
        
        .faq-answer p {
            padding-bottom: 24px;
        }

        /* =========================================
           11. Footer
           ========================================= */
        .footer {
            background-color: var(--color-bg-dark);
            color: white;
            padding: 80px 0 24px;
        }

        .footer__content {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 40px;
            margin-bottom: 60px;
            border-bottom: 1px solid rgba(255,255,255,0.1);
            padding-bottom: 40px;
        }

        .footer__info h3 {
            font-size: 1.5rem;
            margin-bottom: 24px;
            color: white;
        }
        
        .footer__address {
            color: #94a3b8;
            font-size: 0.9rem;
            line-height: 1.8;
        }

        .footer__copy {
            text-align: center;
            font-size: 0.8rem;
            color: #64748b;
        }
    </style>
</head>
<body>

    <!-- 1. ヘッダー -->
    <header class="header">
        <div class="container header__inner">
            <a href="#" class="header__logo">With AI <span>.</span></a>
            
            <nav class="header__nav" id="js-nav">
                <a href="#problem" class="header__link">導入の課題</a>
                <a href="#feature" class="header__link">サービス特徴</a>
                <a href="#curriculum" class="header__link">カリキュラム</a>
                <a href="#pricing" class="header__link">料金</a>
                <a href="#case" class="header__link">事例</a>
                <a href="#contact" class="btn btn--primary">無料相談・デモ</a>
            </nav>

            <button class="hamburger" id="js-hamburger" aria-label="メニュー">
                <span></span>
                <span></span>
                <span></span>
            </button>
        </div>
    </header>

    <main>
        <!-- 2. ファーストビュー（ヒーロー） -->
        <section id="hero" class="hero">
            <div class="container hero__container">
                <div class="hero__content fade-in-up">
                    <h1 class="hero__title">たった1つの動画プログラムで、<br>御社の“AI人材不足”に<br>終止符を。</h1>
                    <p class="hero__description">
                        ツール導入だけでは進まない現場のAI活用。<br>
                        経営層から現場まで「共通言語」を作る、法人特化型AIリスキリング講座。
                    </p>
                    <div class="hero__actions">
                        <a href="#contact" class="btn btn--primary">今すぐ無料相談に申し込む</a>
                        <a href="#" class="btn btn--text">まずは資料ダウンロード &rarr;</a>
                    </div>
                </div>
                <div class="hero__image fade-in-up" style="transition-delay: 0.2s;">
                    <div class="hero__video-card">
                        <div class="hero__thumbnail">
                            <div class="play-icon">▶</div>
                        </div>
                        <div style="color: white; font-weight: 700;">第1章：AI時代のビジネス設計図（サンプル）</div>
                        <div style="height: 6px; background: rgba(255,255,255,0.2); border-radius: 3px; overflow: hidden;">
                            <div style="width: 40%; background: var(--color-primary); height: 100%;"></div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 3. 課題セクション (Problem) -->
        <section id="problem" class="section section--white">
            <div class="container">
                <div class="section__header fade-in-up">
                    <h2 class="section__title">中小企業がAI活用で<br>つまずく3つの理由</h2>
                    <p class="section__subtitle">高額なツールを入れても、成果が出ないのには原因があります</p>
                </div>
                <div class="problem__grid">
                    <div class="card problem-card fade-in-up">
                        <span class="problem-card__icon">🤔</span>
                        <h3 class="problem-card__title">使い道がわからない</h3>
                        <p class="problem-card__text">「ChatGPTとりあえず契約した」止まりで、具体的な業務への落とし込み方が現場に浸透していない。</p>
                    </div>
                    <div class="card problem-card fade-in-up" style="transition-delay: 0.1s;">
                        <span class="problem-card__icon">👮‍♂️</span>
                        <h3 class="problem-card__title">リスクへの不安</h3>
                        <p class="problem-card__text">情報漏洩や著作権侵害が怖く、社内ルールも整備されていないため、従業員が萎縮して使えない。</p>
                    </div>
                    <div class="card problem-card fade-in-up" style="transition-delay: 0.2s;">
                        <span class="problem-card__icon">📚</span>
                        <h3 class="problem-card__title">教育リソース不足</h3>
                        <p class="problem-card__text">詳しい社員が一人もおらず、外部コンサルを雇う予算もないため、組織的な学習が進まない。</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- 4. 解決コンセプト (Solution) -->
        <section class="section section--gray">
            <div class="container solution__container">
                <div class="solution__content fade-in-up">
                    <h2 class="section__title" style="text-align: left;">With AI ビデオプログラムが<br>その課題を解決します</h2>
                    <p class="section__subtitle" style="text-align: left;">知識ゼロから実務レベルまで、最短距離で導く設計。</p>
                    
                    <ul class="solution__list">
                        <li class="solution__item">
                            <span class="check-icon">✓</span>
                            <span>専門用語を使わない「現場目線」のわかりやすい解説</span>
                        </li>
                        <li class="solution__item">
                            <span class="check-icon">✓</span>
                            <span>明日から使える「プロンプト集」と「社内規定雛形」付き</span>
                        </li>
                        <li class="solution__item">
                            <span class="check-icon">✓</span>
                            <span>スマホ視聴OK。忙しい社員でもスキマ時間で学習完了</span>
                        </li>
                    </ul>
                    
                    <a href="#curriculum" class="btn btn--primary">カリキュラムを見る</a>
                </div>
                <div class="solution__image fade-in-up">
                    <img src="https://images.unsplash.com/photo-1600880292203-757bb62b4baf?q=80&w=2070&auto=format&fit=crop" alt="オフィスの会議風景">
                </div>
            </div>
        </section>

        <!-- 5. こんな企業におすすめ (Who) -->
        <section class="section section--white">
            <div class="container who__container">
                <div class="who__content fade-in-up">
                    <h2 class="section__title" style="text-align: left; font-size: 1.8rem;">こんな課題をお持ちの<br>企業様におすすめです</h2>
                    <div class="who__bubbles">
                        <div class="bubble">「AIやるぞ」と言ったものの、社員がついてこない</div>
                        <div class="bubble">若手社員への教育コストを削減し、自走させたい</div>
                        <div class="bubble">セキュリティ研修とセットでAIリテラシーを高めたい</div>
                        <div class="bubble">DX推進室を作ったが、具体的な成果物が出てこない</div>
                    </div>
                </div>
                <div class="who__image fade-in-up">
                    <img src="https://images.unsplash.com/photo-1556761175-b413da4baf72?q=80&w=1974&auto=format&fit=crop" alt="悩む経営者">
                </div>
            </div>
        </section>

        <!-- 6. コンテンツ紹介 (What you get) -->
        <section id="feature" class="section section--gray">
            <div class="container">
                <div class="section__header fade-in-up">
                    <h2 class="section__title">このプログラムで手に入るもの</h2>
                    <p class="section__subtitle">動画を見るだけではありません。実務変革のキットを提供します。</p>
                </div>
                <div class="feature__grid">
                    <div class="card feature-card fade-in-up">
                        <span class="feature-badge">動画教材</span>
                        <h3 class="feature-card__title">経営戦略×AIの全体像</h3>
                        <p class="problem-card__text">なぜ今AIなのか？経営インパクトは？という上流から、現場での具体的なユースケースまでを網羅。</p>
                    </div>
                    <div class="card feature-card fade-in-up" style="transition-delay: 0.1s;">
                        <span class="feature-badge">特典資料</span>
                        <h3 class="feature-card__title">そのまま使える規定テンプレ</h3>
                        <p class="problem-card__text">社内稟議を通しやすい「生成AI利用ガイドライン」のWordテンプレートをプレゼント。</p>
                    </div>
                    <div class="card feature-card fade-in-up" style="transition-delay: 0.2s;">
                        <span class="feature-badge">実践ワーク</span>
                        <h3 class="feature-card__title">業務改善プロンプト集</h3>
                        <p class="problem-card__text">議事録要約、メール作成、アイデア出しなど、部署別にそのまま使えるプロンプト100選。</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- 7. カリキュラム (Curriculum) -->
        <section id="curriculum" class="section section--white">
            <div class="container">
                <div class="section__header fade-in-up">
                    <h2 class="section__title">動画カリキュラム</h2>
                    <p class="section__subtitle">全6章・合計約3時間の集中プログラム</p>
                </div>
                <div class="timeline fade-in-up">
                    <div class="timeline__item">
                        <div class="timeline__number">1</div>
                        <div class="timeline__content">
                            <h3 class="timeline__title">AI概論とビジネスインパクト</h3>
                            <p class="timeline__desc">生成AIの仕組みと、なぜ今ビジネスで必須なのかを理解する。</p>
                        </div>
                    </div>
                    <div class="timeline__item">
                        <div class="timeline__number">2</div>
                        <div class="timeline__content">
                            <h3 class="timeline__title">リスクマネジメントとセキュリティ</h3>
                            <p class="timeline__desc">著作権、情報漏洩、ハルシネーションなどのリスク対策。</p>
                        </div>
                    </div>
                    <div class="timeline__item">
                        <div class="timeline__number">3</div>
                        <div class="timeline__content">
                            <h3 class="timeline__title">基本操作とプロンプトエンジニアリング</h3>
                            <p class="timeline__desc">意図した回答を引き出すための指示出しテクニック。</p>
                        </div>
                    </div>
                    <div class="timeline__item">
                        <div class="timeline__number">4</div>
                        <div class="timeline__content">
                            <h3 class="timeline__title">部署別活用ケーススタディ（営業・人事・開発）</h3>
                            <p class="timeline__desc">各職種における具体的な時短・効率化事例の実演。</p>
                        </div>
                    </div>
                    <div class="timeline__item">
                        <div class="timeline__number">5</div>
                        <div class="timeline__content">
                            <h3 class="timeline__title">社内導入のロードマップ作成</h3>
                            <p class="timeline__desc">自社にAI文化を根付かせるためのステップ論。</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 8. 導入イメージ/事例 (Case) -->
        <section id="case" class="section section--gray">
            <div class="container">
                <div class="case__container">
                    <div class="case__content fade-in-up">
                        <h2 class="section__title" style="text-align: left;">導入はとてもシンプルです</h2>
                        <div class="step-flow">
                            <div class="step-item">
                                <span class="step-num">STEP 1</span>
                                <span>お申し込み・アカウント発行</span>
                            </div>
                            <div class="step-item">
                                <span class="step-num">STEP 2</span>
                                <span>管理者様によるユーザー登録</span>
                            </div>
                            <div class="step-item">
                                <span class="step-num">STEP 3</span>
                                <span>社員各自で動画視聴（進捗管理可能）</span>
                            </div>
                            <div class="step-item">
                                <span class="step-num">STEP 4</span>
                                <span>実践ワーク・社内への展開</span>
                            </div>
                        </div>
                        <div class="case-box">
                            <h4 style="font-weight: 700; margin-bottom: 12px;">株式会社テック商事 様（従業員50名）</h4>
                            <p style="font-size: 0.95rem; line-height: 1.6; color: var(--color-text-sub);">
                                「導入前は『AIなんてうちは関係ない』という空気でしたが、動画研修後、営業部から『顧客メールのドラフト作成に使いたい』と提案が出るように。月間100時間以上の工数削減に成功しました。」
                            </p>
                        </div>
                    </div>
                    <div class="case__image fade-in-up">
                        <img src="https://images.unsplash.com/photo-1531482615713-2afd69097998?q=80&w=2070&auto=format&fit=crop" alt="研修を受ける社員" style="border-radius: var(--radius-card);">
                    </div>
                </div>
            </div>
        </section>

        <!-- 9. 料金セクション (Pricing) -->
        <section id="pricing" class="section section--white">
            <div class="container">
                <div class="section__header fade-in-up">
                    <h2 class="section__title">料金・提供形式</h2>
                    <p class="section__subtitle">企業の規模やニーズに合わせたプランをご用意しています</p>
                </div>
                <div class="pricing__grid">
                    <!-- プラン1 -->
                    <div class="card pricing-card fade-in-up">
                        <h3 style="font-size: 1.2rem; font-weight: 700;">ライトプラン</h3>
                        <div class="pricing-price">5<span>万円</span></div>
                        <p style="font-size: 0.9rem; color: var(--color-text-sub); margin-bottom: 24px;">買い切り / 視聴人数制限なし</p>
                        <ul class="pricing-features">
                            <li>動画本編（MP4提供）</li>
                            <li>テキスト教材PDF</li>
                            <li>視聴期間：無期限</li>
                        </ul>
                        <a href="#contact" class="btn btn--primary" style="background: #e2e8f0; color: #111;">詳細を見る</a>
                    </div>
                    
                    <!-- プラン2 おすすめ -->
                    <div class="card pricing-card pricing-card--recommend fade-in-up" style="transition-delay: 0.1s;">
                        <span class="recommend-badge">おすすめ</span>
                        <h3 style="font-size: 1.2rem; font-weight: 700;">スタンダードプラン</h3>
                        <div class="pricing-price">15<span>万円</span></div>
                        <p style="font-size: 0.9rem; color: var(--color-text-sub); margin-bottom: 24px;">クラウド学習管理システム利用</p>
                        <ul class="pricing-features">
                            <li>動画視聴（クラウド上）</li>
                            <li>社員の受講進捗管理機能</li>
                            <li>理解度テスト機能付き</li>
                            <li>ガイドライン雛形・プロンプト集</li>
                        </ul>
                        <a href="#contact" class="btn btn--primary">無料相談に申し込む</a>
                    </div>
                    
                    <!-- プラン3 -->
                    <div class="card pricing-card fade-in-up" style="transition-delay: 0.2s;">
                        <h3 style="font-size: 1.2rem; font-weight: 700;">エンタープライズ</h3>
                        <div class="pricing-price" style="font-size: 2rem; padding: 6px 0;">お問い合わせ</div>
                        <p style="font-size: 0.9rem; color: var(--color-text-sub); margin-bottom: 24px;">伴走支援コンサルティング付き</p>
                        <ul class="pricing-features">
                            <li>スタンダードプラン全機能</li>
                            <li>導入キックオフMTG開催</li>
                            <li>個別カスタマイズ研修</li>
                            <li>月1回の定例活用相談</li>
                        </ul>
                        <a href="#contact" class="btn btn--primary" style="background: #e2e8f0; color: #111;">相談する</a>
                    </div>
                </div>
            </div>
        </section>

        <!-- 10. FAQ Section -->
        <section class="section section--gray">
            <div class="container">
                <div class="section__header fade-in-up">
                    <h2 class="section__title">よくある質問</h2>
                </div>
                <div class="faq__container fade-in-up">
                    <div class="faq-item">
                        <button class="faq-question">AIの知識が全くない状態でも大丈夫ですか？</button>
                        <div class="faq-answer">
                            <p>はい、問題ありません。本プログラムは非エンジニアのビジネスパーソン向けに作られており、専門用語を極力使わずに解説しています。</p>
                        </div>
                    </div>
                    <div class="faq-item">
                        <button class="faq-question">動画の視聴期限はありますか？</button>
                        <div class="faq-answer">
                            <p>ライトプラン（買い切り）の場合は期限はありません。クラウド型のスタンダードプランの場合は、ご契約期間中（通常1年間～）は何度でも視聴可能です。</p>
                        </div>
                    </div>
                    <div class="faq-item">
                        <button class="faq-question">請求書払いは可能ですか？</button>
                        <div class="faq-answer">
                            <p>はい、法人様向けのサービスですので、請求書払い（月末締め翌月末払い）に対応しております。</p>
                        </div>
                    </div>
                    <div class="faq-item">
                        <button class="faq-question">自社の業務に合わせたカスタマイズは可能ですか？</button>
                        <div class="faq-answer">
                            <p>エンタープライズプランにて、貴社の業界や業務フローに合わせた追加講義の作成や、ワークショップの開催が可能です。詳細はお問い合わせください。</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 11. Footer -->
        <footer id="contact" class="footer">
            <div class="container">
                <div class="footer__content">
                    <div class="footer__info">
                        <h3>With AI .</h3>
                        <div class="footer__address">
                            <p>運営：株式会社With AI Solutions</p>
                            <p>〒100-0005 東京都千代田区丸の内1-1-1 AIビルディング 8F</p>
                            <p>Email: contact@example.com</p>
                            <p>Tel: 03-1234-5678 (平日 10:00-18:00)</p>
                        </div>
                    </div>
                    <div class="footer__links">
                        <ul style="display: flex; gap: 24px; color: #cbd5e1; font-size: 0.9rem;">
                            <li><a href="#">会社概要</a></li>
                            <li><a href="#">特定商取引法に基づく表記</a></li>
                            <li><a href="#">プライバシーポリシー</a></li>
                        </ul>
                    </div>
                </div>
                <div class="footer__copy">
                    &copy; 2024 With AI Solutions Inc. All Rights Reserved.
                </div>
            </div>
        </footer>

    </main>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            
            // 1. スクロールフェードインアニメーション
            const observerOptions = {
                root: null,
                rootMargin: '0px',
                threshold: 0.1
            };

            const observer = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('is-visible');
                        observer.unobserve(entry.target); // 一度発火したら監視解除
                    }
                });
            }, observerOptions);

            const fadeElements = document.querySelectorAll('.fade-in-up');
            fadeElements.forEach(el => observer.observe(el));


            // 2. ハンバーガーメニュー
            const hamburger = document.getElementById('js-hamburger');
            const nav = document.getElementById('js-nav');
            const navLinks = document.querySelectorAll('.header__link, .header__nav .btn');

            hamburger.addEventListener('click', () => {
                const isOpen = nav.classList.contains('is-open');
                if (isOpen) {
                    nav.classList.remove('is-open');
                    hamburger.setAttribute('aria-expanded', 'false');
                } else {
                    nav.classList.add('is-open');
                    hamburger.setAttribute('aria-expanded', 'true');
                }
            });

            // メニューリンククリック時に閉じる
            navLinks.forEach(link => {
                link.addEventListener('click', () => {
                    if (nav.classList.contains('is-open')) {
                        nav.classList.remove('is-open');
                    }
                });
            });


            // 3. FAQアコーディオン
            const questions = document.querySelectorAll('.faq-question');
            
            questions.forEach(question => {
                question.addEventListener('click', () => {
                    // 現在の状態を取得
                    const answer = question.nextElementSibling;
                    const isOpen = question.classList.contains('is-open');

                    // 一度全ての質問を閉じる（オプション：一つだけ開く仕様にする場合）
                    // questions.forEach(q => {
                    //     q.classList.remove('is-open');
                    //     q.nextElementSibling.style.maxHeight = null;
                    // });

                    if (!isOpen) {
                        question.classList.add('is-open');
                        answer.style.maxHeight = answer.scrollHeight + "px";
                    } else {
                        question.classList.remove('is-open');
                        answer.style.maxHeight = null;
                    }
                });
            });
        });
    </script>
</body>
</html>
