
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="theme-color" content="#071a35">
  <meta name="description" content="Discover destinations and search flights for your next journey with SkyVoyage.">
  <title>SkyVoyage | Discover Your Next Journey</title>

  <style>
    :root {
      --navy: #071a35;
      --blue: #1769ff;
      --text: #14233d;
      --muted: #69778c;
      --bg: #f4f7fc;
    }

    * { box-sizing: border-box; }

    html { scroll-behavior: smooth; }

    body {
      margin: 0;
      font-family: Inter, -apple-system, BlinkMacSystemFont,
        "Segoe UI", Arial, sans-serif;
      color: var(--text);
      background: var(--bg);
    }

    a { text-decoration: none; color: inherit; }

    .nav {
      min-height: 76px;
      padding: 0 7%;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 20px;
      background: white;
    }

    .logo {
      font-size: 23px;
      font-weight: 850;
      letter-spacing: -1px;
      color: var(--navy);
    }

    .logo span { color: var(--blue); }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 28px;
      font-size: 14px;
      font-weight: 600;
      color: #536177;
    }

    .nav-cta {
      background: var(--blue);
      color: white;
      padding: 12px 19px;
      border-radius: 9px;
    }

    .hero {
      padding: 76px 7% 110px;
      color: white;
      background:
        linear-gradient(100deg, rgba(5, 20, 43, .95),
        rgba(8, 39, 79, .72)),
        linear-gradient(135deg, #123d70, #397dc5);
      position: relative;
      overflow: hidden;
    }

    .hero::after {
      content: "✈";
      position: absolute;
      right: 9%;
      top: 45px;
      font-size: clamp(130px, 24vw, 280px);
      color: rgba(255,255,255,.07);
      transform: rotate(-12deg);
      pointer-events: none;
    }

    .hero-content {
      max-width: 850px;
      position: relative;
      z-index: 1;
    }

    .eyebrow {
      color: #a9c9ff;
      font-size: 12px;
      font-weight: 800;
      letter-spacing: 2px;
      text-transform: uppercase;
    }

    h1 {
      font-size: clamp(39px, 6vw, 68px);
      line-height: 1.08;
      letter-spacing: -2px;
      max-width: 750px;
      margin: 20px 0;
    }

    .hero p {
      color: #d6e3f6;
      font-size: 17px;
      line-height: 1.8;
      max-width: 570px;
    }

    .search-wrap {
      max-width: 1100px;
      margin: -48px auto 0;
      padding: 0 22px;
      position: relative;
      z-index: 3;
    }

    .search-card {
      background: white;
      padding: 30px;
      border-radius: 19px;
      box-shadow: 0 18px 60px rgba(14, 35, 71, .12);
    }

    .search-heading {
      margin: 0 0 8px;
      font-size: 23px;
      letter-spacing: -.5px;
    }

    .search-subtitle {
      color: var(--muted);
      font-size: 14px;
      margin: 0 0 24px;
      line-height: 1.7;
    }

    /* Travelpayouts flight search widget */
    #tpwl-tickets {
      display: block;
      width: 100%;
      min-height: 180px;
      overflow: visible;
    }

    .section {
      max-width: 1150px;
      margin: auto;
      padding: 78px 24px;
    }

    .section-head {
      display: flex;
      justify-content: space-between;
      align-items: end;
      gap: 20px;
      margin-bottom: 28px;
    }

    .section h2 {
      font-size: clamp(27px, 4vw, 36px);
      letter-spacing: -1px;
      margin: 10px 0;
    }

    .section-head p, .intro {
      color: var(--muted);
      line-height: 1.7;
    }

    .destinations {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 22px;
    }

    .destination {
      overflow: hidden;
      background: white;
      border-radius: 16px;
      border: 1px solid #e8edf5;
      transition: transform .2s, box-shadow .2s;
    }

    .destination:hover {
      transform: translateY(-4px);
      box-shadow: 0 15px 35px #14233d12;
    }

    .destination img {
      display: block;
      width: 100%;
      height: 210px;
      object-fit: cover;
      background: #dce8f6;
    }

    .destination-info { padding: 20px; }

    .destination-info h3 {
      margin: 0 0 8px;
      font-size: 20px;
    }

    .destination-info p {
      margin: 0;
      color: var(--muted);
      font-size: 14px;
      line-height: 1.6;
    }

    .features {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 20px;
      margin-top: 30px;
    }

    .feature {
      padding: 25px;
      border-radius: 15px;
      border: 1px solid #e6ecf5;
      background: white;
    }

    .feature-icon {
      font-size: 27px;
      margin-bottom: 16px;
    }

    .feature h3 { margin: 0 0 10px; }

    .feature p {
      color: var(--muted);
      line-height: 1.7;
      font-size: 14px;
      margin: 0;
    }

    .cta {
      background: var(--navy);
      border-radius: 20px;
      padding: 40px;
      color: white;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 25px;
    }

    .cta h2 { margin-top: 0; }

    .cta p {
      color: #c3d1e5;
      line-height: 1.7;
    }

    .button {
      display: inline-block;
      background: var(--blue);
      color: white;
      padding: 14px 22px;
      border-radius: 9px;
      font-weight: 700;
      white-space: nowrap;
    }

    footer {
      background: #041126;
      color: #d0d9e8;
      padding: 35px 7%;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 20px;
      flex-wrap: wrap;
      font-size: 13px;
    }

    footer p { line-height: 1.7; }

    footer a { color: white; }

    @media (max-width: 720px) {
      .nav { padding: 18px 5%; }
      .nav-links { gap: 12px; }
      .nav-links .optional { display: none; }
      .nav-cta { padding: 10px 12px; }
      .hero { padding: 60px 6% 85px; }
      .hero p { font-size: 15px; }
      .search-wrap { padding: 0 13px; }
      .search-card { padding: 21px 16px; }
      .destinations, .features {
        grid-template-columns: 1fr;
      }
      .destination img { height: 230px; }
      .section { padding: 55px 18px; }
      .section-head { display: block; }
      .cta { padding: 27px 22px; flex-direction: column; align-items: flex-start; }
      footer { padding: 28px 6%; }
    }
  </style>
