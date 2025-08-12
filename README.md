<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>우아한 착장단 모집</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@300;400;500;600;700&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Noto Sans KR', sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #fdf2e9 0%, #f8e6d3 50%, #f0d8c4 100%);
            min-height: 100vh;
        }
        
        .container {
            max-width: 900px;
            margin: 0 auto;
            background: white;
            box-shadow: 0 20px 60px rgba(0,0,0,0.1);
            overflow: hidden;
        }
        
        .hero {
            background: linear-gradient(135deg, #8e6a5b 0%, #a0785c 50%, #b8956d 100%);
            color: white;
            padding: 60px 40px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><circle cx="20" cy="20" r="2" fill="rgba(255,255,255,0.1)"/><circle cx="80" cy="40" r="3" fill="rgba(255,255,255,0.05)"/><circle cx="40" cy="70" r="1.5" fill="rgba(255,255,255,0.1)"/><circle cx="90" cy="90" r="2.5" fill="rgba(255,255,255,0.05)"/></svg>');
            pointer-events: none;
        }
        
        .hero h1 {
            font-size: 3em;
            font-weight: 700;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            position: relative;
            z-index: 1;
        }
        
        .hero .subtitle {
            font-size: 1.3em;
            font-weight: 300;
            opacity: 0.95;
            font-style: italic;
            position: relative;
            z-index: 1;
        }
        
        .content {
            padding: 50px 40px;
        }
        
        .section {
            margin-bottom: 50px;
        }
        
        .section h2 {
            font-size: 2em;
            color: #8e6a5b;
            margin-bottom: 25px;
            text-align: center;
            position: relative;
        }
        
        .section h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 3px;
            background: linear-gradient(90deg, #8e6a5b, #b8956d);
            border-radius: 2px;
        }
        
        .intro-box {
            background: linear-gradient(135deg, #faf7f0 0%, #f5f0e8 100%);
            border: 2px solid #e8d5c9;
            border-radius: 20px;
            padding: 30px;
            margin: 30px 0;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
        }
        
        .intro-box p {
            font-size: 1.1em;
            line-height: 1.8;
            color: #5d4e37;
        }
        
        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
            margin: 30px 0;
        }
        
        .card {
            background: white;
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.08);
            border: 1px solid #f0e6d2;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(0,0,0,0.12);
        }
        
        .card h3 {
            color: #8e6a5b;
            font-size: 1.3em;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .card-icon {
            font-size: 1.5em;
        }
        
        .benefit-list {
            list-style: none;
            padding: 0;
        }
        
        .benefit-list li {
            padding: 8px 0;
            border-bottom: 1px solid #f5f0e8;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .benefit-list li:last-child {
            border-bottom: none;
        }
        
        .benefit-list li::before {
            content: '✨';
            font-size: 1.2em;
        }
        
        .target-section {
            background: linear-gradient(135deg, #f8f5f0 0%, #f0e8d8 100%);
            border-radius: 20px;
            padding: 30px;
            margin: 30px 0;
        }
        
        .target-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        
        .target-card {
            background: white;
            border-radius: 12px;
            padding: 20px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }
        
        .target-card h4 {
            color: #8e6a5b;
            margin-bottom: 10px;
            font-size: 1.1em;
        }
        
        .highlight-box {
            background: linear-gradient(135deg, #fff9f0 0%, #fef5eb 100%);
            border: 2px solid #f4a261;
            border-radius: 15px;
            padding: 25px;
            margin: 25px 0;
            text-align: center;
        }
        
        .highlight-box h3 {
            color: #d68910;
            font-size: 1.4em;
            margin-bottom: 15px;
        }
        
        .cta-section {
            background: linear-gradient(135deg, #8e6a5b 0%, #a0785c 100%);
            color: white;
            padding: 50px 40px;
            text-align: center;
            margin-top: 50px;
        }
        
        .cta-section h2 {
            color: white;
            font-size: 2.2em;
            margin-bottom: 20px;
        }
        
        .cta-section h2::after {
            background: white;
        }
        
        .cta-button {
            display: inline-block;
            background: linear-gradient(135deg, #f4a261 0%, #e76f51 100%);
            color: white;
            padding: 15px 40px;
            border-radius: 50px;
            text-decoration: none;
            font-size: 1.2em;
            font-weight: 600;
            margin: 20px 10px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
            transition: all 0.3s ease;
        }
        
        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 35px rgba(0,0,0,0.3);
        }
        
        .quote-section {
            background: #f8f5f0;
            padding: 40px;
            text-align: center;
            font-style: italic;
            border-top: 3px solid #8e6a5b;
        }
        
        .quote-text {
            font-size: 1.3em;
            color: #5d4e37;
            margin-bottom: 15px;
            line-height: 1.8;
        }
        
        .quote-author {
            font-size: 1.1em;
            color: #8e6a5b;
            font-weight: 600;
        }
        
        .emoji {
            font-size: 1.2em;
            margin: 0 5px;
        }
        
        @media (max-width: 768px) {
            .hero {
                padding: 40px 20px;
            }
            
            .hero h1 {
                font-size: 2.2em;
            }
            
            .content {
                padding: 30px 20px;
            }
            
            .cta-section {
                padding: 40px 20px;
            }
            
            .cards-grid {
                grid-template-columns: 1fr;
            }
        }
        
        .floating-shapes {
            position: fixed;
            pointer-events: none;
            z-index: -1;
        }
        
        .shape {
            position: absolute;
            opacity: 0.1;
            animation: float 6s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }
        
        .shape:nth-child(1) {
            top: 20%;
            left: 10%;
            animation-delay: 0s;
        }
        
        .shape:nth-child(2) {
            top: 60%;
            right: 10%;
            animation-delay: 2s;
        }
        
        .shape:nth-child(3) {
            bottom: 20%;
            left: 20%;
            animation-delay: 4s;
        }
    </style>
</head>
<body>
    <div class="floating-shapes">
        <div class="shape" style="font-size: 3em;">👗</div>
        <div class="shape" style="font-size: 2.5em;">✨</div>
        <div class="shape" style="font-size: 3.5em;">🌸</div>
    </div>

    <div class="container">
        <div class="hero">
            <h1><span class="emoji">⚡</span> 우아한 착장단 <span class="emoji">⚡</span></h1>
            <div class="subtitle">"니들이 안 입어주면 우리가 입고 평가하겠어!"</div>
        </div>
        
        <div class="content">
            <div class="section">
                <h2><span class="emoji">🔥</span> 우아한 착장단이란?</h2>
                <div class="intro-box">
                    <p>
                        <strong>66, 77, 88 사이즈의 집단지성 착장 평가단!</strong><br>
                        우리는 모델이 아니에요. <strong>진짜 일상을 사는 여자들의 리얼 착장 평가단</strong>입니다!<br><br>
                        예쁜 모델들이 안 보여주는 현실 핏을 우리가 직접 입고 평가해서 진실을 밝혀내요!
                    </p>
                </div>
            </div>
            
            <div class="section">
                <h2><span class="emoji">💪</span> 우아한 착장단이 하는 일</h2>
                <div class="cards-grid">
                    <div class="card">
                        <h3><span class="card-icon">🔍</span> 리얼 핏 체크</h3>
                        <ul class="benefit-list">
                            <li>예쁜 모델들이 안 보여주는 뒷모습까지 공개</li>
                            <li>앉았을 때, 걸을 때, 팔 올릴 때 실제 착용감</li>
                            <li>66, 77, 88 사이즈별 착용 비교</li>
                            <li>"광고와 다른데?" 솔직한 현실 체크</li>
                        </ul>
                    </div>
                    
                    <div class="card">
                        <h3><span class="card-icon">⚡</span> 브랜드 사기 척결</h3>
                        <ul class="benefit-list">
                            <li>브랜드별 사이즈 사기 폭로 작전</li>
                            <li>"66사이즈인데 77 같아요" 솔직 고발</li>
                            <li>광고 모델 vs 우리가 입었을 때 비교</li>
                            <li>소비자를 위한 진실 규명</li>
                        </ul>
                    </div>
                    
                    <div class="card">
                        <h3><span class="card-icon">🧠</span> 집단지성 활용</h3>
                        <ul class="benefit-list">
                            <li>여러 체형이 함께 착용해서 데이터 축적</li>
                            <li>"이 옷 살까 말까?" 집단 판단</li>
                            <li>착장 고민 함께 해결</li>
                            <li>66, 77, 88의 진짜 후기 데이터베이스</li>
                        </ul>
                    </div>
                </div>
            </div>
            
            <div class="section">
                <h2><span class="emoji">🎁</span> 우아한 착장단의 혜택</h2>
                <div class="highlight-box">
                    <h3><span class="emoji">👚</span> 의상 혜택</h3>
                    <ul class="benefit-list">
                        <li><strong>마음에 든 착샷 옷 무료 증정</strong> (월 1-2벌)</li>
                        <li>신상품 우선 체험 기회</li>
                        <li>브랜드 협찬 아이템 무료 제공</li>
                        <li>집단지성 참여로 얻는 뿌듯함과 성취감</li>
                        <li>진짜 도움되는 착장 정보 공유의 기쁨</li>
                    </ul>
                </div>
            </div>
            
            <div class="section">
                <h2><span class="emoji">📋</span> 모집 대상</h2>
                <div class="target-section">
                    <div class="target-grid">
                        <div class="target-card">
                            <h4><span class="emoji">💝</span> 자격요건</h4>
                            <p>66, 77, 88 사이즈<br>솔직함 레벨 MAX</p>
                        </div>
                        
                        <div class="target-card">
                            <h4><span class="emoji">💪</span> 성격</h4>
                            <p>예쁜 모델 보고<br>속 터진 경험 有</p>
                        </div>
                        
                        <div class="target-card">
                            <h4><span class="emoji">🌍</span> 지역</h4>
                            <p>전국 어디서나<br>온라인 활동</p>
                        </div>
                        
                        <div class="target-card">
                            <h4><span class="emoji">🔥</span> 의지</h4>
                            <p>집단지성 참여<br>의지 활활</p>
                        </div>
                    </div>
                    
                    <div class="intro-box" style="margin-top: 30px;">
                        <h4 style="color: #8e6a5b; margin-bottom: 15px;"><span class="emoji">⚠️</span> 이런 분은 환영해요!</h4>
                        <p style="font-size: 1em;">
                            "나도 저거 입으면 저럴까?" 의심 많은 분 • "이거 광고랑 다른데?" 솔직한 분<br>
                            온라인 쇼핑 실패 경험 풍부한 분 • 집단지성으로 진실 찾고 싶은 분
                        </p>
                    </div>

                    <div class="intro-box" style="margin-top: 20px; background: #fff5f5; border: 2px solid #fed7d7;">
                        <h4 style="color: #c53030; margin-bottom: 15px;"><span class="emoji">🚫</span> 이런 분은 안 맞아요!</h4>
                        <p style="font-size: 1em; color: #c53030;">
                            모델 지망생 • 완벽한 몸매 보유자 • 솔직하지 못한 분 • 광고성 후기 쓰는 분
                        </p>
                    </div>
                </div>
            </div>
            
            <div class="section">
                <h2><span class="emoji">💫</span> 우아한 착장단만의 특별함</h2>
                <div class="cards-grid">
                    <div class="card">
                        <h3><span class="card-icon">🎯</span> 진짜 소비자 관점</h3>
                        <p>광고가 아닌 진짜 사용자 관점으로, "이거 사면 안 돼요" 솔직 경고까지!</p>
                    </div>
                    
                    <div class="card">
                        <h3><span class="card-icon">⚡</span> 반항 정신</h3>
                        <p>"모델만 예뻐 보이는 옷은 거부한다!" 우리만의 패션 혁명 정신!</p>
                    </div>
                    
                    <div class="card">
                        <h3><span class="card-icon">🔥</span> 집단지성의 힘</h3>
                        <p>혼자서는 몰랐던 것들을 함께 발견하고, 서로 도움되는 진짜 정보 공유!</p>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="cta-section">
            <h2><span class="emoji">⚡</span> 우아한 착장 혁명을 일으켜요!</h2>
            <p style="font-size: 1.2em; margin-bottom: 30px; line-height: 1.8;">
                우아한 착장단은 단순한 모델 활동이 아니에요.<br>
                66, 77, 88 사이즈도 충분히 멋져 보일 수 있다는 걸<br>
                우리가 직접 증명하는 <strong>우아한 패션 혁명</strong>이에요!
            </p>
            
            <div style="margin: 30px 0;">
                <h3 style="color: white; margin-bottom: 15px;"><span class="emoji">🔥</span> 첫 번째 우아한 착장단은 10명 한정!</h3>
                <p style="opacity: 0.9;">"니들이 안 입어주면 우리가 입고 평가하겠어!" 함께 외칠 용감한 착장단을 찾습니다!</p>
            </div>
            
            <a href="https://docs.google.com/forms/d/e/1FAIpQLSdzqwD9GonftP04XxSiEyrmfiXL_BZ3lx6qzMhdEV18ejHVng/viewform?usp=header" target="_blank" class="cta-button"><span class="emoji">⚡</span> 우아한 착장단 지원하기</a>
            <a href="https://open.kakao.com/o/sDgPLSIh" target="_blank" class="cta-button"><span class="emoji">💬</span> 문의하기</a>
        </div>
        
        <div class="quote-section">
            <div class="quote-text">
                "모델들이 보여주지 않는 진실,<br>
                우리가 직접 입고 평가해서 세상에 알리자!"
            </div>
            <div class="quote-author">- 우아한 착장단 대표 노바 <span class="emoji">⚡</span></div>
        </div>
    </div>
    
    <script>
        // 부드러운 스크롤 애니메이션
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });
        
        // 스크롤 시 카드 애니메이션
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);
        
        // 카드들에 관찰자 적용
        document.querySelectorAll('.card').forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(30px)';
            card.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            observer.observe(card);
        });
    </script>
</body>
</html>
