# Restaurant-website
<!DOCTYPE html>
<html lang="el">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Το Εστιατόριό μας</title>
  <meta name="description" content="Εστιατόριο με μεσογειακή κουζίνα – μενού, φωτογραφίες πιάτων και σύστημα κρατήσεων." />
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Manrope:wght@300;400;600;700&display=swap" rel="stylesheet">
  <style>
    :root{
      /* ΧΡΩΜΑΤΑ (primary γαλάζιο, background γκρι) */
      --bg:#2b2f36;--card:#151923;--muted:#8b95a7;--text:#e6e8ee;
      --brand:#5cc8ff;--brand-2:#2ea0f0;--accent:#ffcc6f;--danger:#ff6b6b;
      --radius:18px;--shadow:0 10px 30px rgba(0,0,0,.35);
    }
    *{box-sizing:border-box}
    html{scroll-behavior:smooth}
    body{
      margin:0;font-family:Manrope,system-ui,-apple-system,Segoe UI,Roboto,Ubuntu,"Helvetica Neue",Arial;
      color:var(--text);
      background:radial-gradient(1200px 800px at 20% -20%,#3a3f47 0%,#2b2f36 55%),var(--bg)
    }
    a{color:inherit;text-decoration:none}
    img{max-width:100%;display:block;border-radius:14px}
    .container{width:min(1150px,92vw);margin-inline:auto}

    /* Header */
    header{position:sticky;top:0;z-index:50;backdrop-filter:saturate(1.2) blur(10px); background:rgba(10,12,18,.55); border-bottom:1px solid rgba(255,255,255,.06)}
    .nav{display:flex;align-items:center;justify-content:space-between;gap:16px;padding:14px 0}
    .brand{display:flex;align-items:center;gap:12px;font-weight:800}
    .logo { width: 40px; height: 40px; object-fit: contain; border-radius: 8px; box-shadow: 0 8px 18px rgba(95,200,255,.15); }
    .nav ul{display:flex;gap:18px;list-style:none;padding:0;margin:0}
    .nav a{padding:10px 14px;border-radius:12px;color:var(--text);opacity:.9}
    .nav a:hover{background:rgba(255,255,255,.06);opacity:1}
    .btn{display:inline-flex;align-items:center;gap:8px;padding:12px 16px;border-radius:14px;border:1px solid rgba(255,255,255,.12);background:linear-gradient(180deg,rgba(255,255,255,.06),rgba(255,255,255,.02));box-shadow:var(--shadow);cursor:pointer}
    .btn.primary{background:linear-gradient(180deg,var(--brand),var(--brand-2));color:#ffffff;border-color:transparent;font-weight:800}
/* Language Switch */
.lang-switch {
  display: flex;
  gap: 8px;
  align-items: center;
}
.lang-btn {
  background: transparent;
  border: 1px solid rgba(255,255,255,.2);
  border-radius: 10px;
  padding: 6px 10px;
  color: var(--text);
  cursor: pointer;
  transition: all .2s ease;
}
.lang-btn.active,
.lang-btn:hover {
  background: var(--brand);
  border-color: var(--brand);
  color: #fff;
}

    /* Hero */
    .hero{
      padding:20px 0 20px;
    }
    .hero .wrap{display:grid;grid-template-columns:1.1fr .9fr;gap:26px;align-items:center}
    .hero h1{font-size:46px;line-height:1.05;margin:0 0 12px}
    .hero p{color:var(--muted);font-size:18px;margin:0 0 22px}
    .badges{display:flex;gap:10px;flex-wrap:wrap;margin:18px 0}
    .badge{padding:8px 12px;border-radius:999px;background:rgba(92,200,255,.15);color:var(--brand);font-weight:700;border:1px solid rgba(92,200,255,.35)}
    .hero-card{background:linear-gradient(180deg,#1a2030,#121622);border:1px solid rgba(255,255,255,.06);border-radius:24px;padding:16px;display:grid;gap:16px}
    .hero-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px}

    /* Sections */
    section{padding:62px 0}
    .section-title{font-size:32px;margin:0 0 18px}
    .muted{color:var(--muted)}
    .grid-3{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}
    .card{background:var(--card);border:1px solid rgba(255,255,255,.06);border-radius:18px;padding:16px;box-shadow:var(--shadow)}

    /* Menu */
    .menu-item{display:flex;gap:12px;align-items:flex-start}
    .menu-item h4{margin:0;font-size:18px}
    .price{margin-left:auto;font-weight:800}
    .tag{font-size:12px;padding:4px 8px;border:1px solid rgba(255,255,255,.12);border-radius:999px;color:#fff;opacity:.7}
    /* Menu responsive grid */
    .menu-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:18px}

    /* Gallery */
    .gallery{display:grid;grid-template-columns:repeat(3,1fr);gap:12px}
    .gallery img{aspect-ratio:4/3;object-fit:cover}

    /* Reservations */
    form{display:grid;gap:12px}
    .row{display:grid;grid-template-columns:1fr 1fr;gap:12px}
    input,select,textarea{width:100%;padding:12px 14px;border-radius:12px;border:1px solid rgba(255,255,255,.12);background:#0f1320;color:var(--text)}
    label{font-size:14px;color:var(--muted)}
    .hint{font-size:12px;color:var(--muted)}
    .notice{padding:12px;border-radius:12px;background:rgba(92,200,255,.12);border:1px solid rgba(92,200,255,.35);color:var(--text)}
    .error{background:rgba(255,107,107,.12);border-color:rgba(255,107,107,.45)}

    /* Contact & Footer */
    .contact{display:grid;grid-template-columns:1fr 1fr;gap:18px}
    iframe{width:100%;height:320px;border:0;border-radius:18px}
    footer{padding:40px 0;color:var(--muted);border-top:1px solid rgba(255,255,255,.06)}

    /* Small screens */
    @media (max-width:920px){
      .hero .wrap{grid-template-columns:1fr}
      .grid-3{grid-template-columns:1fr}
      .gallery{grid-template-columns:1fr 1fr}
      .row{grid-template-columns:1fr}
      .contact{grid-template-columns:1fr}
    }
  </style>
</head>
<body>
  <!-- Header -->
   <header>
    <div class="container nav">
      <a class="brand" href="#top" aria-label="Αρχική">
        <img class="logo" src="./loloo.png" alt="Λογότυπο εστιατορίου">
        <span data-key="brandName">Εστιατόριο Ενδοχώρα</span>
      </a>
      <nav aria-label="Κύριο μενού">
        <ul>
          <li><a href="#about" data-key="menuAbout">Σχετικά</a></li>
          <li><a href="#gallery" data-key="menuGallery">Πιάτα</a></li>
          <li><a href="#reservations" class="btn primary" data-key="menuReserve">Κρατήσεις</a></li>
          <li><a href="#contact" data-key="menuContact">Επικοινωνία</a></li>
          <div class="lang-switch">
            <button class="lang-btn active" data-lang="gr">GR</button>
            <button class="lang-btn" data-lang="en">EN</button>
          </div>
        </ul>
      </nav>
    </div>
  </header>

  <!-- Hero -->
  <main id="top" class="hero">
    <div class="container wrap">
      <div>
        <div class="badges">
          <span class="badge" data-key="badge1">Μεσογειακή κουζίνα</span>
          <span class="badge" data-key="badge2">Farm-to-table</span>
          <span class="badge" data-key="badge3">Vegan επιλογές</span>
        </div>
        <h1 data-key="heroTitle">Φρέσκες γεύσεις, ζεστή φιλοξενία.</h1>
        <p data-key="heroText">Από τοπικές πρώτες ύλες σε πιάτα που μιλούν από μόνα τους. Κάνε κράτηση online και ετοιμάσου για μια υπέροχη εμπειρία.</p>
        <div style="display:flex;gap:10px;flex-wrap:wrap">
          <a class="btn primary" href="#reservations" data-key="heroBtnReserve">Κλείσε τραπέζι</a>
          <a class="btn" href="#gallery" data-key="heroBtnMenu">Δες το μενού</a>
        </div>
      </div>
      <div class="hero-card">
        <div class="hero-grid">
          <img src="./andr.png" alt=""/>
          <img src="./end.png" alt=""/>
          <img src="./kr.png" alt=""/>
          <img src="./out.png" alt=""/>
          <img src="./cockt.png" alt=""/>
          <img src="./far.png" alt=""/>
        </div>
      </div>
    </div>
  </main>

  <!-- About -->
  <section id="about">
    <div class="container">
      <h2 class="section-title" data-key="aboutTitle">Σχετικά με εμάς</h2>
      <p class="muted" data-key="aboutText">Στην καρδιά της Άνδρου, δημιουργούμε καθημερινά εποχικά πιάτα με έμφαση στην ποιότητα και την απλότητα.</p>
      <div class="grid-3" style="margin-top:18px">
        <div class="card">
          <h3 data-key="hoursTitle">Ώρες λειτουργίας</h3>
          <p class="muted" data-key="hoursText">Δευ–Κυρ: 18:00–00:00</p>
        </div>
        <div class="card">
          <h3 data-key="addressTitle">Διεύθυνση</h3>
          <p class="muted" data-key="addressText">Γεωργίου Εμπειρίκου, Χώρα Άνδρου 84 500</p>
        </div>
        <div class="card">
          <h3 data-key="phoneTitle">Τηλέφωνο</h3>
          <p class="muted" data-key="phoneText">22820 23207</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Gallery -->
  <section id="gallery">
    <div class="container">
      <h2 class="section-title" data-key="galleryTitle">Τα πιάτα μας</h2>
      <div class="gallery" aria-label="Γκαλερί πιάτων">
        <img src="./salend.png" alt="Σαλάτα Ενδοχώρα"/>
        <img src="./nis.png" alt="Σαλάτα νησιώτικη"/>
        <img src="./androise.png" alt="Σαλάτα ανδρουάζ"/>
        <img src="./kal.png" alt="Καλαμάρι ψητό"/>
        <img src="./dol.png" alt="Ντολμαδάκια"/>
        <img src="./xtap.png" alt="Χταπόδι ψητό"/>
        <img src="./riz.png" alt="Ριζότο γαρίδες"/>
        <img src="./thal.png" alt="Μακαρονάδα θαλασσινή"/>
        <img src="./voun.png" alt="Μακαρονάδα βουνίσια"/>
        <img src="./tal.png" alt="Ταλιάτα Μοσχαρίσια"/>
        <img src="./kot.png" alt="Κοτόπουλο ψητό"/>
        <img src="./sel.png" alt="Stake σελινόριζας"/>
        <img src="./soum.png" alt="Κρέμα σουμάδας"/>
        <img src="./marys.png" alt="Το γλυκό της Μαίρης"/>
      </div>
    </div>
  </section>

  <!-- Reservations -->
  <section id="reservations">
    <div class="container">
      <h2 class="section-title" data-key="reserveTitle">Κρατήσεις</h2>
      <p class="muted" data-key="reserveText">Συμπλήρωσε τα στοιχεία σου. Θα λάβεις άμεσα επιβεβαίωση στην οθόνη.</p>

      <form id="reservationForm" novalidate>
        <div class="row">
          <div>
            <label data-key="nameLabel" for="name">Ονοματεπώνυμο</label>
            <input id="name" name="name" placeholder="π.χ. Μαρία Παπαδοπούλου" required />
          </div>
          <div>
            <label data-key="phoneLabel" for="phone">Τηλέφωνο</label>
            <input id="phone" name="phone" type="tel" placeholder="69xxxxxxxx" required />
          </div>
        </div>
        <div class="row">
          <div>
            <label data-key="dateLabel" for="date">Ημερομηνία</label>
            <input id="date" name="date" type="date" required />
          </div>
          <div>
            <label data-key="timeLabel" for="time">Ώρα</label>
            <input id="time" name="time" type="time" required />
          </div>
        </div>
        <div class="row">
          <div>
            <label data-key="guestsLabel" for="guests">Άτομα</label>
            <select id="guests" name="guests" required>
              <option disabled selected>Επιλογή...</option>
              <option>1</option><option>2</option><option>3</option><option>4</option>
              <option>5</option><option>6</option><option>7</option><option>8</option>
            </select>
          </div>
          <div>
            <label data-key="notesLabel" for="notes">Σχόλια</label>
            <input id="notes" name="notes" placeholder="Αλλεργίες, παιδικό κάθισμα κ.λπ." />
          </div>
        </div>
        <div style="display:flex;gap:10px;">
          <button class="btn primary" type="submit" data-key="submitReserve">Υποβολή κράτησης</button>
        </div>
      </form>
    </div>
  </section>

  <!-- Reviews -->
  <section id="reviews">
    <div class="container">
      <h2 class="section-title" data-key="reviewTitle">Κριτικές Πελατών</h2>
      <p class="muted" data-key="reviewDesc">Μοιράσου την εμπειρία σου από το εστιατόριό μας!</p>

      <form id="reviewForm" style="margin-top:20px;">
        <label for="rating" data-key="ratingLabel">Βαθμολογία:</label>
        <div id="stars" style="font-size:28px;cursor:pointer;margin:6px 0;">★★★★★</div>

        <label for="comment" data-key="commentLabel">Σχόλιο:</label>
        <textarea id="comment" name="comment" rows="4" placeholder="Γράψε τη γνώμη σου..." required></textarea>

        <button type="submit" class="btn primary" data-key="submitReview">Υποβολή Κριτικής</button>
      </form>

      <div id="reviewList" style="margin-top:24px;"></div>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact">
    <div class="container">
      <h2 class="section-title" data-key="contactTitle">Στοιχεία επικοινωνίας</h2>
      <div class="contact">
        <div class="card">
          <h3 data-key="infoTitle">Στοιχεία</h3>
          <p class="muted" data-key="infoText">Γεωργίου Εμπειρίκου, Χώρα Άνδρου 84 500<br>Τηλέφωνο: 22820 23207</p>
          <a class="btn" href="#reservations" data-key="infoBtn">Κάνε κράτηση</a>
        </div>
        <div>
          <iframe loading="lazy" allowfullscreen referrerpolicy="no-referrer-when-downgrade" src="https://www.google.com/maps?q=37.8380382,24.9391268&z=16&output=embed"></iframe>
        </div>
      </div>
    </div>
  </section>

  <footer>
    <div class="container">© <span id="year"></span> <span data-key="footerText">Το Εστιατόριό μας • Όλα τα δικαιώματα διατηρούνται.</span></div>
  </footer>

  <footer>
    <div class="container">© <span id="year"></span> Το Εστιατόριό μας • Όλα τα δικαιώματα διατηρούνται.</div>
  </footer>

 <script>
document.addEventListener('DOMContentLoaded', () => {

  // βοηθητικά
  const $ = (sel, ctx = document) => ctx.querySelector(sel);
  const $$ = (sel, ctx = document) => Array.from((ctx || document).querySelectorAll(sel));

  // toast (αν δεν υπάρχει #alert θα χρησιμοποιήσει alert())
  const alertBox = $('#alert');
  function toast(msg, type = 'ok') {
    if (!alertBox) { alert(msg); return; }
    alertBox.textContent = msg;
    alertBox.className = 'notice' + (type === 'error' ? ' error' : '');
    alertBox.style.display = 'block';
    clearTimeout(alertBox._t);
    alertBox._t = setTimeout(() => { alertBox.style.display = 'none'; }, 4200);
  }

  /* =========================
     Μεταφράσεις (translations)
     ========================= */
  const translations = {
    gr: {
      brandName:"Εστιατόριο Ενδοχώρα",
      menuAbout:"Σχετικά",
      menuGallery:"Πιάτα",
      menuReserve:"Κρατήσεις",
      menuContact:"Επικοινωνία",
      badge1:"Μεσογειακή κουζίνα",
      badge2:"Από το χωράφι στο τραπέζι",
      badge3:"Vegan επιλογές",
      heroTitle:"Φρέσκες γεύσεις, ζεστή φιλοξενία.",
      heroText:"Από τοπικές πρώτες ύλες σε πιάτα που μιλούν από μόνα τους.",
      heroBtnReserve:"Κλείσε τραπέζι",
      heroBtnMenu:"Δες το μενού",
      aboutTitle:"Σχετικά με εμάς",
      aboutText:"Στην καρδιά της Άνδρου, δημιουργούμε καθημερινά εποχικά πιάτα με έμφαση στην ποιότητα.",
      reserveTitle:"Κρατήσεις",
      reserveText:"Συμπλήρωσε τα στοιχεία σου και λάβε άμεσα επιβεβαίωση.",
      reviewTitle:"Κριτικές Πελατών",
      reviewDesc:"Μοιράσου την εμπειρία σου από το εστιατόριό μας!",
      submitReview:"Υποβολή Κριτικής",
      contactTitle:"Στοιχεία επικοινωνίας",
      infoTitle:"Στοιχεία",
      infoBtn:"Κάνε κράτηση",
      footerText:"Το Εστιατόριό μας • Όλα τα δικαιώματα διατηρούνται.",
      nameLabel: "Ονοματεπώνυμο",
      phoneLabel: "Τηλέφωνο",
      dateLabel: "Ημερομηνία",
      timeLabel: "Ώρα",
      guestsLabel: "Άτομα",
      notesLabel: "Σχόλια",
      submitReserve: "Υποβολή κράτησης",
      ratingLabel: "Βαθμολογία:",
      commentLabel: "Σχόλιο:"
    },
    en: {
      brandName:"Endochora Restaurant",
      menuAbout:"About",
      menuGallery:"Dishes",
      menuReserve:"Reservations",
      menuContact:"Contact",
      badge1:"Mediterranean cuisine",
      badge2:"Farm-to-table",
      badge3:"Vegan options",
      heroTitle:"Fresh flavors, warm hospitality.",
      heroText:"From local ingredients to dishes that speak for themselves.",
      heroBtnReserve:"Book a Table",
      heroBtnMenu:"View Menu",
      aboutTitle:"About Us",
      aboutText:"In the heart of Andros, we create seasonal dishes with emphasis on quality and simplicity.",
      reserveTitle:"Reservations",
      reserveText:"Fill in your details and get instant confirmation.",
      reviewTitle:"Customer Reviews",
      reviewDesc:"Share your experience at our restaurant!",
      submitReview:"Submit Review",
      contactTitle:"Contact Information",
      infoTitle:"Details",
      infoBtn:"Book Now",
      footerText:"Our Restaurant • All rights reserved.",
      nameLabel: "Name",
      phoneLabel: "Phone",
      dateLabel: "Date",
      timeLabel: "Time",
      guestsLabel: "Guests",
      notesLabel: "Notes",
      submitReserve: "Submit Reservation",
      ratingLabel: "Rating:",
      commentLabel: "Comment:"
    }
  };

  // Εφαρμογή μεταφράσεων: βρίσκει όλα τα elements με data-key και βάζει το αντίστοιχο κείμενο
  function applyTranslations(lang) {
    const dict = translations[lang];
    if (!dict) return;
    $$('[data-key]').forEach(el => {
      const key = el.dataset.key;
      if (!key) return;
      const val = dict[key];
      if (typeof val === 'undefined') return;
      // Αν το στοιχείο είναι input/textarea και θέλουμε placeholder, χειριζόμαστε ξεχωριστά
      if (el.tagName === 'INPUT' || el.tagName === 'TEXTAREA') {
        // αν υπάρχει συγκεκριμένο placeholder key
        if (el.dataset.placeholderKey && dict[el.dataset.placeholderKey]) {
          el.placeholder = dict[el.dataset.placeholderKey];
        } else {
        }
      } else {
        el.textContent = val;
      }
    });

    // set placeholders for common inputs
    if ($('#name')) $('#name').placeholder = dict.nameLabel || '';
    if ($('#phone')) $('#phone').placeholder = dict.phoneLabel || '';
    if ($('#notes')) $('#notes').placeholder = dict.notesLabel || '';
    if ($('#comment')) $('#comment').placeholder = dict.commentLabel || $('#comment').placeholder || '';
  }

  // ενεργοποίηση κουμπιών γλώσσας
  const langButtons = $$('.lang-btn');
  function setActiveLangBtn(lang) {
    langButtons.forEach(b => {
      if (b.dataset.lang === lang) b.classList.add('active');
      else b.classList.remove('active');
    });
  }
  // add listeners 
  if (langButtons.length) {
    langButtons.forEach(btn => {
      btn.addEventListener('click', () => {
        const lang = btn.dataset.lang || 'gr';
        setActiveLangBtn(lang);
        applyTranslations(lang);
        localStorage.setItem('siteLang', lang);
        document.documentElement.lang = (lang === 'en' ? 'en' : 'el');
        toast(lang === 'en' ? 'Language switched to English' : 'Επιλέχθηκαν Ελληνικά');
      });
    });
  }

  // αρχική γλώσσα
  const savedLang = localStorage.getItem('siteLang') || (langButtons[0] && langButtons[0].dataset.lang) || 'gr';
  setActiveLangBtn(savedLang);
  applyTranslations(savedLang);
  document.documentElement.lang = (savedLang === 'en' ? 'en' : 'el');


  /* =========================
     Αρχική ρύθμιση Ημερομηνίας/Ωρας
     ========================= */
  (function initDateTime() {
    const dateInput = $('#date');
    const timeInput = $('#time');
    if (!dateInput || !timeInput) return;
    const d = new Date();
    const iso = d.toISOString().slice(0,10);
    dateInput.min = iso;
    dateInput.value = iso;
    const m = d.getMinutes();
    const add = (30 - (m % 30)) % 30;
    d.setMinutes(m + add);
    timeInput.value = d.toTimeString().slice(0,5);
  })();


    // Φόρμα Κρατήσεων (απλό demo - localStorage)
    
  const reservationForm = $('#reservationForm');
  if (reservationForm) {
    reservationForm.addEventListener('submit', (e) => {
      e.preventDefault();
      const fd = new FormData(reservationForm);
      const data = Object.fromEntries(fd.entries());
      // απλή επικύρωση
      if (!data.name || !data.phone || !data.date || !data.time || !data.guests) {
        toast('Συμπλήρωσε όλα τα πεδία.', 'error');
        return;
      }
      // αποθήκευση
      const key = `resv-${data.date}-${data.time}`;
      const list = JSON.parse(localStorage.getItem(key) || '[]');
      list.push(data);
      localStorage.setItem(key, JSON.stringify(list));
      reservationForm.reset();
      toast('Η κράτηση καταχωρήθηκε (demo). Θα επικοινωνήσουμε για επιβεβαίωση.');
    });
  }

  // Προβολή πρόχειρων κρατήσεων (αν υπάρχει #savedList)
  function renderSavedReservations() {
    const savedDiv = $('#savedList');
    if (!savedDiv) return;
    const keys = Object.keys(localStorage).filter(k => k.startsWith('resv-')).sort();
    if (!keys.length) {
      $('#saved') && ($('#saved').style.display = 'none');
      return;
    }
    const items = keys.flatMap(k => JSON.parse(localStorage.getItem(k) || '[]').map(r => ({ k, ...r })));
    savedDiv.innerHTML = items.map(r => `
      <div class="card" style="margin:8px 0">
        <strong>${r.name}</strong> — ${r.date} ${r.time} • ${r.guests} άτομα
        <div class="muted">${r.phone}${r.notes?` • ${r.notes}` : ''}</div>
      </div>`).join('');
    $('#saved') && ($('#saved').style.display = 'block');
  }
  renderSavedReservations();


 
    // Reviews 
     
  const starsContainer = $('#stars');
  const reviewForm = $('#reviewForm');
  const reviewList = $('#reviewList');

  // Helper: render reviews from storage
  function renderReviews() {
    const reviews = JSON.parse(localStorage.getItem('reviews') || '[]');
    if (!reviewList) return;
    if (!reviews.length) {
      reviewList.innerHTML = '<p class="muted">Δεν υπάρχουν κριτικές ακόμα.</p>';
      return;
    }
    reviewList.innerHTML = reviews.slice().reverse().map(r => `
      <div class="card" style="margin-bottom:10px">
        <div style="font-size:18px">${'★'.repeat(r.rating)}${'☆'.repeat(5 - r.rating)}</div>
        <p class="muted" style="margin-top:8px">${escapeHtml(r.comment)}</p>
      </div>
    `).join('');
  }

  // αρχική ρύθμιση stars 
  let currentRating = 0;
  if (starsContainer) {
    // κατασκευάζουμε 5 span
    starsContainer.innerHTML = '';
    for (let i = 1; i <= 5; i++) {
      const span = document.createElement('span');
      span.textContent = '☆';
      span.dataset.value = i;
      span.style.padding = '0 4px';
      span.style.userSelect = 'none';
      starsContainer.appendChild(span);
    }

    // mouseover / mouseout / click handlers
    starsContainer.addEventListener('mouseover', (e) => {
      if (!e.target.dataset.value) return;
      const v = Number(e.target.dataset.value);
      highlightStars(v);
    });
    starsContainer.addEventListener('mouseout', () => {
      highlightStars(currentRating);
    });
    starsContainer.addEventListener('click', (e) => {
      if (!e.target.dataset.value) return;
      currentRating = Number(e.target.dataset.value);
      highlightStars(currentRating);
    });
  }

  function highlightStars(n) {
    if (!starsContainer) return;
    Array.from(starsContainer.children).forEach((ch, idx) => {
      ch.textContent = (idx < n) ? '★' : '☆';
    });
  }

  // escape για ασφάλεια όταν εμφανίζουμε σχόλια
  function escapeHtml(str = '') {
    return String(str).replace(/[&<>"']/g, s => ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[s]));
  }

  if (reviewForm) {
    reviewForm.addEventListener('submit', (e) => {
      e.preventDefault();
      const commentEl = $('#comment');
      const comment = commentEl ? commentEl.value.trim() : '';
      if (!currentRating || !comment) {
        toast('Συμπλήρωσε βαθμολογία και σχόλιο.', 'error');
        return;
      }
      const list = JSON.parse(localStorage.getItem('reviews') || '[]');
      list.push({ rating: currentRating, comment });
      localStorage.setItem('reviews', JSON.stringify(list));
      // reset
      if (commentEl) commentEl.value = '';
      currentRating = 0;
      highlightStars(0);
      toast('Ευχαριστούμε για την κριτική!');
      renderReviews();
    });
  }

  renderReviews();

  // utility: ensure year in footer
  (function setYear() {
    const y = new Date().getFullYear();
    const el = $('#year');
    if (el) el.textContent = y;
  })();

  // αν χρειαστεί: εκθέτουμε μερικές συναρτήσεις στο window (για debugging)
  window.__endocha_helpers = { applyTranslations, renderReviews, renderSavedReservations };

}); // DOMContentLoaded
</script>
