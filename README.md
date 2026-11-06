# 📊 FEEDLYTICS — Instagram Performance Hub

FEEDLYTICS is an executive-level, interactive Power BI performance dashboard built to analyze Instagram post engagement, reach distribution, follower dynamics, and content category performance. 

Designed with a custom dark-mode UI inspired by modern mobile analytics apps, it features custom-built DAX slicers, interactive KPI metrics, and seamless cross-filtering capabilities.

---
<img width="1322" height="737" alt="WhatsApp Image 2026-11-06 at 8 48 46 PM" src="https://github.com/user-attachments/assets/4f8e572c-d26b-48c9-ba1e-c04fd531d0d6" />

## 🌟 Key Features

* **Custom Category Navigation Slicer:** Powered by a dynamic DAX `SWITCH` measure and direct CDN-hosted vector icons for smooth, CORS-compliant category filtering.
* **Interactive Content Breakdown:** Evaluates share rates, impression counts, and follower gains across post types (Photo, Video, Carousel, Reel).
* **3D Visual Hook Design:** Built using a custom layered background canvas designed for optimal visual hierarchy and zero-clutter scanning.
* **Dynamic DAX Aggregations:** Pre-calculated key performance indicators including engagement rate, reach distribution, and total saves/shares.

---

## 📐 Data Architecture & Key DAX Measures

### Category Icon Slicer (`Slicer_Icon_URL`)
Standardizes category selection while ensuring high-compatibility image rendering:

```dax
Slicer_Icon_URL = 
VAR CurrentCategory = TRIM(LOWER(SELECTEDVALUE('Instagram_Post_Analytics'[content_category])))
RETURN
SWITCH(
    CurrentCategory,
    "beauty", "[https://raw.githubusercontent.com/twitter/twemoji/master/assets/72x72/1f484.png](https://raw.githubusercontent.com/twitter/twemoji/master/assets/72x72/1f484.png)",
    "comedy", "[https://raw.githubusercontent.com/twitter/twemoji/master/assets/72x72/1f3ad.png](https://raw.githubusercontent.com/twitter/twemoji/master/assets/72x72/1f3ad.png)",
    "fashion", "[https://raw.githubusercontent.com/twitter/twemoji/master/assets/72x72/1f457.png](https://raw.githubusercontent.com/twitter/twemoji/master/assets/72x72/1f457.png)",
    "fitness", "[https://raw.githubusercontent.com/twitter/twemoji/master/assets/72x72/1f3cb.png](https://raw.githubusercontent.com/twitter/twemoji/master/assets/72x72/1f3cb.png)",
    "food", "[https://raw.githubusercontent.com/twitter/twemoji/master/assets/72x72/1f354.png](https://raw.githubusercontent.com/twitter/twemoji/master/assets/72x72/1f354.png)",
    "lifestyle", "[https://raw.githubusercontent.com/twitter/twemoji/master/assets/72x72/1f343.png](https://raw.githubusercontent.com/twitter/twemoji/master/assets/72x72/1f343.png)",
    "music", "[https://raw.githubusercontent.com/twitter/twemoji/master/assets/72x72/1f3b5.png](https://raw.githubusercontent.com/twitter/twemoji/master/assets/72x72/1f3b5.png)",
    "photography", "[https://raw.githubusercontent.com/twitter/twemoji/master/assets/72x72/1f4f7.png](https://raw.githubusercontent.com/twitter/twemoji/master/assets/72x72/1f4f7.png)",
    "technology", "[https://raw.githubusercontent.com/twitter/twemoji/master/assets/72x72/1f4bb.png](https://raw.githubusercontent.com/twitter/twemoji/master/assets/72x72/1f4bb.png)",
    "[https://raw.githubusercontent.com/twitter/twemoji/master/assets/72x72/1f310.png](https://raw.githubusercontent.com/twitter/twemoji/master/assets/72x72/1f310.png)"
)
```

## 🛠️ Tech Stack & Tools
Analytics & Visualization: Power BI Desktop, DAX, Power Query (M)

Visual Styling & Assets: GitHub Raw CDN (Twemoji), PowerPoint/Figma (Canvas Frame Design)

Deployment & Hosting: Power BI Service / Web Embed, Vercel

## 🚀 How to Run Locally

1. **Download the file directly:** 
   [Download Insta-Analytics.pbix](https://github.com/Amrisha7/Instagram_Performance_Analysis/raw/main/Insta-Analytics.pbix)

2. **Or clone via terminal:**
   ```bash
   git clone [https://github.com/Amrisha7/Instagram_Performance_Analysis.git](https://github.com/Amrisha7/Instagram_Performance_Analysis.git)
   ```
Ensure an active internet connection so external vector image icons load in the slicer visual.
