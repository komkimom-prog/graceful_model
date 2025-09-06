<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>우아한 옷장연대</title>
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
            <h1><span class="emoji">✨</span> 우아한 옷장연대 <span class="emoji">✨</span></h1>
            <div class="subtitle">"같이 실패하고, 같이 웃고, 같이 성장하는 패션 커뮤니티"</div>
        </div>
        
        <div class="content">
            <div class="section">
                <h2><span class="emoji">👗</span> 우아한 옷장연대란?</h2>
                <div class="intro-box">
                    <p>
                        반짝반짝 잘 입는 패션 인스타그램? 그건 우리 얘기가 아니에요.<br>
                        여기는 <strong>우아한 옷장연대</strong>입니다! ✨<br><br>
                        저 혼자만의 패션 성공담이 아니라, <strong>66·77·88 현실 사이즈의 실패담, 반품담, 좌절담</strong>을 모두가 함께 꺼내놓는 자리예요.
                    </p>
                </div>
            </div>
            
            <div class="section">
                <h2><span class="emoji">💡</span> 옷장연대에서 하는 일</h2>
                <div class="cards-grid">
                    <div class="card">
                        <h3><span class="card-icon">❌</span> 솔직한 실패담 나누기</h3>
                        <ul class="benefit-list">
                            <li>실패템, 반품템 솔직히 자랑하기</li>
                            <li>망한 것도 기록하면 콘텐츠!</li>
                            <li>"이거 왜 샀을까?" 후회 스토리</li>
                            <li>브랜드별 실패 경험 공유</li>
                        </ul>
                    </div>
                    
                    <div class="card">
                        <h3><span class="card-icon">🗳️</span> 함께 결정하기</h3>
                        <ul class="benefit-list">
                            <li>"살까? 반품할까?" 투표로 같이 결정</li>
                            <li>애매한 옷들 집단 판단</li>
                            <li>구매 전 미리 물어보기</li>
                            <li>실시간 고민 상담</li>
                        </ul>
                    </div>
                    
                    <div class="card">
                        <h3><span class="card-icon">👭</span> 공감과 연대</h3>
                        <ul class="benefit-list">
                            <li>같은 체형, 같은 고민을 가진 언니들과 소통</li>
                            <li>현실적인 조언과 위로</li>
                            <li>패션 고민 함께 해결</li>
                            <li>가끔은 득템템 자랑도!</li>
                        </ul>
                    </div>
                </div>
            </div>
            
            <div class="section">
                <h2><span class="emoji">🎯</span> 연대의 특별함</h2>
                <div class="highlight-box">
                    <h3><span class="emoji">💫</span> 완벽하지 않아서 더 진짜</h3>
                    <ul class="benefit-list">
                        <li><strong>실패도 함께 나누니까</strong> 부담 없어요</li>
                        <li>비슷한 고민을 가진 사람들과의 진짜 소통</li>
                        <li>공동 득템으로 함께 기뻐하기</li>
                        <li>혼자가 아닌 함께의 힘</li>
                        <li>현실적이고 솔직한 패션 이야기</li>
                    </ul>
                </div>
            </div>
            
            <div class="section">
                <h2><span class="emoji">🌈</span> 이런 분들을 기다려요</h2>
                <div class="target-section">
                    <div class="target-grid">
                        <div class="target-card">
                            <h4><span class="emoji">💝</span> 현실 사이즈</h4>
                            <p>66, 77, 88<br>현실적인 고민 보유자</p>
                        </div>
                        
                        <div class="target-card">
                            <h4><span class="emoji">😅</span> 실패 경험</h4>
                            <p>온라인 쇼핑<br>실패담 풍부</p>
                        </div>
                        
                        <div class="target-card">
                            <h4><span class="emoji">💬</span> 소통 의지</h4>
                            <p>함께 고민하고<br>함께 성장하고픈 마음</p>
                        </div>
                        
                        <div class="target-card">
                            <h4><span class="emoji">✨</span> 솔직함</h4>
                            <p>완벽하지 않아도<br>진짜 이야기 나눌 용기</p>
                        </div>
                    </div>
                    
                    <div class="intro-box" style="margin-top: 30px;">
                        <h4 style="color: #8e6a5b; margin-bottom: 15px;"><span class="emoji">💡</span> 이런 마음이시라면 환영!</h4>
                        <p style="font-size: 1em;">
                            "나만 이런 고민 하나?" 궁금한 분 • "혼자 결정하기 어려워요" 우유부단한 분<br>
                            "실패담도 누군가에겐 도움이 될 텐데" 나눔의 마음 있는 분 • "함께하면 더 재밌을 것 같아" 연대 정신 있는 분
                        </p>
                    </div>

                    <div class="intro-box" style="margin-top: 20px; background: #fff5f5; border: 2px solid #fed7d7;">
                        <h4 style="color: #c53030; margin-bottom: 15px;"><span class="emoji">🙅‍♀️</span> 이런 건 아니에요!</h4>
                        <p style="font-size: 1em; color: #c53030;">
                            완벽한 코디만 보여주는 곳 • 브랜드 홍보성 후기 • 가르치려는 마음 • 남의 실패를 비웃는 마음
                        </p>
                    </div>
                </div>
            </div>
            
            <div class="section">
                <h2><span class="emoji">🤗</span> 우아한 옷장연대의 약속</h2>
                <div class="cards-grid">
                    <div class="card">
                        <h3><span class="card-icon">🫂</span> 서로 응원하기</h3>
                        <p>실패도 성공도 함께 나누며, 서로를 격려하고 응원하는 따뜻한 공간을 만들어요.</p>
                    </div>
                    
                    <div class="card">
                        <h3><span class="card-icon">💯</span> 솔직하게 소통</h3>
                        <p>가식 없는 진짜 이야기로 서로에게 진짜 도움이 되는 커뮤니티를 지향해요.</p>
                    </div>
                    
                    <div class="card">
                        <h3><span class="card-icon">🌱</span> 함께 성장하기</h3>
                        <p>혼자서는 해결하기 어려운 고민들을 함께 풀어가며 모두가 성장하는 공간이에요.</p>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="cta-section">
            <h2><span class="emoji">🤝</span> 우아한 옷장연대에 함께해요!</h2>
            <p style="font-size: 1.2em; margin-bottom: 30px; line-height: 1.8;">
                옷장연대는 완벽한 코디쇼가 아닙니다.<br>
                <strong>같이 실패하고, 같이 웃고, 같이 성장하는 패션 커뮤니티</strong>입니다.<br><br>
                혼자 끙끙 앓던 패션 고민, 이제 함께 나눠봐요!
            </p>
            
            <div style="margin: 30px 0;">
                <h3 style="color: white; margin-bottom: 15px;"><span class="emoji">💌</span> 진짜 동지들을 찾습니다!</h3>
                <p style="opacity: 0.9;">완벽하지 않아도 괜찮아요. 오히려 그래서 더 진짜예요!</p>
            </div>
            
            <a href="https://docs.google.com/forms/d/e/1FAIpQLSdzqwD9GonftP04XxSiEyrmfiXL_BZ3lx6qzMhdEV18ejHVng/viewform?usp=header" target="_blank" class="cta-button"><span class="emoji">🤗</span> 옷장연대 참여하기</a>
            <a href="https://open.kakao.com/o/sDgPLSIh" target="_blank" class="cta-button"><span class="emoji">💬</span> 궁금한 점 문의하기</a>
        </div>
        
        <div class="quote-section">
            <div class="quote-text">
                "혼자서는 실패였던 것들이<br>
                함께하니 소중한 경험이 되었어요"
            </div>
            <div class="quote-author">- 우아한 옷장연대 회원들의 마음 <span class="emoji">✨</span></div>
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
