# Aplikasi-Berbasis-Platform-
Aplikasi Berbasis Platform tugas 3 


/sika/
- index.html (dari Tugas 2, ditambah link css)
- css/
   - style.css (EKSTERNAL - ini intinya)
- docs/
   - style-guide.md
   - responsive-test-matrix.md
   - ui-security-checklist.md
   - peer-review-note.md


<link rel="stylesheet" href="css/style.css">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

/* STYLE GUIDE - SIKA */
:root {
  --primary: #1a56db;
  --bg: #f8fafc;
  --text: #1e293b;
  --border: #e2e8f0;
  --error: #dc2626;
  --radius: 8px;
  --font: 'Inter', system-ui, sans-serif;
}

* { margin:0; padding:0; box-sizing:border-box; }
body { font-family: var(--font); color: var(--text); background: var(--bg); line-height: 1.6; }

/* LAYOUTING - Flexbox untuk Header & Grid untuk Content */
header { 
  display: flex; justify-content: space-between; align-items: center;
  padding: 16px 32px; background: white; border-bottom: 1px solid var(--border);
}
.main-container {
  display: grid;
  grid-template-columns: 250px 1fr;
  gap: 24px;
  padding: 24px;
}
.card {
  background: white; border: 1px solid var(--border); border-radius: var(--radius);
  padding: 20px;
}

/* VISUAL HIERARCHY & STATES - Ini untuk Security Focus */
input, button { font-family: inherit; padding: 10px 14px; border-radius: var(--radius); border: 1px solid var(--border); }
input:focus { outline: 2px solid var(--primary); border-color: transparent; } /* focus state WAJIB dapat diuji */
input[aria-invalid="true"] { border-color: var(--error); }
.error-message { color: var(--error); font-size: 0.875rem; }
button { background: var(--primary); color: white; cursor: pointer; }
button:hover { opacity: 0.9; }
button:focus-visible { outline: 3px solid var(--primary); outline-offset: 2px; }

/* RESPONSIVE - Media Query */
@media (max-width: 768px) {
  .main-container { grid-template-columns: 1fr; }
  header { flex-direction: column; gap: 12px; padding: 16px; }
}
@media (max-width: 480px) {
  .main-container { padding: 12px; }
}

/* SALAH - JANGAN LAKUKAN */
.admin-menu { display: none; } /* dikira user biasa nggak bisa lihat */
.nim-rahasia { color: transparent; }