</head>

<body>
  <header class="nav">
    <a class="logo" href="#" aria-label="SkyVoyage home">
      Sky<span>Voyage</span>
    </a>

    <nav class="nav-links" aria-label="Main navigation">
      <a class="optional" href="#destinations">Destinations</a>
      <a class="optional" href="#why-us">Why us</a>
      <a class="nav-cta" href="#flights">Search Flights</a>
    </nav>
  </header>

  <main>
    <section class="hero">
      <div class="hero-content">
        <div class="eyebrow">Your journey begins here</div>
        <h1>Discover the world.<br>One flight at a time.</h1>
        <p>
          Find your next adventure, explore inspiring destinations
          and plan your journey with our flight search experience.
        </p>
      </div>
    </section>

    <section class="search-wrap" id="flights" aria-label="Flight search">
      <div class="search-card">
        <h2 class="search-heading">Where would you like to go?</h2>
        <p class="search-subtitle">
          Explore flight options for your next journey.
        </p>

        <div id="tpwl-tickets"></div>
      </div>
    </section>

    <section class="section" id="destinations">
      <div class="section-head">
        <div>
          <div class="eyebrow" style="color:#1769ff">Get inspired</div>
          <h2>Explore popular destinations</h2>
          <p>From vibrant cities to unforgettable escapes.</p>
        </div>
      </div>

      <div class="destinations">
        <article class="destination">
          <img
            src="https://images.unsplash.com/photo-1519501025264-65ba15a82390?auto=format&fit=crop&w=800&q=80"
            alt="New York city skyline"
            loading="lazy">
          <div class="destination-info">
            <h3>New York, USA</h3>
            <p>Discover iconic sights and the energy of the city.</p>
          </div>
        </article>

        <article class="destination">
          <img
            src="https://images.unsplash.com/photo-1502602898657-3e91760cbb34?auto=format&fit=crop&w=800&q=80"
            alt="Paris and the Eiffel Tower"
            loading="lazy">
          <div class="destination-info">
            <h3>Paris, France</h3>
            <p>Enjoy beautiful streets, art and unforgettable views.</p>
          </div>
        </article>

        <article class="destination">
          <img
            src="https://images.unsplash.com/photo-1512453979798-5ea266f8880c?auto=format&fit=crop&w=800&q=80"
            alt="Dubai skyline"
            loading="lazy">
          <div class="destination-info">
            <h3>Dubai, UAE</h3>
            <p>Experience modern architecture and desert adventures.</p>
          </div>
        </article>
      </div>
    </section>

    <section class="section" id="why-us">
      <div class="eyebrow" style="color:#1769ff">Travel with confidence</div>
      <h2>Make planning your trip easier</h2>
      <p class="intro">
        Everything starts with finding a journey that fits your plans.
      </p>

      <div class="features">
        <article class="feature">
          <div class="feature-icon">✈️</div>
          <h3>Flight discovery</h3>
          <p>Use the flight search widget to explore available options.</p>
        </article>

        <article class="feature">
          <div class="feature-icon">🌍</div>
          <h3>Explore the world</h3>
          <p>Find inspiration for your next city break or holiday.</p>
        </article>

        <article class="feature">
          <div class="feature-icon">📱</div>
          <h3>Travel anywhere</h3>
          <p>Browse our website on mobile, tablet or desktop.</p>
        </article>
      </div>
    </section>

    <section class="section">
      <div class="cta">
        <div>
          <h2>Your next adventure awaits.</h2>
          <p>Start exploring flights and plan your next journey.</p>
        </div>
        <a class="button" href="#flights">Find Flights →</a>
      </div>
    </section>
  </main>

  <footer>
    <div>
      <a class="logo" href="#" style="color:white">
        Sky<span>Voyage</span>
      </a>
      <p>Discover more. Travel further.</p>
    </div>
    <div>
      <p>Flight search is provided through an external widget.</p>
      <p>Flight prices and booking terms are determined by the relevant provider.</p>
      <p>© <span id="year"></span> SkyVoyage</p>
    </div>
  </footer>

  <script>
    document.getElementById("year").textContent =
      new Date().getFullYear();
  </script>

  <!-- Travelpayouts White Label Web widget -->
  <script nowprocket data-noptimize="1" data-cfasync="false"
    data-wpfc-render="false" seraph-accel-crit="1" data-no-defer="1">
    (function () {
      var script = document.createElement("script");
      script.async = 1;
      script.type = "module";
      script.src =
        "https://tpwgts.com/wl_web/main.js?wl_id=20293";
      document.head.appendChild(script);
    })();
  </script>
</body>
</html>
