<!DOCTYPE html>
<html>
<head>
<title>¿Quieres ser mi San Valentín?</title>
<style>
  body {
    font-family: sans-serif;
    text-align: center;
    background-color: #f0f0f0; /* Color de fondo */
  }
  #pregunta {
    font-size: 2em;
    margin-bottom: 20px;
  }
  button {
    padding: 10px 20px;
    font-size: 1.2em;
    margin: 0 10px;
    cursor: pointer;
  }
  #video {
    display: none;
    margin-top: 20px;
  }
  #no {
    position: absolute;
  }
</style>
</head>
<body>

<h1 id="pregunta">¿QUIERES SER MI SAN VALENTÍN???</h1>

<button id="si">Sí</button>
<button id="no">No</button>

<div id="video">
  <video id="miVideo" width="400" controls>
    Tu navegador no soporta la reproducción de videos.
  </video>
</div>

<script>
  const siBtn = document.getElementById('si');
  const noBtn = document.getElementById('no');
  const videoDiv = document.getElementById('video');
  const miVideo = document.getElementById('miVideo');
  const pregunta = document.getElementById('pregunta');

  siBtn.addEventListener('click', () => {
    mostrarVideo('video_si.mp4'); // Reemplaza con la ruta de tu video
  });

  noBtn.addEventListener('click', () => {
    mostrarVideo('video_no.mp4'); // Reemplaza con la ruta de tu video
    cambiarPosicionNo();
  });

  function mostrarVideo(rutaVideo) {
    pregunta.style.display = 'none';
    siBtn.style.display = 'none';
    noBtn.style.display = 'none';
    videoDiv.style.display = 'block';
    miVideo.src = rutaVideo;
    miVideo.play();
  }

  function cambiarPosicionNo() {
    const maxX = window.innerWidth - noBtn.offsetWidth;
    const maxY = window.innerHeight - noBtn.offsetHeight;

    const randomX = Math.floor(Math.random() * maxX);
    const randomY = Math.floor(Math.random() * maxY);

    noBtn.style.left = randomX + 'px';
    noBtn.style.top = randomY + 'px';
  }

  miVideo.addEventListener('ended', () => {
    location.reload(); // Recarga la página al finalizar el video
  });

  cambiarPosicionNo(); // Cambia la posición del botón "No" al cargar la página
</script>

</body>
</html>
