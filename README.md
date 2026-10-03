<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ангелина — Веб-разработчик</title>
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }
  
  body {
    font-family: -apple-system, 'Segoe UI', Roboto, sans-serif;
    background: #0a0e1a;
    color: #e2e8f0;
    line-height: 1.7;
    overflow-x: hidden;
  }

  header {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 60px 24px;
    position: relative;
    background: radial-gradient(circle at 50% 40%, #1e2a4a 0%, #0a0e1a 70%);
    overflow: hidden;
  }

  header::before {
    content: '';
    position: absolute;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: 
      radial-gradient(circle at 20% 30%, rgba(59, 130, 246, 0.15), transparent 40%),
      radial-gradient(circle at 80% 70%, rgba(139, 92, 246, 0.15), transparent 40%);
    animation: pulse 10s ease-in-out infinite;
  }

  @keyframes pulse {
    0%, 100% { transform: scale(1); opacity: 0.8; }
    50% { transform: scale(1.1); opacity: 1; }
  }

  .header-content {
    position: relative;
    z-index: 2;
    max-width: 800px;
  }

  .status {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(16, 185, 129, 0.1);
    border: 1px solid rgba(16, 185, 129, 0.3);
    color: #10b981;
    padding: 8px 18px;
    border-radius: 50px;
    font-size: 13px;
    letter-spacing: 0.5px;
    margin-bottom: 30px;
    font-weight: 600;
  }

  .status-dot {
    width: 8px;
    height: 8px;
    background: #10b981;
    border-radius: 50%;
    box-shadow: 0 0 10px #10b981;
    animation: blink 2s infinite;
  }

  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.4; }
  }

  h1 {
    font-size: 68px;
    font-weight: 800;
    color: #fff;
    margin-bottom: 20px;
    letter-spacing: -2px;
    line-height: 1.1;
  }

  .gradient-text {
    background: linear-gradient(135deg, #3b82f6, #8b5cf6, #06b6d4);
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .subtitle {
    font-size: 22px;
    color: #94a3b8;
    margin-bottom: 45px;
    font-weight: 400;
    max-width: 600px;
    margin-left: auto;
    margin-right: auto;
  }

  .header-buttons {
    display: flex;
    gap: 15px;
    justify-content: center;
    flex-wrap: wrap;
  }

  .btn {
    display: inline-block;
    padding: 16px 36px;
    border-radius: 12px;
    text-decoration: none;
    font-size: 16px;
    font-weight: 600;
    transition: all 0.3s;
    border: 2px solid transparent;
    cursor: pointer;
    letter-spacing: 0.3px;
  }

  .btn-primary {
    background: linear-gradient(135deg, #3b82f6, #6366f1);
    color: #fff;
    box-shadow: 0 10px 30px rgba(59, 130, 246, 0.4);
  }

  .btn-primary:hover {
    transform: translateY(-3px);
    box-shadow: 0 15px 40px rgba(59, 130, 246, 0.6);
  }

  .btn-outline {
    background: transparent;
    color: #e2e8f0;
    border: 2px solid #334155;
  }

  .btn-outline:hover {
    border-color: #3b82f6;
    color: #3b82f6;
  }

  section {
    padding: 100px 24px;
    max-width: 1100px;
    margin: 0 auto;
  }

  .section-label {
    display: block;
    color: #3b82f6;
    font-size: 14px;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 15px;
    text-align: center;
  }

  h2 {
    font-size: 44px;
    color: #fff;
    text-align: center;
    margin-bottom: 20px;
    font-weight: 800;
    letter-spacing: -1px;
  }

  .section-subtitle {
    text-align: center;
    color: #94a3b8;
    font-size: 18px;
    margin-bottom: 60px;
    max-width: 600px;
    margin-left: auto;
    margin-right: auto;
  }

  .about-text {
    max-width: 800px;
    margin: 0 auto;
    text-align: center;
    font-size: 18px;
    color: #cbd5e1;
    line-height: 1.9;
  }

  .about-stats {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 20px;
    margin-top: 60px;
  }

  .stat {
    background: rgba(30, 41, 59, 0.5);
    border: 1px solid #1e293b;
    border-radius: 16px;
    padding: 30px 20px;
    text-align: center;
    transition: all 0.3s;
  }

  .stat:hover {
    border-color: #3b82f6;
    transform: translateY(-5px);
  }

  .stat-number {
    font-size: 42px;
    font-weight: 800;
    color: #fff;
    margin-bottom: 8px;
  }

  .stat-label {
    color: #94a3b8;
    font-size: 14px;
  }

  .services {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 24px;
  }

  .service {
    background: rgba(30, 41, 59, 0.4);
    border: 1px solid #1e293b;
    border-radius: 20px;
    padding: 40px 32px;
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
  }

  .service::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 3px;
    background: linear-gradient(90deg, #3b82f6, #8b5cf6, #06b6d4);
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.4s;
  }

  .service:hover {
    border-color: #334155;
    transform: translateY(-8px);
    background: rgba(30, 41, 59, 0.7);
  }

  .service:hover::before {
    transform: scaleX(1);
  }

  .service-number {
    font-size: 14px;
    font-weight: 700;
    color: #3b82f6;
    letter-spacing: 2px;
    margin-bottom: 20px;
  }

  .service-title {
    font-size: 24px;
    color: #fff;
    margin-bottom: 15px;
    font-weight: 700;
  }

  .service-desc {
    color: #94a3b8;
    font-size: 16px;
    line-height: 1.7;
  }

  .portfolio {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 28px;
  }

  .work {
    background: rgba(30, 41, 59, 0.4);
    border: 1px solid #1e293b;
    border-radius: 20px;
    overflow: hidden;
    text-decoration: none;
    transition: all 0.3s;
    display: block;
  }

  .work:hover {
    transform: translateY(-8px);
    border-color: #3b82f6;
    box-shadow: 0 20px 50px rgba(59, 130, 246, 0.2);
  }

  .work-preview {
    height: 200px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 64px;
    font-weight: 800;
    color: #fff;
    letter-spacing: -3px;
    position: relative;
    overflow: hidden;
  }

  .work-preview-1 { background: linear-gradient(135deg, #ec4899, #8b5cf6); }
  .work-preview-2 { background: linear-gradient(135deg, #f59e0b, #ec4899); }
  .work-preview-3 { background: linear-gradient(135deg, #10b981, #06b6d4); }
  .work-preview-4 { background: linear-gradient(135deg, #8b4513, #cd853f); }

  .work-info {
    padding: 28px;
  }

  .work-title {
    font-size: 20px;
    color: #fff;
    margin-bottom: 8px;
    font-weight: 700;
  }

  .work-desc {
    color: #94a3b8;
    font-size: 15px;
    margin-bottom: 15px;
    line-height: 1.6;
  }

  .work-tag {
    display: inline-block;
    background: rgba(59, 130, 246, 0.15);
    color: #60a5fa;
    padding: 5px 14px;
    border-radius: 20px;
    font-size: 12px;
    font-weight: 600;
    letter-spacing: 0.5px;
  }

  .cta {
    background: linear-gradient(135deg, #1e293b, #0f172a);
    border-top: 1px solid #1e293b;
    border-bottom: 1px solid #1e293b;
    text-align: center;
    padding: 100px 24px;
  }

  .cta h2 {
    margin-bottom: 25px;
  }

  .cta-btn {
    display: inline-block;
    padding: 20px 50px;
    background: linear-gradient(135deg, #3b82f6, #6366f1);
    color: #fff;
    text-decoration: none;
    border-radius: 14px;
    font-size: 18px;
    font-weight: 700;
    box-shadow: 0 15px 40px rgba(59, 130, 246, 0.4);
    transition: all 0.3s;
    letter-spacing: 0.5px;
  }

  .cta-btn:hover {
    transform: translateY(-3px);
    box-shadow: 0 20px 50px rgba(59, 130, 246, 0.6);
  }

  .contacts-section {
    text-align: center;
  }

  .contact-link {
    display: inline-flex;
    align-items: center;
    gap: 12px;
    padding: 18px 40px;
    background: rgba(59, 130, 246, 0.1);
    border: 2px solid rgba(59, 130, 246, 0.3);
    color: #60a5fa;
    text-decoration: none;
    border-radius: 14px;
    font-size: 17px;
    font-weight: 600;
    transition: all 0.3s;
    margin-top: 20px;
  }

  .contact-link:hover {
    background: rgba(59, 130, 246, 0.2);
    border-color: #3b82f6;
    transform: translateY(-3px);
  }

  footer {
    background: #05070d;
    color: #64748b;
    text-align: center;
    padding: 40px 24px;
    font-size: 14px;
    border-top: 1px solid #1e293b;
  }

  @media (max-width: 700px) {
    h1 { font-size: 42px; letter-spacing: -1px; }
    h2 { font-size: 30px; }
    .subtitle { font-size: 17px; }
    section { padding: 70px 20px; }
    .header-buttons { flex-direction: column; align-items: stretch; }
    .btn { text-align: center; }
    .about-text { font-size: 16px; }
    .service { padding: 30px 24px; }
    .stat-number { font-size: 34px; }
    .cta-btn { padding: 16px 32px; font-size: 16px; }
  }
</style>
</head>
<body>

<header>
  <div class="header-content">
    <div class="status">
      <span class="status-dot"></span>
      Открыта для новых проектов
    </div>
    <h1>Ангелина <span class="gradient-text">Веб-разработчик</span></h1>
    <p class="subtitle">Создаю сайты-визитки, лендинги и игры в браузере. Быстро, красиво, без лишних сложностей.</p>
    <div class="header-buttons">
      <a href="#portfolio" class="btn btn-primary">Смотреть работы</a>
      <a href="https://t.me/a_nggelinsss" class="btn btn-outline">Связаться</a>
    </div>
  </div>
</header>

<section>
  <span class="section-label">Обо мне</span>
  <h2>Кто я</h2>
  <p class="about-text">
    Я — веб-разработчик. Делаю современные сайты для малого бизнеса, личных проектов и портфолио. Работаю с GitHub Pages — это значит, что сайты получаются быстрыми, надёжными и без навязчивой рекламы.
  </p>
  <p class="about-text" style="margin-top: 20px;">
    Каждый проект делаю с вниманием к деталям: от структуры до последней кнопки.
  </p>

  <div class="about-stats">
    <div class="stat">
      <div class="stat-number">4+</div>
      <div class="stat-label">Готовых проекта</div>
    </div>
    <div class="stat">
      <div class="stat-number">7</div>
      <div class="stat-label">Дней на проект</div>
    </div>
    <div class="stat">
      <div class="stat-number">100%</div>
      <div class="stat-label">Адаптивный дизайн</div>
    </div>
  </div>
</section>

<section>
  <span class="section-label">Услуги</span>
  <h2>Что я делаю</h2>
  <p class="section-subtitle">Выберите то, что подходит вашему проекту</p>

  <div class="services">
    <div class="service">
      <div class="service-number">01</div>
      <div class="service-title">Сайт-визитка</div>
      <div class="service-desc">Красивый одностраничный сайт для мастера, услуги или бизнеса. Услуги, цены, контакты, кнопки связи.</div>
    </div>
    <div class="service">
      <div class="service-number">02</div>
      <div class="service-title">Лендинг</div>
      <div class="service-desc">Продающая страница для продвижения одной услуги или продукта. Продуманная структура и убедительные блоки.</div>
    </div>
    <div class="service">
      <div class="service-number">03</div>
      <div class="service-title">Игра в браузере</div>
      <div class="service-desc">Мини-игра для сайта или развлечения: змейка, кликер, викторина. Работает на телефоне и компьютере.</div>
    </div>
    <div class="service">
      <div class="service-number">04</div>
      <div class="service-title">Сайт под ключ</div>
      <div class="service-desc">Полный цикл: от обсуждения идеи до публикации. Помогу с текстом, структурой и запуском.</div>
    </div>
  </div>
</section>

<section id="portfolio">
  <span class="section-label">Портфолио</span>
  <h2>Мои работы</h2>
  <p class="section-subtitle">Несколько проектов, которые я сделала</p>

  <div class="portfolio">
    <a href="https://angelina3007383.github.io/-maksim-love-2025/" class="work" target="_blank">
      <div class="work-preview work-preview-1">LOVE</div>
      <div class="work-info">
        <div class="work-title">Сайт-признание</div>
        <div class="work-desc">Персональный сайт с фото, музыкой, анимацией и таймером.</div>
        <span class="work-tag">Личный проект</span>
      </div>
    </a>

    <a href="https://angelina3007383.github.io/nails-studio/" class="work" target="_blank">
      <div class="work-preview work-preview-2">NAILS</div>
      <div class="work-info">
        <div class="work-title">Nails Studio</div>
        <div class="work-desc">Сайт-визитка мастера маникюра: услуги, цены, отзывы, контакты.</div>
        <span class="work-tag">Сайт-визитка</span>
      </div>
    </a>

    <a href="https://angelina3007383.github.io/snake-game/" class="work" target="_blank">
      <div class="work-preview work-preview-3">SNAKE</div>
      <div class="work-info">
        <div class="work-title">Игра «Змейка»</div>
        <div class="work-desc">Браузерная игра с управлением свайпами и сохранением рекорда.</div>
        <span class="work-tag">Игра</span>
      </div>
    </a>

    <a href="https://angelina3007383.github.io/-glina-studio/" class="work" target="_blank">
      <div class="work-preview work-preview-4">GLINA</div>
      <div class="work-info">
        <div class="work-title">Студия «Глина»</div>
        <div class="work-desc">Сайт студии керамики: мастер-классы, изделия, отзывы, контакты.</div>
        <span class="work-tag">Для бизнеса</span>
      </div>
    </a>
  </div>
</section>

<div class="cta">
  <span class="section-label">Стоимость</span>
  <h2>Хотите узнать цену?</h2>
  <p class="section-subtitle">Напишите мне — обсудим ваш проект, сроки и стоимость. Отвечу быстро.</p>
  <a href="https://t.me/a_nggelinsss" class="cta-btn">Узнать стоимость</a>
</div>

<section class="contacts-section">
  <span class="section-label">Контакты</span>
  <h2>Свяжитесь со мной</h2>
  <p class="section-subtitle">Открыта для новых проектов и сотрудничества</p>
  <a href="https://t.me/a_nggelinsss" class="contact-link">Telegram — @a_nggelinsss</a>
</section>

<footer>
  <p>© 2025 Ангелина. Веб-разработчик.</p>
  <p style="margin-top: 8px;">Все проекты сделаны на GitHub Pages</p>
</footer>

</body>
</html>