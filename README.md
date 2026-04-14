<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>董卓然 - 个人主页</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: "Microsoft YaHei", sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        .card {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 24px;
            padding: 40px;
            margin-bottom: 30px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.15);
            position: relative;
            overflow: hidden;
        }

        .card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.3) 0%, transparent 70%);
            pointer-events: none;
        }

        .hero-card {
            text-align: center;
            padding: 60px 40px;
        }

        .avatar-container {
            position: relative;
            width: 150px;
            height: 150px;
            margin: 0 auto 30px;
        }

        .avatar {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: linear-gradient(135deg, #667eea, #764ba2);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 60px;
            color: white;
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.4);
            animation: float 3s ease-in-out infinite;
            position: relative;
            z-index: 1;
        }

        .avatar::after {
            content: '';
            position: absolute;
            width: 180px;
            height: 180px;
            border-radius: 50%;
            border: 3px dashed rgba(102, 126, 234, 0.3);
            animation: spin 20s linear infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }

        @keyframes spin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .name {
            font-size: 42px;
            font-weight: 800;
            background: linear-gradient(135deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
            animation: bounce 2s ease-in-out infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.02); }
        }

        .tagline {
            font-size: 18px;
            color: #666;
            margin-bottom: 20px;
        }

        .badges {
            display: flex;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
            margin-top: 20px;
        }

        .badge {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 8px 20px;
            border-radius: 50px;
            font-size: 14px;
            font-weight: 500;
            animation: pulse 2s ease-in-out infinite;
            box-shadow: 0 4px 15px rgba(102, 126, 234, 0.3);
        }

        .badge:nth-child(2) { animation-delay: 0.3s; }
        .badge:nth-child(3) { animation-delay: 0.6s; }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .section-title {
            font-size: 24px;
            font-weight: 700;
            color: #333;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .section-title::before {
            content: '🎯';
            font-size: 28px;
        }

        .intro-text {
            font-size: 16px;
            color: #555;
            line-height: 1.8;
            text-align: justify;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
        }

        .skill-card {
            background: linear-gradient(135deg, #f5f7fa 0%, #e4e8f0 100%);
            padding: 25px;
            border-radius: 16px;
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .skill-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }

        .skill-icon {
            font-size: 40px;
            margin-bottom: 15px;
            display: block;
        }

        .skill-name {
            font-size: 16px;
            font-weight: 600;
            color: #333;
        }

        .skill-desc {
            font-size: 13px;
            color: #777;
            margin-top: 8px;
        }

        .timeline {
            position: relative;
            padding-left: 30px;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 8px;
            top: 0;
            bottom: 0;
            width: 3px;
            background: linear-gradient(to bottom, #667eea, #764ba2, #f093fb);
            border-radius: 3px;
        }

        .timeline-item {
            position: relative;
            margin-bottom: 30px;
            padding: 20px;
            background: #f9f9f9;
            border-radius: 12px;
            transition: all 0.3s ease;
        }

        .timeline-item:hover {
            transform: translateX(10px);
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.08);
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -26px;
            top: 25px;
            width: 14px;
            height: 14px;
            background: #667eea;
            border-radius: 50%;
            border: 3px solid white;
            box-shadow: 0 0 0 3px #667eea;
        }

        .timeline-date {
            font-size: 13px;
            color: #667eea;
            font-weight: 600;
            margin-bottom: 5px;
        }

        .timeline-title {
            font-size: 16px;
            font-weight: 700;
            color: #333;
            margin-bottom: 5px;
        }

        .timeline-desc {
            font-size: 14px;
            color: #666;
            line-height: 1.6;
        }

        .links-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }

        .link-card {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 20px;
            background: linear-gradient(135deg, #f5f7fa 0%, #e4e8f0 100%);
            border-radius: 16px;
            text-decoration: none;
            color: #333;
            transition: all 0.3s ease;
        }

        .link-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
        }

        .link-icon {
            font-size: 30px;
        }

        .link-text {
            flex: 1;
        }

        .link-label {
            font-size: 12px;
            opacity: 0.7;
        }

        .link-value {
            font-size: 15px;
            font-weight: 600;
        }

        .footer {
            text-align: center;
            padding: 30px;
            color: rgba(255, 255, 255, 0.8);
            font-size: 14px;
        }

        .footer span {
            animation: heartbeat 1.5s ease-in-out infinite;
            display: inline-block;
        }

        @keyframes heartbeat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.2); }
        }

        .floating-elements {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
            overflow: hidden;
        }

        .floating-item {
            position: absolute;
            font-size: 30px;
            opacity: 0.6;
            animation: floatAround 15s ease-in-out infinite;
        }

        @keyframes floatAround {
            0%, 100% {
                transform: translate(0, 0) rotate(0deg);
            }
            25% {
                transform: translate(100px, 50px) rotate(90deg);
            }
            50% {
                transform: translate(50px, 100px) rotate(180deg);
            }
            75% {
                transform: translate(-50px, 50px) rotate(270deg);
            }
        }

        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .star {
            position: absolute;
            width: 4px;
            height: 4px;
            background: white;
            border-radius: 50%;
            animation: twinkle 2s ease-in-out infinite;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.3; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.5); }
        }

        @media (max-width: 600px) {
            .container {
                padding: 20px 15px;
            }
            .card {
                padding: 30px 20px;
            }
            .hero-card {
                padding: 40px 20px;
            }
            .name {
                font-size: 32px;
            }
            .avatar {
                width: 120px;
                height: 120px;
                font-size: 48px;
            }
            .avatar::after {
                width: 150px;
                height: 150px;
            }
        }
    </style>
