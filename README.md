# Famalautos 

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Famal Autos | Find Your Dream Car</title>

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    :root {
      --gold: #e5b84b;
      --dark: #101010;
      --card: #1b1b1b;
      --light: #f5f5f5;
      --muted: #b5b5b5;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: Arial, sans-serif;
      background: var(--dark);
      color: var(--light);
      line-height: 1.6;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    button, input, select {
      font: inherit;
    }

    .container {
      width: min(1150px, 92%);
      margin: auto;
    }

    header {
      background: #080808;
      border-bottom: 1px solid #292929;
      position: sticky;
      top: 0;
      z-index: 10;
    }

    .navbar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 15px;
      padding: 16px 0;
    }

    .logo {
      color: var(--gold);
      font-size: 25px;
      font-weight: 900;
      white-space: nowrap;
    }

    .logo span {
      color: white;
    }

    nav {
      display: flex;
      gap: 20px;
      align-items: center;
    }

    nav a {
      font-size: 14px;
    }

    nav a:hover {
      color: var(--gold);
    }

    .contact-nav {
      background: var(--gold);
      color: #111;
      padding: 9px 13px;
      border-radius: 5px;
      font-weight: bold;
    }

    .hero {
      min-height: 440px;
      display: flex;
      align-items: center;
      background:
        linear-gradient(90deg, rgba(0,0,0,.94),
        rgba(0,0,0,.55)),
        url("https://images.unsplash.com/photo-1492144534655-ae79c964c9d7?auto=format&fit=crop&w=1800&q=85")
        center/cover;
    }

    .hero-content {
      padding: 75px 0;
      max-width: 650px;
    }

    .tag {
      color: var(--gold);
      font-size: 13px;
      font-weight: bold;
      letter-spacing: 3px;
      text-transform: uppercase;
    }

    h1 {
      font-size: clamp(38px, 7vw, 66px);
      line-height: 1.1;
      margin: 18px 0;
    }

    h1 span {
      color: var(--gold);
    }

    .hero p {
      color: #ddd;
      max-width: 490px;
      margin-bottom: 25px;
    }

    .btn {
      display: inline-block;
      background: var(--gold);
      color: #111;
      padding: 12px 20px;
      border: none;
      border-radius: 5px;
      font-weight: bold;
      cursor: pointer;
    }

    .btn:hover {
      background: #f4d47c;
    }

    .btn-outline {
      background: transparent;
      color: white;
      border: 1px solid var(--gold);
      margin-left: 8px;
    }

    .btn-outline:hover {
      background: var(--gold);
      color: #111;
    }

    .features {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 15px;
      padding: 25px 0;
      border-bottom: 1px solid #292929;
    }

    .feature {
      text-align: center;
      padding: 12px;
    }

    .feature strong {
      display: block;
      color: var(--gold);
      font-size: 17px;
    }

    .feature small {
      color: var(--muted);
    }

    section {
      padding: 65px 0;
    }

    .section-heading {
      text-align: center;
      margin-bottom: 30px;
    }

    .section-heading h2 {
      font-size: 32px;
      margin: 8px 0;
    }

    .section-heading p {
      color: var(--muted);
    }

    .search-bar {
      display: grid;
      grid-template-columns: 2fr 1fr auto;
      gap: 12px;
      margin-bottom: 30px;
    }

    .search-bar input,
    .search-bar select {
      width: 100%;
      padding: 13px;
      border-radius: 5px;
      border: 1px solid #414141;
      background: #202020;
      color: white;
      min-width: 0;
    }

    .cars-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 22px;
    }

    .car-card {
      background: var(--card);
      border: 1px solid #303030;
      border-radius: 9px;
      overflow: hidden;
      transition: transform .2s, border-color .2s;
    }

    .car-card:hover {
      transform: translateY(-5px);
      border-color: var(--gold);
    }

    .car-card img {
      width: 100%;
      height: 200px;
      object-fit: cover;
      display: block;
      background: #292929;
    }

    .car-info {
      padding: 18px;
    }

    .car-type {
      color: var(--gold);
      font-size: 12px;
      text-transform: uppercase;
      font-weight: bold;
    }

    .car-info h3 {
      font-size: 20px;
      margin: 5px 0;
    }

    .car-info p {
      color: var(--muted);
      font-size: 13px;
    }

    .car-price {
      font-size: 21px;
      color: var(--gold);
      font-weight: bold;
      margin: 13px 0;
    }

    .car-actions {
      display: flex;
      gap: 9px;
    }

    .car-actions a {
      flex: 1;
      text-align: center;
      padding: 10px 5px;
      border: 1px solid var(--gold);
      border-radius: 4px;
      font-size: 13px;
      font-weight: bold;
    }

    .car-actions a:first-child {
      background: var(--gold);
      color: #111;
    }

    .car-actions a:hover {
      opacity: .8;
    }

    .no-results {
      text-align: center;
      color: var(--muted);
      padding: 30px;
      grid-column: 1 / -1;
    }

    .about {
      background: #181818;
    }

    .about-content {
      display: grid;
      grid-template-columns: 1fr 1fr;
      align-items: center;
      gap: 40px;
    }

    .about-content h2 {
      font-size: 34px;
      margin: 10px 0 15px;
    }

    .about-content p {
      color: #ccc;
      margin-bottom: 15px;
    }

    .about-list {
      list-style: none;
    }

    .about-list li {
      margin: 10px 0;
    }

    .about-list li::before {
      content: "✓ ";
      color: var(--gold);
      font-weight: bold;
    }

    .about-image {
      width: 100%;
      border-radius: 9px;
      max-height: 340px;
      object-fit: cover;
    }

    .contact-box {
      text-align: center;
      background: #202020;
      border: 1px solid #353535;
      border-radius: 10px;
      padding: 35px 20px;
    }

    .contact-box h2 {
      font-size: 30px;
      margin: 10px 0;
    }

    .contact-box p {
      color: var(--muted);
      margin-bottom: 20px;
    }

    footer {
      padding: 28px 0;
      text-align: center;
      border-top: 1px solid #303030;
      color: var(--muted);
      font-size: 13px;
    }

    footer strong {
      color: var(--gold);
    }

    @media (max-width: 850px) {
      .cars-grid {
        grid-template-columns: repeat(2, 1fr);
      }

      .navbar {
        flex-wrap: wrap;
      }

      nav {
        gap: 12px;
        flex-wrap: wrap;
      }

      .about-content {
        grid-template-columns: 1fr;
      }
    }

    @media (max-width: 560px) {
      .cars-grid {
        grid-template-columns: 1fr;
      }

      .search-bar {
        grid-template-columns: 1fr;
      }

      .features {
        gap: 5px;
      }

      .feature strong {
        font-size: 14px;
      }

      .feature small {
        font-size: 11px;
      }

      nav {
        width: 100%;
        justify-content: space-between;
      }

      nav a {
        font-size: 12px;
      }

      .hero {
        min-height: 390px;
      }

      .hero-content {
        padding: 55px 0;
      }

      .btn-outline {
        margin: 10px 0 0;
      }

      section {
        padding: 45px 0;
      }
    }
  </style>
