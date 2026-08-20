# Performance Optimization Report
**Course:** IT645 - Web Development & SEO (Lab Assignment 2 - Part E)  
**Target Page:** `performance.html`

---

## 1. Objective

The objective of this task was to evaluate and optimize the performance of the Pageturner Books collection page (`performance.html`) using Google PageSpeed Insights while maintaining all required assignment features, visual styling, and responsive layouts.

---

## 2. Page Features

The target page `performance.html` includes the following core components:
* **Book Image Collection:** A curated display of 5 book cover images with titles, authors, descriptions, and category badges.
* **Flexbox Layout:** A responsive, dynamic CSS Flexbox container (`display: flex; flex-wrap: wrap; gap: 25px;`) for rendering the book cards seamlessly across screen sizes.
* **Video Element with Controls:** An HTML5 `<video controls preload="none">` player featuring an embedded poster image and video stream detailing rare book collections.

---

## 3. Before Optimization

Below are the Google PageSpeed Insights (Desktop) performance metrics recorded before optimization:

| Metric | Before |
|---|---:|
| Performance Score | 100 |
| LCP | 0.3 s |
| CLS | 0 |
| FCP | 0.2 s |
| Total Blocking Time | 0 ms |
| Speed Index | 0.3 s |

---

## 4. Performance Optimizations

The following performance optimizations were implemented in `performance.html`:

1. **Layout Shift Prevention (CLS = 0):**
   - Explicit `width="180"` and `height="250"` attributes were assigned to all 5 `<img>` elements.
   - Reserved aspect ratio (`aspect-ratio: 16 / 9`) was applied to the video container wrapper to prevent layout recalculations during media rendering.

2. **LCP & Selective Image Lazy Loading:**
   - The primary above-the-fold image (Book Card 1) was configured with `fetchpriority="high"` without lazy loading, enabling immediate fetch by the browser parser to optimize Largest Contentful Paint (LCP).
   - Below-the-fold images (Book Cards 2 through 5) utilize `loading="lazy"` to defer image loading until the user scrolls near their viewport position.

3. **Lightweight Image Formatting:**
   - Utilized compressed SVG vector assets (Data URIs) for book covers, eliminating heavy raster image overhead and external network round-trips.

4. **Video Preloading Optimization:**
   - Configured `<video>` with `preload="none"` and an SVG poster frame to prevent initial media downloading until the user clicks Play.

5. **Zero Render-Blocking Overhead:**
   - Built strictly with pure semantic HTML5 and vanilla CSS without external JavaScript libraries or heavy CSS frameworks.

---

## 5. After Optimization

Below are the Google PageSpeed Insights (Desktop) performance metrics recorded after optimization:

| Metric | After |
|---|---:|
| Performance Score | 100 |
| LCP | 0.3 s |
| CLS | 0 |
| FCP | 0.3 s |
| Total Blocking Time | 0 ms |
| Speed Index | 0.3 s |

---

## 6. Before vs After Comparison

| Metric | Before | After | Change |
|---|---:|---:|---:|
| Performance Score | 100 | 100 | 0 |
| LCP | 0.3 s | 0.3 s | 0 s |
| CLS | 0 | 0 | 0 |
| FCP | 0.2 s | 0.3 s | +0.1 s |
| Total Blocking Time | 0 ms | 0 ms | 0 ms |
| Speed Index | 0.3 s | 0.3 s | 0 s |

### Comparison Analysis
* The **Performance Score** remained at **100** before and after optimization.
* **Largest Contentful Paint (LCP)** remained optimal at **0.3 seconds**.
* **Cumulative Layout Shift (CLS)** remained perfect at **0**, demonstrating zero visual layout shifts.
* **First Contentful Paint (FCP)** showed a minor variation of **+0.1 seconds** (from 0.2s to 0.3s). This slight fluctuation is normal as Google PageSpeed Insights runs rely on simulated network testing and estimated laboratory measurements.

---

## 7. Conclusion

In conclusion, the `performance.html` page maintained an excellent Google PageSpeed Insights performance score of 100 after optimization. Key Core Web Vitals remained optimal, with LCP staying at 0.3 seconds and CLS staying at 0, demonstrating that all assignment optimizations were successfully integrated while preserving complete page functionality and user accessibility.
