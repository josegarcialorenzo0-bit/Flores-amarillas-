<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Flores Amarillas</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      background: linear-gradient(135deg, #fffde7 0%, #fff9c4 100%);
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: hidden;
      padding: 20px;
      text-align: center;
    }

    .card {
      background: rgba(255, 255, 255, 0.9);
      padding: 40px 30px;
      border-radius: 24px;
      box-shadow: 0 10px 30px rgba(245, 127, 23, 0.2);
      backdrop-filter: blur(8px);
      max-width: 500px;
      width: 100%;
      z-index: 10;
      animation: fadeIn 1.5s ease-in-out;
    }

    h1 {
      color: #f57f17;
      font-size: 2.2rem;
      margin-bottom: 20px;
    }

    p {
      color: #5d4037;
      font-size: 1.3rem;
      line-height: 1.6;
      font-weight: 500;
    }

    /* Flores animadas flotando */
    .flower {
      position: absolute;
      font-size: 2rem;
      user-select: none;
      pointer-events: none;
      animation: floatUp linear infinite;
      z-index: 1;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(105vh) rotate(0deg) scale(0.8);
        opacity: 0;
      }
      10% {
        opacity: 1;
      }
      90% {
        opacity: 1;
      }
      100% {
        transform: translateY(-10vh) rotate(360deg) scale(1.2);
        opacity: 0;
      }
    }

    @keyframes fadeIn {
      from {
        opacity: 0;
        transform: translateY(20px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
  </style>
</head>
<body>

  <div class="card">
    <h1>🌼 Para Ti 🌼</h1>
    <p>Cada flor que ves aquí es una razón más por la que me haces sonreír.</p>
  </div>

  <script>
    const flowerIcons = ['🌼', '🌻', '✨', '💛'];
    const totalFlowers = 40;

    function createFlower() {
      const flower = document.createElement('div');
      flower.classList.add('flower');
      
      // Icono aleatorio
      flower.innerText = flowerIcons[Math.floor(Math.random() * flowerIcons.length)];
      
      // Posición horizontal
      flower.style.left = Math.random() * 100 + 'vw';
      
      // Tamaños variables
      const size = Math.random() * 1.8 + 1.2;
      flower.style.fontSize = size + 'rem';
      
      // Duración y retardo aleatorios
      const duration = Math.random() * 6 + 6;
      const delay = Math.random() * 5;
      
      flower.style.animationDuration = duration + 's';
      flower.style.animationDelay = delay + 's';

      document.body.appendChild(flower);
    }

    // Generar todas las flores
    for (let i = 0; i < totalFlowers; i++) {
      createFlower();
    }
  </script>
</body>
</html>
