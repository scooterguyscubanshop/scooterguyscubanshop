<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Scooters Guys – Envíos desde USA a Cuba</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css"/>
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
  <style>
    :root {
      --primary: #6b21a8;     /* Morado principal */
      --primary-dark: #4c1d95;
      --accent: #a78bfa;      /* Morado claro para highlights */
      --dark: #0f0f0f;
      --dark-gray: #1f1f1f;
      --gray: #888;
      --light-gray: #e5e5e5;
    }
    * { margin:0; padding:0; box-sizing:border-box; }
    body {
      font-family: 'Poppins', sans-serif;
      color: #eee;
      background: var(--dark);
      line-height: 1.6;
      overflow-x: hidden;
    }
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;800&display=swap');

    @keyframes fadeIn { 0% { opacity: 0; transform: translateY(50px); } 100% { opacity: 1; transform: translateY(0); } }
    @keyframes slideIn { 0% { transform: translateX(-100%); } 100% { transform: translateX(0); } }
    @keyframes zoom { 0% { transform: scale(1); } 100% { transform: scale(1.05); } }
    .fade-in { animation: fadeIn 1s ease-out forwards; }
    .slide-in { animation: slideIn 1.2s ease-out forwards; }

    header {
      background: linear-gradient(to right, var(--primary), var(--accent));
      color: white;
      padding: 12px 5%;
      position: sticky;
      top: 0;
      z-index: 100;
      box-shadow: 0 2px 8px rgba(0,0,0,0.15);
    }
    .header-top {
      display: flex;
      justify-content: space-between;
      align-items: center;
      max-width: 1400px;
      margin: 0 auto;
    }
    .logo {
      font-size: 1.8rem;
      font-weight: bold;
      letter-spacing: 1px;
    }
    .nav-icons a {
      color: white;
      margin-left: 20px;
      font-size: 1.1rem;
      text-decoration: none;
    }
    .nav-icons a:hover { opacity: 0.7; }

    .collection-hero {
      background: #f8f8f8;
      text-align: center;
      padding: 40px 20px;
      border-bottom: 1px solid var(--light-gray);
    }
    .collection-hero h1 {
      font-size: 2.2rem;
      margin-bottom: 8px;
      color: var(--primary);
    }
    .collection-hero p {
      color: var(--gray);
      max-width: 700px;
      margin: 0 auto;
    }

    .offers-banner {
      background: var(--secondary);
      color: white;
      text-align: center;
      padding: 20px;
      margin: 20px 0;
      border-radius: 8px;
    }
    .offers-banner h2 {
      font-size: 1.8rem;
      margin-bottom: 12px;
    }
    .offers-banner ul {
      list-style: none;
      padding: 0;
    }
    .offers-banner li {
      margin: 8px 0;
      font-size: 1.1rem;
    }

    .container {
      max-width: 1400px;
      margin: 0 auto;
      padding: 30px 5%;
    }

    .products-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 30px 20px;
      margin: 40px 0;
    }

    .product-card {
      background: white;
      border: 1px solid var(--light-gray);
      border-radius: 6px;
      overflow: hidden;
      transition: transform 0.15s, box-shadow 0.15s;
      text-decoration: none;
      color: inherit;
      display: flex;
      flex-direction: column;
    }
    .product-card:hover {
      transform: translateY(-4px);
      box-shadow: 0 10px 20px rgba(0,0,0,0.1);
    }
    .product-image {
      height: 260px;
      background: #f5f5f5;
      display: flex;
      align-items: center;
      justify-content: center;
      position: relative;
    }
    .product-image img {
      max-height: 100%;
      max-width: 100%;
      object-fit: contain;
    }
    .product-info {
      padding: 16px;
      flex-grow: 1;
      display: flex;
      flex-direction: column;
    }
    .product-title {
      font-size: 1.05rem;
      margin-bottom: 8px;
      font-weight: 500;
    }
    .product-price {
      font-size: 1.1rem;
      font-weight: bold;
      color: var(--primary);
      margin-top: auto;
    }
    .product-price del {
      color: var(--gray);
      font-weight: normal;
      margin-left: 8px;
      font-size: 0.95rem;
    }
    .offer-tag {
      background: var(--secondary);
      color: white;
      font-size: 0.85rem;
      padding: 4px 8px;
      border-radius: 4px;
      margin-top: 8px;
      display: inline-block;
    }

    .pagination {
      display: flex;
      justify-content: center;
      gap: 12px;
      margin: 50px 0 30px;
    }
    .pagination a, .pagination span {
      width: 40px;
      height: 40px;
      display: flex;
      align-items: center;
      justify-content: center;
      border: 1px solid var(--light-gray);
      border-radius: 6px;
      text-decoration: none;
      color: #333;
      font-weight: 500;
    }
    .pagination .current {
      background: var(--primary);
      color: white;
      border-color: var(--primary);
    }
    .pagination a:hover:not(.current) {
      background: #f0f0f0;
    }

    footer {
      background: #111;
      color: #ccc;
      padding: 60px 5% 30px;
      text-align: center;
    }
    .footer-text {
      margin-top: 30px;
      font-size: 0.9rem;
    }

    @media (max-width: 768px) {
      .products-grid { grid-template-columns: repeat(auto-fill, minmax(240px, 1fr)); }
    }
    @media (max-width: 480px) {
      .products-grid { grid-template-columns: 1fr; }
      .collection-hero h1 { font-size: 1.8rem; }
    }
  </style>