</head>

<body>

  <!-- NAVIGATION -->
  <header>
    <div class="container navbar">
      <a href="#home" class="logo">FAMAL <span>AUTOS</span></a>

      <nav>
        <a href="#home">Home</a>
        <a href="#cars">Cars</a>
        <a href="#about">About</a>
        <a href="#contact" class="contact-nav">Contact Us</a>
      </nav>
    </div>
  </header>

  <!-- HERO SECTION -->
  <main>
    <section class="hero" id="home">
      <div class="container hero-content">
        <div class="tag">Welcome to Famal Autos</div>

        <h1>Find Your <span>Dream Car.</span></h1>

        <p>
          Discover quality vehicles at competitive prices.
          Your next car is waiting for you at Famal Autos.
        </p>

        <a href="#cars" class="btn">Explore Our Cars</a>
        <a href="#contact" class="btn btn-outline">Contact Us</a>
      </div>
    </section>

    <!-- FEATURES -->
    <div class="container features">
      <div class="feature">
        <strong>Quality Cars</strong>
        <small>Explore our selection</small>
      </div>

      <div class="feature">
        <strong>Clear Prices</strong>
        <small>See listed prices</small>
      </div>

      <div class="feature">
        <strong>Easy Enquiries</strong>
        <small>Contact us directly</small>
      </div>
    </div>

    <!-- CAR LISTINGS -->
    <section id="cars">
      <div class="container">

        <div class="section-heading">
          <div class="tag">Our Collection</div>
          <h2>Explore Our Cars</h2>
          <p>Find a car that matches your needs and budget.</p>
        </div>

        <div class="search-bar">
          <input
            type="search"
            id="searchInput"
            placeholder="Search by car name..."
            aria-label="Search cars"
          >

          <select id="categoryFilter" aria-label="Filter by car type">
            <option value="all">All Categories</option>
            <option value="sedan">Sedan</option>
            <option value="suv">SUV</option>
            <option value="sports">Sports Car</option>
          </select>

          <button class="btn" id="searchButton" type="button">
            Search
          </button>
        </div>

        <div class="cars-grid" id="carsGrid">

          <!-- CAR 1 -->
          <article class="car-card" data-name="Toyota Camry" data-category="sedan">
            <img
              src="https://images.unsplash.com/photo-1621007947382-bb3c3994e3fb?auto=format&fit=crop&w=900&q=80"
              alt="Toyota Camry"
              loading="lazy"
            >
            <div class="car-info">
              <span class="car-type">Sedan</span>
              <h3>Toyota Camry 2020</h3>
              <p>2020 model · Automatic · Petrol</p>
              <div class="car-price">₦18,500,000</div>
              <div class="car-actions">
                <a href="#contact" class="enquire" data-car="Toyota Camry 2020">Enquire Now</a>
                <a href="#contact">Details</a>
              </div>
            </div>
          </article>

          <!-- CAR 2 -->
          <article class="car-card" data-name="Mercedes Benz C Class" data-category="sedan">
            <img
              src="https://images.unsplash.com/photo-1618843479313-40f8afb4b4d8?auto=format&fit=crop&w=900&q=80"
              alt="Mercedes-Benz car"
              loading="lazy"
            >
            <div class="car-info">
              <span class="car-type">Luxury Sedan</span>
              <h3>Mercedes-Benz C-Class</h3>
              <p>2021 model · Automatic · Petrol</p>
              <div class="car-price">₦32,000,000</div>
              <div class="car-actions">
                <a href="#contact" class="enquire" data-car="Mercedes-Benz C-Class">Enquire Now</a>
                <a href="#contact">Details</a>
              </div>
            </div>
          </article>

          <!-- CAR 3 -->
          <article class="car-card" data-name="Toyota RAV4" data-category="suv">
            <img
              src="https://images.unsplash.com/photo-1519641471654-76ce0107ad1b?auto=format&fit=crop&w=900&q=80"
              alt="SUV"
              loading="lazy"
            >
            <div class="car-info">
              <span class="car-type">SUV</span>
              <h3>Toyota RAV4</h3>
              <p>2021 model · Automatic · Petrol</p>
              <div class="car-price">₦28,000,000</div>
              <div class="car-actions">
                <a href="#contact" class="enquire" data-car="Toyota RAV4">Enquire Now</a>
                <a href="#contact">Details</a>
              </div>
            </div>
          </article>

          <!-- CAR 4 -->
          <article class="car-card" data-name="Honda Accord" data-category="sedan">
            <img
              src="https://images.unsplash.com/photo-1606152421802-db97b9c7a11b?auto=format&fit=crop&w=900&q=80"
              alt="Honda Accord"
              loading="lazy"
            >
            <div class="car-info">
              <span class="car-type">Sedan</span>
              <h3>Honda Accord</h3>
              <p>2020 model · Automatic · Petrol</p>
              <div class="car-price">₦20,000,000</div>
              <div class="car-actions">
                <a href="#contact" class="enquire" data-car="Honda Accord">Enquire Now</a>
                <a href="#contact">Details</a>
              </div>
            </div>
          </article>

          <!-- CAR 5 -->
          <article class="car-card" data-name="Range Rover Sport" data-category="suv">
            <img
              src="https://images.unsplash.com/photo-1519681393784-d120267933ba?auto=format&fit=crop&w=900&q=80"
              alt="Luxury vehicle"
              loading="lazy"
            >
            <div class="car-info">
              <span class="car-type">Luxury SUV</span>
              <h3>Range Rover Sport</h3>
              <p>2022 model · Automatic · Petrol</p>
              <div class="car-price">₦75,000,000</div>
              <div class="car-actions">
                <a href="#contact" class="enquire" data-car="Range Rover Sport">Enquire Now</a>
                <a href="#contact">Details</a>
              </div>
            </div>
          </article>

          <!-- CAR 6 -->
          <article class="car-card" data-name="Porsche 911" data-category="sports">
            <img
              src="https://images.unsplash.com/photo-1503376780353-7e6692767b70?auto=format&fit=crop&w=900&q=80"
              alt="Porsche sports car"
              loading="lazy"
            >
            <div class="car-info">
              <span class="car-type">Sports Car</span>
              <h3>Porsche 911</h3>
              <p>2021 model · Automatic · Petrol</p>
              <div class="car-price">₦120,000,000</div>
              <div class="car-actions">
                <a href="#contact" class="enquire" data-car="Porsche 911">Enquire Now</a>
                <a href="#contact">Details</a>
              </div>
            </div>
          </article>

        </div>
      </div>
    </section>

    <!-- ABOUT -->
    <section class="about" id="about">
      <div class="container about-content">
        <div>
          <div class="tag">About Us</div>
          <h2>Welcome to Famal Autos</h2>

          <p>
            Famal Autos is your online destination for discovering
            cars, comparing listed prices, and making enquiries
            about your next vehicle.
          </p>

          <ul class="about-list">
            <li>Browse different car categories</li>
            <li>View prices and vehicle information</li>
            <li>Contact us about a car you like</li>
            <li>Discover your next dream car</li>
          </ul>
        </div>

        <img
          class="about-image"
          src="https://images.unsplash.com/photo-1493238792000-8113da705763?auto=format&fit=crop&w=1000&q=80"
          alt="Cars displayed in a showroom"
          loading="lazy"
        >
      </div>
    </section>

    <!-- CONTACT -->
    <section id="contact">
      <div class="container">
        <div class="contact-box">
          <div class="tag">Get In Touch</div>
          <h2>Found Your Dream Car?</h2>

          <p>
            Interested in one of our listings?
            Contact Famal Autos to make an enquiry.
          </p>

          <!-- Replace the number in the JavaScript below -->
          <a
            href="https://wa.me/2348000000000"
            class="btn"
            id="whatsappMain"
            target="_blank"
            rel="noopener"
          >
            Chat on WhatsApp
          </a>
        </div>
      </div>
    </section>
  </main>

  <!-- FOOTER -->
  <footer>
    <div class="container">
      <p><strong>FAMAL AUTOS</strong> — Find Your Dream Car.</p>
      <p>© <span id="year"></span> Famal Autos. All rights reserved.</p>
    </div>
  </footer>

  <script>
    // UPDATE THIS WITH YOUR WHATSAPP NUMBER.
    // Use country code and number, without + or spaces.
    const WHATSAPP_NUMBER = "2348000000000";

    const searchInput = document.getElementById("searchInput");
    const categoryFilter = document.getElementById("categoryFilter");
    const searchButton = document.getElementById("searchButton");
    const carCards = document.querySelectorAll(".car-card");
    const carsGrid = document.getElementById("carsGrid");

    // Search and filter cars
    function filterCars() {
      const searchTerm = searchInput.value.toLowerCase().trim();
      const selectedCategory = categoryFilter.value;
      let visibleCars = 0;

      document.querySelectorAll(".no-results").forEach(item => item.remove());

      carCards.forEach(card => {
        const carName = card.dataset.name.toLowerCase();
        const category = card.dataset.category;

        const matchesName = carName.includes(searchTerm);
        const matchesCategory =
          selectedCategory === "all" || category === selectedCategory;

        if (matchesName && matchesCategory) {
          card.style.display = "";
          visibleCars++;
        } else {
          card.style.display = "none";
        }
      });

      if (visibleCars === 0) {
        const message = document.createElement("p");
        message.className = "no-results";
        message.textContent = "No cars found. Try another search.";
        carsGrid.appendChild(message);
      }
    }

    searchButton.addEventListener("click", filterCars);

    searchInput.addEventListener("input", filterCars);

    categoryFilter.addEventListener("change", filterCars);

    // Set the footer year automatically
    document.getElementById("year").textContent =
      new Date().getFullYear();

    // Set up WhatsApp links
    function makeWhatsAppLink(message) {
      return "https://wa.me/" + WHATSAPP_NUMBER +
        "?text=" + encodeURIComponent(message);
    }

    document.getElementById("whatsappMain").href =
      makeWhatsAppLink("Hello Famal Autos, I would like to enquire about your cars.");

    document.querySelectorAll(".enquire").forEach(button => {
      button.addEventListener("click", function(event) {
        event.preventDefault();

        const car = this.dataset.car;
        const message =
          "Hello Famal Autos, I am interested in the " +
          car + ". Is it available?";

        window.open(makeWhatsAppLink(message), "_blank");
      });
    });
  </script>

</body>
</html>
