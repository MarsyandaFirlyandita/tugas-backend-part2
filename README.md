<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>README — Web Portofolio Marsyanda</title>
  <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet" />
  <style>
    :root {
      --bg: #0d0d0d;
      --surface: #161616;
      --border: #2a2a2a;
      --accent: #c8f04f;
      --accent2: #7b61ff;
      --text: #e8e8e8;
      --muted: #888;
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'DM Sans', sans-serif;
      font-size: 15px;
      line-height: 1.7;
      min-height: 100vh;
    }

    /* HERO */
    .hero {
      border-bottom: 1px solid var(--border);
      padding: 60px 0 40px;
      position: relative;
      overflow: hidden;
    }
    .hero::before {
      content: '';
      position: absolute;
      top: -80px; right: -80px;
      width: 350px; height: 350px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(123,97,255,0.15), transparent 70%);
      pointer-events: none;
    }
    .hero::after {
      content: '';
      position: absolute;
      bottom: -60px; left: 10%;
      width: 250px; height: 250px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(200,240,79,0.08), transparent 70%);
      pointer-events: none;
    }

    .container {
      max-width: 780px;
      margin: 0 auto;
      padding: 0 32px;
    }

    .badge {
      display: inline-block;
      background: rgba(200,240,79,0.12);
      color: var(--accent);
      border: 1px solid rgba(200,240,79,0.3);
      border-radius: 20px;
      padding: 4px 14px;
      font-size: 12px;
      font-family: 'Syne', sans-serif;
      font-weight: 600;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      margin-bottom: 20px;
    }

    .hero h1 {
      font-family: 'Syne', sans-serif;
      font-size: clamp(2rem, 5vw, 3.2rem);
      font-weight: 800;
      line-height: 1.1;
      margin-bottom: 16px;
    }
    .hero h1 span {
      color: var(--accent);
    }

    .hero p {
      color: var(--muted);
      font-size: 16px;
      max-width: 520px;
      margin-bottom: 28px;
    }

    .tags {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
    }
    .tag {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 6px;
      padding: 5px 12px;
      font-size: 13px;
      color: var(--muted);
      font-family: monospace;
    }

    /* CONTENT */
    .content {
      padding: 48px 0;
    }

    .section {
      margin-bottom: 48px;
      animation: fadeUp 0.5s ease both;
    }
    .section:nth-child(1) { animation-delay: 0.05s; }
    .section:nth-child(2) { animation-delay: 0.1s; }
    .section:nth-child(3) { animation-delay: 0.15s; }
    .section:nth-child(4) { animation-delay: 0.2s; }

    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(16px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    .section-label {
      font-family: 'Syne', sans-serif;
      font-size: 11px;
      font-weight: 700;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 14px;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .section-label::after {
      content: '';
      flex: 1;
      height: 1px;
      background: var(--border);
    }

    .section h2 {
      font-family: 'Syne', sans-serif;
      font-size: 1.3rem;
      font-weight: 700;
      margin-bottom: 12px;
    }

    .section p {
      color: #bbb;
      margin-bottom: 10px;
    }

    /* TECH GRID */
    .tech-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
      gap: 12px;
      margin-top: 4px;
    }
    .tech-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 16px;
      transition: border-color 0.2s, transform 0.2s;
    }
    .tech-card:hover {
      border-color: var(--accent2);
      transform: translateY(-2px);
    }
    .tech-card .icon {
      font-size: 20px;
      margin-bottom: 8px;
    }
    .tech-card .name {
      font-family: 'Syne', sans-serif;
      font-weight: 600;
      font-size: 14px;
    }
    .tech-card .desc {
      font-size: 12px;
      color: var(--muted);
      margin-top: 2px;
    }

    /* FOLDER STRUCTURE */
    .folder-tree {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 24px;
      font-family: monospace;
      font-size: 14px;
      line-height: 2;
    }
    .folder-tree .folder { color: var(--accent); }
    .folder-tree .file   { color: #aaa; }
    .folder-tree .indent { padding-left: 22px; }
    .folder-tree .indent2 { padding-left: 44px; }

    /* AUTHOR CARD */
    .author-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 14px;
      padding: 24px 28px;
      display: flex;
      align-items: center;
      gap: 20px;
    }
    .author-avatar {
      width: 56px; height: 56px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--accent2), var(--accent));
      display: flex; align-items: center; justify-content: center;
      font-family: 'Syne', sans-serif;
      font-weight: 800;
      font-size: 20px;
      color: #000;
      flex-shrink: 0;
    }
    .author-info .name {
      font-family: 'Syne', sans-serif;
      font-weight: 700;
      font-size: 16px;
    }
    .author-info .role {
      font-size: 13px;
      color: var(--muted);
      margin-top: 2px;
    }
    .author-info a {
      display: inline-block;
      margin-top: 8px;
      font-size: 13px;
      color: var(--accent);
      text-decoration: none;
      border-bottom: 1px solid transparent;
      transition: border-color 0.2s;
    }
    .author-info a:hover { border-color: var(--accent); }

    /* FOOTER */
    footer {
      border-top: 1px solid var(--border);
      padding: 24px 0;
      text-align: center;
      color: var(--muted);
      font-size: 13px;
    }
  </style>
