# galeri.github.io
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Galeri Foto Proyek</title>
  <style>
    body {
      font-family: "Segoe UI", sans-serif;
      background-color: #f4f4f4;
      margin: 0;
      padding: 20px;
    }

    h1 {
      text-align: center;
      color: #333;
      margin-bottom: 30px;
    }

    .gallery {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 15px;
    }

    .gallery img {
      width: 100%;
      border-radius: 10px;
      cursor: pointer;
      transition: transform 0.3s, box-shadow 0.3s;
    }

    .gallery img:hover {
      transform: scale(1.05);
      box-shadow: 0 4px 15px rgba(0,0,0,0.2);
    }

    /* Popup lightbox */
    .lightbox {
      display: none;
      position: fixed;
      z-index: 100;
      padding-top: 60px;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      overflow: auto;
      background-color: rgba(0,0,0,0.9);
    }

    .lightbox img {
      margin: auto;
      display: block;
      max-width: 90%;
      max-height: 80vh;
      border-radius: 10px;
    }

    .close {
      position: absolute;
      top: 20px;
      right: 35px;
      color: #fff;
      font-size: 40px;
      font-weight: bold;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <h1>Galeri Foto Proyek Rumah Kayu</h1>

  <div class="gallery">
    <img src="img1.jpg" alt="Foto 1">
    <img src="img2.jpg" alt="Foto 2">
    <img src="img3.jpg" alt="Foto 3">
    <img src="img4.jpg" alt="Foto 4">
  </div>

  <!-- Lightbox -->
  <div id="lightbox" class="lightbox">
    <span class="close">&times;</span>
    <img id="lightbox-img">
  </div>

  <script>
    const images = document.querySelectorAll('.gallery img');
    const lightbox = document.getElementById('lightbox');
    const lightboxImg = document.getElementById('lightbox-img');
    const closeBtn = document.querySelector('.close');

    images.forEach(img => {
      img.addEventListener('click', () => {
        lightbox.style.display = 'block';
        lightboxImg.src = img.src;
      });
    });

    closeBtn.addEventListener('click', () => {
      lightbox.style.display = 'none';
    });

    lightbox.addEventListener('click', (e) => {
      if (e.target === lightbox) lightbox.style.display = 'none';
    });
  </script>

</body>
</html>
