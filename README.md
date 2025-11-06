<html lang="ko">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Hyuntae Jeong | Research</title>
  <meta name="description" content="Research homepage showcasing projects, publications, images, and videos." />
  <style>
    /* ===== CSS RESET (lightweight) ===== */
    *, *::before, *::after { box-sizing: border-box; }
    html, body { margin: 0; padding: 0; }

    /* ===== THEME ===== */
    :root {
      --bg: #ffffff;
      --text: #111827; /* slate-900 */
      --muted: #6b7280; /* gray-500 */
      --card: #f8fafc; /* slate-50 */
      --accent: #2563eb; /* blue-600 */
      --accent-2: #1d4ed8; /* blue-700 */
      --border: #e5e7eb; /* gray-200 */
      --shadow: 0 10px 25px rgba(0,0,0,.08);
    }
    @media (prefers-color-scheme: dark) {
      :root {
        --bg: #0b0f17; /* near-black */
        --text: #e5e7eb; /* gray-200 */
        --muted: #9ca3af; /* gray-400 */
        --card: #0f172a; /* slate-900 */
        --accent: #60a5fa; /* blue-400 */
        --accent-2: #93c5fd; /* blue-300 */
        --border: #1f2937; /* gray-800 */
        --shadow: 0 10px 25px rgba(0,0,0,.35);
      }
    }
    .dark {
      --bg: #0b0f17;
      --text: #e5e7eb;
      --muted: #9ca3af;
      --card: #0f172a;
      --accent: #60a5fa;
      --accent-2: #93c5fd;
      --border: #1f2937;
      --shadow: 0 10px 25px rgba(0,0,0,.35);
    }

    body { font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji", "Segoe UI Emoji"; background: var(--bg); color: var(--text); line-height: 1.6; }
    a { color: var(--accent); text-decoration: none; }
    a:hover { color: var(--accent-2); }

    /* ===== LAYOUT ===== */
    .container { width: 100%; max-width: 1100px; margin: 0 auto; padding: 0 20px; }
    .grid { display: grid; gap: 1.25rem; }
    .grid-2 { grid-template-columns: repeat(2, minmax(0, 1fr)); }
    .grid-3 { grid-template-columns: repeat(3, minmax(0, 1fr)); }
    .grid-4 { grid-template-columns: repeat(4, minmax(0, 1fr)); }
    @media (max-width: 960px) { .grid-3, .grid-4 { grid-template-columns: repeat(2, minmax(0, 1fr)); } }
    @media (max-width: 640px) { .grid-2, .grid-3, .grid-4 { grid-template-columns: 1fr; } }

    .card { background: var(--card); border: 1px solid var(--border); border-radius: 16px; box-shadow: var(--shadow); overflow: hidden; }
    .card-pad { padding: 1.1rem 1.25rem; }

    .section { padding: 64px 0; }
    .section h2 { font-size: clamp(1.5rem, 1.1rem + 1.4vw, 2.25rem); margin: 0 0 8px; }
    .section p.lead { color: var(--muted); margin-top: 4px; margin-bottom: 18px; }

    /* ===== NAVBAR ===== */
    .nav { position: sticky; top: 0; z-index: 50; backdrop-filter: saturate(180%) blur(8px); background: color-mix(in srgb, var(--bg), transparent 10%); border-bottom: 1px solid var(--border); }
    .nav-inner { display: flex; align-items: center; justify-content: space-between; height: 64px; }
    .brand { font-weight: 800; letter-spacing: .3px; }
    .nav-links a { margin: 0 10px; font-weight: 600; color: var(--text); }
    .nav-links a:hover { color: var(--accent); }
    .toggle { border: 1px solid var(--border); background: var(--card); color: var(--text); border-radius: 12px; padding: 6px 10px; cursor: pointer; }

    /* ===== HERO ===== */
    .hero { padding: 36px 0 20px; }
    .hero-wrap { display: grid; grid-template-columns: 1.2fr .8fr; gap: 24px; align-items: center; }
    @media (max-width: 860px){ .hero-wrap { grid-template-columns: 1fr; } }
    .hero h1 { font-size: clamp(1.5rem, 1.0rem + 2.0vw, 2.5rem); line-height: 1.15; margin: 0; }
    .hero p { color: var(--muted); margin-top: 12px; }
    .hero .badge { display: inline-block; background: var(--card); border: 1px solid var(--border); padding: 6px 10px; margin-top: 12px; border-radius: 999px; font-size: .9rem; }
    .hero .figure { aspect-ratio: 4/3; background: var(--card); border: 1px solid var(--border); border-radius: 16px; overflow: hidden; box-shadow: var(--shadow); }
    .hero .figure img, .hero .figure video { width: 100%; height: 100%; object-fit: cover; display: block; }

    /* ===== PROJECTS ===== */
    .project { display: grid; grid-template-columns: 120px 1fr; gap: 18px; align-items: start; }
    .project .thumb { width: 100%; aspect-ratio: 1/1; border-radius: 12px; overflow: hidden; border: 1px solid var(--border); background: #000; }
    .project .thumb img { width: 100%; height: 100%; object-fit: cover; display: block; }
    .chip { display: inline-block; padding: 4px 8px; border-radius: 999px; border: 1px solid var(--border); background: color-mix(in srgb, var(--card), transparent 25%); margin-right: 6px; margin-top: 6px; font-size: .85rem; color: var(--muted); }

    /* ===== GALLERY ===== */
    .gallery img { width: 100%; height: 200px; object-fit: cover; border-radius: 12px; border: 1px solid var(--border); cursor: zoom-in; }
    .filters { display: flex; flex-wrap: wrap; gap: 8px; margin: 12px 0 20px; }
    .filters button { padding: 6px 12px; border-radius: 999px; border: 1px solid var(--border); background: var(--card); color: var(--text); cursor: pointer; }
    .filters button.active { background: var(--accent); color: white; border-color: var(--accent); }

    /* ===== VIDEO GRID ===== */
    .video { position: relative; border-radius: 12px; border: 1px solid var(--border); overflow: hidden; background: #000; }
    .video iframe, .video video { width: 100%; height: 100%; aspect-ratio: 16/9; display: block; }

    /* ===== PUBLICATIONS ===== */
    .pub { display: grid; grid-template-columns: 1fr auto; gap: 8px; border-bottom: 1px dashed var(--border); padding: 14px 0; }
    .pub .meta { color: var(--muted); font-size: .95rem; }
    .btn { display: inline-block; padding: 6px 10px; border-radius: 10px; border: 1px solid var(--border); background: var(--card); }

    /* ===== LIGHTBOX MODAL ===== */
    .modal { position: fixed; inset: 0; background: rgba(0,0,0,.8); display: none; align-items: center; justify-content: center; padding: 20px; z-index: 100; }
    .modal.open { display: flex; }
    .modal img, .modal video { max-width: 92vw; max-height: 86vh; border-radius: 12px; box-shadow: var(--shadow); }
    .modal .close { position: absolute; top: 18px; right: 20px; background: #000; color: #fff; border: 0; border-radius: 999px; width: 40px; height: 40px; font-size: 22px; cursor: pointer; opacity: .7; }

    /* ===== FOOTER ===== */
    footer { border-top: 1px solid var(--border); padding: 28px 0; color: var(--muted); }
  </style>
</head>
<body>
  <!-- ===== NAV ===== -->
  <nav class="nav">
    <div class="container nav-inner">
      <div class="brand">Hyuntae Jeong</div>
      <div class="nav-links" role="navigation">
        <a href="#about">About</a>
        <a href="#research">Research</a>
        <a href="#publications">Publication</a>
        <a href="#gallery">Gallery</a>
        <a href="#videos">Videos</a>
        <a href="#contact">Contact</a>
      </div>
      <button id="themeToggle" class="toggle" aria-label="Toggle dark mode">🌓</button>
    </div>
  </nav>

  <!-- ===== HERO ===== -->
  <header class="hero">
    <div class="container hero-wrap">
      <div>
        <h1>Collective Cell Migration & Cell Mechanics</h1>
        <p>I investigate <strong>형태·분자 상태</strong>와 <strong>집단적 상호작용</strong>이 어떻게 이동 특성을 만들고 조직 수준의 물성을 바꾸는지 탐구합니다. 머신러닝/컴퓨터비전 + 실험 데이터를 통합해 <em>해석·예측</em> 가능한 모델을 구축합니다.</p>
        <span class="badge">Brown University · Wong Lab · Postdoctoral Researcher</span>
        <div style="margin-top:14px">
          <a class="btn" href="#publications">주요 논문 보기</a>
          <a class="btn" href="#research" style="margin-left:8px">프로젝트 둘러보기</a>
        </div>
      </div>
      <figure class="figure">
        <!-- 대표 이미지나 티저 영상 (video 태그로 바꿔도 됨) -->
        <img src="assets/hero_placeholder.jpg" alt="Research teaser image (put your figure here)" />
      </figure>
    </div>
  </header>

  <!-- ===== ABOUT ===== -->
  <section id="about" class="section">
    <div class="container grid grid-2">
      <div class="card card-pad">
        <h2>소개</h2>
        <p class="lead">형태·모빌리티·발현을 통합한 세포 집단행동의 물리학</p>
        <p>세포 마이그레이션, EMT, 집단 유동학을 중심으로 이미징·세그멘테이션·특징추출·그래프러닝을 결합합니다. <strong>형태 기반 레이블링</strong>, <strong>이웃 상호작용 특징</strong>, <strong>마코프 전이</strong> 등을 통해 
          집단적 이질성과 시간적 변화를 정량화합니다.</p>
        <p><a href="assets/CV_HyeontaeJeong.pdf" download>CV 다운로드</a> · 
           <a href="https://github.com/" target="_blank" rel="noopener">GitHub</a> · 
           <a href="mailto:your_email@example.com">이메일</a></p>
      </div>
      <div class="card card-pad">
        <h2>연구 키워드</h2>
        <div>
          <span class="chip">Collective Cell Migration</span>
          <span class="chip">EMT</span>
          <span class="chip">Traction Force Microscopy</span>
          <span class="chip">Autoencoder · UMAP</span>
          <span class="chip">GNN (PyG)</span>
          <span class="chip">Image Segmentation</span>
          <span class="chip">Markov Chains</span>
        </div>
      </div>
    </div>
  </section>

  <!-- ===== RESEARCH PROJECTS ===== -->
  <section id="research" class="section">
    <div class="container">
      <h2>연구 프로젝트</h2>
      <p class="lead">이미지/영상/코드를 쉽게 첨부할 수 있도록 설계되었습니다.</p>
      <div class="grid grid-2">
        <!-- Project 1 -->
        <article class="card card-pad project">
          <div class="thumb">
            <img src="assets/projects/proj1_thumb.jpg" alt="Project thumbnail" />
          </div>
          <div>
            <h3>형태-모빌리티 융합 모델</h3>
            <p>세포 형태(UMAP/PCA)와 이동성(MSD/속도/루프점수)을 결합하여 EMT 상태별 행동을 설명하는 예측 모델. 그래프 신경망으로 이웃 특성(거리/유사도)을 통합.</p>
            <div>
              <span class="chip">Python</span>
              <span class="chip">PyTorch Geometric</span>
              <span class="chip">KDE / JSD</span>
            </div>
            <p style="margin-top:6px">
              <a class="btn" href="assets/projects/proj1_poster.pdf" target="_blank">포스터</a>
              <a class="btn" href="https://github.com/yourname/proj1" target="_blank" rel="noopener">코드</a>
              <a class="btn open-modal" data-type="image" data-src="assets/projects/proj1_fig1.png">그림 보기</a>
              <a class="btn open-modal" data-type="video" data-src="assets/projects/proj1_teaser.mp4">티저 영상</a>
            </p>
          </div>
        </article>

        <!-- Project 2 -->
        <article class="card card-pad project">
          <div class="thumb">
            <img src="assets/projects/proj2_thumb.jpg" alt="Project thumbnail" />
          </div>
          <div>
            <h3>TFM 기반 응력 지도와 상처 치유</h3>
            <p>Traction force와 경계 곡률/방사-원주 변형을 연결하고, 집단 응력 전파의 시공간 메커니즘을 규명.</p>
            <div>
              <span class="chip">MATLAB</span>
              <span class="chip">TFM</span>
              <span class="chip">Wound Healing</span>
            </div>
            <p style="margin-top:6px">
              <a class="btn open-modal" data-type="image" data-src="assets/projects/proj2_dart.png">DART 그림</a>
              <a class="btn" href="https://github.com/yourname/proj2" target="_blank" rel="noopener">분석 코드</a>
            </p>
          </div>
        </article>

        <!-- 더 많은 프로젝트 카드 복제 가능 -->
      </div>
    </div>
  </section>

  <!-- ===== PUBLICATIONS ===== -->
  <section id="publications" class="section">
    <div class="container">
      <h2>출판물</h2>
      <p class="lead">최근 논문과 사전공개(preprint) 링크를 업데이트하세요.</p>
      <div class="card card-pad">
        <article class="pub">
          <div>
            <strong>Title of the Paper</strong><br/>
            Author One, <u>Hyeontae Jeong</u>, Author Three<br/>
            <span class="meta">Journal Name, 2025 · DOI: <a href="#">10.xxxx/xxxxx</a></span>
          </div>
          <div>
            <a class="btn" href="#">PDF</a>
          </div>
        </article>
        <article class="pub">
          <div>
            <strong>Another Research Article</strong><br/>
            <u>Hyeontae Jeong</u>, et al.<br/>
            <span class="meta">bioRxiv, 2025 · <a href="#">Preprint</a></span>
          </div>
          <div>
            <a class="btn" href="#">PDF</a>
          </div>
        </article>
        <!-- 항목 복제하여 추가 -->
      </div>
    </div>
  </section>

  <!-- ===== IMAGE GALLERY ===== -->
  <section id="gallery" class="section">
    <div class="container">
      <h2>이미지 갤러리</h2>
      <p class="lead">피겨/스냅샷을 카테고리별로 정리하고 라이트박스로 확대합니다.</p>

      <div class="filters" aria-label="gallery filters">
        <button class="active" data-filter="all">전체</button>
        <button data-filter="figure">피겨</button>
        <button data-filter="microscopy">현미경</button>
        <button data-filter="plot">그래프</button>
      </div>

      <div class="grid grid-3 gallery">
        <!-- 각 img에 data-tags로 필터 태그 지정 -->
        <img src="assets/gallery/fig1.jpg" alt="Figure 1" data-tags="figure" />
        <img src="assets/gallery/micro1.jpg" alt="Microscopy image" data-tags="microscopy" />
        <img src="assets/gallery/plot1.jpg" alt="Plot image" data-tags="plot" />
        <img src="assets/gallery/fig2.jpg" alt="Figure 2" data-tags="figure" />
        <img src="assets/gallery/micro2.jpg" alt="Microscopy image" data-tags="microscopy" />
        <img src="assets/gallery/plot2.jpg" alt="Plot image" data-tags="plot" />
      </div>
    </div>
  </section>

  <!-- ===== VIDEOS ===== -->
  <section id="videos" class="section">
    <div class="container">
      <h2>영상</h2>
      <p class="lead">YouTube/Vimeo 임베드 또는 직접 호스팅한 mp4를 지원합니다.</p>
      <div class="grid grid-2">
        <!-- YouTube embed 예시 -->
        <div class="video card">
          <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="YouTube video" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
        </div>
        <!-- 로컬/서버 mp4 예시 -->
        <div class="video card">
          <video controls preload="metadata" src="assets/videos/sample_teaser.mp4" aria-label="Project teaser video"></video>
        </div>
      </div>
    </div>
  </section>

  <!-- ===== NEWS ===== -->
  <section id="news" class="section">
    <div class="container">
      <h2>소식</h2>
      <div class="card card-pad">
        <ul>
          <li><strong>2025-11-06</strong> · 홈페이지 초기 버전 공개 (GitHub Pages).</li>
          <li><strong>2025-10-15</strong> · ICERM 워크숍 포스터 발표.</li>
          <!-- 항목 추가 -->
        </ul>
      </div>
    </div>
  </section>

  <!-- ===== CONTACT ===== -->
  <section id="contact" class="section">
    <div class="container grid grid-2">
      <div class="card card-pad">
        <h2>연락처</h2>
        <p class="lead">협업/세미나/학생지도 문의 환영합니다.</p>
        <p>
          📧 <a href="mailto:your_email@example.com">your_email@example.com</a><br/>
          🏛️ Brown University, School of Engineering, ERC 245H
        </p>
      </div>
      <div class="card card-pad">
        <h2>링크</h2>
        <p>
          <a href="https://scholar.google.com/" target="_blank" rel="noopener">Google Scholar</a><br/>
          <a href="https://orcid.org/" target="_blank" rel="noopener">ORCID</a><br/>
          <a href="https://github.com/" target="_blank" rel="noopener">GitHub</a>
        </p>
      </div>
    </div>
  </section>

  <footer>
    <div class="container">© <span id="year"></span> Hyeontae Jeong · Built for GitHub Pages</div>
  </footer>

  <!-- ===== LIGHTBOX MODAL ===== -->
  <div id="modal" class="modal" role="dialog" aria-modal="true" aria-label="media viewer">
    <button class="close" aria-label="close modal">×</button>
    <div id="modalContent"></div>
  </div>

  <script>
    // ===== YEAR =====
    document.getElementById('year').textContent = new Date().getFullYear();

    // ===== THEME TOGGLE =====
    const toggleBtn = document.getElementById('themeToggle');
    toggleBtn.addEventListener('click', () => {
      document.documentElement.classList.toggle('dark');
      localStorage.setItem('prefers-dark', document.documentElement.classList.contains('dark') ? '1' : '0');
    });
    // load preference
    const pref = localStorage.getItem('prefers-dark');
    if (pref === '1') document.documentElement.classList.add('dark');

    // ===== GALLERY FILTER =====
    const filterButtons = document.querySelectorAll('.filters button');
    const galleryItems = document.querySelectorAll('.gallery img');

    filterButtons.forEach(btn => {
      btn.addEventListener('click', () => {
        filterButtons.forEach(b => b.classList.remove('active'));
        btn.classList.add('active');
        const tag = btn.dataset.filter;
        galleryItems.forEach(img => {
          const tags = (img.dataset.tags || '').split(',');
          const show = tag === 'all' || tags.includes(tag);
          img.style.display = show ? 'block' : 'none';
        });
      });
    });

    // ===== LIGHTBOX (Images & Videos) =====
    const modal = document.getElementById('modal');
    const modalContent = document.getElementById('modalContent');
    const closeBtn = modal.querySelector('.close');

    function openModal(el) {
      const type = el.dataset.type || (el.tagName === 'IMG' ? 'image' : 'video');
      const src = el.dataset.src || el.getAttribute('src');
      modalContent.innerHTML = '';
      if (type === 'image') {
        const img = document.createElement('img');
        img.src = src; img.alt = el.alt || 'image';
        modalContent.appendChild(img);
      } else if (type === 'video') {
        const vid = document.createElement('video');
        vid.src = src; vid.controls = true; vid.autoplay = true;
        modalContent.appendChild(vid);
      }
      modal.classList.add('open');
    }
    function closeModal() {
      modal.classList.remove('open');
      modalContent.innerHTML = '';
    }
    closeBtn.addEventListener('click', closeModal);
    modal.addEventListener('click', (e) => { if (e.target === modal) closeModal(); });

    // Open from gallery images
    galleryItems.forEach(img => {
      img.addEventListener('click', () => openModal(img));
    });
    // Open from buttons with data-type/data-src
    document.querySelectorAll('.open-modal').forEach(btn => {
      btn.addEventListener('click', () => openModal(btn));
    });
  </script>

  <!-- =============================
       사용 가이드 (주석):
       1) 이 파일을 repo 루트에 index.html로 저장
       2) /assets 폴더에 이미지/영상/PDF 배치
          - assets/hero_placeholder.jpg
          - assets/projects/*  (썸네일, 그림, 동영상)
          - assets/gallery/*   (갤러리 이미지)
          - assets/videos/*    (mp4 등)
          - assets/CV_HyeontaeJeong.pdf
       3) GitHub Pages 활성화: Settings → Pages → Deploy from branch → main/docs 등 선택
       4) 섹션/카드 복제하여 프로젝트와 논문을 쉽게 추가
       5) 다크모드: 우상단 🌓 토글
  ============================== -->
</body>
</html>