</head>
<body>

  <!-- HERO -->
  <div class="hero">
    <div class="container">
      <div class="badge">📄 README</div>
      <h1>Web <span>Portofolio</span><br>Marsyanda Firlyandita</h1>
      <p>Website portofolio pribadi yang menampilkan profil, skill, pengalaman, sertifikat, dan galeri karya desain.</p>
      <div class="tags">
        <span class="tag">HTML5</span>
        <span class="tag">CSS3</span>
        <span class="tag">Bootstrap 5</span>
        <span class="tag">Responsive</span>
      </div>
    </div>
  </div>

  <!-- CONTENT -->
  <div class="content">
    <div class="container">

      <!-- DESKRIPSI -->
      <div class="section">
        <div class="section-label">Deskripsi Project</div>
        <p>
          Website ini dibuat sebagai portofolio digital untuk memperkenalkan diri sebagai seorang
          <strong style="color: var(--text)">UI/UX Designer & Graphic Designer</strong> dengan pengalaman lebih dari 2 tahun.
        </p>
        <p>
          Website menampilkan berbagai informasi mulai dari profil singkat, keahlian, pengalaman kerja,
          sertifikat, hingga galeri portofolio desain.
        </p>
      </div>

      <!-- TEKNOLOGI -->
      <div class="section">
        <div class="section-label">Teknologi yang Digunakan</div>
        <div class="tech-grid">
          <div class="tech-card">
            <div class="icon">🌐</div>
            <div class="name">HTML5</div>
            <div class="desc">Struktur halaman</div>
          </div>
          <div class="tech-card">
            <div class="icon">🎨</div>
            <div class="name">CSS3</div>
            <div class="desc">Styling & layout</div>
          </div>
          <div class="tech-card">
            <div class="icon">⚡</div>
            <div class="name">Bootstrap 5</div>
            <div class="desc">Framework CSS</div>
          </div>
          <div class="tech-card">
            <div class="icon">🔤</div>
            <div class="name">Google Fonts</div>
            <div class="desc">Font Ubuntu</div>
          </div>
        </div>
      </div>

      <!-- STRUKTUR FOLDER -->
      <div class="section">
        <div class="section-label">Struktur Folder</div>
        <div class="folder-tree">
          <div class="folder">📁 portofolio-web/</div>
          <div class="indent file">📄 index.html</div>
          <div class="indent folder">📁 css/</div>
          <div class="indent2 file">📄 style.css</div>
          <div class="indent folder">📁 Img/</div>
          <div class="indent2 file">🖼️ (aset gambar)</div>
        </div>
      </div>

      <!-- AUTHOR -->
      <div class="section">
        <div class="section-label">Author</div>
        <div class="author-card">
          <div class="author-avatar">MF</div>
          <div class="author-info">
            <div class="name">Marsyanda Firlyandita</div>
            <div class="role">UI/UX Design &nbsp;|&nbsp; Graphic Design</div>
            <a href="https://www.linkedin.com/in/marsyanda-firlyandita-94421128b/" target="_blank">
              🔗 LinkedIn Profile
            </a>
          </div>
        </div>
      </div>

    </div>
  </div>

  <footer>
    <div class="container">
      Made with ♥ by Marsyanda Firlyandita &nbsp;·&nbsp; Web Development & UI/UX Design Program
    </div>
  </footer>

</body>
</html>
