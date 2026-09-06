Ini adalah kode HTML untuk website portfolio personal Della Aurellia yang modern, minimalis, dan responsif. Kode ini menggabungkan Tailwind CSS untuk tata letak, JavaScript untuk interaktivitas, dan menyajikan semua bagian yang Anda minta dalam satu file siap pakai.
```html
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.5" />
  <meta name="description" content="Portfolio personal Della Aurellia - Pelajar aktif, kreatif, dan berjiwa juang." />
  <title>Della Aurellia · Portfolio</title>
  <!-- Tailwind via CDN (ringan & cepat) -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Google Font (inter & fallback) -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700&display=swap" rel="stylesheet" />
  <!-- Font Awesome 6 (gratis) untuk ikon -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
  <style>
    * { font-family: 'Inter', sans-serif; scroll-behavior: smooth; }
    body { background: #fefcf7; } /* cream base */
    .bg-cream { background-color: #fef8f0; }
    .bg-soft-pink { background-color: #ffe8ec; }
    .text-pink-modern { color: #d44c6e; }
    .border-pink-modern { border-color: #d44c6e; }
    .btn-pink { background: #d44c6e; color: white; transition: all 0.2s; }
    .btn-pink:hover { background: #b83c5a; transform: scale(1.02); }
    .nav-sticky { background: rgba(255, 252, 247, 0.92); backdrop-filter: blur(8px); box-shadow: 0 4px 20px rgba(0,0,0,0.02); }
    .card-hover { transition: 0.25s ease; }
    .card-hover:hover { transform: translateY(-6px); box-shadow: 0 20px 30px -12px rgba(212, 76, 110, 0.15); }
    .testimoni-slider { transition: opacity 0.4s ease; }
    .grid-photo img { transition: 0.2s; cursor: pointer; }
    .grid-photo img:hover { transform: scale(1.01); box-shadow: 0 8px 24px rgba(0,0,0,0.05); }
    .zoom-active { transform: scale(1.02); transition: 0.2s; }
    .active-tab { border-bottom: 3px solid #d44c6e; color: #1e1e1e; font-weight: 600; }
    .tab-btn { padding: 0.5rem 0.25rem; border-bottom: 3px solid transparent; transition: 0.15s; font-weight: 500; }
    .tab-btn:hover { border-bottom-color: #d44c6e40; }
    .section { scroll-margin-top: 80px; }
    @media (max-width: 640px) { .grid-photo { grid-template-columns: repeat(2, 1fr); } }
  </style>
</head>
<body class="text-gray-800 antialiased bg-cream">

<!-- NAVIGASI STICKY -->
<nav id="navbar" class="fixed top-0 left-0 w-full z-50 transition-all duration-300 bg-white/80 backdrop-blur-md shadow-sm">
  <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex items-center justify-between h-16">
      <div class="flex items-center gap-2">
        <span class="text-xl font-bold text-pink-modern">Della</span>
        <span class="text-sm font-light text-gray-500 hidden sm:inline">· portfolio</span>
      </div>
      <!-- menu desktop -->
      <div class="hidden md:flex space-x-1 text-sm font-medium">
        <a href="#beranda" class="tab-btn px-2 py-1 active-tab" data-tab="beranda">Beranda</a>
        <a href="#tentang" class="tab-btn px-2 py-1" data-tab="tentang">Tentang</a>
        <a href="#cv" class="tab-btn px-2 py-1" data-tab="cv">CV</a>
        <a href="#karya" class="tab-btn px-2 py-1" data-tab="karya">Karya</a>
        <a href="#foto" class="tab-btn px-2 py-1" data-tab="foto">Foto</a>
        <a href="#artikel" class="tab-btn px-2 py-1" data-tab="artikel">Artikel</a>
        <a href="#sosial" class="tab-btn px-2 py-1" data-tab="sosial">Sosial</a>
        <a href="#kontak" class="tab-btn px-2 py-1" data-tab="kontak">Kontak</a>
        <a href="#testimoni" class="tab-btn px-2 py-1" data-tab="testimoni">Testimoni</a>
      </div>
      <!-- mobile hamburger -->
      <div class="md:hidden flex items-center">
        <button id="menuBtn" class="text-gray-700 focus:outline-none text-xl"><i class="fas fa-bars"></i></button>
      </div>
    </div>
    <!-- mobile menu -->
    <div id="mobileMenu" class="md:hidden hidden flex-col pb-4 space-y-2 text-sm border-t border-gray-100 mt-1 pt-2">
      <a href="#beranda" class="tab-mobile py-1 px-2 active-mobile" data-tab="beranda">Beranda</a>
      <a href="#tentang" class="tab-mobile py-1 px-2" data-tab="tentang">Tentang</a>
      <a href="#cv" class="tab-mobile py-1 px-2" data-tab="cv">CV</a>
      <a href="#karya" class="tab-mobile py-1 px-2" data-tab="karya">Karya</a>
      <a href="#foto" class="tab-mobile py-1 px-2" data-tab="foto">Foto</a>
      <a href="#artikel" class="tab-mobile py-1 px-2" data-tab="artikel">Artikel</a>
      <a href="#sosial" class="tab-mobile py-1 px-2" data-tab="sosial">Sosial</a>
      <a href="#kontak" class="tab-mobile py-1 px-2" data-tab="kontak">Kontak</a>
      <a href="#testimoni" class="tab-mobile py-1 px-2" data-tab="testimoni">Testimoni</a>
    </div>
  </div>
</nav>

<!-- KONTEN UTAMA -->
<main class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 pt-24 pb-10">

  <!-- 1. BERANDA -->
  <section id="beranda" class="section flex flex-col md:flex-row items-center gap-8 md:gap-12 py-8 md:py-12">
    <div class="flex-1 order-2 md:order-1">
      <div class="inline-block bg-soft-pink text-pink-modern text-sm font-semibold px-4 py-1 rounded-full mb-3">✨ #SemangatPelajar</div>
      <h1 class="text-4xl sm:text-5xl font-bold leading-tight">Della Aurellia</h1>
      <p class="text-xl text-gray-600 mt-1 font-light">Pelajar · Aktif & Berjiwa Juang</p>
      <p class="text-gray-500 mt-3 max-w-md">Membangun mimpi lewat kode, desain, dan foto. Siap belajar dan berkarya.</p>
      <div class="flex flex-wrap gap-3 mt-6">
        <a href="#karya" class="btn-pink px-6 py-2.5 rounded-full text-sm font-semibold shadow-sm"><i class="far fa-eye mr-2"></i>Lihat Karya</a>
        <a href="#kontak" class="border border-pink-modern text-pink-modern px-6 py-2.5 rounded-full text-sm font-semibold hover:bg-pink-50 transition"><i class="far fa-paper-plane mr-2"></i>Hubungi Saya</a>
      </div>
    </div>
    <div class="flex-1 order-1 md:order-2 flex justify-center">
      <div class="w-52 h-52 md:w-64 md:h-64 rounded-full overflow-hidden border-4 border-white shadow-xl bg-soft-pink flex items-center justify-center">
        <!-- foto profil placeholder (ikon) -->
        <i class="fas fa-user-circle text-8xl text-pink-modern/60"></i>
      </div>
    </div>
  </section>

  <!-- 2. TENTANG -->
  <section id="tentang" class="section bg-white/60 rounded-3xl p-6 md:p-10 my-12 shadow-sm">
    <h2 class="text-2xl font-bold text-pink-modern flex items-center gap-2"><i class="fas fa-user-astronaut"></i> Tentang Saya</h2>
    <div class="grid md:grid-cols-5 gap-6 mt-4">
      <div class="md:col-span-3 space-y-3">
        <p class="text-gray-700 leading-relaxed">Halo! Saya <strong>Della Aurellia</strong>, seorang pelajar di <strong>SMKN 42 Jakarta</strong> dengan semangat juang tinggi dan mental tangguh. Saya aktif dalam berbagai kegiatan, suka memecahkan masalah, dan percaya bahwa kerja keras serta konsistensi adalah kunci.</p>
        <p class="text-gray-700 leading-relaxed">Saya memiliki ketertarikan di dunia teknologi, desain, dan visual storytelling. Saat ini saya terus mengasah kemampuan di bidang pengembangan web dan desain grafis.</p>
        <div class="flex flex-wrap gap-3 pt-2">
          <span class="bg-soft-pink text-pink-modern px-4 py-1 rounded-full text-sm">💻 Web Dev</span>
          <span class="bg-soft-pink text-pink-modern px-4 py-1 rounded-full text-sm">🎨 Desain</span>
          <span class="bg-soft-pink text-pink-modern px-4 py-1 rounded-full text-sm">📸 Fotografi</span>
          <span class="bg-soft-pink text-pink-modern px-4 py-1 rounded-full text-sm">⚡ Berjiwa Juang</span>
        </div>
      </div>
      <div class="md:col-span-2 flex items-center justify-center bg-soft-pink/40 rounded-2xl p-4">
        <div class="w-full h-36 md:h-44 rounded-xl bg-white/60 flex items-center justify-center text-pink-modern/40"><i class="fas fa-image text-6xl"></i></div>
      </div>
    </div>
  </section>

  <!-- 3. CV (timeline) -->
  <section id="cv" class="section my-12">
    <h2 class="text-2xl font-bold text-pink-modern flex items-center gap-2"><i class="fas fa-graduation-cap"></i> CV · Pendidikan</h2>
    <div class="mt-4 bg-white/70 rounded-2xl p-6 shadow-sm border-l-4 border-pink-modern">
      <div class="flex flex-col md:flex-row gap-6 items-start">
        <div class="md:w-1/3">
          <span class="bg-soft-pink text-pink-modern font-semibold px-3 py-1 rounded-full text-sm">2023 - sekarang</span>
          <h3 class="text-xl font-bold mt-2">SMKN 42 Jakarta</h3>
          <p class="text-gray-600">Jurusan Pengembangan Perangkat Lunak & Game</p>
        </div>
        <div class="md:w-2/3 border-l-2 border-pink-modern/30 pl-4 md:pl-6 space-y-2">
          <p><span class="font-semibold">Pelajar aktif</span> · Berprestasi di bidang desain dan pengembangan web.</p>
          <p><span class="font-semibold">Berjiwa juang & tangguh</span> · Menyukai tantangan dan selalu berusaha memberikan yang terbaik.</p>
          <p class="text-sm text-gray-500"><i class="far fa-calendar-alt mr-1"></i> 2026 · terus berkembang</p>
        </div>
      </div>
    </div>
  </section>

  <!-- 4. KARYA (galeri project) -->
  <section id="karya" class="section my-12">
    <h2 class="text-2xl font-bold text-pink-modern flex items-center gap-2"><i class="fas fa-th-large"></i> Hasil Karya</h2>
    <div class="flex gap-3 mt-3 flex-wrap">
      <button class="filter-btn px-4 py-1 rounded-full border border-pink-modern text-pink-modern text-sm font-medium hover:bg-pink-50 active:bg-soft-pink" data-filter="semua">Semua</button>
      <button class="filter-btn px-4 py-1 rounded-full border border-pink-modern text-pink-modern text-sm font-medium hover:bg-pink-50" data-filter="web">Web</button>
      <button class="filter-btn px-4 py-1 rounded-full border border-pink-modern text-pink-modern text-sm font-medium hover:bg-pink-50" data-filter="desain">Desain</button>
      <button class="filter-btn px-4 py-1 rounded-full border border-pink-modern text-pink-modern text-sm font-medium hover:bg-pink-50" data-filter="foto">Foto</button>
    </div>
    <div id="karyaGrid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 mt-5">
      <!-- item akan diisi JS -->
    </div>
  </section>

  <!-- 5. FOTO (grid 3 kolom) -->
  <section id="foto" class="section my-12">
    <h2 class="text-2xl font-bold text-pink-modern flex items-center gap-2"><i class="fas fa-camera"></i> Galeri Foto</h2>
    <div class="grid grid-cols-2 sm:grid-cols-3 gap-4 mt-4 grid-photo">
      <div class="bg-white rounded-xl overflow-hidden shadow-sm"><img src="https://picsum.photos/seed/della1/400/300" alt="foto 1" class="w-full h-48 object-cover" /></div>
      <div class="bg-white rounded-xl overflow-hidden shadow-sm"><img src="https://picsum.photos/seed/della2/400/300" alt="foto 2" class="w-full h-48 object-cover" /></div>
      <div class="bg-white rounded-xl overflow-hidden shadow-sm"><img src="https://picsum.photos/seed/della3/400/300" alt="foto 3" class="w-full h-48 object-cover" /></div>
      <div class="bg-white rounded-xl overflow-hidden shadow-sm"><img src="https://picsum.photos/seed/della4/400/300" alt="foto 4" class="w-full h-48 object-cover" /></div>
      <div class="bg-white rounded-xl overflow-hidden shadow-sm"><img src="https://picsum.photos/seed/della5/400/300" alt="foto 5" class="w-full h-48 object-cover" /></div>
      <div class="bg-white rounded-xl overflow-hidden shadow-sm"><img src="https://picsum.photos/seed/della6/400/300" alt="foto 6" class="w-full h-48 object-cover" /></div>
    </div>
    <p class="text-xs text-gray-400 mt-2 text-center italic">Klik foto untuk zoom (efek)</p>
  </section>

  <!-- 6. ARTIKEL -->
  <section id="artikel" class="section my-12">
    <h2 class="text-2xl font-bold text-pink-modern flex items-center gap-2"><i class="fas fa-newspaper"></i> Artikel Terbaru</h2>
    <div class="grid md:grid-cols-3 gap-6 mt-4">
      <div class="bg-white rounded-2xl shadow-sm p-5 card-hover"><span class="text-xs text-pink-modern bg-soft-pink px-2 py-0.5 rounded-full">12 Jan 2026</span><h3 class="font-bold text-lg mt-2">Belajar Koding dari Nol</h3><p class="text-gray-500 text-sm">Pengalaman pertama menulis baris kode dan semangat untuk terus belajar.</p><a href="#" class="text-pink-modern text-sm font-semibold inline-block mt-3">Baca Selengkapnya →</a></div>
      <div class="bg-white rounded-2xl shadow-sm p-5 card-hover"><span class="text-xs text-pink-modern bg-soft-pink px-2 py-0.5 rounded-full">8 Jan 2026</span><h3 class="font-bold text-lg mt-2">Desain Visual untuk Pemula</h3><p class="text-gray-500 text-sm">Tip sederhana memulai desain grafis dengan tools gratis.</p><a href="#" class="text-pink-modern text-sm font-semibold inline-block mt-3">Baca Selengkapnya →</a></div>
      <div class="bg-white rounded-2xl shadow-sm p-5 card-hover"><span class="text-xs text-pink-modern bg-soft-pink px-2 py-0.5 rounded-full">3 Jan 2026</span><h3 class="font-bold text-lg mt-2">Fotografi & Komposisi</h3><p class="text-gray-500 text-sm">Menangkap momen dengan komposisi yang menarik dan natural.</p><a href="#" class="text-pink-modern text-sm font-semibold inline-block mt-3">Baca Selengkapnya →</a></div>
    </div>
  </section>

  <!-- 7. SOSIAL MEDIA -->
  <section id="sosial" class="section my-12 bg-white/70 rounded-2xl p-6 text-center">
    <h2 class="text-2xl font-bold text-pink-modern flex items-center justify-center gap-2"><i class="fas fa-share-alt"></i> Media Sosial</h2>
    <div class="flex justify-center gap-8 text-3xl mt-4">
      <a href="#" class="text-pink-modern/70 hover:text-pink-modern transition"><i class="fab fa-instagram"></i> <span class="text-sm font-medium block -mt-1">bbvterfliee._</span></a>
      <a href="#" class="text-pink-modern/70 hover:text-pink-modern transition"><i class="fab fa-twitter"></i> <span class="text-sm font-medium block -mt-1">oreL</span></a>
      <a href="#" class="text-pink-modern/70 hover:text-pink-modern transition"><i class="fab fa-youtube"></i> <span class="text-sm font-medium block -mt-1">Urell</span></a>
    </div>
  </section>

  <!-- 8. KONTAK + MAPS -->
  <section id="kontak" class="section my-12 grid md:grid-cols-2 gap-8 bg-white/60 rounded-3xl p-6 md:p-8">
    <div>
      <h2 class="text-2xl font-bold text-pink-modern flex items-center gap-2"><i class="fas fa-envelope"></i> Kontak</h2>
      <form class="space-y-4 mt-4">
        <input type="text" placeholder="Nama" class="w-full border border-gray-200 rounded-xl px-4 py-3 focus:ring-2 focus:ring-pink-modern/20 outline-none" />
        <input type="email" placeholder="Email" class="w-full border border-gray-200 rounded-xl px-4 py-3 focus:ring-2 focus:ring-pink-modern/20 outline-none" />
        <textarea rows="4" placeholder="Pesan" class="w-full border border-gray-200 rounded-xl px-4 py-3 focus:ring-2 focus:ring-pink-modern/20 outline-none"></textarea>
        <button type="submit" class="btn-pink w-full rounded-xl py-3 font-semibold"><i class="far fa-paper-plane mr-2"></i>Kirim Pesan</button>
      </form>
      <div class="mt-4 text-sm space-y-1 text-gray-600"><p><i class="fas fa-map-pin text-pink-modern w-5"></i> Jl. Kapuk Rawa Gabus RT.008/RW.011</p><p><i class="fas fa-envelope text-pink-modern w-5"></i> dellaaurellia878@gmail.com</p><p><i class="fas fa-phone text-pink-modern w-5"></i> 0857-0998-0651</p></div>
    </div>
    <div class="rounded-xl overflow-hidden h-64 md:h-auto bg-gray-100">
      <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3966.521!2d106.768!3d-6.150!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2e69f5c2b1e5d8f7%3A0x9c3b7e8b5a4d2c1f!2sJakarta!5e0!3m2!1sid!2sid!4v1647867345678" width="100%" height="100%" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
    </div>
  </section>

  <!-- 9. TESTIMONI slider -->
  <section id="testimoni" class="section my-12 bg-white/50 rounded-3xl p-6 text-center">
    <h2 class="text-2xl font-bold text-pink-modern flex items-center justify-center gap-2"><i class="fas fa-quote-right"></i> Testimoni</h2>
    <div id="testimoniContainer" class="relative max-w-2xl mx-auto mt-5 min-h-[180px]">
      <div id="testimoniSlide" class="testimoni-slider bg-white rounded-2xl shadow p-6">
        <!-- diisi JS -->
      </div>
      <div class="flex justify-center gap-3 mt-4">
        <button id="prevTesti" class="bg-soft-pink text-pink-modern px-4 py-1 rounded-full text-sm"><i class="fas fa-chevron-left"></i></button>
        <button id="nextTesti" class="bg-soft-pink text-pink-modern px-4 py-1 rounded-full text-sm"><i class="fas fa-chevron-right"></i></button>
      </div>
    </div>
  </section>

</main>

<!-- FOOTER -->
<footer class="border-t border-gray-200/60 bg-white/70 text-center text-sm text-gray-500 py-6 mt-6">
  <p>© 2026 Della Aurellia · Dibuat dengan <i class="fas fa-heart text-pink-modern"></i> & semangat</p>
</footer>

<script>
  (function() {
    // ---- data ----
    const karyaData = [
      { title: 'Portfolio Web', category: 'web', desc: 'Website portfolio personal dengan Tailwind' },
      { title: 'Desain Poster', category: 'desain', desc: 'Poster kreatif untuk event sekolah' },
      { title: 'Foto Makro', category: 'foto', desc: 'Detail bunga dengan cahaya alami' },
      { title: 'Aplikasi Kasir', category: 'web', desc: 'Web kasir sederhana berbasis JS' },
      { title: 'Logo Brand', category: 'desain', desc: 'Identitas visual untuk UMKM lokal' },
      { title: 'Potret Malam', category: 'foto', desc: 'Long exposure di kota' },
    ];

    const testimoniData = [
      { name: 'Rina S.', job: 'Guru', comment: 'Della siswa yang sangat tangguh dan kreatif. Karya-karyanya selalu mengesankan!', img: '👩‍🏫' },
      { name: 'Budi P.', job: 'Klien', comment: 'Kerja sama dengan Della sangat menyenangkan. Hasil desainnya melebihi ekspektasi.', img: '👨‍💼' },
      { name: 'Siti M.', job: 'Teman', comment: 'Della selalu penuh semangat dan menginspirasi. Pantang menyerah!', img: '👩‍🎓' },
    ];

    // ---- render karya ----
    const grid = document.getElementById('karyaGrid');
    function renderKarya(filter = 'semua') {
      const filtered = filter === 'semua' ? karyaData : karyaData.filter(k => k.category === filter);
      grid.innerHTML = filtered.map((k, idx) => `
        <div class="bg-white rounded-2xl shadow-sm p-4 card-hover border border-gray-50">
          <div class="h-32 bg-soft-pink/40 rounded-xl flex items-center justify-center text-4xl text-pink-modern/30"><i class="fas fa-${k.category === 'web' ? 'code' : k.category === 'desain' ? 'paint-brush' : 'camera'}"></i></div>
          <h3 class="font-bold text-lg mt-3">${k.title}</h3>
          <p class="text-sm text-gray-500">${k.desc}</p>
          <span class="inline-block mt-2 text-xs bg-soft-pink text-pink-modern px-2 py-0.5 rounded-full">${k.category}</span>
        </div>
      `).join('');
    }
    renderKarya('semua');
    document.querySelectorAll('.filter-btn').forEach(btn => {
      btn.addEventListener('click', function() {
        document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('bg-soft-pink', 'border-pink-modern'));
        this.classList.add('bg-soft-pink', 'border-pink-modern');
        renderKarya(this.dataset.filter);
      });
    });
    // default active
    document.querySelector('.filter-btn[data-filter="semua"]')?.classList.add('bg-soft-pink', 'border-pink-modern');

    // ---- testimoni slider ----
    let testiIdx = 0;
    const slideEl = document.getElementById('testimoniSlide');
    function renderTesti(index) {
      const t = testimoniData[index % testimoniData.length];
      slideEl.innerHTML = `
        <div class="flex items-center gap-4 flex-col sm:flex-row">
          <div class="text-5xl">${t.img}</div>
          <div class="text-left"><p class="font-semibold text-lg">${t.name}</p><p class="text-sm text-pink-modern">${t.job}</p><p class="text-gray-600 italic mt-1">"${t.comment}"</p></div>
        </div>
      `;
    }
    renderTesti(0);
    document.getElementById('prevTesti').addEventListener('click', () => { testiIdx = (testiIdx - 1 + testimoniData.length) % testimoniData.length; renderTesti(testiIdx); });
    document.getElementById('nextTesti').addEventListener('click', () => { testiIdx = (testiIdx + 1) % testimoniData.length; renderTesti(testiIdx); });

    // ---- foto zoom (klik) ----
    document.querySelectorAll('.grid-photo img').forEach(img => {
      img.addEventListener('click', function() {
        this.classList.toggle('zoom-active');
        if (this.classList.contains('zoom-active')) {
          this.style.transform = 'scale(1.04)';
          this.style.boxShadow = '0 12px 32px rgba(212,76,110,0.15)';
        } else {
          this.style.transform = 'scale(1)';
          this.style.boxShadow = 'none';
        }
      });
    });

    // ---- navbar sticky & tab active ----
    const navbar = document.getElementById('navbar');
    const sections = document.querySelectorAll('.section');
    const tabBtns = document.querySelectorAll('.tab-btn');
    const mobileBtns = document.querySelectorAll('.tab-mobile');

    function updateActiveTab(id) {
      tabBtns.forEach(b => b.classList.remove('active-tab'));
      mobileBtns.forEach(b => b.classList.remove('active-mobile', 'text-pink-modern'));
      tabBtns.forEach(b => { if (b.dataset.tab === id) b.classList.add('active-tab'); });
      mobileBtns.forEach(b => { if (b.dataset.tab === id) { b.classList.add('active-mobile', 'text-pink-modern'); } });
    }

    window.addEventListener('scroll', () => {
      // sticky effect
      if (window.scrollY > 20) navbar.classList.add('nav-sticky');
      else navbar.classList.remove('nav-sticky');
      // active section
      let current = 'beranda';
      sections.forEach(sec => {
        const rect = sec.getBoundingClientRect();
        if (rect.top <= 120) current = sec.id;
      });
      updateActiveTab(current);
    });

    // ---- mobile menu toggle ----
    document.getElementById('menuBtn').addEventListener('click', function() {
      document.getElementById('mobileMenu').classList.toggle('hidden');
    });
    // close mobile on click link
    document.querySelectorAll('.tab-mobile').forEach(link => {
      link.addEventListener('click', function(e) {
        document.getElementById('mobileMenu').classList.add('hidden');
        const id = this.dataset.tab;
        updateActiveTab(id);
      });
    });

    // ---- tab click smooth ----
    document.querySelectorAll('.tab-btn, .tab-mobile').forEach(link => {
      link.addEventListener('click', function(e) {
        const target = document.getElementById(this.dataset.tab);
        if (target) target.scrollIntoView({ behavior: 'smooth' });
      });
    });

    // ---- seo friendly : add hidden h1 for robots? already have h1 ----
    console.log('✨ Portfolio Della Aurellia siap!');
  })();
</script>
</body>
</html>
```
