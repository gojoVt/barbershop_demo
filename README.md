<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kings & Cuts Barbershop — Sterling, VA</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet">
<style>
  :root {
    --black: #0a0a0a;
    --cream: #f5f0e8;
    --gold: #c9a84c;
    --red: #b03a2e;
    --gray: #2a2a2a;
    --light-gray: #888;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--black);
    color: var(--cream);
    font-family: 'DM Sans', sans-serif;
    font-weight: 300;
    overflow-x: hidden;
  }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; justify-content: space-between; align-items: center;
    padding: 24px 48px;
    background: linear-gradient(to bottom, rgba(10,10,10,0.95), transparent);
  }
  .logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 28px;
    letter-spacing: 4px;
    color: var(--gold);
  }
  .logo span { color: var(--cream); }
  nav ul { list-style: none; display: flex; gap: 36px; }
  nav ul a {
    text-decoration: none; color: var(--cream);
    font-size: 13px; letter-spacing: 2px; text-transform: uppercase;
    opacity: 0.7; transition: opacity 0.2s;
  }
  nav ul a:hover { opacity: 1; }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    position: relative;
    overflow: hidden;
  }

  .hero-left {
    display: flex; flex-direction: column; justify-content: center;
    padding: 120px 64px 80px 64px;
    position: relative; z-index: 2;
  }

  .eyebrow {
    font-size: 11px; letter-spacing: 5px; text-transform: uppercase;
    color: var(--gold); margin-bottom: 24px;
    display: flex; align-items: center; gap: 12px;
  }
  .eyebrow::before {
    content: ''; display: block;
    width: 32px; height: 1px; background: var(--gold);
  }

  h1 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(72px, 8vw, 120px);
    line-height: 0.9;
    letter-spacing: 2px;
    margin-bottom: 32px;
  }
  h1 em { color: var(--gold); font-style: normal; }

  .hero-desc {
    font-size: 16px; line-height: 1.8;
    color: rgba(245,240,232,0.65);
    max-width: 380px; margin-bottom: 48px;
  }

  .btn-group { display: flex; gap: 16px; flex-wrap: wrap; }

  .btn-primary {
    background: var(--gold); color: var(--black);
    padding: 16px 36px; border: none; cursor: pointer;
    font-family: 'DM Sans', sans-serif;
    font-size: 13px; font-weight: 500;
    letter-spacing: 2px; text-transform: uppercase;
    text-decoration: none;
    transition: background 0.2s, transform 0.2s;
    display: inline-block;
  }
  .btn-primary:hover { background: #e0bc6a; transform: translateY(-2px); }

  .btn-outline {
    background: transparent; color: var(--cream);
    padding: 16px 36px;
    border: 1px solid rgba(245,240,232,0.3); cursor: pointer;
    font-family: 'DM Sans', sans-serif;
    font-size: 13px; font-weight: 400;
    letter-spacing: 2px; text-transform: uppercase;
    text-decoration: none;
    transition: border-color 0.2s, transform 0.2s;
    display: inline-block;
  }
  .btn-outline:hover { border-color: var(--cream); transform: translateY(-2px); }

  .hero-right {
    position: relative; overflow: hidden;
  }
  .hero-right::before {
    content: '';
    position: absolute; inset: 0;
    background: linear-gradient(to right, var(--black) 0%, transparent 30%),
                linear-gradient(to top, var(--black) 0%, transparent 20%);
    z-index: 1;
  }
  .hero-image {
    width: 100%; height: 100%;
    object-fit: cover; opacity: 0.7;
    display: block;
  }
  .hero-image-placeholder {
    width: 100%; height: 100%;
    background: 
      repeating-linear-gradient(
        45deg,
        #1a1a1a 0px, #1a1a1a 2px,
        #141414 2px, #141414 20px
      );
    display: flex; align-items: center; justify-content: center;
  }
  .barber-icon {
    font-size: 120px; opacity: 0.15; z-index: 0;
  }

  /* big decorative text */
  .deco-text {
    position: absolute; bottom: 60px; right: -20px;
    font-family: 'Bebas Neue', sans-serif;
    font-size: 180px; line-height: 1;
    color: transparent;
    -webkit-text-stroke: 1px rgba(201,168,76,0.15);
    letter-spacing: 8px;
    z-index: 0; user-select: none;
    pointer-events: none;
  }

  /* stats row */
  .stats {
    display: flex; gap: 48px; margin-top: 64px;
    padding-top: 48px;
    border-top: 1px solid rgba(245,240,232,0.1);
  }
  .stat-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 42px; color: var(--gold); line-height: 1;
  }
  .stat-label {
    font-size: 11px; letter-spacing: 2px; text-transform: uppercase;
    color: rgba(245,240,232,0.5); margin-top: 4px;
  }

  /* ── SERVICES ── */
  #services {
    padding: 120px 64px;
    position: relative;
  }
  .section-header {
    display: flex; justify-content: space-between; align-items: flex-end;
    margin-bottom: 64px;
  }
  .section-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(48px, 5vw, 72px);
    letter-spacing: 3px; line-height: 1;
  }
  .section-title em { color: var(--gold); font-style: normal; }
  .section-sub {
    font-size: 13px; letter-spacing: 2px; text-transform: uppercase;
    color: var(--light-gray);
  }

  .services-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2px;
  }
  .service-card {
    background: var(--gray);
    padding: 48px 40px;
    position: relative; overflow: hidden;
    transition: background 0.3s;
    cursor: default;
  }
  .service-card:hover { background: #333; }
  .service-card::after {
    content: '';
    position: absolute; bottom: 0; left: 0; right: 0;
    height: 3px; background: var(--gold);
    transform: scaleX(0); transform-origin: left;
    transition: transform 0.3s;
  }
  .service-card:hover::after { transform: scaleX(1); }

  .service-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 64px; color: rgba(201,168,76,0.12);
    line-height: 1; position: absolute;
    top: 20px; right: 24px;
  }
  .service-name {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 28px; letter-spacing: 2px;
    margin-bottom: 12px; margin-top: 8px;
  }
  .service-desc {
    font-size: 14px; line-height: 1.7;
    color: rgba(245,240,232,0.55);
    margin-bottom: 24px;
  }
  .service-price {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 36px; color: var(--gold);
  }
  .service-price span {
    font-family: 'DM Sans', sans-serif;
    font-size: 13px; color: var(--light-gray);
    font-weight: 300;
  }

  /* ── ABOUT ── */
  #about {
    padding: 120px 64px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: center;
    background: #0f0f0f;
  }
  .about-eyebrow {
    font-size: 11px; letter-spacing: 5px; text-transform: uppercase;
    color: var(--gold); margin-bottom: 24px;
    display: flex; align-items: center; gap: 12px;
  }
  .about-eyebrow::before {
    content: ''; display: block;
    width: 32px; height: 1px; background: var(--gold);
  }
  #about h2 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(42px, 4vw, 64px);
    letter-spacing: 2px; line-height: 1.05;
    margin-bottom: 28px;
  }
  #about h2 em { color: var(--gold); font-style: normal; }
  #about p {
    font-size: 15px; line-height: 1.9;
    color: rgba(245,240,232,0.6);
    margin-bottom: 20px;
  }
  .about-visual {
    position: relative;
  }
  .about-box {
    width: 100%; aspect-ratio: 4/5;
    background: var(--gray);
    display: flex; align-items: center; justify-content: center;
    font-size: 80px; opacity: 0.3;
    position: relative; overflow: hidden;
  }
  .about-box::before {
    content: '';
    position: absolute;
    top: -50%; left: -50%;
    width: 200%; height: 200%;
    background: repeating-linear-gradient(
      45deg,
      transparent, transparent 18px,
      rgba(201,168,76,0.04) 18px, rgba(201,168,76,0.04) 20px
    );
  }
  .about-badge {
    position: absolute;
    bottom: -20px; right: -20px;
    width: 120px; height: 120px;
    background: var(--gold);
    display: flex; flex-direction: column;
    align-items: center; justify-content: center;
  }
  .about-badge-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 42px; color: var(--black); line-height: 1;
  }
  .about-badge-text {
    font-size: 10px; letter-spacing: 1px;
    text-transform: uppercase; color: var(--black);
    font-weight: 500; text-align: center;
    line-height: 1.3;
  }

  /* ── HOURS / CONTACT ── */
  #contact {
    padding: 120px 64px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
  }
  #contact h2 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(42px, 4vw, 64px);
    letter-spacing: 2px; line-height: 1.05;
    margin-bottom: 48px;
  }
  #contact h2 em { color: var(--gold); font-style: normal; }

  .hours-list { list-style: none; }
  .hours-list li {
    display: flex; justify-content: space-between;
    padding: 18px 0;
    border-bottom: 1px solid rgba(245,240,232,0.08);
    font-size: 14px;
  }
  .hours-list li .day { letter-spacing: 1px; text-transform: uppercase; font-size: 12px; }
  .hours-list li .time { color: var(--gold); }
  .hours-list li.closed .time { color: var(--light-gray); }

  .contact-info { display: flex; flex-direction: column; gap: 32px; }
  .contact-item {}
  .contact-label {
    font-size: 10px; letter-spacing: 3px; text-transform: uppercase;
    color: var(--light-gray); margin-bottom: 8px;
  }
  .contact-value {
    font-size: 20px; color: var(--cream);
  }

  .book-block {
    margin-top: 48px;
    padding: 40px;
    background: var(--gold);
    text-align: center;
  }
  .book-block p {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 28px; letter-spacing: 3px;
    color: var(--black); margin-bottom: 20px;
  }
  .book-block a {
    display: inline-block;
    background: var(--black); color: var(--gold);
    padding: 14px 36px;
    font-size: 12px; letter-spacing: 3px; text-transform: uppercase;
    text-decoration: none; font-weight: 500;
    transition: background 0.2s;
  }
  .book-block a:hover { background: #1a1a1a; }

  /* ── FOOTER ── */
  footer {
    background: #060606;
    padding: 40px 64px;
    display: flex; justify-content: space-between; align-items: center;
    border-top: 1px solid rgba(245,240,232,0.06);
  }
  .footer-logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 22px; letter-spacing: 4px; color: var(--gold);
  }
  footer p {
    font-size: 12px; color: rgba(245,240,232,0.3);
    letter-spacing: 1px;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }
  .hero-left > * {
    animation: fadeUp 0.8s ease forwards;
    opacity: 0;
  }
  .hero-left > *:nth-child(1) { animation-delay: 0.1s; }
  .hero-left > *:nth-child(2) { animation-delay: 0.25s; }
  .hero-left > *:nth-child(3) { animation-delay: 0.4s; }
  .hero-left > *:nth-child(4) { animation-delay: 0.55s; }
  .hero-left > *:nth-child(5) { animation-delay: 0.7s; }

  /* ── RESPONSIVE ── */
  @media (max-width: 900px) {
    nav { padding: 20px 24px; }
    nav ul { display: none; }
    .hero { grid-template-columns: 1fr; }
    .hero-right { display: none; }
    .hero-left { padding: 100px 24px 60px; }
    .services-grid { grid-template-columns: 1fr; }
    #about, #contact { grid-template-columns: 1fr; padding: 60px 24px; }
    #services { padding: 60px 24px; }
    footer { flex-direction: column; gap: 12px; text-align: center; padding: 32px 24px; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="logo">Kings <span>&</span> Cuts</div>
  <ul>
    <li><a href="#services">Services</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-left">
    <div class="eyebrow">Sterling, Virginia · Est. 2011</div>
    <h1>SHARP<br>LOOKS.<br><em>REAL</em><br>SKILL.</h1>
    <p class="hero-desc">Premium cuts, straight-razor shaves, and old-school craft — delivered by barbers who've been doing this for decades. Walk in. Walk out looking like a king.</p>
    <div class="btn-group">
      <a href="#contact" class="btn-primary">Book a Cut</a>
      <a href="#services" class="btn-outline">See Services</a>
    </div>
    <div class="stats">
      <div>
        <div class="stat-num">12+</div>
        <div class="stat-label">Years Open</div>
      </div>
      <div>
        <div class="stat-num">4.9★</div>
        <div class="stat-label">Google Rating</div>
      </div>
      <div>
        <div class="stat-num">3K+</div>
        <div class="stat-label">Happy Clients</div>
      </div>
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-image-placeholder">
      <div class="barber-icon">✂</div>
    </div>
    <div class="deco-text">KINGS</div>
  </div>
</section>

<!-- SERVICES -->
<section id="services">
  <div class="section-header">
    <h2 class="section-title">OUR<br><em>SERVICES</em></h2>
    <div class="section-sub">All cuts include hot towel finish</div>
  </div>
  <div class="services-grid">
    <div class="service-card">
      <div class="service-num">01</div>
      <div class="service-name">Classic Cut</div>
      <p class="service-desc">Scissor or clipper cut, styled and finished with a hot towel. The foundation of every great look.</p>
      <div class="service-price">$30 <span>/ per visit</span></div>
    </div>
    <div class="service-card">
      <div class="service-num">02</div>
      <div class="service-name">Fade & Design</div>
      <p class="service-desc">Skin fade, taper, or mid-fade with custom line work. Precision down to every edge.</p>
      <div class="service-price">$40 <span>/ per visit</span></div>
    </div>
    <div class="service-card">
      <div class="service-num">03</div>
      <div class="service-name">Beard Trim</div>
      <p class="service-desc">Shape, line-up, and condition. Add a straight-razor finish for the cleanest edges in NoVA.</p>
      <div class="service-price">$20 <span>/ add-on $15</span></div>
    </div>
    <div class="service-card">
      <div class="service-num">04</div>
      <div class="service-name">Hot Shave</div>
      <p class="service-desc">Full straight-razor shave with warm lather, hot towel, and aftercare balm. Pure luxury.</p>
      <div class="service-price">$35 <span>/ per visit</span></div>
    </div>
    <div class="service-card">
      <div class="service-num">05</div>
      <div class="service-name">Kids Cut</div>
      <p class="service-desc">For the young kings. Patient, careful, and fun. Ages 12 and under welcome anytime.</p>
      <div class="service-price">$22 <span>/ per visit</span></div>
    </div>
    <div class="service-card">
      <div class="service-num">06</div>
      <div class="service-name">Full Package</div>
      <p class="service-desc">Cut + beard trim + hot towel + lineup. The complete treatment from top to bottom.</p>
      <div class="service-price">$60 <span>/ best value</span></div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="about-content">
    <div class="about-eyebrow">Our Story</div>
    <h2>NOT JUST<br>A <em>HAIRCUT.</em><br>AN EXPERIENCE.</h2>
    <p>Kings & Cuts has been a cornerstone of the Sterling community since 2011. Founded by Marcus Johnson — a barber with 20+ years of experience — our shop is built on the belief that every man deserves to look and feel his best.</p>
    <p>We don't rush. We don't cut corners. We take the time to listen to what you want and deliver every single time. No appointments needed — just walk in and we've got you.</p>
    <a href="#contact" class="btn-primary" style="margin-top: 16px;">Come In Today</a>
  </div>
  <div class="about-visual">
    <div class="about-box">✂</div>
    <div class="about-badge">
      <div class="about-badge-num">20+</div>
      <div class="about-badge-text">Years of Craft</div>
    </div>
  </div>
</section>

<!-- HOURS & CONTACT -->
<section id="contact">
  <div>
    <h2>HOURS &<br><em>LOCATION</em></h2>
    <ul class="hours-list">
      <li><span class="day">Monday</span><span class="time">9:00 AM – 7:00 PM</span></li>
      <li><span class="day">Tuesday</span><span class="time">9:00 AM – 7:00 PM</span></li>
      <li><span class="day">Wednesday</span><span class="time">9:00 AM – 7:00 PM</span></li>
      <li><span class="day">Thursday</span><span class="time">9:00 AM – 8:00 PM</span></li>
      <li><span class="day">Friday</span><span class="time">9:00 AM – 8:00 PM</span></li>
      <li><span class="day">Saturday</span><span class="time">8:00 AM – 6:00 PM</span></li>
      <li class="closed"><span class="day">Sunday</span><span class="time">Closed</span></li>
    </ul>
  </div>
  <div>
    <h2>GET IN<br><em>TOUCH</em></h2>
    <div class="contact-info">
      <div class="contact-item">
        <div class="contact-label">Address</div>
        <div class="contact-value">123 Broad Run Dr<br>Sterling, VA 20164</div>
      </div>
      <div class="contact-item">
        <div class="contact-label">Phone</div>
        <div class="contact-value">(571) 555-0182</div>
      </div>
      <div class="contact-item">
        <div class="contact-label">Walk-ins</div>
        <div class="contact-value">Always Welcome</div>
      </div>
    </div>
    <div class="book-block">
      <p>READY FOR YOUR BEST CUT?</p>
      <a href="tel:5715550182">Call to Book Now</a>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">Kings & Cuts</div>
  <p>© 2025 Kings & Cuts Barbershop · Sterling, VA</p>
  <p>Made with ♥ for the community</p>
</footer>

</body>
</html>
