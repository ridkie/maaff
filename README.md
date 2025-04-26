<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Permintaan Maaf</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin-top: 100px;
      background-color: #fce4ec;
      overflow: hidden;
    }
    #message {
      font-size: 24px;
      margin-bottom: 30px;
    }
    button {
      font-size: 20px;
      margin: 10px;
      padding: 10px 20px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: opacity 0.5s ease; /* Tambah transisi */
    }
    #forgive {
      background-color: #8bc34a;
      color: white;
    }
    #naughty {
      background-color: #f44336;
      color: white;
      position: absolute;
    }
    #response {
      margin-top: 30px;
      font-size: 24px;
    }
    img {
      margin-top: 20px;
      width: 150px;
    }
  </style>
</head>
<body>

<div id="message">Maafin aku yahh udah bikin kamu ngambek...</div>

<button id="forgive">Aku maafin deh</button>
<button id="naughty">Gak bakal</button>

<div id="response"></div>

<script>
const forgiveBtn = document.getElementById('forgive');
const naughtyBtn = document.getElementById('naughty');
const responseDiv = document.getElementById('response');
const emojis = ["😜", "😹", "🤭"];

forgiveBtn.addEventListener('click', () => {
  // Tampilkan pesan maaf dan stiker
  responseDiv.innerHTML = `Maaciw kembang sidrap yang cantik n gemesh<br> 
    <img src="https://media.giphy.com/media/12kOK9LMm6HbgI/giphy.gif" alt="Stiker Kaget Kesenangan">`;

  // Mulai animasi fade out
  naughtyBtn.style.opacity = '0';

  // Setelah animasi selesai (0.5 detik), sembunyikan tombol
  setTimeout(() => {
    naughtyBtn.style.display = 'none';
  }, 500);
});

naughtyBtn.addEventListener('click', () => {
  const randomX = Math.floor(Math.random() * (window.innerWidth - 150));
  const randomY = Math.floor(Math.random() * (window.innerHeight - 150));
  naughtyBtn.style.left = `${randomX}px`;
  naughtyBtn.style.top = `${randomY}px`;
  responseDiv.innerHTML = emojis[Math.floor(Math.random() * emojis.length)];
});
</script>

</body>
</html>
