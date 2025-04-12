# dpzktxf.github.io
<!DOCTYPE html><html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Undangan Pernikahan</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500;700&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      font-family: 'Playfair Display', serif;
      background-color: #fff;
      color: #4a1c1c;
    }
    header {
      background-color: #800000;
      color: white;
      text-align: center;
      padding: 2rem 1rem;
    }
    .section {
      padding: 2rem 1rem;
      text-align: center;
    }
    .section h2 {
      color: #800000;
    }
    .countdown {
      font-size: 1.5rem;
      margin-top: 1rem;
    }
    iframe {
      width: 100%;
      height: 300px;
      border: none;
    }
    .rsvp, .gift, .ucapan {
      max-width: 500px;
      margin: auto;
      text-align: left;
    }
    input, textarea, button {
      width: 100%;
      padding: 0.5rem;
      margin-top: 0.5rem;
      font-family: inherit;
      font-size: 1rem;
    }
    button {
      background-color: #800000;
      color: white;
      border: none;
      cursor: pointer;
    }
    .daftar-ucapan {
      max-width: 500px;
      margin: 2rem auto;
      background-color: #f9f9f9;
      padding: 1rem;
      border: 1px solid #ccc;
      border-radius: 8px;
    }
    .ucapan-item {
      border-bottom: 1px solid #ddd;
      padding: 0.5rem 0;
    }
    .ucapan-item:last-child {
      border-bottom: none;
    }
  </style>
</head>
<body>
  <header>
    <h1>Undangan Pernikahan</h1>
    <p>Minggu, 28 Desember 2025</p>
  </header>  <section class="section">
    <h2>Akad Nikah</h2>
    <p>08.00 WIB - 11.30 WIB</p>
    <h2>Resepsi</h2>
    <p>13.30 WIB - 17.30 WIB</p>
  </section>  <section class="section">
    <h2>Hitung Mundur</h2>
    <div id="countdown" class="countdown"></div>
  </section>  <section class="section">
    <h2>Putar Musik</h2>
    <audio controls autoplay loop>
      <source src="musik-kamu.mp3" type="audio/mpeg">
      Browser kamu tidak mendukung audio.
    </audio>
  </section>  <section class="section">
    <h2>Lokasi Acara</h2>
    <iframe src="https://www.google.com/maps/embed?pb=!1m18!...">Loading Map...</iframe>
  </section>  <section class="section rsvp">
    <h2>Konfirmasi Kehadiran (RSVP)</h2>
    <form>
      <label>Nama:</label>
      <input type="text" name="nama" required />
      <label>Jumlah Tamu:</label>
      <input type="number" name="jumlah" required />
      <label>Ucapan:</label>
      <textarea name="pesan"></textarea>
      <button type="submit">Kirim</button>
    </form>
  </section>  <section class="section ucapan">
    <h2>Ucapan untuk Mempelai</h2>
    <form id="formUcapan">
      <label>Nama:</label>
      <input type="text" name="nama_ucapan" required />
      <label>Ucapan:</label>
      <textarea name="isi_ucapan" required></textarea>
      <button type="submit">Kirim Ucapan</button>
    </form>
  </section>  <section class="section daftar-ucapan">
    <h2>Daftar Ucapan</h2>
    <div id="listUcapan"></div>
  </section>  <section class="section gift">
    <h2>Kirim Hadiah</h2>
    <p>Transfer ke rekening berikut:</p>
    <p><strong>Bank ABC</strong><br>No. Rekening: 1234567890<br>Atas Nama: Nama Mempelai</p>
  </section>  <script>
    const targetDate = new Date("2025-12-28T08:00:00").getTime();
    const countdown = document.getElementById("countdown");

    setInterval(() => {
      const now = new Date().getTime();
      const distance = targetDate - now;

      const days = Math.floor(distance / (1000 * 60 * 60 * 24));
      const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((distance % (1000 * 60)) / 1000);

      countdown.innerHTML = `${days} Hari ${hours} Jam ${minutes} Menit ${seconds} Detik`;
    }, 1000);

    const formUcapan = document.getElementById('formUcapan');
    const listUcapan = document.getElementById('listUcapan');

    formUcapan.addEventListener('submit', function(e) {
      e.preventDefault();
      const nama = formUcapan.nama_ucapan.value.trim();
      const isi = formUcapan.isi_ucapan.value.trim();
      if(nama && isi) {
        const item = document.createElement('div');
        item.className = 'ucapan-item';
        item.innerHTML = `<strong>${nama}</strong><br>${isi}`;
        listUcapan.prepend(item);
        formUcapan.reset();
      }
    });
  </script></body>
</html>