</head>
<body>

  <!-- Header -->
  <header>
    <div class="header-top">
      <img src="https://i.ibb.co/0jZ5R9F/scooter-guys-logo.png" alt="Scooters Guys Logo" class="logo" style="height: 50px;">
      <div class="nav-icons">
        <a href="#"><i class="fas fa-search"></i></a>
        <a href="#"><i class="fas fa-user"></i></a>
        <a href="#" id="open-cart"><i class="fas fa-shopping-cart"></i> <span id="cart-count">0</span></a>
      </div>
    </div>
  </header>

  <!-- Hero con logo y movimiento -->
  <section id="hero">
    <div class="hero-bg"></div>
    <div class="hero-overlay"></div>
    <img src="https://i.ibb.co/0jZ5R9F/scooter-guys-logo.png" alt="Scooters Guys Logo Float" class="hero-logo-float">
    <div class="hero-content fade-in">
      <h1>¡Desde USA Directo a Cuba!</h1>
      <p class="hero-slogan">Envíos rápidos, seguros y llenos de energía – Tu moto, nevera o kit solar llega con estilo</p>
      <a href="#products" class="hero-cta">Ver Ofertas Ahora</a>
    </div>
  </section>

  <!-- Banner de ofertas especiales -->
  <section class="offers-banner">
    <h2>Ofertas Atractivas – ¡No te las pierdas!</h2>
    <ul>
      <li>Kit Solar 1000W + Panel 120W: $699 (envío gratis a Cuba)</li>
      <li>Bundle Moto Eléctrica + Batería Extra: 20% off</li>
      <li>Electrodomésticos con recarga Cubacel gratis en compras > $500</li>
      <li>Envíos express como Panavan: Llega en 7-10 días</li>
    </ul>
  </section>

  <div class="container">

    <!-- Grid de productos -->
    <div class="products-grid">

      <a href="#" class="product-card">
        <div class="product-image">
          <img src="https://via.placeholder.com/300x260/eee/333?text=Moto+Eléctrica+Pro" alt="Moto Eléctrica Pro">
        </div>
        <div class="product-info">
          <h3 class="product-title">Moto Eléctrica Pro – 1000W</h3>
          <div class="product-price">$450 <del>$550</del></div>
          <span class="offer-tag">20% Off + Envío a Cuba</span>
        </div>
      </a>

      <a href="#" class="product-card">
        <div class="product-image">
          <img src="https://via.placeholder.com/300x260/eee/333?text=Moto+Combustión+Classic" alt="Moto Combustión Classic">
        </div>
        <div class="product-info">
          <h3 class="product-title">Moto Combustión Classic – 150cc</h3>
          <div class="product-price">$800 <del>$950</del></div>
          <span class="offer-tag">Bundle con Casco Gratis</span>
        </div>
      </a>

      <a href="#" class="product-card">
        <div class="product-image">
          <img src="https://via.placeholder.com/300x260/eee/333?text=Nevera+Eficiente" alt="Nevera Eficiente">
        </div>
        <div class="product-info">
          <h3 class="product-title">Nevera Electrodoméstica – 200L</h3>
          <div class="product-price">$350</div>
          <span class="offer-tag">Envío Express a Cuba</span>
        </div>
      </a>

      <a href="#" class="product-card">
        <div class="product-image">
          <img src="https://via.placeholder.com/300x260/eee/333?text=Kit+Solar+2000W" alt="Kit Solar 2000W">
        </div>
        <div class="product-info">
          <h3 class="product-title">Kit Solar 2000W + Panel 200W</h3>
          <div class="product-price">$1,449 <del>$1,600</del></div>
          <span class="offer-tag">Oferta Especial como Cuba Max</span>
        </div>
      </a>

      <a href="#" class="product-card">
        <div class="product-image">
          <img src="https://via.placeholder.com/300x260/eee/333?text=Lavadora+Automática" alt="Lavadora Automática">
        </div>
        <div class="product-info">
          <h3 class="product-title">Lavadora Automática – 8kg</h3>
          <div class="product-price">$400 <del>$480</del></div>
          <span class="offer-tag">15% Off para Envíos a Cuba</span>
        </div>
      </a>

      <a href="#" class="product-card">
        <div class="product-image">
          <img src="https://via.placeholder.com/300x260/eee/333?text=Moto+Eléctrica+Kids" alt="Moto Eléctrica Kids">
        </div>
        <div class="product-info">
          <h3 class="product-title">Moto Eléctrica para Niños</h3>
          <div class="product-price">$200</div>
          <span class="offer-tag">Envío Gratis en Bundles</span>
        </div>
      </a>

    </div>

    <!-- Paginación -->
    <nav class="pagination">
      <a href="?page=1">1</a>
      <span class="current">2</span>
      <a href="?page=3">3</a>
      <a href="?page=4">4</a>
      <a href="?page=3">→</a>
    </nav>

  </div>

  <!-- Footer simplificado -->
  <footer>
    <div class="footer-text">
      © 2026 Scooters Guys – Envíos a Cuba desde Amsterdam y USA<br>
      Ofertas rápidas • Garantía • Soporte 24/7
    </div>
  </footer>

</body>
</html>
