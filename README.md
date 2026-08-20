# IT645 Lab Assignment 2 - Pageturner Books SEO & Performance Guide

This directory contains the completed assignment files for **Pageturner Books** website, incorporating Schema.org JSON-LD structured data, XML & HTML sitemaps, `robots.txt`, Flexbox performance optimization page, keyword research, and validation procedures.

---

## 📁 Final Project Structure

```text
LAB_2/
├── index.html            # Main landing page with BookStore JSON-LD & SEO metadata
├── menu.html             # Categorized Book Store Catalog & Menu
├── contact.html          # Store contact details, opening hours, address & contact form
├── performance.html      # Flexbox book cards, lazy-loaded video & image performance showcase
├── sitemap.xml           # Standard XML sitemap (v0.9 schema)
├── sitemap.html          # Visually styled HTML sitemap for visitors
├── robots.txt            # Search crawler directives disallowing /admin/ and /test/
├── keyword-research.md   # Semrush keyword research report, gap analysis & strategy
└── README.md             # Validation instructions & validation tool links
```

---

## 🛠️ Step-by-Step Validation Instructions

### 1. JSON-LD Structured Data Validation

**Validation Tools:**
- Schema.org Validator: `https://validator.schema.org/`
- Redirection.io Structured Data Tester: `https://redirection.io/tools/structured-data/test`

**Steps to Validate:**
1. Open `index.html` in your text editor and copy the entire file contents (or extract the `<script type="application/ld+json">` block).
2. Visit `https://validator.schema.org/`.
3. Click on the **Code Snippet** tab.
4. Paste the HTML or JSON-LD code into the box and click **RUN TEST**.
5. **Expected Result:** The validator will detect `@type: "BookStore"` with zero errors and zero warnings, confirming valid properties (`name`, `description`, `url`, `telephone`, `address`, `openingHoursSpecification`).

---

### 2. XML Sitemap Validation

**Validation Tool:**
- XML-Sitemaps Validator: `https://www.xml-sitemaps.com/validate-xml-sitemap.html`

**Steps to Validate:**
1. If your site is hosted live or via local tunnel (e.g. ngrok / GitHub Pages), paste your URL pointing to `sitemap.xml` into `https://www.xml-sitemaps.com/validate-xml-sitemap.html`.
2. Alternatively, validate the raw XML structure locally using an XML syntax validator or Python:
   ```bash
   python -c "import xml.etree.ElementTree as ET; ET.parse('sitemap.xml'); print('XML Sitemap is Valid!')"
   ```
3. **Expected Result:** The validator confirms that `sitemap.xml` is valid XML with correctly formatted `<url>`, `<loc>`, `<lastmod>`, `<changefreq>`, and `<priority>` elements.

---

### 3. Page Performance & Core Web Vitals Validation

**Validation Tool:**
- Google PageSpeed Insights: `https://pagespeed.web.dev/`

**Steps to Validate:**
1. Deploy `performance.html` to a public URL (or local host tunnel like ngrok / Vercel / GitHub Pages).
2. Enter the page URL into `https://pagespeed.web.dev/` and click **Analyze**.
3. Evaluate the **Core Web Vitals**:
   - **LCP (Largest Contentful Paint):** Target `< 2.5s` (Achieved via compressed inline vector SVG covers and zero heavy external scripts).
   - **INP (Interaction to Next Paint):** Target `< 200ms` (Achieved via lightweight pure CSS interactions).
   - **CLS (Cumulative Layout Shift):** Target `< 0.1` (Achieved by specifying explicit `width` and `height` attributes on all `<img>` and `<video>` tags).
4. Verify that lazy loading (`loading="lazy"` and `preload="none"`) is detected by Lighthouse.

---

## 📝 Manual Submission Checklist

Before submitting the assignment, ensure you have gathered:
- [x] Updated `index.html` containing valid `<script type="application/ld+json">`.
- [x] `menu.html`, `contact.html`, and `performance.html` created and linked.
- [x] `sitemap.xml` and `sitemap.html` placed in the root directory.
- [x] `robots.txt` placed in the root directory.
- [x] `keyword-research.md` updated with your live Semrush metrics (if accessing Semrush account).
- [ ] Screenshot of **Schema.org Validator** results for `index.html`.
- [ ] Screenshot of **XML Sitemap Validator** results for `sitemap.xml`.
- [ ] Screenshot of **Google PageSpeed Insights** score before/after for `performance.html`.