</head>
<body>
    <div class="floating-elements" id="floatingElements"></div>
    <div class="stars" id="stars"></div>

    <div class="container">
        <div class="card hero-card">
            <div class="avatar-container">
                <div class="avatar">🎓</div>
            </div>
            <h1 class="name">董卓然</h1>
            <p class="tagline">浙江大学 · 云峰学园 · 2025级</p>
            <div class="badges">
                <span class="badge">🌾 农学</span>
                <span class="badge">💻 信息管理</span>
                <span class="badge">📚 信息系统</span>
            </div>
        </div>

        <div class="card">
            <h2 class="section-title">关于我</h2>
            <p class="intro-text">
                具备农学与信息处理双重背景，目标深耕基层治理与数字农业探索。现任班级团支书，拥有丰富的学生组织经验与极强的执行力。致力于通过跨学科视角，在知行合一中投身公共服务与选调事业。
            </p>
        </div>

        <div class="card">
            <h2 class="section-title">技能特长</h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <span class="skill-icon">🎨</span>
                    <div class="skill-name">多媒体制作</div>
                    <div class="skill-desc">Photoshop图形处理</div>
                </div>
                <div class="skill-card">
                    <span class="skill-icon">🤖</span>
                    <div class="skill-name">AIGC工具</div>
                    <div class="skill-desc">AI辅助创意生成</div>
                </div>
                <div class="skill-card">
                    <span class="skill-icon">🐍</span>
                    <div class="skill-name">Python</div>
                    <div class="skill-desc">CS61A项目实践</div>
                </div>
                <div class="skill-card">
                    <span class="skill-icon">📊</span>
                    <div class="skill-name">数字化管理</div>
                    <div class="skill-desc">数据统计与分析</div>
                </div>
            </div>
        </div>

        <div class="card">
            <h2 class="section-title">经历荣誉</h2>
            <div class="timeline">
                <div class="timeline-item">
                    <div class="timeline-date">2025.09 - 至今</div>
                    <div class="timeline-title">浙江大学云峰学园 · 班级团支书</div>
                    <div class="timeline-desc">策划《习近平的七年知青岁月》主题读书分享会，统筹校级"人文思想节"活动</div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-date">2023.09 - 2024.06</div>
                    <div class="timeline-title">高中学生会 · 学生会主席</div>
                    <div class="timeline-desc">负责全校学生组织统筹运营，百人以上校园活动决策规划与跨部门协调</div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-date">2023.07 - 2023.08</div>
                    <div class="timeline-title">地摊经济专题调研 · 负责人</div>
                    <div class="timeline-desc">山东菏泽地摊经济现状调研，形成体系化调研报告</div>
                </div>
            </div>
        </div>

        <div class="card">
            <h2 class="section-title">联系方式</h2>
            <div class="links-grid">
                <a href="tel:15757004727" class="link-card">
                    <span class="link-icon">📞</span>
                    <div class="link-text">
                        <div class="link-label">电话</div>
                        <div class="link-value">15757004727</div>
                    </div>
                </a>
                <a href="mailto:3250102672@zju.edu.cn" class="link-card">
                    <span class="link-icon">✉️</span>
                    <div class="link-text">
                        <div class="link-label">邮箱</div>
                        <div class="link-value">3250102672@zju.edu.cn</div>
                    </div>
                </a>
            </div>
        </div>
    </div>

    <div class="footer">
        <p>Made with <span>❤️</span> by 董卓然 · 2026</p>
    </div>

    <script>
        function createFloatingElements() {
            const container = document.getElementById('floatingElements');
            const emojis = ['🌟', '✨', '💫', '🌈', '☀️', '🌙', '⭐', '🎈', '🎯', '💡'];
            
            for (let i = 0; i < 15; i++) {
                const item = document.createElement('div');
                item.className = 'floating-item';
                item.textContent = emojis[Math.floor(Math.random() * emojis.length)];
                item.style.left = Math.random() * 100 + '%';
                item.style.top = Math.random() * 100 + '%';
                item.style.animationDelay = Math.random() * 10 + 's';
                item.style.animationDuration = (15 + Math.random() * 10) + 's';
                container.appendChild(item);
            }
        }

        function createStars() {
            const container = document.getElementById('stars');
            
            for (let i = 0; i < 50; i++) {
                const star = document.createElement('div');
                star.className = 'star';
                star.style.left = Math.random() * 100 + '%';
                star.style.top = Math.random() * 100 + '%';
                star.style.animationDelay = Math.random() * 2 + 's';
                star.style.animationDuration = (1.5 + Math.random() * 1.5) + 's';
                container.appendChild(star);
            }
        }

        document.addEventListener('DOMContentLoaded', function() {
            createFloatingElements();
            createStars();
        });
    </script>
</body>
</html>
