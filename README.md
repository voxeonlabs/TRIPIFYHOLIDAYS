<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Tripify Holidays</title>
  <meta name="description" content="Premium holiday packages tailored for beaches, mountains, city escapes and honeymoon getaways." />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Manrope:wght@400;500;600;700;800&family=Playfair+Display:wght@600;700;800&display=swap" rel="stylesheet" />
  <style>
    :root {
      --royal: #1b3a8c;
      --ocean: #2563c4;
      --sky: #5ba3e8;
      --sky-soft: #eaf3fc;
      --ink: #132038;
      --gray: #62738b;
      --surface: #f5f7fb;
      --line: #e3e9f2;
      --gold: #c9962e;
      --green: #1d8a5e;
      --red: #c43c3c;
      --shadow: 0 8px 26px rgba(19, 32, 56, 0.08);
      --shadow-lg: 0 18px 46px rgba(19, 32, 56, 0.14);
      --nav-h: 72px;
      --radius: 18px;
    }

   *{ box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
      margin: 0;
      font-family: 'Manrope', sans-serif;
      background: #fff;
      color: var(--ink);
      line-height: 1.55;
    }
    a { color: inherit; text-decoration: none; }
    img { max-width: 100%; display: block; }
    button, input, select, textarea { font: inherit; }
    h1, h2, h3, h4, .serif { font-family: 'Playfair Display', serif; }
    .container { width: min(1200px, calc(100% - 32px)); margin: 0 auto; }
    section { padding: 72px 0; }
    .eyebrow {
      display: inline-block;
      font-size: 12px;
      text-transform: uppercase;
      letter-spacing: 0.18em;
      font-weight: 800;
      color: var(--ocean);
    }
    .sec-title {
      font-size: clamp(28px, 3vw, 42px);
      margin: 10px 0 12px;
      line-height: 1.1;
    }
    .sec-sub { max-width: 620px; color: var(--gray); }

   .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      border: 1px solid transparent;
      border-radius: 12px;
      padding: 13px 22px;
      font-weight: 800;
      cursor: pointer;
      transition: transform .18s ease, box-shadow .18s ease, border-color .2s ease, background .2s ease;
      white-space: nowrap;
    }
    .btn:hover { transform: translateY(-1px); }
    .btn-primary {
      background: linear-gradient(135deg, var(--royal), var(--ocean));
      color: #fff;
      box-shadow: 0 10px 25px rgba(27, 58, 140, 0.24);
    }
    .btn-secondary {
      background: #fff;
      color: var(--ink);
      border-color: var(--line);
    }
    .btn-ghost {
      background: transparent;
      border-color: var(--line);
      color: var(--ink);
    }

  .chip {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      padding: 6px 12px;
      border-radius: 999px;
      background: var(--sky-soft);
      color: var(--ocean);
      font-size: 12px;
      font-weight: 800;
    }

   .card {
      background: #fff;
      box-shadow: var(--shadow);
      border-radius: var(--radius);
      overflow: hidden;
    }
    .nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      height: var(--nav-h);
      z-index: 100;
      background: rgba(255,255,255,0.72);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid transparent;
      transition: background .25s ease, border-color .25s ease, box-shadow .25s ease;
    }
    .nav.scrolled {
      background: rgba(255,255,255,0.94);
      border-color: var(--line);
      box-shadow: 0 8px 24px rgba(19, 32, 56, 0.06);
    }
    .nav-inner {
      height: 100%;
      display: flex;
      align-items: center;
      gap: 28px;
    }
    .logo {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      color: var(--royal);
      font-weight: 800;
      font-size: 20px;
      font-family: 'Playfair Display', serif;
      letter-spacing: 0.04em;
    }
    .logo small {
      display: block;
      font-size: 10px;
      letter-spacing: 0.28em;
      font-family: 'Manrope', sans-serif;
      color: var(--gray);
      margin-top: 2px;
    }
    .nav-links {
      display: flex;
      align-items: center;
      gap: 26px;
      margin-left: auto;
      font-weight: 700;
      font-size: 14px;
    }
    .nav-links a { position: relative; padding: 4px 0; color: var(--ink); }
    .nav-links a::after {
      content: ''; position: absolute; left: 0; bottom: -4px; width: 0; height: 2px; background: var(--ocean); border-radius: 999px; transition: width .2s ease;
    }
    .nav-links a.active::after, .nav-links a:hover::after { width: 100%; }
    .nav-actions { display: flex; align-items: center; gap: 12px; }
    .burger { display: none; }
    .mobile-menu {
      position: fixed;
      top: var(--nav-h);
      left: 0; right: 0;
      background: rgba(255,255,255,0.98);
      display: none;
      flex-direction: column;
      padding: 18px 20px 22px;
      gap: 14px;
      box-shadow: var(--shadow-lg);
      z-index: 90;
    }
    .mobile-menu.open { display: flex; }

   .page { display: none; min-height: 100vh; }
    .page.on { display: block; }

   .hero {
      position: relative;
      min-height: 92vh;
      display: flex;
      align-items: center;
      background: var(--royal);
      overflow: hidden;
      padding-top: var(--nav-h);
    }
    .hero::before {
      content: '';
      position: absolute; inset: 0;
      background: url('https://images.unsplash.com/photo-1501785888041-af3ef285b470?auto=format&fit=crop&w=1800&q=80') center/cover no-repeat;
      transform: scale(1.08);
      opacity: 0.8;
    }
    .hero::after {
      content: '';
      position: absolute; inset: 0;
      background: linear-gradient(100deg, rgba(9,18,45,0.92), rgba(17,36,87,0.72), rgba(37,99,196,0.32));
    }
    .hero-inner {
      position: relative;
      z-index: 1;
      color: #fff;
      max-width: 660px;
      padding: 60px 0;
    }
    .hero-eyebrow {
      font-size: 12px;
      letter-spacing: 0.22em;
      text-transform: uppercase;
      font-weight: 800;
      color: var(--sky);
    }
    .hero h1 {
      font-size: clamp(42px, 5vw, 68px);
      line-height: 1.08;
      margin: 18px 0 18px;
    }
    .hero h1 em { font-style: normal; color: var(--sky); }
    .hero p {
      margin: 0;
      max-width: 540px;
      color: rgba(255,255,255,0.82);
      font-size: 18px;
    }
    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 14px;
      margin-top: 28px;
    }
    .hero .btn-secondary { border-color: rgba(255,255,255,0.4); color: #fff; background: rgba(255,255,255,0.04); }

   .search-wrap {
      position: relative;
      z-index: 5;
      margin-top: -70px;
      margin-bottom: 12px;
    }
    .search-box {
      background: #fff;
      padding: 22px;
      border-radius: 20px;
      box-shadow: var(--shadow-lg);
      display: grid;
      grid-template-columns: repeat(5, minmax(0, 1fr)) auto;
      gap: 14px;
      align-items: end;
    }
    .field { width: 100%; }
    .field label {
      display: block;
      margin-bottom: 6px;
      font-size: 12px;
      font-weight: 800;
      letter-spacing: 0.03em;
   color: var(--gray);
      text-transform: uppercase;
    }
    .field input, .field select, .field textarea {
      width: 100%;
      border: 1.5px solid var(--line);
      border-radius: 10px;
      background: #fff;
      padding: 12px 12px;
      color: var(--ink);
      font-size: 15px;
    }
    .field textarea { min-height: 92px; resize: vertical; }
    .field input:focus, .field select:focus, .field textarea:focus { outline: none; border-color: var(--ocean); box-shadow: 0 0 0 3px rgba(37,99,196,0.12); }

  .caro-wrap { position: relative; }
    .caro {
      display: flex;
      gap: 20px;
      overflow-x: auto;
      padding: 8px 4px 18px;
      scrollbar-width: none;
      scroll-snap-type: x proximity;
    }
    .caro::-webkit-scrollbar { display: none; }
    .caro > * { scroll-snap-align: start; }
    .caro-btn {
      position: absolute;
  top: 48%;
      transform: translateY(-50%);
      width: 42px; height: 42px;
      display: flex; align-items: center; justify-content: center;
      border-radius: 50%;
      background: #fff;
      box-shadow: var(--shadow-lg);
      color: var(--royal);
      cursor: pointer;
      z-index: 2;
      border: 1px solid rgba(19,32,56,0.04);
    }
    .caro-btn.prev { left: -14px; }
    .caro-btn.next { right: -14px; }

   .dest-card {
      position: relative;
      width: 250px;
      height: 300px;
      border-radius: var(--radius);
      overflow: hidden;
      cursor: pointer;
      box-shadow: var(--shadow);
      background: #dfeafc;
      flex: 0 0 auto;
    }
    .dest-card img {
      width: 100%; height: 100%; object-fit: cover;
  transition: transform .4s ease;
    }
    .dest-card:hover img { transform: scale(1.06); }
    .dest-overlay {
      position: absolute; inset: 0;
      background: linear-gradient(180deg, transparent 35%, rgba(11,24,52,0.88));
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      padding: 18px;
      color: #fff;
    }
    .dest-overlay h3 { margin: 0; font-size: 22px; }
    .dest-overlay span { opacity: 0.82; font-size: 13px; }

   .pkg-card {
      width: 320px;
      flex: 0 0 auto;
      background: #fff;
      border-radius: var(--radius);
      overflow: hidden;
      border: 1px solid var(--line);
      box-shadow: var(--shadow);
      position: relative;
    }
    .pkg-image-wrap { position: relative; }
    .pkg-image-wrap img {
      width: 100%; height: 200px; object-fit: cover; cursor: pointer;
  transition: transform .35s ease;
    }
    .pkg-card:hover .pkg-image-wrap img { transform: scale(1.05); }
    .floating-heart {
      position: absolute;
      top: 14px; right: 14px;
      width: 38px; height: 38px;
      border-radius: 50%;
      background: rgba(255,255,255,0.9);
      display: flex; align-items: center; justify-content: center;
      color: var(--gray);
      border: 0;
      cursor: pointer;
      box-shadow: var(--shadow);
      transition: transform .2s ease, color .2s ease;
    }
    .floating-heart.active { color: var(--red); }
    .floating-heart:hover { transform: scale(1.08); }
    .tag {
      position: absolute;
      left: 14px; top: 14px;
      background: rgba(201, 150, 46, 0.96);
      color: #fff;
      font-size: 11px;
      font-weight: 800;
      letter-spacing: 0.06em;
      text-transform: uppercase;
      border-radius: 9px;
      padding: 6px 8px;
   }
    .pkg-body {
      padding: 18px 18px 16px;
      display: flex;
      flex-direction: column;
      gap: 10px;
    }
    .pkg-meta {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      align-items: center;
      color: var(--gray);
      font-size: 12px;
      font-weight: 700;
    }
    .pkg-body h3 {
      margin: 0;
      font-size: 20px;
      line-height: 1.25;
      cursor: pointer;
    }
    .pkg-foot {
      margin-top: auto;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 12px;
  padding-top: 12px;
      border-top: 1px solid var(--line);
    }
    .price { color: var(--royal); }
    .price strong { font-size: 22px; font-family: 'Playfair Display', serif; }
    .price span { font-size: 12px; color: var(--gray); }

   .features-grid { display: grid; grid-template-columns: repeat(4, minmax(0, 1fr)); gap: 22px; }
    .feature {
      background: var(--surface);
      border-radius: var(--radius);
      padding: 26px 24px;
      border: 1px solid rgba(227, 233, 242, 0.7);
      transition: transform .2s ease, background .2s ease;
    }
    .feature:hover { transform: translateY(-4px); background: var(--sky-soft); }
    .feature-icon {
      width: 52px; height: 52px; border-radius: 14px;
      background: linear-gradient(135deg, var(--royal), var(--ocean));
      color: #fff; display: flex; align-items: center; justify-content: center;
      margin-bottom: 14px;
    }
    .feature h3 { margin: 0 0 8px; font-size: 20px; }
    .feature p { margin: 0; color: var(--gray); }

   .offer-box {
      position: relative;
      display: grid;
      grid-template-columns: 1fr auto;
  align-items: center;
      gap: 30px;
      background: linear-gradient(135deg, var(--royal), var(--ocean));
      color: #fff;
      border-radius: 28px;
      padding: 52px 42px;
      overflow: hidden;
    }
    .offer-box::before {
      content: '';
      position: absolute;
      width: 300px; height: 300px;
      right: -90px; top: -100px;
      background: rgba(255,255,255,0.08);
      border-radius: 50%;
    }
    .offer-pill {
      display: inline-block;
      padding: 7px 16px;
      border-radius: 999px;
      background: rgba(255,255,255,0.14);
      font-size: 12px; font-weight: 800; letter-spacing: 0.08em; text-transform: uppercase;
    }
    .offer-box h2 { margin: 12px 0 8px; font-size: clamp(28px, 2.8vw, 42px); }
    .offer-box p { margin: 0; color: rgba(255,255,255,0.82); }

   .testimonial-wrap { max-width: 760px; margin: 26px auto 0; }
    .testimonial {
      display: none;
   text-align: center;
    }
    .testimonial.active { display: block; }
    .testimonial img {
      width: 72px; height: 72px; border-radius: 50%; object-fit: cover; margin: 0 auto 18px; border: 4px solid var(--sky-soft);
    }
    .testimonial-quote {
      font-size: clamp(18px, 2vw, 22px);
      margin: 12px 0;
      font-style: italic;
      color: var(--ink);
    }
    .testimonial-name {
      font-size: 15px;
      font-weight: 800;
      color: var(--ocean);
    }
    .testimonial-trip { color: var(--gray); font-size: 13px; margin-top: 4px; }
    .dots {
      display: flex; justify-content: center; gap: 8px; margin-top: 18px;
    }
    .dot {
      width: 10px; height: 10px; border-radius: 50%; background: var(--line); border: 0; cursor: pointer; transition: width .2s ease, background .2s ease;
    }
    .dot.active { width: 26px; border-radius: 999px; background: var(--ocean); }

   .newsletter {
      background: var(--surface);
  border-radius: 24px;
      padding: 30px 26px;
      display: grid;
      grid-template-columns: 1.2fr 1fr;
      gap: 20px;
      align-items: center;
    }
    .newsletter form {
      display: flex;
      align-items: center;
      gap: 10px;
    }
    .newsletter input { min-width: 0; }

   .pageheader {
      background: linear-gradient(120deg, var(--royal), var(--ocean));
      color: #fff;
      padding: 72px 0 96px;
    }
    .pageheader h1 { margin: 10px 0 0; font-size: clamp(28px, 3vw, 42px); }

   .search-layout {
      display: grid;
      grid-template-columns: 270px minmax(0, 1fr);
      gap: 28px;
      margin-top: -56px;
      align-items: start;
    }
  .filter-panel {
      background: #fff;
      box-shadow: var(--shadow);
      border-radius: var(--radius);
      padding: 20px 18px;
      position: sticky; top: calc(var(--nav-h) + 18px);
    }
    .filter-section {
      border-bottom: 1px solid var(--line);
      padding-bottom: 16px;
      margin-bottom: 16px;
    }
    .filter-section:last-child { border-bottom: 0; margin-bottom: 0; }
    .filter-section h4 {
      margin: 0 0 12px;
      font-size: 14px;
      text-transform: uppercase;
      letter-spacing: 0.06em;
      color: var(--gray);
    }
    .check-row {
      display: flex;
      align-items: center;
      gap: 10px;
      color: var(--gray);
      font-weight: 600;
      padding: 6px 0;
    }
  input[type="checkbox"], input[type="radio"] { width: 16px; height: 16px; accent-color: var(--ocean); }
    .toolbar {
      display: flex; align-items: center; justify-content: space-between; gap: 12px; flex-wrap: wrap;
      background: #fff; box-shadow: var(--shadow); border-radius: var(--radius); padding: 12px 18px; margin-bottom: 18px;
    }
    .results-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
      gap: 22px;
    }
    .results-grid .pkg-card { width: 100%; }
    .empty-state {
      display: none;
      text-align: center;
      padding: 80px 16px 40px;
      color: var(--gray);
    }
    .empty-icon {
      width: 78px; height: 78px;
      border-radius: 22px;
      background: var(--sky-soft);
      color: var(--ocean);
      display: flex; align-items: center; justify-content: center; margin: 0 auto 16px;
    }

   .detail-page { padding-top: 80px; }
    .detail-hero {
      display: grid;
   grid-template-columns: 2fr 1fr 1fr;
      grid-template-rows: 200px 200px;
      gap: 10px;
      margin-bottom: 28px;
      border-radius: 24px;
      overflow: hidden;
    }
    .detail-hero img {
      width: 100%; height: 100%; object-fit: cover; cursor: pointer; transition: transform .3s ease;
    }
    .detail-hero img:hover { transform: scale(1.04); }
    .detail-hero .feature-col { grid-row: 1 / span 2; }
    .detail-layout {
      display: grid;
      grid-template-columns: minmax(0,1fr) 320px;
      gap: 30px;
      align-items: start;
    }
    .detail-panel, .booking-panel, .auth-panel, .dash-panel, .admin-panel {
      background: #fff;
      border: 1px solid var(--line);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      padding: 24px;
    }
    .detail-panel + .detail-panel { margin-top: 22px; }
    .title-row {
      display: flex; justify-content: space-between; align-items: flex-start; gap: 18px; flex-wrap: wrap;
      margin-bottom: 16px;
    }
   .detail-header h1 { margin: 0 0 8px; font-size: clamp(28px, 3vw, 40px); }
    .detail-sub {
      margin: 0; color: var(--gray); font-size: 14px;
    }
    .rating-line {
      display: flex; align-items: center; gap: 8px;
      margin-top: 10px;
      font-weight: 700; color: var(--gray);
    }
    .detail-sides {
      position: sticky; top: calc(var(--nav-h) + 16px);
      display: flex; flex-direction: column; gap: 12px;
    }
    .price-box {
      background: var(--sky-soft);
      border-radius: 18px;
      padding: 18px 18px 10px;
      border: 1px solid rgba(37,99,196,0.1);
    }
    .price-box .from { color: var(--gray); font-size: 13px; }
    .price-box .amount {
      font-family: 'Playfair Display', serif;
      font-size: 42px;
      color: var(--royal);
      margin: 8px 0 4px;
    }
    .price-box .status { color: var(--green); font-weight: 800; font-size: 13px; }
    .summary-list { color: var(--gray); font-size: 14px; line-height: 1.9; }
    .itinerary-list { display: grid; gap: 18px; }
   .itinerary-item {
      display: grid;
      grid-template-columns: 40px 1fr;
      gap: 12px;
      align-items: start;
      padding-top: 2px;
    }
    .itinerary-item .badge {
      width: 34px; height: 34px; border-radius: 50%; background: var(--ocean); color: #fff; display: flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 800;
      box-shadow: 0 0 0 6px var(--sky-soft);
    }
    .itinerary-item h4 { margin: 0 0 4px; }
    .itinerary-item p { margin: 0; color: var(--gray); font-size: 14px; }
    .chip-row { display: flex; flex-wrap: wrap; gap: 8px; }

   .checkout-shell { padding-top: 82px; }
    .checkout-layout {
      display: grid;
      grid-template-columns: minmax(0,1fr) 330px;
      gap: 26px;
      align-items: start;
    }
    .booking-panel h3 { margin: 0 0 18px; }
    .form-grid {
      display: grid;
      grid-template-columns: repeat(2, minmax(0,1fr));
      gap: 16px;
    }
   .checkout-summary {
      display: grid;
      gap: 10px;
      font-size: 14px;
    }
    .checkout-summary-row {
      display: flex; justify-content: space-between; gap: 16px;
      padding: 4px 0;
    }
    .checkout-summary-row.total {
      border-top: 1px solid var(--line); margin-top: 8px; padding-top: 12px; font-weight: 800; color: var(--royal); font-size: 18px;
    }
    .success-box {
      text-align: center;
      padding: 24px 10px 8px;
    }
    .success-icon {
      width: 90px; height: 90px; border-radius: 50%; background: #e9f8f0; color: var(--green); display: flex; align-items: center; justify-content: center; font-size: 40px; margin: 0 auto 18px;
    }

   .auth-panel {
      max-width: 440px;
      margin: 70px auto 0;
    }
   .auth-panel h2 { margin: 0 0 8px; }
    .auth-panel p { margin: 0 0 20px; color: var(--gray); }
    .auth-panel form { display: grid; gap: 14px; }
    .auth-panel .btn { width: 100%; }

   .dash-layout {
      display: grid;
      grid-template-columns: 220px minmax(0,1fr);
      gap: 28px;
      margin-top: -56px;
      align-items: start;
    }
    .sidebar {
      background: #fff; border: 1px solid var(--line); border-radius: var(--radius); box-shadow: var(--shadow); padding: 14px; position: sticky; top: calc(var(--nav-h) + 18px);
    }
    .sidebar a {
      display: flex; align-items: center; gap: 10px; width: 100%;
      padding: 12px 14px; border-radius: 10px; font-weight: 700; color: var(--gray);
      transition: background .2s ease, color .2s ease;
    }
    .sidebar a.active, .sidebar a:hover { background: var(--sky-soft); color: var(--ocean); }
    .dashboard-grid {
      display: grid; grid-template-columns: repeat(4, minmax(0,1fr)); gap: 18px; margin-bottom: 20px;
    }
   .metric-card {
      background: #fff; border-radius: var(--radius); box-shadow: var(--shadow); padding: 18px 16px;
    }
    .metric-card span { display: block; font-size: 12px; font-weight: 800; letter-spacing: 0.08em; text-transform: uppercase; color: var(--gray); }
    .metric-card strong { display: block; margin-top: 6px; font-size: 32px; font-family: 'Playfair Display', serif; color: var(--royal); }
    .metric-card small { display: block; margin-top: 6px; color: var(--green); font-weight: 700; }

  .table-wrap { overflow-x: auto; }
    table { width: 100%; border-collapse: collapse; min-width: 640px; }
    th, td {
      padding: 12px 10px;
      border-bottom: 1px solid var(--line);
      text-align: left;
      vertical-align: top;
    }
    th {
  font-size: 11px; text-transform: uppercase; letter-spacing: 0.08em; color: var(--gray); font-weight: 800;
    }
    .status-pill {
      display: inline-flex; padding: 6px 10px; border-radius: 999px; font-weight: 800; font-size: 12px;
    }
    .status-pill.confirmed { background: #eaf9f1; color: var(--green); }
    .status-pill.pending { background: #fff1d8; color: #a46a00; }

   .modal-backdrop {
      position: fixed; inset: 0; background: rgba(10, 19, 40, 0.56); display: none; z-index: 200; align-items: center; justify-content: center; padding: 20px;
    }
    .modal-backdrop.on { display: flex; }
    .modal {
      width: min(540px, 100%);
  background: #fff; border-radius: 22px; box-shadow: var(--shadow-lg); padding: 26px; max-height: 88vh; overflow: auto;
   }
  .toast-container {
   position: fixed; right: 18px; bottom: 18px; z-index: 250; display: flex; flex-direction: column; gap: 10px;
   }
   .toast {
   background: var(--ink); color: #fff; padding: 12px 16px; border-radius: 12px; box-shadow: var(--shadow-lg); font-size: 14px; font-weight: 700;
   animation: slideIn .25s ease;
   }
  .toast.success { background: var(--green); }
  .toast.error { background: var(--red); }
  @keyframes slideIn { from { transform: translateX(30px); opacity: 0; } to { transform: translateX(0); opacity: 1; } }

  .footer {
   margin-top: 18px;
   background: #0e1b3d;
   color: #d6def2;
   padding: 60px 0 26px;
  }
  .footer-grid {
   display: grid;
   grid-template-columns: 1.6fr 1fr 1fr 1fr;
  gap: 26px;
  }
  .footer h4 {
  color: #fff; margin: 0 0 14px; font-size: 15px; font-weight: 800;
   }
   .footer a {
   display: block; color: #d6def2; padding: 5px 0; font-size: 14px;
   }
   .footer a:hover { color: #fff; }
   .footer .logo { color: #fff; }
   .footer-bottom {
   margin-top: 28px; padding-top: 18px; border-top: 1px solid rgba(255,255,255,0.12);
   display: flex; justify-content: space-between; gap: 12px; flex-wrap: wrap; font-size: 13px; color: #c4cef0;
   }

   @media (max-width: 1100px) {
   .features-grid, .dashboard-grid { grid-template-columns: repeat(2, minmax(0,1fr)); }
   .search-box { grid-template-columns: repeat(2, minmax(0,1fr)); }
   .search-box .btn { grid-column: 1 / -1; }
   .detail-layout, .checkout-layout, .dash-layout { grid-template-columns: 1fr; }
   .detail-sides { position: static; }
   .newsletter, .footer-grid { grid-template-columns: 1fr 1fr; }
   .offer-box { grid-template-columns: 1fr; }
   }

   @media (max-width: 760px) {
      .nav-links, .nav-actions .btn-secondary { display: none; }
      .burger { display: inline-flex; align-items: center; justify-content: center; width: 42px; height: 42px; border-radius: 12px; background: var(--sky-soft);  border: 0; color: var(--ocean); }
   .search-layout { display: block; }
   .filter-panel { display: none; }
   .results-grid { grid-template-columns: 1fr; }
   .pkg-card { width: 100%; }
   .features-grid, .dashboard-grid, .form-grid, .newsletter, .footer-grid { grid-template-columns: 1fr; }
   .detail-hero { grid-template-columns: 1fr 1fr; grid-template-rows: 180px 180px 180px; }
   .detail-hero .feature-col { grid-column: 1 / -1; grid-row: auto; }
   section { padding: 56px 0; }
   }
  </style>
</head>
<body>
  <nav class="nav" id="mainNav">
    <div class="container nav-inner">
      <a href="#/home" class="logo" aria-label="Tripify Holidays home">
        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
          <circle cx="12" cy="12" r="9"></circle>
          <path d="M3 12h18M12 3a15 15 0 0 1 0 18M12 3a15 15 0 0 0 0 18"></path>
        </svg>
        <div>TRIPIFY<small>HOLIDAYS</small></div>
      </a>

  <div class="nav-links" id="navLinks">
        <a href="#/home" class="active">Home</a>
        <a href="#/search">Packages</a>
        <a href="#/offers">Offers</a>
        <a href="#/account">My Account</a>
        <a href="#/admin">Admin</a>
      </div>

   <div class="nav-actions" id="navActions"></div>
      <button class="burger" id="burgerBtn" aria-label="Open menu">
        <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 6h18M3 12h18M3 18h18"/></svg>
      </button>
  </div>
  </nav>

  <div class="mobile-menu" id="mobileMenu">
    <a href="#/home">Home</a>
    <a href="#/search">Packages</a>
    <a href="#/offers">Offers</a>
    <a href="#/account">My Account</a>
    <a href="#/admin">Admin</a>
    <a href="#/login">Sign in</a>
  </div>

  <div id="page-home" class="page on">
    <header class="hero">
      <div class="container hero-inner">
        <span class="hero-eyebrow">Curated journeys, crafted for you</span>
        <h1>Where will your<br>next story <em>begin?</em></h1>
        <p>Hand-picked premium holiday packages across dream destinations with flights, stays, and experiences bundled into one seamless booking.</p>
        <div class="hero-actions">
          <a href="#/search" class="btn btn-primary">Explore Packages</a>
          <a href="#/offers" class="btn btn-secondary">View Offers</a>
        </div>
      </div>
    </header>

   <div class="container search-wrap">
      <form class="search-box" id="homeSearchForm">
        <div class="field">
          <label for="homeDestination">Destination</label>
          <select id="homeDestination">
            <option value="">Anywhere</option>
          </select>
        </div>
        <div class="field">
          <label for="homeCity">Departure city</label>
          <input id="homeCity" type="text" placeholder="e.g. Mumbai" />
        </div>
        <div class="field">
          <label for="homeDate">Travel dates</label>
          <input id="homeDate" type="date" />
        </div>
        <div class="field">
          <label for="homeGuests">Guests</label>
          <select id="homeGuests">
            <option>2 Adults</option>
            <option>1 Adult</option>
            <option>2 Adults + 1 Child</option>
            <option>2 Adults + 2 Children</option>
            <option>4+ Guests</option>
          </select>
        </div>
        <div class="field">
          <label for="homeBudget">Max budget</label>
          <select id="homeBudget">
            <option value="">Any</option>
            <option value="25000">₹25,000</option>
            <option value="50000">₹50,000</option>
            <option value="100000">₹1,00,000</option>
            <option value="200000">₹2,00,000</option>
          </select>
        </div>
        <button class="btn btn-primary" type="submit">Search</button>
      </form>
    </div>

  <section>
      <div class="container">
        <span class="eyebrow">Trending now</span>
        <h2 class="sec-title">Destinations travellers love</h2>
        <div class="caro-wrap">
          <button class="caro-btn prev" data-scroll-target="destCaro" data-direction="-1" aria-label="Previous destinations">&#8592;</button>
          <div class="caro" id="destCaro"></div>
          <button class="caro-btn next" data-scroll-target="destCaro" data-direction="1" aria-label="Next destinations">&#8594;</button>
        </div>
      </div>
    </section>

   <section>
      <div class="container">
        <span class="eyebrow">Campus vibes</span>
        <h2 class="sec-title">College IV Packages</h2>
        <div class="caro-wrap">
          <button class="caro-btn prev" data-scroll-target="collegeCaro" data-direction="-1" aria-label="Previous college iv package">&#8592;</button>
          <div class="caro" id="collegeCaro"></div>
          <button class="caro-btn next" data-scroll-target="collegeCaro" data-direction="1" aria-label="Next college iv package">&#8594;</button>
        </div>
      </div>
    </section>

   <section style="background: var(--surface);">
      <div class="container">
        <span class="eyebrow">Featured</span>
        <h2 class="sec-title">Featured holiday packages</h2>
        <div class="caro-wrap">
          <button class="caro-btn prev" data-scroll-target="featCaro" data-direction="-1" aria-label="Previous package">&#8592;</button>
          <div class="caro" id="featCaro"></div>
          <button class="caro-btn next" data-scroll-target="featCaro" data-direction="1" aria-label="Next package">&#8594;</button>
        </div>
      </div>
    </section>

  <section>
      <div class="container">
        <span class="eyebrow">Why Tripify</span>
        <h2 class="sec-title">Travel with total confidence</h2>
        <p class="sec-sub">Every package is designed and vetted by experts so your holiday feels effortless, secure, and memorable.</p>
        <div class="features-grid" style="margin-top: 30px;">
          <article class="feature">
            <div class="feature-icon"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="m12 2 3 6 6 1-4.5 4.5 1.1 6.5L12 0.5 6.4 14l1.1-6.5L3 9l6-1 3-6Z"/></svg></div>
            <h3>Curated quality</h3>
            <p>Only top-rated stays, transfers, and experiences make it into a Tripify package.</p>
          </article>
          <article class="feature">
            <div class="feature-icon"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2 5 5v6c0 5 3.4 9.3 7 11 3.6-1.7 7-6 7-11V5l-7-3Z"/></svg></div>
            <h3>Secure payments</h3>
            <p>Encrypted checkout and transparent pricing with no hidden surprises.</p>
          </article>
          <article class="feature">
            <div class="feature-icon"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 12a8 8 0 1 1 16 0"/><path d="M12 16v-4l3-2"/></svg></div>
            <h3>24/7 support</h3>
            <p>Friendly travel experts available before, during, and after your trip.</p>
          </article>
          <article class="feature">
            <div class="feature-icon"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 12a9 9 0 0 1 18 0"/><path d="M3 5v7h7"/><path d="M16 7v5l3 3"/></svg></div>
            <h3>Flexible cancellation</h3>
            <p>Most packages allow free rescheduling up to 15 days before departure.</p>
          </article>
        </div>
      </div>
    </section>

   <section>
      <div class="container">
        <div class="offer-box" id="offers-anchor">
          <div>
            <span class="offer-pill">Limited time</span>
            <h2>Flat ₹5,000 off your first international trip</h2>
            <p>Use coupon <strong>TRIPFIRST</strong> at checkout. Valid on bookings above ₹50,000.</p>
          </div>
          <a href="#/search" class="btn btn-secondary" style="background:#fff; color:var(--royal); border-color:transparent;">Browse eligible trips</a>
        </div>
      </div>
    </section>

   <section style="background: var(--surface);">
      <div class="container">
        <span class="eyebrow">Testimonials</span>
        <h2 class="sec-title" style="text-align:center;">Loved by 40,000+ travellers</h2>
        <div class="testimonial-wrap">
          <div id="testimonialBox"></div>
          <div class="dots" id="testimonialDots"></div>
        </div>
      </div>
    </section>
    <section>
      <div class="container">
        <div class="newsletter">
          <div>
            <span class="eyebrow">Newsletter</span>
            <h2 class="sec-title" style="font-size: 30px;">Get travel deals before anyone else</h2>
            <p class="sec-sub">One email a week. Curated deals, no spam.</p>
          </div>
          <form id="newsletterForm">
            <input type="email" id="newsletterEmail" placeholder="you@example.com" required />
            <button type="submit" class="btn btn-primary">Subscribe</button>
          </form>
        </div>
      </div>
    </section>
  </div>

  <div id="page-search" class="page">
    <div class="pageheader">
      <div class="container">
        <span class="eyebrow" style="color: var(--sky);">Explore</span>
        <h1>Find your perfect package</h1>
      </div>
    </div>
    <div class="container search-layout" style="padding-bottom: 60px;">
      <aside class="filter-panel">
        <div style="display:flex; justify-content:space-between; gap:12px; align-items:center; margin-bottom:12px;">
          <h3 style="margin: 0; font-size: 19px;">Filters</h3>
          <button type="button" class="btn btn-ghost" style="padding: 7px 12px; font-size: 12px;" id="clearFiltersBtn">Clear all</button>
        </div>
        <div id="filterBody"></div>
      </aside>

   <div>
        <div class="toolbar">
          <span id="resultCount" style="font-weight: 800; color: var(--ink);">0 packages</span>
          <div style="display:flex; align-items:center; gap:10px; flex-wrap:wrap;">
            <button type="button" class="btn btn-ghost" id="mobileFilterBtn" style="display:none; padding: 9px 14px; font-size: 13px;">Filters</button>
            <select id="sortBy" style="min-width: 170px; border: 1.5px solid var(--line); border-radius: 10px; padding: 10px 12px; background:#fff; color: var(--ink);">
              <option value="recommended">Recommended</option>
              <option value="priceAsc">Price: Low to High</option>
              <option value="priceDesc">Price: High to Low</option>
              <option value="rating">Rating</option>
              <option value="duration">Duration</option>
            </select>
          </div>
        </div>
      <div class="results-grid" id="resultsGrid"></div>
        <div class="empty-state" id="emptyState">
          <div class="empty-icon"><svg width="30" height="30" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="11" cy="11" r="7"></circle><path d="m21 21-4.3-4.3"></path></svg></div>
          <h3 style="margin: 0 0 8px; color: var(--ink);">No packages match your filters</h3>
          <p style="margin: 0 0 18px;">Try changing your budget or clearing one or two filters.</p>
          <button type="button" class="btn btn-primary" id="resetSearchBtn">Clear filters</button>
        </div>
      </div>
    </div>
  </div>

  <div id="page-offers" class="page">
    <div class="pageheader">
      <div class="container">
        <span class="eyebrow" style="color: var(--sky);">Special deals</span>
        <h1>Unbeatable offers for your next getaway</h1>
      </div>
    </div>
    <div class="container" style="padding: 40px 0 60px;">
      <div class="results-grid" id="offersGrid"></div>
    </div>
  </div>

  <div id="page-detail" class="page detail-page">
    <div class="container" id="detailBody"></div>
  </div>

  <div id="page-checkout" class="page checkout-shell">
    <div class="container" id="checkoutBody"></div>
  </div>

  <div id="page-login" class="page">
    <div class="container">
      <div class="auth-panel">
        <h2>Welcome back</h2>
        <p>Sign in to manage your trips and bookings.</p>
        <form id="loginForm">
          <div class="field">
            <label>Email</label>
            <input type="email" id="loginEmail" required />
          </div>
          <div class="field">
            <label>Password</label>
            <input type="password" id="loginPassword" minlength="6" required />
          </div>
          <button type="submit" class="btn btn-primary">Sign in</button>
        </form>
        <p style="text-align:center; margin-top:18px; font-size:14px;">New here? <a href="#/register" style="color:var(--ocean); font-weight:800;">Create account</a></p>
      </div>
    </div>
  </div>

  <div id="page-register" class="page">
    <div class="container">
      <div class="auth-panel">
        <h2>Create your account</h2>
        <p>Join 40,000+ travellers planning smarter holidays.</p>
        <form id="registerForm">
          <div class="field">
            <label>Full name</label>
            <input type="text" id="registerName" minlength="3" required />
          </div>
          <div class="field">
            <label>Email</label>
            <input type="email" id="registerEmail" required />
          </div>
          <div class="field">
            <label>Phone</label>
            <input type="tel" id="registerPhone" pattern="[0-9]{10}" required />
          </div>
          <div class="field">
            <label>Password</label>
            <input type="password" id="registerPassword" minlength="6" required />
          </div>
          <button type="submit" class="btn btn-primary">Create account</button>
        </form>
        <p style="text-align:center; margin-top:18px; font-size:14px;">Already registered? <a href="#/login" style="color:var(--ocean); font-weight:800;">Sign in</a></p>
      </div>
    </div>
  </div>

  <div id="page-account" class="page">
    <div class="pageheader">
      <div class="container">
        <h1>My Account</h1>
        <p id="accountGreeting" style="margin: 10px 0 0; color: rgba(255,255,255,0.85);"></p>
      </div>
    </div>

   <div class="container dash-layout" style="padding-bottom: 50px;">
      <aside class="sidebar">
        <a href="#/account" class="active" data-account-tab="bookings">My bookings</a>
        <a href="#/account" data-account-tab="wishlist">Wishlist</a>
        <a href="#/account" data-account-tab="profile">Profile</a>
      </aside>
      <div id="accountBody" class="dash-panel"></div>
    </div>
  </div>

  <div id="page-admin" class="page">
    <div class="pageheader">
      <div class="container">
        <span class="eyebrow" style="color: var(--sky);">Admin panel</span>
        <div style="display:flex; align-items:center; justify-content:space-between; gap:16px; flex-wrap:wrap;">
          <h1>Operations dashboard</h1>
          <button type="button" class="btn btn-ghost" id="adminLogoutBtn" style="display:none;">Sign out</button>
        </div>
      </div>
    </div>
    <div class="container dash-layout" style="padding-bottom: 50px;">
      <aside class="sidebar" id="adminSidebar">
        <a href="#/admin" class="active" data-admin-tab="dashboard">Dashboard</a>
        <a href="#/admin" data-admin-tab="bookings">Bookings</a>
        <a href="#/admin" data-admin-tab="packages">Packages</a>
        <a href="#/admin" data-admin-tab="destinations">Destinations</a>
        <a href="#/admin" data-admin-tab="coupons">Coupons</a>
      </aside>
      <div id="adminBody" class="admin-panel"></div>
    </div>
  </div>

  <div class="modal-backdrop" id="modalBackdrop">
    <div class="modal" id="modalContent"></div>
  </div>

  <div class="toast-container" id="toastContainer"></div>

  <footer class="footer">
    <div class="container">
      <div class="footer-grid">
        <div>
          <a href="#/home" class="logo" aria-label="Tripify Holidays home">
            <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="#5ba3e8" stroke-width="1.7"><circle cx="12" cy="12" r="9"></circle><path d="M3 12h18M12 3a15 15 0 0 1 0 18M12 3a15 15 0 0 0 0 18"></path></svg>
            <div>TRIPIFY<small style="color:#8ea3cc;">HOLIDAYS</small></div>
          </a>
          <p style="margin-top:16px; color:#d6def2; max-width: 280px;">Curated premium holidays designed to feel personal, easy, and unforgettable from the first click.</p>
        </div>
        <div>
          <h4>Company</h4>
          <a href="#/home">About us</a>
          <a href="#/offers">Offers</a>
          <a href="#/search">Packages</a>
          <a href="#/home">Press</a>
        </div>
        <div>
          <h4>Support</h4>
          <a href="#/home">Help centre</a>
          <a href="#/home">Cancellation policy</a>
          <a href="#/home">Contact us</a>
          <a href="#/home">Trust & safety</a>
        </div>
        <div>
          <h4>Top destinations</h4>
          <a href="#/search">Bali</a>
          <a href="#/search">Maldives</a>
          <a href="#/search">Switzerland</a>
          <a href="#/search">Dubai</a>
        </div>
      </div>
      <div class="footer-bottom">
        <span>© 2025 Tripify Holidays Pvt. Ltd. All rights reserved.</span>
        <span><a href="#/home" style="display:inline-block; margin-right:14px;">Terms</a><a href="#/home" style="display:inline-block;">Refunds</a></span>
      </div>
    </div>
  </footer>

  <script>
    const DESTS = [
      { id: 'bali', name: 'Bali, Indonesia', tag: 'Beaches & temples', image: 'https://images.unsplash.com/photo-1537996194471-e657df975ab4?auto=format&fit=crop&w=900&q=80' },
      { id: 'maldives', name: 'Maldives', tag: 'Overwater luxury', image: 'https://images.unsplash.com/photo-1514282401047-d79a71a590e8?auto=format&fit=crop&w=900&q=80' },
      { id: 'swiss', name: 'Swiss Alps', tag: 'Mountain escape', image: 'https://images.unsplash.com/photo-1501785888041-af3ef285b470?auto=format&fit=crop&w=900&q=80' },
      { id: 'dubai', name: 'Dubai, UAE', tag: 'Skyline & desert', image: 'https://images.unsplash.com/photo-1512453979798-5ea266f8880c?auto=format&fit=crop&w=900&q=80' },
      { id: 'japan', name: 'Japan', tag: 'Culture & cherry blossoms', image: 'https://images.unsplash.com/photo-1493976040374-85c8e12f0c0e?auto=format&fit=crop&w=900&q=80' },
      { id: 'thailand', name: 'Thailand', tag: 'Island hopping', image: 'https://images.unsplash.com/photo-1508009603885-50cf7c579a4a?auto=format&fit=crop&w=900&q=80' },
      { id: 'kochi', name: 'Kochi, Kerala', tag: 'City & coast', image: 'https://images.unsplash.com/photo-1521295121783-8a321d551ad2?auto=format&fit=crop&w=900&q=80' },
      { id: 'thrissur', name: 'Thrissur, Kerala', tag: 'Culture & celebration', image: 'https://images.unsplash.com/photo-1552465011-b4e21bf6e79a?auto=format&fit=crop&w=900&q=80' }
    ];

    const PKGS = [
      { id: 'P001', name: 'Bali Bliss 6N', dest: 'bali', days: 6, price: 28999, rating: 4.8, reviews: 1234, feature: true, category: 'beach', image: 'https://images.unsplash.com/photo-1507525428034-b723cf961d34?auto=format&fit=crop&w=1000&q=80', includes: ['Flights', '4★ stay', 'Breakfast', 'Airport transfers'], itinerary: ['Arrival and welcome dinner', 'Ubud temple trail and waterfalls', 'Beach day and spa', 'Sunset cruise and local market', 'Departure transfer'] },
      { id: 'P002', name: 'Maldives Overwater Escape', dest: 'maldives', days: 5, price: 65999, rating: 4.9, reviews: 980, feature: true, category: 'honeymoon', image: 'https://images.unsplash.com/photo-1573843981267-be1999ff37cd?auto=format&fit=crop&w=1000&q=80', includes: ['Flights', 'Overwater villa', 'Breakfast', 'Snorkelling'], itinerary: ['Arrival and beach welcome', 'Private island experience', 'Snorkel and lagoon lunch', 'Sunset cruise', 'Departure day'] },
      { id: 'P003', name: 'Swiss Explorer 7N', dest: 'swiss', days: 7, price: 326299, rating: 4.7, reviews: 1160, feature: true, category: 'mountain', image: 'https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=1000&q=80', includes: ['Flights', 'Rail pass', 'Hotel', 'Sightseeing'], itinerary: ['Zurich arrival', 'Interlaken mountain tour', 'Lucerne lakeside walk', 'GoldenPass scenic route', 'Adventure day and return'] },
      { id: 'P004', name: 'Dubai City & Desert', dest: 'dubai', days: 4, price: 125599, rating: 4.6, reviews: 780, feature: false, category: 'city', image: 'https://images.unsplash.com/photo-1512453979798-5ea266f8880c?auto=format&fit=crop&w=1000&q=80', includes: ['Flights', 'Desert safari', 'Resort stay', 'Burj access'], itinerary: ['Arrival and marina walk', 'Old town & souk', 'Desert safari evening', 'Beach and shopping'] },
      { id: 'P005', name: 'Japan Cherry Trail', dest: 'japan', days: 8, price: 242999, rating: 4.8, reviews: 1320, feature: true, category: 'adventure', image: 'https://images.unsplash.com/photo-1493976040374-85c8e12f0c0e?auto=format&fit=crop&w=1000&q=80', includes: ['Flights', 'Hotel', 'Rail tickets', 'Sightseeing'], itinerary: ['Tokyo arrival', 'Asakusa and food tour', 'Kyoto heritage walk', 'Hike and hot springs', 'Return day'] },
      { id: 'P006', name: 'Thai Island Hopper', dest: 'thailand', days: 6, price: 34999, rating: 4.5, reviews: 920, feature: false, category: 'beach', image: 'https://images.unsplash.com/photo-1508009603885-50cf7c579a4a?auto=format&fit=crop&w=1000&q=80', includes: ['Flights', 'Island stays', 'Breakfast', 'Boat transfers'], itinerary: ['Bangkok arrival', 'Phuket beach day', 'Phi Phi island tour', 'Krabi kayaking', 'Departure'] },
      { id: 'P007', name: 'Iceland Aurora Hunt', dest: 'iceland', days: 6, price: 74999, rating: 4.9, reviews: 760, feature: true, category: 'adventure', image: 'https://images.unsplash.com/photo-1500530855697-b586d89ba3ee?auto=format&fit=crop&w=1000&q=80', includes: ['Flights', 'Hotel', 'Northern lights tour', 'Transfers'], itinerary: ['Reykjavik arrival', 'Golden circle tour', 'Blue lagoon', 'Night sky chase', 'Departure'] },
      { id: 'P008', name: 'Santorini Romance', dest: 'greece', days: 5, price: 52999, rating: 4.8, reviews: 1100, feature: false, category: 'honeymoon', image: 'https://images.unsplash.com/photo-1570077188670-e3a8d69ac5ff?auto=format&fit=crop&w=1000&q=80', includes: ['Flights', 'Boutique stay', 'Breakfast', 'Sunset cruise'], itinerary: ['Arrival and caldera view', 'Beach club access', 'Wine tour', 'Private sunset dinner', 'Departure'] },
      { id: 'P009', name: 'Vietnam Discovery', dest: 'vietnam', days: 7, price: 45999, rating: 4.6, reviews: 860, feature: false, category: 'city', image: 'https://images.unsplash.com/photo-1528127269322-800941a7d638?auto=format&fit=crop&w=1000&q=80', includes: ['Flights', 'Hotel', 'Meals', 'Sightseeing'], itinerary: ['Hanoi arrival', 'Halong Bay cruises', 'HCMC city tour', 'Street food evening', 'Departure'] },
      { id: 'P010', name: 'Morocco & Sahara', dest: 'morocco', days: 6, price: 57999, rating: 4.7, reviews: 690, feature: true, category: 'adventure', image: 'https://images.unsplash.com/photo-1518548419970-58e3b4079ab2?auto=format&fit=crop&w=1000&q=80', includes: ['Flights', 'Hotel', 'Desert camp', 'Transfers'], itinerary: ['Casablanca arrival', 'Marrakech old city tour', 'Atlas mountains', 'Sahara camp', 'Departure'] },
      { id: 'CIV1', name: 'IV Pack 1', dest: 'kochi', days: 1, price: 1499, rating: 4.7, reviews: 120, feature: true, category: 'college', image: 'https://images.unsplash.com/photo-1517457373958-b7bdd4587205?auto=format&fit=crop&w=1000&q=80', includes: ['Lunch', 'Dinner', 'Breakfast', 'Water activities', 'DJ'], itinerary: ['Arrival at campus meetup', 'Water activities and games', 'Dinner and DJ night', 'Return journey'] },
      { id: 'CIV2', name: 'IV Pack 2', dest: 'thrissur', days: 1, price: 1299, rating: 4.5, reviews: 96, feature: true, category: 'college', image: 'https://images.unsplash.com/photo-1523240795612-9a054b0db644?auto=format&fit=crop&w=1000&q=80', includes: ['Lunch', 'Dinner', 'Breakfast', 'Activities', 'DJ'], itinerary: ['Arrival and ice breakers', 'Activity zone and fun games', 'DJ evening', 'Departure'] },
      { id: 'CIV3', name: 'IV Pack 3', dest: 'kochi/tvm', days: 2, price: 2999, rating: 4.8, reviews: 142, feature: true, category: 'college', image: 'https://images.unsplash.com/photo-1507525428034-b723cf961d34?auto=format&fit=crop&w=1000&q=80', includes: ['Resort stay', 'Food', 'DJ', 'Activities'], itinerary: ['Check-in and welcome', 'Resort activities and games', 'Night DJ event', 'Second day adventure and departure'] }
    ];

    const COUPONS = [
      { code: 'TRIPFIRST', type: 'flat', value: 5000, minSpend: 50000 },
      { code: 'SUMMER10', type: 'percent', value: 10, minSpend: 30000 },
      { code: 'HONEY15', type: 'percent', value: 15, minSpend: 80000 }
    ];

    const state = {
      user: JSON.parse(sessionStorage.getItem('tripifyUser') || 'null'),
      wishlist: JSON.parse(localStorage.getItem('tripifyWishlist') || '[]'),
      users: JSON.parse(localStorage.getItem('tripifyUsers') || '[]'),
      bookings: JSON.parse(localStorage.getItem('tripifyBookings') || '[]'),
      currentPkg: null,
      currentBooking: null,
      activeAccountTab: 'bookings',
      activeAdminTab: 'dashboard',
      coupon: null,
      testimonials: [
        { name: 'Priya & Arjun', trip: 'Maldives Overwater Escape', quote: 'Absolutely seamless from booking to return flight. The villa was even better than the photos.', image: 'https://images.unsplash.com/photo-1524504388940-b1c1722653e1?auto=format&fit=crop&w=400&q=80' },
        { name: 'Raj', trip: 'Swiss Explorer 7N', quote: 'The rail itinerary was flawlessly planned. Every transfer was on time. Worth every rupee.', image: 'https://images.unsplash.com/photo-1500648767791-00dcc994a43e?auto=format&fit=crop&w=400&q=80' },
        { name: 'Anna', trip: 'Bali Bliss 6N', quote: 'Our host made Bali feel personal — hidden cafes, private temple tour, and a gorgeous beach villa.', image: 'https://images.unsplash.com/photo-1494790108377-be9c29b29330?auto=format&fit=crop&w=400&q=80' }
      ],
      testimonialIndex: 0
    };

    let adminAuthorization = null;

    function saveData() {
      localStorage.setItem('tripifyWishlist', JSON.stringify(state.wishlist));
      localStorage.setItem('tripifyUsers', JSON.stringify(state.users));
      localStorage.setItem('tripifyBookings', JSON.stringify(state.bookings));
    }

    function fmt(value) {
      return new Intl.NumberFormat('en-IN', { style: 'currency', currency: 'INR', maximumFractionDigits: 0 }).format(value);
    }

    function escHtml(str) {
      return String(str ?? '').replace(/[&<>"']/g, (char) => ({ '&': '&amp;', '<': '&lt;', '>': '&gt;', '"': '&quot;', "'": '&#39;' }[char]));
    }

    function toast(message, type = 'success') {
      const toast = document.createElement('div');
      toast.className = `toast ${type === 'error' ? 'error' : 'success'}`;
      toast.textContent = message;
      document.getElementById('toastContainer').appendChild(toast);
      setTimeout(() => toast.remove(), 3000);
    }

    function updateNav() {
      const actions = document.getElementById('navActions');
      if (!actions) return;
      if (state.user) {
        actions.innerHTML = `
          <button class="btn btn-ghost" type="button" style="padding: 9px 16px; font-size: 13px;" data-action="open-account">${state.user.name.split(' ')[0]}</button>
          <button class="btn btn-secondary" type="button" style="padding: 9px 16px; font-size: 13px;" data-action="logout">Sign out</button>
        `;
      } else {
        actions.innerHTML = `
          <a href="#/login" class="btn btn-ghost" style="padding: 9px 16px; font-size: 13px;">Sign in</a>
          <a href="#/register" class="btn btn-primary" style="padding: 9px 16px; font-size: 13px;">Get Started</a>
        `;
      }
    }

    function setActiveNav() {
      const hash = (location.hash || '#/home').replace('#/', '').split('/')[0];
      const navLinks = document.querySelectorAll('.nav-links a');
      navLinks.forEach((link) => {
        const page = link.getAttribute('href').replace('#/', '');
        link.classList.toggle('active', page === hash || (hash === 'home' && page === 'home'));
      });
    }

    function router() {
      const hash = location.hash || '#/home';
      const route = hash.startsWith('#/') ? hash.slice(2) : hash;
      const currentPage = route.split('/')[0] || 'home';
      document.querySelectorAll('.page').forEach((page) => page.classList.remove('on'));
      const target = document.getElementById('page-' + currentPage);
      if (target) target.classList.add('on');

      setActiveNav();
      const mobileMenu = document.getElementById('mobileMenu');
      if (mobileMenu) mobileMenu.classList.remove('open');

      if (currentPage === 'search') {
        renderSearchFilters();
        renderSearchResults();
      }
      if (currentPage === 'detail') {
        renderDetailPage();
      }
      if (currentPage === 'checkout') {
        renderCheckoutPage();
      }
      if (currentPage === 'account') {
        renderAccountPage();
      }
      if (currentPage === 'admin') {
        renderAdminPage();
      }
      if (currentPage === 'offers') {
        renderOffersPage();
      }
      if (currentPage === 'home') {
        renderHome();
      }
      if (currentPage === 'login' || currentPage === 'register') {
        window.scrollTo({ top: 0 });
      }
    }

    function loadHomeDestinations() {
      const destCaro = document.getElementById('destCaro');
      const homeDestination = document.getElementById('homeDestination');
      if (homeDestination) {
        homeDestination.innerHTML = '<option value="">Anywhere</option>' + DESTS.map((dest) => `<option value="${dest.id}">${dest.name}</option>`).join('');
      }
      if (destCaro) {
        destCaro.innerHTML = DESTS.map((dest) => `
          <article class="dest-card" data-action="open-search-destination" data-destination="${dest.id}">
            <img src="${dest.image}" alt="${escHtml(dest.name)}" loading="lazy" />
            <div class="dest-overlay">
              <h3>${escHtml(dest.name)}</h3>
              <span>${escHtml(dest.tag)}</span>
            </div>
          </article>
        `).join('');
      }
    }

    function loadFeaturedPackages() {
      const featCaro = document.getElementById('featCaro');
      if (featCaro) {
        featCaro.innerHTML = PKGS.filter((pkg) => pkg.feature && pkg.category !== 'college').map(pkgCard).join('');
      }
    }

    function loadCollegeIVPackages() {
      const collegeCaro = document.getElementById('collegeCaro');
      if (collegeCaro) {
        collegeCaro.innerHTML = PKGS.filter((pkg) => pkg.category === 'college').map(pkgCard).join('');
      }
    }

    function pkgCard(pkg) {
      const saved = state.wishlist.includes(pkg.id);
      const destinationName = DESTS.find((dest) => dest.id === pkg.dest)?.name || 'Destination';
      return `
        <article class="pkg-card">
          <div class="pkg-image-wrap">
            ${pkg.feature ? '<span class="tag">Featured</span>' : ''}
            <button type="button" class="floating-heart ${saved ? 'active' : ''}" data-action="toggle-wishlist" data-id="${pkg.id}" aria-label="Toggle wishlist">♥</button>
            <img src="${pkg.image}" alt="${escHtml(pkg.name)}" data-action="open-package" data-id="${pkg.id}" />
          </div>
          <div class="pkg-body">
            <div class="pkg-meta">
              <span>★ ${pkg.rating}</span>
              <span>•</span>
              <span>${pkg.reviews} reviews</span>
              <span>•</span>
              <span>${pkg.days}D / ${pkg.days - 1}N</span>
            </div>
            <h3 data-action="open-package" data-id="${pkg.id}">${escHtml(pkg.name)}</h3>
            <div class="pkg-meta" style="margin-top: -4px;">${escHtml(destinationName)}</div>
            <div class="pkg-foot">
              <div class="price"><strong>${fmt(pkg.price)}</strong><span> / person</span></div>
              <button type="button" class="btn btn-primary" data-action="open-package" data-id="${pkg.id}" style="padding: 9px 16px; font-size: 13px;">View</button>
            </div>
          </div>
        </article>
      `;
    }

    function renderHome() {
      loadHomeDestinations();
      loadFeaturedPackages();
      loadCollegeIVPackages();
      renderTestimonials();
    }

    function renderSearchFilters() {
      const filterBody = document.getElementById('filterBody');
      if (!filterBody) return;
      const categoryOptions = ['beach', 'mountain', 'city', 'adventure', 'honeymoon'];
      const categoryLabels = { beach: 'Beach', mountain: 'Mountains', city: 'City', adventure: 'Adventure', honeymoon: 'Honeymoon' };

      filterBody.innerHTML = `
        <div class="filter-section">
          <h4>Category</h4>
          ${categoryOptions.map((option) => `
            <label class="check-row">
              <input type="checkbox" class="filter-cat" value="${option}" />
              <span>${categoryLabels[option]}</span>
            </label>
          `).join('')}
        </div>

        <div class="filter-section">
          <h4>Destination</h4>
          <select id="fDest" style="width:100%; border: 1.5px solid var(--line); border-radius: 10px; padding: 10px 12px;">
            <option value="">All destinations</option>
            ${DESTS.map((dest) => `<option value="${dest.id}">${dest.name}</option>`).join('')}
          </select>
        </div>

        <div class="filter-section">
          <h4>Max price</h4>
          <input id="fPrice" type="range" min="25000" max="200000" step="5000" value="200000" style="width:100%; accent-color: var(--ocean);" />
          <div id="fPriceLabel" style="margin-top: 8px; font-weight: 800; color: var(--ocean);">Up to ₹2,00,000</div>
        </div>

        <div class="filter-section">
          <h4>Duration</h4>
          <select id="fDur" style="width:100%; border: 1.5px solid var(--line); border-radius: 10px; padding: 10px 12px;">
            <option value="">Any duration</option>
            <option value="5">Up to 5 days</option>
            <option value="7">Up to 7 days</option>
            <option value="9">9+ days</option>
          </select>
        </div>

        <div class="filter-section" style="margin-bottom:0; border-bottom:0; padding-bottom:0;">
          <h4>Minimum rating</h4>
          <label class="check-row"><input type="radio" name="fRate" value="0" checked /> Any rating</label>
          <label class="check-row"><input type="radio" name="fRate" value="4.5" /> 4.5+ stars</label>
          <label class="check-row"><input type="radio" name="fRate" value="4.7" /> 4.7+ stars</label>
          <label class="check-row"><input type="radio" name="fRate" value="4.9" /> 4.9+ stars</label>
        </div>
      `;

      const clearBtn = document.getElementById('clearFiltersBtn');
      if (clearBtn) clearBtn.addEventListener('click', resetFilters);
      const resetBtn = document.getElementById('resetSearchBtn');
      if (resetBtn) resetBtn.addEventListener('click', resetFilters);
      const mobileFilterBtn = document.getElementById('mobileFilterBtn');
      if (mobileFilterBtn) mobileFilterBtn.addEventListener('click', renderSearchFiltersMobile);
      const slider = document.getElementById('fPrice');
      if (slider) {
        slider.addEventListener('input', function () {
          const label = document.getElementById('fPriceLabel');
          if (label) label.textContent = 'Up to ' + fmt(Number(this.value));
          renderSearchResults();
        });
      }
      document.querySelectorAll('.filter-cat, #fDest, #fDur, input[name="fRate"]').forEach((input) => {
        input.addEventListener('change', renderSearchResults);
      });

      renderSearchResults();
    }

    function renderSearchFiltersMobile() {
      const modalContent = document.getElementById('modalContent');
      const modalBackdrop = document.getElementById('modalBackdrop');
      if (!modalContent || !modalBackdrop) return;
      modalContent.innerHTML = `
        <div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:16px;">
          <h3 style="margin:0;">Filters</h3>
          <button type="button" class="btn btn-ghost" style="padding: 8px 12px; font-size: 12px;" data-close-modal="true">Close</button>
        </div>
        <div id="mobileFilterBody"></div>
      `;
      const mobileFilterBody = document.getElementById('mobileFilterBody');
      mobileFilterBody.innerHTML = document.getElementById('filterBody').innerHTML;
      modalBackdrop.classList.add('on');

      const closeBtn = document.querySelector('[data-close-modal="true"]');
      if (closeBtn) closeBtn.addEventListener('click', () => modalBackdrop.classList.remove('on'));
      const applyBtn = document.createElement('button');
      applyBtn.type = 'button';
      applyBtn.className = 'btn btn-primary';
      applyBtn.style.width = '100%';
      applyBtn.style.marginTop = '18px';
      applyBtn.textContent = 'Apply filters';
      applyBtn.addEventListener('click', () => {
        renderSearchResults();
        modalBackdrop.classList.remove('on');
      });
      modalContent.appendChild(applyBtn);
    }

    function resetFilters() {
      document.querySelectorAll('.filter-cat').forEach((box) => { box.checked = false; });
      const fDest = document.getElementById('fDest');
      if (fDest) fDest.value = '';
      const price = document.getElementById('fPrice');
      if (price) price.value = 200000;
      const priceLabel = document.getElementById('fPriceLabel');
      if (priceLabel) priceLabel.textContent = 'Up to ₹2,00,000';
      const fDur = document.getElementById('fDur');
      if (fDur) fDur.value = '';
      const ratings = document.querySelectorAll('input[name="fRate"]');
      ratings.forEach((radio) => {
        radio.checked = radio.value === '0';
      });
      renderSearchResults();
    }

    function renderSearchResults() {
      const resultsGrid = document.getElementById('resultsGrid');
      const resultCount = document.getElementById('resultCount');
      const emptyState = document.getElementById('emptyState');
      if (!resultsGrid || !resultCount) return;

      const selectedCats = Array.from(document.querySelectorAll('.filter-cat:checked')).map((el) => el.value);
      const destination = document.getElementById('fDest')?.value || '';
      const maxPrice = Number(document.getElementById('fPrice')?.value || 200000);
      const duration = document.getElementById('fDur')?.value || '';
      const ratingValue = Number(document.querySelector('input[name="fRate"]:checked')?.value || 0);
      const sortBy = document.getElementById('sortBy')?.value || 'recommended';

      let filtered = PKGS.filter((pkg) => {
        if (selectedCats.length && !selectedCats.includes(pkg.category)) return false;
        if (destination && pkg.dest !== destination) return false;
        if (pkg.price > maxPrice) return false;
        if (duration === '5' && pkg.days > 5) return false;
        if (duration === '7' && pkg.days > 7) return false;
        if (duration === '9' && pkg.days < 9) return false;
        if (ratingValue && pkg.rating < ratingValue) return false;
        return true;
      });

      if (sortBy === 'priceAsc') filtered.sort((a, b) => a.price - b.price);
      if (sortBy === 'priceDesc') filtered.sort((a, b) => b.price - a.price);
      if (sortBy === 'rating') filtered.sort((a, b) => b.rating - a.rating);
      if (sortBy === 'duration') filtered.sort((a, b) => a.days - b.days);

      resultsGrid.innerHTML = filtered.map(pkgCard).join('');
      resultCount.textContent = `${filtered.length} package${filtered.length === 1 ? '' : 's'} found`;
      emptyState.style.display = filtered.length ? 'none' : 'block';
      if (filtered.length === 0) {
        resultsGrid.innerHTML = '';
      }
    }

    function renderDetailPage() {
      const hash = location.hash || '#/home';
      const pkgId = hash.match(/#\/detail\/([^/]+)/)?.[1] || null;
      const pkg = PKGS.find((item) => item.id === pkgId) || PKGS[0];
      state.currentPkg = pkg;
      const destination = DESTS.find((item) => item.id === pkg.dest) || DESTS[0];
      const saved = state.wishlist.includes(pkg.id);
      document.getElementById('detailBody').innerHTML = `
        <div class="detail-hero">
          <img class="feature-col" src="${pkg.image}" alt="${escHtml(pkg.name)}" data-open-lightbox="${pkg.image}" />
          <img src="${pkg.image}" alt="${escHtml(pkg.name)}" data-open-lightbox="${pkg.image}" />
          <img src="${destination.image}" alt="${escHtml(destination.name)}" data-open-lightbox="${destination.image}" />
          <img src="https://images.unsplash.com/photo-1500530855697-b586d89ba3ee?auto=format&fit=crop&w=1000&q=80" alt="Additional trip view" data-open-lightbox="https://images.unsplash.com/photo-1500530855697-b586d89ba3ee?auto=format&fit=crop&w=1000&q=80" />
        </div>

        <div class="detail-layout">
          <div>
            <div class="detail-panel">
              <div class="title-row">
                <div class="detail-header">
                  <h1>${escHtml(pkg.name)}</h1>
                  <p class="detail-sub">${escHtml(destination.name)} • ${pkg.days} days / ${pkg.days - 1} nights</p>
                  <div class="rating-line">
                    <span>★ ${pkg.rating}</span>
                    <span>•</span>
                    <span>${pkg.reviews} reviews</span>
                  </div>
                </div>
                <button type="button" class="btn ${saved ? 'btn-primary' : 'btn-ghost'}" data-action="toggle-wishlist" data-id="${pkg.id}">${saved ? 'Saved' : 'Save'} wishlist</button>
              </div>
              <div class="chip-row" style="margin-top: 8px;">
                ${pkg.includes.map((item) => `<span class="chip">${escHtml(item)}</span>`).join('')}
              </div>
            </div>

            <div class="detail-panel">
              <h3 style="margin: 0 0 16px;">Day-by-day itinerary</h3>
              <div class="itinerary-list">
                ${pkg.itinerary.map((item, index) => `
                  <div class="itinerary-item">
                    <div class="badge">${index + 1}</div>
                    <div>
                      <h4>${escHtml(item)}</h4>
                      <p>Enjoy a hand-picked local experience with time to relax, explore, and create lasting memories.</p>
                    </div>
                  </div>
                `).join('')}
              </div>
            </div>

            <div class="detail-panel">
              <h3 style="margin:0 0 12px;">What is included</h3>
              <ul style="margin:0; padding-left:18px; color: var(--gray); line-height: 2; font-size:14px;">
                ${pkg.includes.map((item) => `<li>${escHtml(item)}</li>`).join('')}
                <li>Premium support and flexible booking assistance</li>
              </ul>
            </div>
          </div>

          <aside class="detail-sides">
            <div class="price-box">
              <div class="from">Per person from</div>
              <div class="amount">${fmt(pkg.price)}</div>
              <div class="status">✓ Free cancellation up to 15 days before departure</div>
            </div>
            <button type="button" class="btn btn-primary" data-action="start-booking" data-id="${pkg.id}" style="width:100%;">Book this package</button>
            <button type="button" class="btn btn-ghost" data-action="toggle-wishlist" data-id="${pkg.id}" style="width:100%;">${saved ? '♥ In wishlist' : '♡ Add to wishlist'}</button>
            <div class="detail-panel" style="padding: 16px 18px;">
              <div class="summary-list">
                <div>✦ Instant confirmation</div>
                <div>✦ EMI from ${fmt(Math.round(pkg.price / 12))}/month</div>
                <div>✦ 24x7 support on trip</div>
              </div>
            </div>
          </aside>
        </div>
      `;
      const triggers = document.querySelectorAll('[data-open-lightbox]');
      triggers.forEach((trigger) => {
        trigger.addEventListener('click', () => {
          openLightbox(trigger.getAttribute('data-open-lightbox'));
        });
      });
    }

    function renderCheckoutPage() {
      if (!state.user) {
        location.hash = '#/login';
        return;
      }
      const pkg = state.currentPkg || PKGS[0];
      const guestCount = 2;
      const subtotal = pkg.price * guestCount;
      const taxes = Math.round(subtotal * 0.05);
      const coupon = state.coupon;
      let discount = 0;
      if (coupon) {
        if (coupon.type === 'percent') discount = Math.round(subtotal * (coupon.value / 100));
        else discount = coupon.value;
      }
      const total = Math.max(subtotal + taxes - discount, 0);

      document.getElementById('checkoutBody').innerHTML = `
        <div class="checkout-layout">
          <div class="booking-panel">
            <h3>Traveller details</h3>
            <form id="checkoutForm">
              <div class="form-grid">
                <div class="field">
                  <label>Lead traveller</label>
                  <input type="text" id="travellerName" value="${escHtml(state.user.name)}" required />
                </div>
                <div class="field">
                  <label>Email</label>
                  <input type="email" id="travellerEmail" value="${escHtml(state.user.email)}" required />
                </div>
                <div class="field">
                  <label>Phone</label>
                  <input type="tel" id="travellerPhone" value="${escHtml(state.user.phone || '')}" pattern="[0-9]{10}" required />
                </div>
                <div class="field">
                  <label>Departure date</label>
                  <input type="date" id="departureDate" min="${new Date(Date.now() + 7 * 86400000).toISOString().slice(0, 10)}" required />
                </div>
              </div>

              <div class="field" style="margin-top:18px;">
                <label>Special requests</label>
                <textarea id="travellerNotes" placeholder="Any room preferences, dietary needs, or special requests?"></textarea>
              </div>

              <div class="field" style="margin-top:18px;">
                <label>Coupon code</label>
                <div style="display:flex; gap:10px;">
                  <input id="couponInput" type="text" placeholder="TRIPFIRST" value="${coupon ? coupon.code : ''}" style="flex:1;" />
                  <button type="button" class="btn btn-ghost" id="applyCouponBtn">Apply</button>
                </div>
                <div id="couponMessage" style="margin-top: 8px; font-size: 13px; min-height: 18px; ${coupon ? 'color: var(--green);' : ''}">${coupon ? 'Coupon applied: ' + coupon.code : ''}</div>
              </div>

              <button type="submit" class="btn btn-primary" style="margin-top:18px;">Confirm booking</button>
            </form>
          </div>

          <aside class="detail-panel" style="position: sticky; top: calc(var(--nav-h) + 18px);">
            <h3 style="margin-top: 0;">Trip summary</h3>
            <img src="${pkg.image}" alt="${escHtml(pkg.name)}" style="width:100%; height:135px; object-fit:cover; border-radius:12px; margin-bottom:12px;" />
            <div style="font-weight:800; font-size: 18px; margin-bottom: 4px;">${escHtml(pkg.name)}</div>
            <div style="color: var(--gray); font-size: 14px; margin-bottom: 12px;">${escHtml(DESTS.find((d) => d.id === pkg.dest)?.name || '')} • ${pkg.days} days</div>
            <div class="checkout-summary">
              <div class="checkout-summary-row"><span>Guests</span><strong>${guestCount}</strong></div>
              <div class="checkout-summary-row"><span>Trip subtotal</span><strong>${fmt(subtotal)}</strong></div>
              <div class="checkout-summary-row"><span>Taxes & fees</span><strong>${fmt(taxes)}</strong></div>
              ${coupon ? `<div class="checkout-summary-row" style="color: var(--green);"><span>Coupon (${coupon.code})</span><strong>- ${fmt(discount)}</strong></div>` : ''}
              <div class="checkout-summary-row total"><span>Total</span><strong>${fmt(total)}</strong></div>
            </div>
          </aside>
        </div>
      `;

      document.getElementById('checkoutForm').addEventListener('submit', function (event) {
        event.preventDefault();
        const travellerName = document.getElementById('travellerName').value.trim();
        const travellerEmail = document.getElementById('travellerEmail').value.trim();
        const travellerPhone = document.getElementById('travellerPhone').value.trim();
        const departureDate = document.getElementById('departureDate').value;

        if (!travellerName || !travellerEmail || !travellerPhone || !departureDate || !/^\d{10}$/.test(travellerPhone)) {
          toast('Please complete all traveller details correctly.', 'error');
          return;
        }

        const total = Math.max(subtotal + taxes - discount, 0);
        const newBooking = {
          id: 'BK' + Date.now().toString().slice(-8),
          pkgId: pkg.id,
          guestName: travellerName,
          email: travellerEmail,
          phone: travellerPhone,
          date: departureDate,
          notes: document.getElementById('travellerNotes').value.trim(),
          total: total,
          status: 'Confirmed'
        };

        state.bookings.push(newBooking);
        saveData();
        state.currentBooking = newBooking;
        state.coupon = null;
        location.hash = '#/account';
        toast('Booking confirmed successfully!');
      });

      document.getElementById('applyCouponBtn').addEventListener('click', function () {
        const code = (document.getElementById('couponInput').value || '').trim().toUpperCase();
        const coupon = COUPONS.find((item) => item.code === code);
        const couponMessage = document.getElementById('couponMessage');
        if (!coupon) {
          state.coupon = null;
          couponMessage.textContent = 'Invalid coupon code';
          couponMessage.style.color = 'var(--red)';
          return;
        }
        if (subtotal < coupon.minSpend) {
          state.coupon = null;
          couponMessage.textContent = `Coupon requires a minimum spend of ${fmt(coupon.minSpend)}`;
          couponMessage.style.color = 'var(--red)';
          return;
        }
        state.coupon = coupon;
        couponMessage.textContent = `Coupon applied: ${coupon.code}`;
        couponMessage.style.color = 'var(--green)';
        renderCheckoutPage();
      });
    }

    function renderAccountPage() {
      if (!state.user) {
        location.hash = '#/login';
        return;
      }
      const greeting = document.getElementById('accountGreeting');
      if (greeting) greeting.textContent = 'Signed in as ' + state.user.email;

      const body = document.getElementById('accountBody');
      const activeTab = state.activeAccountTab || 'bookings';
      const bookings = state.bookings.filter((item) => item.email === state.user.email);
      const wishlistPackages = PKGS.filter((pkg) => state.wishlist.includes(pkg.id));

      document.querySelectorAll('[data-account-tab]').forEach((tab) => {
        tab.classList.toggle('active', tab.dataset.accountTab === activeTab);
      });

      if (activeTab === 'bookings') {
        body.innerHTML = `
          <div class="detail-panel">
            <h3 style="margin-top:0;">My bookings</h3>
            ${bookings.length ? bookings.map((booking) => {
              const pkg = PKGS.find((item) => item.id === booking.pkgId) || PKGS[0];
              return `
                <div style="display:flex; gap:14px; align-items:flex-start; padding:12px 0; border-bottom:1px solid var(--line);">
                  <img src="${pkg.image}" alt="${escHtml(pkg.name)}" style="width:120px; height:80px; object-fit:cover; border-radius:10px;" />
                  <div style="flex:1; min-width:0;">
                    <div style="font-weight:800; margin-bottom:4px;">${escHtml(pkg.name)}</div>
                    <div style="font-size:13px; color:var(--gray);">${escHtml(booking.id)} • ${booking.date}</div>
                    <div style="font-size:13px; color:var(--gray); margin-top:4px;">${escHtml(booking.guestName)}</div>
                  </div>
                  <div style="text-align:right;">
                    <span class="status-pill confirmed">${escHtml(booking.status)}</span>
                    <div style="font-weight:800; color:var(--royal); margin-top:8px;">${fmt(booking.total)}</div>
                  </div>
                </div>
              `;
            }).join('') : '<p style="margin:0; color:var(--gray);">No bookings yet. <a href="#/search" style="color:var(--ocean); font-weight:800;">Explore packages</a></p>'}
          </div>
        `;
      }

      if (activeTab === 'wishlist') {
        body.innerHTML = `
          <div class="detail-panel">
            <h3 style="margin-top:0;">Wishlist</h3>
            ${wishlistPackages.length ? `<div class="results-grid">${wishlistPackages.map(pkgCard).join('')}</div>` : '<p style="margin:0; color:var(--gray);">Your wishlist is empty. Add packages you love.</p>'}
          </div>
        `;
      }

      if (activeTab === 'profile') {
        body.innerHTML = `
          <div class="detail-panel">
            <h3 style="margin-top:0;">Profile</h3>
            <div class="form-grid">
              <div class="field">
                <label>Name</label>
                <input type="text" id="profileName" value="${escHtml(state.user.name)}" />
              </div>
              <div class="field">
                <label>Phone</label>
                <input type="tel" id="profilePhone" value="${escHtml(state.user.phone || '')}" />
              </div>
              <div class="field" style="grid-column:1 / -1;">
                <label>Email</label>
                <input type="email" value="${escHtml(state.user.email)}" disabled />
              </div>
            </div>
            <div style="display:flex; gap:10px; flex-wrap:wrap; margin-top:18px;">
              <button type="button" class="btn btn-primary" id="saveProfileBtn">Save changes</button>
              <button type="button" class="btn btn-ghost" id="logoutBtn">Sign out</button>
            </div>
          </div>
        `;
        document.getElementById('saveProfileBtn').addEventListener('click', () => {
          const newName = document.getElementById('profileName').value.trim();
          const newPhone = document.getElementById('profilePhone').value.trim();
          if (!newName) {
            toast('Name cannot be empty.', 'error');
            return;
          }
          state.user.name = newName;
          state.user.phone = newPhone;
          sessionStorage.setItem('tripifyUser', JSON.stringify(state.user));
          updateNav();
          renderAccountPage();
          toast('Profile updated successfully.');
        });
        document.getElementById('logoutBtn').addEventListener('click', performLogout);
      }
    }

    function renderAdminPage() {
      const body = document.getElementById('adminBody');
      const logoutButton = document.getElementById('adminLogoutBtn');
      if (logoutButton) logoutButton.style.display = adminAuthorization ? 'inline-flex' : 'none';
      if (!adminAuthorization) {
        body.innerHTML = `
          <div class="auth-panel" style="max-width:440px; margin:0 auto;">
            <h2 style="margin-top:0;">Admin sign in</h2>
            <p style="color:var(--gray);">Enter your administrator credentials to continue.</p>
            <form id="adminLoginForm">
              <div class="field">
                <label for="adminUsername">Username</label>
                <input id="adminUsername" name="username" autocomplete="username" required />
              </div>
              <div class="field" style="margin-top:14px;">
                <label for="adminPassword">Password</label>
                <input id="adminPassword" name="password" type="password" autocomplete="current-password" required />
              </div>
              <p id="adminLoginMessage" role="alert" style="min-height:20px; color:var(--red);"></p>
              <button type="submit" class="btn btn-primary" style="width:100%;">Sign in</button>
            </form>
          </div>
        `;
        document.getElementById('adminLoginForm').addEventListener('submit', async (event) => {
          event.preventDefault();
          const username = document.getElementById('adminUsername').value;
          const password = document.getElementById('adminPassword').value;
          const bytes = new TextEncoder().encode(`${username}:${password}`);
          const encodedCredentials = btoa(Array.from(bytes, (byte) => String.fromCharCode(byte)).join(''));
          const authorization = `Basic ${encodedCredentials}`;
          const message = document.getElementById('adminLoginMessage');
          try {
            const response = await fetch('/api/admin/session', { headers: { Authorization: authorization } });
            const result = response.ok ? await response.json() : null;
            if (!result?.authenticated) {
              message.textContent = 'Invalid administrator credentials.';
              return;
            }
            adminAuthorization = authorization;
            renderAdminPage();
          } catch {
            message.textContent = 'Unable to reach the admin authentication server.';
          }
        });
        return;
      }

      const activeTab = state.activeAdminTab || 'dashboard';
      document.querySelectorAll('[data-admin-tab]').forEach((tab) => {
        tab.classList.toggle('active', tab.dataset.adminTab === activeTab);
      });

      if (activeTab === 'dashboard') {
        const revenue = state.bookings.reduce((sum, booking) => sum + Number(booking.total || 0), 0);
        body.innerHTML = `
          <div>
            <div class="dashboard-grid">
              <div class="metric-card"><span>Total bookings</span><strong>${state.bookings.length}</strong><small>+12% this month</small></div>
              <div class="metric-card"><span>Revenue</span><strong>${fmt(revenue)}</strong><small>+8% this month</small></div>
              <div class="metric-card"><span>Users</span><strong>${state.users.length}</strong><small>Registered</small></div>
              <div class="metric-card"><span>Packages</span><strong>${PKGS.length}</strong><small>Active</small></div>
            </div>
            <div class="detail-panel">
              <h3 style="margin-top:0;">Recent bookings</h3>
              ${state.bookings.length ? state.bookings.slice(-5).reverse().map((booking) => `
                <div style="display:flex; align-items:center; justify-content:space-between; gap:12px; padding:12px 0; border-bottom:1px solid var(--line);">
                  <div>
                    <div style="font-weight:800;">${escHtml(booking.guestName)}</div>
                    <div style="font-size:13px; color:var(--gray);">${escHtml(booking.id)} • ${escHtml(booking.email)}</div>
                  </div>
                  <div style="font-weight:800; color:var(--royal);">${fmt(booking.total)}</div>
                </div>
              `).join('') : '<p style="margin:0; color:var(--gray);">No bookings yet.</p>'}
            </div>
          </div>
        `;
      }

      if (activeTab === 'bookings') {
        body.innerHTML = `
          <div class="detail-panel">
            <h3 style="margin-top:0;">All bookings</h3>
            <div class="table-wrap">
              <table>
                <thead>
                  <tr><th>ID</th><th>Guest</th><th>Package</th><th>Date</th><th>Total</th><th>Status</th></tr>
                </thead>
                <tbody>
                  ${state.bookings.length ? state.bookings.map((booking) => {
                    const pkg = PKGS.find((item) => item.id === booking.pkgId) || PKGS[0];
                    return `<tr><td>${escHtml(booking.id)}</td><td>${escHtml(booking.guestName)}<br><span style="color:var(--gray); font-size:12px;">${escHtml(booking.email)}</span></td><td>${escHtml(pkg.name)}</td><td>${escHtml(booking.date)}</td><td>${fmt(booking.total)}</td><td><span class="status-pill confirmed">${escHtml(booking.status)}</span></td></tr>`;
                  }).join('') : `<tr><td colspan="6" style="color:var(--gray);">No bookings yet</td></tr>`}
                </tbody>
              </table>
            </div>
          </div>
        `;
      }

      if (activeTab === 'packages') {
        body.innerHTML = `
          <div class="detail-panel">
            <h3 style="margin-top:0;">Packages</h3>
            <div class="table-wrap">
              <table>
                <thead><tr><th>ID</th><th>Name</th><th>Destination</th><th>Price</th><th>Rating</th></tr></thead>
                <tbody>
                  ${PKGS.map((pkg) => `<tr><td>${escHtml(pkg.id)}</td><td>${escHtml(pkg.name)}</td><td>${escHtml(DESTS.find((dest) => dest.id === pkg.dest)?.name || '')}</td><td>${fmt(pkg.price)}</td><td>★ ${pkg.rating}</td></tr>`).join('')}
                </tbody>
              </table>
            </div>
          </div>
        `;
      }

      if (activeTab === 'destinations') {
        body.innerHTML = `
          <div class="detail-panel">
            <h3 style="margin-top:0;">Destinations</h3>
            <div class="results-grid">
              ${DESTS.map((dest) => `
                <div class="card" style="overflow:hidden;">
                  <img src="${dest.image}" alt="${escHtml(dest.name)}" style="width:100%; height:150px; object-fit:cover;" />
                  <div style="padding:14px;">
                    <div style="font-weight:800; margin-bottom:4px;">${escHtml(dest.name)}</div>
                    <div style="color:var(--gray); font-size:13px;">${escHtml(dest.tag)}</div>
                  </div>
                </div>
              `).join('')}
            </div>
          </div>
        `;
      }

      if (activeTab === 'coupons') {
        body.innerHTML = `
          <div class="detail-panel">
            <h3 style="margin-top:0;">Coupons</h3>
            ${COUPONS.map((coupon) => `
              <div style="display:flex; justify-content:space-between; align-items:center; gap:12px; padding:12px 0; border-bottom:1px solid var(--line);">
                <div>
                  <div style="font-family: 'Consolas', monospace; font-weight:800; letter-spacing: 0.08em; font-size: 16px;">${coupon.code}</div>
                  <div style="color:var(--gray); font-size:13px; margin-top:4px;">${coupon.type === 'flat' ? 'Flat ' + fmt(coupon.value) + ' off' : coupon.value + '% off'} • Min ${fmt(coupon.minSpend)}</div>
                </div>
                <span class="status-pill confirmed">Active</span>
              </div>
            `).join('')}
          </div>
        `;
      }
    }

    function renderOffersPage() {
      const offers = [
        { code: 'TRIPFIRST', title: 'First trip treat', detail: 'Flat ₹5,000 off your first booking above ₹50,000.', image: 'https://images.unsplash.com/photo-1501785888041-af3ef285b470?auto=format&fit=crop&w=1000&q=80' },
        { code: 'SUMMER10', title: 'Summer bonanza', detail: '10% instant discount on bookings above ₹30,000.', image: 'https://images.unsplash.com/photo-1507525428034-b723cf961d34?auto=format&fit=crop&w=1000&q=80' },
        { code: 'HONEY15', title: 'Honeymoon special', detail: '15% off romantic getaways above ₹80,000.', image: 'https://images.unsplash.com/photo-1527631746610-bca00a040d0a?auto=format&fit=crop&w=1000&q=80' }
      ];

      const offersGrid = document.getElementById('offersGrid');
      if (!offersGrid) return;

      offersGrid.innerHTML = offers.map((offer) => `
        <div style="background: linear-gradient(rgba(10,19,40,0.55), rgba(10,19,40,0.8)), url('${offer.image}') center/cover; border-radius:22px; padding:26px; color:#fff; min-height:220px; display:flex; flex-direction:column; justify-content:flex-end; position:relative; box-shadow: var(--shadow);">
          <span class="tag" style="top:18px; left:18px;">${offer.code}</span>
          <h3 style="margin:0 0 8px; font-size:28px;">${offer.title}</h3>
          <p style="margin:0 0 14px; color: rgba(255,255,255,0.85);">${offer.detail}</p>
          <button type="button" class="btn btn-primary" data-copy-code="${offer.code}">Copy ${offer.code}</button>
        </div>
      `).join('');

      offersGrid.querySelectorAll('[data-copy-code]').forEach((button) => {
        button.addEventListener('click', () => {
          const code = button.getAttribute('data-copy-code');
          navigator.clipboard?.writeText(code);
          toast(`Coupon ${code} copied.`);
        });
      });
    }

    function renderTestimonials() {
      const testimonialBox = document.getElementById('testimonialBox');
      const testimonialDots = document.getElementById('testimonialDots');
      if (!testimonialBox || !testimonialDots) return;

      const current = state.testimonials[state.testimonialIndex];
      testimonialBox.innerHTML = `
        <div class="testimonial active">
          <img src="${current.image}" alt="${escHtml(current.name)}" />
          <div style="color: #f5a623; font-size: 18px; font-weight: 800; letter-spacing: 0.10em;">★★★★★</div>
          <p class="testimonial-quote">“${escHtml(current.quote)}”</p>
          <div class="testimonial-name">${escHtml(current.name)}</div>
          <div class="testimonial-trip">${escHtml(current.trip)}</div>
        </div>
      `;

      testimonialDots.innerHTML = state.testimonials.map((_, index) => `
        <button type="button" class="dot ${index === state.testimonialIndex ? 'active' : ''}" data-testimonial-index="${index}" aria-label="See testimonial ${index + 1}"></button>
      `).join('');

      testimonialDots.querySelectorAll('.dot').forEach((dot) => {
        dot.addEventListener('click', () => {
          state.testimonialIndex = Number(dot.dataset.testimonialIndex);
          renderTestimonials();
        });
      });
    }

    function openLightbox(src) {
      const modal = document.getElementById('modalBackdrop');
      const content = document.getElementById('modalContent');
      if (!modal || !content) return;
      content.innerHTML = `<img src="${src}" alt="Trip preview" style="width:100%; border-radius:16px; display:block;" />`;
      modal.classList.add('on');
      content.querySelector('img').style.maxHeight = '80vh';
    }

    function closeModal() {
      const modal = document.getElementById('modalBackdrop');
      const content = document.getElementById('modalContent');
      if (modal) modal.classList.remove('on');
      if (content) content.innerHTML = '';
    }

    function handleClick(event) {
      const action = event.target.closest('[data-action]');
      if (action) {
        const kind = action.dataset.action;
        if (kind === 'toggle-wishlist') {
          const id = action.dataset.id;
          toggleWishlist(id);
        }
        if (kind === 'open-package') {
          const id = action.dataset.id;
          location.hash = '#/detail/' + id;
        }
        if (kind === 'start-booking') {
          const id = action.dataset.id;
          state.currentPkg = PKGS.find((pkg) => pkg.id === id) || PKGS[0];
          location.hash = '#/checkout';
        }
        if (kind === 'open-account') {
          location.hash = '#/account';
        }
        if (kind === 'logout') {
          performLogout();
        }
        if (kind === 'open-search-destination') {
          const destination = action.dataset.destination;
          const pkg = PKGS.find((item) => item.dest === destination);
          if (pkg) {
            location.hash = '#/detail/' + pkg.id;
          } else {
            location.hash = '#/search';
            setTimeout(() => {
              const fDest = document.getElementById('fDest');
              if (fDest) {
                fDest.value = destination;
                renderSearchResults();
              }
            }, 80);
          }
        }
      }

      const copyButton = event.target.closest('[data-copy-code]');
      if (copyButton) {
        const code = copyButton.getAttribute('data-copy-code');
        navigator.clipboard?.writeText(code);
        toast(`Coupon ${code} copied.`);
      }

      const toggleDot = event.target.closest('[data-testimonial-index]');
      if (toggleDot) {
        state.testimonialIndex = Number(toggleDot.dataset.testimonialIndex);
        renderTestimonials();
      }

      if (event.target.matches('[data-close-modal="true"]')) {
        closeModal();
      }

      if (event.target.closest('[data-scroll-target]')) {
        const targetId = event.target.closest('[data-scroll-target]').dataset.scrollTarget;
        const target = document.getElementById(targetId);
        const direction = Number(event.target.closest('[data-scroll-target]').dataset.direction || 1);
        if (target) target.scrollBy({ left: direction * 560, behavior: 'smooth' });
      }
    }

    function toggleWishlist(id) {
      const index = state.wishlist.indexOf(id);
      if (index === -1) {
        state.wishlist.push(id);
        toast('Added to wishlist.');
      } else {
        state.wishlist.splice(index, 1);
        toast('Removed from wishlist.');
      }
      localStorage.setItem('tripifyWishlist', JSON.stringify(state.wishlist));
      updateNav();
      if (location.hash.startsWith('#/detail')) renderDetailPage();
      if (location.hash.startsWith('#/search')) renderSearchResults();
      if (location.hash.startsWith('#/account')) renderAccountPage();
    }

    function performLogout() {
      state.user = null;
      sessionStorage.removeItem('tripifyUser');
      updateNav();
      location.hash = '#/home';
      toast('Signed out.');
    }

    function submitLogin(event) {
      event.preventDefault();
      const email = document.getElementById('loginEmail').value.trim();
      const password = document.getElementById('loginPassword').value.trim();
      const match = state.users.find((user) => user.email === email && user.password === password);
      if (!match) {
        toast('Invalid email or password.', 'error');
        return;
      }
      state.user = { name: match.name, email: match.email, phone: match.phone };
      sessionStorage.setItem('tripifyUser', JSON.stringify(state.user));
      updateNav();
      toast(`Welcome back, ${state.user.name.split(' ')[0]}!`);
      const next = sessionStorage.getItem('tripifyNextRoute');
      if (next) {
        location.hash = next;
        sessionStorage.removeItem('tripifyNextRoute');
      } else {
        location.hash = '#/account';
      }
    }

    function submitRegister(event) {
      event.preventDefault();
      const name = document.getElementById('registerName').value.trim();
      const email = document.getElementById('registerEmail').value.trim();
      const phone = document.getElementById('registerPhone').value.trim();
      const password = document.getElementById('registerPassword').value.trim();

      if (name.length < 3 || !/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email) || !/^\d{10}$/.test(phone) || password.length < 6) {
        toast('Please complete all fields correctly.', 'error');
        return;
      }

      const alreadyExists = state.users.some((user) => user.email === email);
      if (alreadyExists) {
        toast('This email is already registered.', 'error');
        return;
      }

      const newUser = { name, email, phone, password };
      state.users.push(newUser);
      saveData();
      state.user = { name, email, phone };
      sessionStorage.setItem('tripifyUser', JSON.stringify(state.user));
      updateNav();
      toast('Account created successfully.');
      location.hash = '#/account';
    }

    function bindEvents() {
      const nav = document.getElementById('mainNav');
      if (nav) {
        window.addEventListener('scroll', () => {
          nav.classList.toggle('scrolled', window.scrollY > 18);
        });
      }

      document.getElementById('burgerBtn')?.addEventListener('click', () => {
        const menu = document.getElementById('mobileMenu');
        menu?.classList.toggle('open');
      });

      document.getElementById('homeSearchForm')?.addEventListener('submit', (event) => {
        event.preventDefault();
        const destination = document.getElementById('homeDestination').value;
        const budget = document.getElementById('homeBudget').value;
        location.hash = '#/search';
        setTimeout(() => {
          const fDest = document.getElementById('fDest');
          if (fDest && destination) fDest.value = destination;
          const fPrice = document.getElementById('fPrice');
          if (fPrice && budget) fPrice.value = budget;
          const priceLabel = document.getElementById('fPriceLabel');
          if (priceLabel) priceLabel.textContent = 'Up to ' + fmt(Number(budget || 200000));
          renderSearchResults();
        }, 80);
      });

      document.getElementById('newsletterForm')?.addEventListener('submit', (event) => {
        event.preventDefault();
        const email = document.getElementById('newsletterEmail');
        if (email && email.value.trim()) {
          email.value = '';
          toast('Subscribed! Expect curated deals soon.');
        }
      });

      document.getElementById('sortBy')?.addEventListener('change', renderSearchResults);
      document.getElementById('mobileFilterBtn')?.addEventListener('click', renderSearchFiltersMobile);
      document.getElementById('clearFiltersBtn')?.addEventListener('click', resetFilters);
      document.getElementById('resetSearchBtn')?.addEventListener('click', resetFilters);

      document.getElementById('loginForm')?.addEventListener('submit', submitLogin);
      document.getElementById('registerForm')?.addEventListener('submit', submitRegister);

      document.querySelectorAll('[data-account-tab]').forEach((tab) => {
        tab.addEventListener('click', () => {
          state.activeAccountTab = tab.dataset.accountTab;
          renderAccountPage();
        });
      });

      document.querySelectorAll('[data-admin-tab]').forEach((tab) => {
        tab.addEventListener('click', () => {
          state.activeAdminTab = tab.dataset.adminTab;
          renderAdminPage();
        });
      });

      document.getElementById('adminLogoutBtn')?.addEventListener('click', () => {
        adminAuthorization = null;
        renderAdminPage();
      });

      document.addEventListener('click', handleClick);
      document.addEventListener('click', (event) => {
        if (event.target.id === 'modalBackdrop') closeModal();
      });
      document.addEventListener('keydown', (event) => {
        if (event.key === 'Escape') closeModal();
      });
    }

    function init() {
      updateNav();
      bindEvents();
      renderHome();
      renderTestimonials();
      if (state.user) {
        updateNav();
      }
      window.addEventListener('hashchange', router);
      router();
      setInterval(() => {
        state.testimonialIndex = (state.testimonialIndex + 1) % state.testimonials.length;
        renderTestimonials();
      }, 5000);
    }

    document.addEventListener('DOMContentLoaded', init);
  </script>
</body>
</html>
