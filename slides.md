---
marp: true
theme: custom
paginate: true
math: true
_class: lead
backgroundColor: '#ffffff'
style: |
  /* --- Custom theme variables --- */
  :root {
    --primary: #0f62fe;
    --accent: #7f5af0;
    --muted: #6b6b6b;
    --bg: #ffffff;
    --card-bg: #fbfcff;
    --text: #0b1021;
    --mono: 'SFMono-Regular', Menlo, Monaco, "Courier New", monospace;
  }

  /* Base */
  section {
    font-family: Inter, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    color: var(--text);
  }

  /* Header */
  h1, h2, h3 { color: var(--primary); margin-bottom: 0.25em; }

  /* Code style */
  code, pre {
    font-family: var(--mono);
    background: rgba(11,16,33,0.04);
    padding: 0.2em 0.4em;
    border-radius: 6px;
  }

  /* Card */
  .card {
    background: var(--card-bg);
    border-radius: 12px;
    padding: 1.2rem;
    box-shadow: 0 6px 18px rgba(11,16,33,0.06);
  }

  /* Footer styling: show email on left and page numbers on right */
  footer.marp-footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 0.85rem;
    color: var(--muted);
    padding: 0.6rem 1rem;
    width: 100%;
  }

  footer.marp-footer .email { font-weight: 600; color: var(--accent); }
  footer.marp-footer .pagenum::after {
    /* Marp supports paginate; these counters work in many renderers */
    content: counter(page) " / " counter(pages);
  }

  /* Title slide tweaks when background used */
  section.hero {
    color: white;
    text-shadow: 0 4px 18px rgba(0,0,0,0.45);
  }

---

<!-- Title slide with a background image -->
<!--
  Use Marp/Marpit background directive. Replace the URL below with your chosen image URL
  or commit an image in the repo and reference it via relative path (e.g., ./assets/bg.jpg).
-->
<!-- background: url('https://raw.githubusercontent.com/VS-Abhijith/marp-slides/main/assets/title-bg.jpg') center / cover no-repeat -->
class: hero

# Product Documentation — WidgetPro SDK
### Technical documentation & examples for developers

<div style="margin-top:1rem;font-size:0.9rem">Author: Technical Writing — <span style="font-weight:700">22ds3000188@ds.study.iitm.ac.in</span></div>

<footer class="marp-footer">
  <div class="email">22ds3000188@ds.study.iitm.ac.in</div>
  <div class="pagenum"></div>
</footer>

---

# Goals & Format
- Maintainable in **git** (single Markdown file + assets folder)  
- Convertible to PDF, HTML, PPTX via Marp CLI or CI pipeline  
- Lightweight theme, consistent layout, and math support

<footer class="marp-footer">
  <div class="email">22ds3000188@ds.study.iitm.ac.in</div>
  <div class="pagenum"></div>
</footer>

---

# How to render
1. Install Marp CLI: `npm i -g @marp-team/marp-cli`  
2. Render to HTML: `marp slides.md`  
3. Export to PDF: `marp --pdf slides.md`  
4. CI: add job to render and attach PDF to release

<footer class="marp-footer">
  <div class="email">22ds3000188@ds.study.iitm.ac.in</div>
  <div class="pagenum"></div>
</footer>

---

# Example: API Overview
<div class="card">
**Endpoints**
- `GET /v1/widgets` — list widgets  
- `POST /v1/widgets` — create widget (JSON body)  
- `GET /v1/widgets/:id` — fetch widget
</div>

```http
GET /v1/widgets HTTP/1.1
Host: api.widgetpro.example
Authorization: Bearer <token>

---

# Contact
For more information, reach out at **22ds3000188@ds.study.iitm.ac.in**

---

# Goals & Format

**Contact:** 22ds3000188@ds.study.iitm.ac.in

- Maintainable in **git** (single Markdown file + assets folder)  
- Convertible to PDF, HTML, PPTX via Marp CLI or CI pipeline  
- Lightweight theme, consistent layout, and math support

