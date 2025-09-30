# Ramo-Hot-wheels
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Ramo de Carritos</title>
  <style>
    body {
      margin: 0;
      font-family: "Comic Sans MS", cursive, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      overflow: hidden;
      background: linear-gradient(135deg, #94dbff, #ffe7a9);
      position: relative;
    }

    /* Corazones de fondo */
    .corazon {
      position: absolute;
      font-size: 20px;
      color: #ff4f7a;
      animation: subir 4s linear infinite;
      opacity: 0;
    }

    @keyframes subir {
      0% {transform: translateY(100vh) scale(0.5); opacity:0;}
      50% {opacity:1;}
      100% {transform: translateY(-50px) scale(1); opacity:0;}
    }

    .inicio, .ramo {
      text-align: center;
      z-index: 2;
    }

    .inicio h1 {
      font-size: 2.5rem;
      color: #333;
    }

    .btn {
      background: #ff6f91;
      color: white;
      padding: 15px 30px;
      border: none;
      border-radius: 20px;
      font-size: 1.2rem;
      cursor: pointer;
      box-shadow: 0px 5px 10px rgba(0,0,0,0.2);
      transition: transform 0.2s ease, background 0.3s ease;
    }

    .btn:hover {
      transform: scale(1.1);
      background: #ff4f7a;
    }

    .ramo {
      display: none;
      flex-direction: column;
      align-items: center;
      animation: aparecer 1s ease forwards;
    }

    .ramo h2 {
      margin-top: 20px;
      font-size: 2rem;
      color: #444;
    }

    .carritos {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 15px;
      margin-top: 20px;
    }

    .carrito {
      width: 80px;
      height: 50px;
      background: linear-gradient(135deg, #ffcc00, #ff6f91);
      border-radius: 10px;
      position: relative;
      box-shadow: 0px 5px 8px rgba(0,0,0,0.2);
      animation: saltar 1s infinite alternate;
    }

    .carrito::before, .carrito::after {
      content: "";
      width: 20px;
      height: 20px;
      background: #333;
      border-radius: 50%;
      position: absolute;
      bottom: -10px;
    }

    .carrito::before { left: 5px; }
    .carrito::after { right: 5px; }

    @keyframes aparecer {
      from {opacity: 0; transform: scale(0.7);}
      to {opacity: 1; transform: scale(1);}
    }

    @keyframes saltar {
      from {transform: translateY(0);}
      to {transform: translateY(-10px);}
    }
  </style>
</head>
<body>

  <!-- Corazones animados -->
  <div id="corazones"></div>

  <div class="inicio" id="inicio">
    <h1> Bienvenido</h1>
    <button class="btn" onclick="mostrarRamo()">💗</button>
  </div>

  <div class="ramo" id="ramo">
    <div class="carritos">
      <div class="carrito"></div>
      <div class="carrito"></div>
      <div class="carrito"></div>
      <div class="carrito"></div>
      <div class="carrito"></div>
    </div>
    <h2>Para ti Emilio </h2>
    <h2>Te quiero..</h2>
    <h3>(son carritos)</h3>
  </div>

  <script>
    function mostrarRamo() {
      document.getElementById("inicio").style.display = "none";
      document.getElementById("ramo").style.display = "flex";

      // Reproducir música al mostrar el ramo
      const musica = document.getElementById("musica");
      musica.play("https://youtu.be/sXCPwNpuulY?si=U4q3C2zh73j9TAtB");
    }

    // Función para generar corazones
    function crearCorazon() {
      const corazon = document.createElement('div');
      corazon.classList.add('corazon');
      corazon.style.left = Math.random() * 100 + 'vw';
      corazon.style.fontSize = (Math.random() * 20 + 10) + 'px';
      corazon.textContent = '💖';
      document.body.appendChild(corazon);

      setTimeout(() => {
        corazon.remove();
      }, 4000);
    }

    // Generar corazones cada 300ms
    setInterval(crearCorazon, 300);
  </script>
</body>
</html>
