<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <title>Pink Pills.</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      background-color: #F2A8AB;
      color: #270302;
      font-family: 'Aktiv Grotesk Corp', sans-serif;
      overflow-x: hidden;
    }

    header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 20px 60px;
      background-color: #E43A3A;
      position: sticky;
      top: 0;
      z-index: 1000;
    }

    .logo {
      font-family: 'Bodoni Seventytwo ITC Book Italic', serif;
      font-size: 2.5rem;
      color: white;
    }

    nav a {
      margin: 0 15px;
      text-decoration: none;
      color: white;
      font-size: 1.1rem;
      letter-spacing: 1px;
      transition: opacity 0.3s ease;
    }

    nav a:hover {
      opacity: 0.7;
    }

    /* Параллакс-геро */
    .hero {
      position: relative;
      height: 80vh;
      overflow: hidden;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      perspective: 1px;
    }

    .hero-bg {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 120%;
      background: url('https://images.unsplash.com/photo-1522199755839-a2bacb67c546?fit=crop&w=1950&q=80') center/cover no-repeat;
      transform: translateZ(-1px) scale(2);
      z-index: -2;
    }

    .overlay {
      position: absolute;
      inset: 0;
      background-color: rgba(242, 168, 171, 0.45);
      z-index: -1;
    }

    .hero-title {
      position: relative;
      color: white;
      font-size: 3rem;
      max-width: 90%;
      font-weight: 600;
      animation: fadeIn 2s ease-in-out;
    }

    @keyframes fadeIn {
      from {opacity: 0; transform: translateY(20px);}
      to {opacity: 1; transform: translateY(0);}
    }

    footer {
      text-align: center;
      background-color: #270302;
      color: #F2A8AB;
      padding: 40px 20px;
    }

    .tags {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      justify-content: center;
      max-width: 1000px;
      margin: 0 auto;
    }

    .tags span {
      display: inline-block;
      margin: 8px;
      padding: 5px 10px;
      font-size: 0.9rem;
      border: 1px solid #F2A8AB;
      border-radius: 20px;
      transition: all 0.3s ease, transform 0.3s ease;
      cursor: pointer;
      opacity: 0;
      transform: translateY(20px);
    }

    .tags span.show {
      opacity: 1;
      transform: translateY(0);
    }

    .tags span:hover {
      background-color: #E43A3A;
      color: white;
      border-color: #E43A3A;
      transform: scale(1.1);
    }

    @media (max-width: 768px) {
      header {
        flex-direction: column;
        padding: 15px 30px;
      }
      nav a {
        margin: 10px 0;
      }
      .hero-title {
        font-size: 2rem;
      }
    }
  </style>
</head>
<body>

  <header>
    <h1 class="logo">Pink Pills.</h1>
    <nav>
      <a href="#">Подборки</a>
      <a href="#">Рецензии</a>
      <a href="#">Стор</a>
      <a href="#">О нас</a>
    </nav>
  </header>

  <section class="hero">
    <div class="hero-bg"></div>
    <div class="overlay"></div>
    <h1 class="hero-title">Вдохновение и кино для женщин</h1>
  </section>

  <footer>
    <div class="tags">
      <span>#женщинывкино</span>
      <span>#индифильмы</span>
      <span>#фемкино</span>
      <span>#pinkculture</span>
      <span>#режиссёрки</span>
      <span>#вдохновение</span>
      <span>#нашифестивали</span>
      <span>#артхаус</span>
      <span>#сестричество</span>
      <span>#pinkreview</span>
      <span>#креативноедело</span>
      <span>#новостикино</span>
      <span>#женскаярежиссура</span>
    </div>
  </footer>

  <script>
    // Анимация появления тегов при прокрутке
    const tags = document.querySelectorAll('.tags span');
    const observer = new IntersectionObserver(entries => {
      entries.forEach(entry => {
        if(entry.isIntersecting){
          entry.target.classList.add('show');
        }
      });
    }, {threshold: 0.1});

    tags.forEach(tag => observer.observe(tag));
  </script>

</body>
</html>
