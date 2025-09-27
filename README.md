
# 🔍 PyBingFetch

*A Python library to fetch image URLs and download them from Bing.com using multithreading.*

---

## 🚀 Features

* ✅ Fetch high-quality image URLs from Bing.com
* ✅ Download images with **multithreading** for faster performance
* ✅ Support for **file type filters** (`png`, `jpg`, etc.)
* ✅ Support for **Bing UI filters** (`aspect-square`, `color2-bw`, etc.)
* ✅ Customize with **extra query params** (e.g., `&first=100&tsc=ImageBasicHover`)
* ✅ Choose output directory & thread pool size
* ✅ Option to only fetch URLs without downloading

---

## 🛠️ Requirements

* **Google Chrome Browser**
* **Chromedriver** → [Download here](https://chromedriver.chromium.org/downloads)
* Add `chromedriver` to your **PATH**

---

## 📦 Installation

```bash
pip install bing-images
```

---

## ⚡ Usage

### Fetch Image URLs

```python
from bing_images import bing

urls = bing.fetch_image_urls(
    "cat", 
    limit=10, 
    file_type='png', 
    filters='+filterui:aspect-square+filterui:color2-bw',
    extra_query_params='&first=1'
)

print(f"{len(urls)} images fetched.")
for i, url in enumerate(urls, 1):
    print(f"{i}: {url}")
```

✅ **Run**

```bash
python fetch_image_urls.py
```

---

### Download Images with Multithreading

```python
from bing_images import bing

bing.download_images(
    "cat",
    20,
    output_dir="cats_dataset",
    pool_size=10,
    file_type="png",
    force_replace=True,
    extra_query_params='&first=1'
)
```

✅ **Run**

```bash
python download.py
```

---

### Download with Filters

```python
from bing_images import bing

bing.download_images(
    "cat",
    20,
    output_dir="cats_dataset",
    pool_size=20,
    file_type="png",
    filters='+filterui:aspect-square+filterui:color2-bw',
    force_replace=True
)
```

---

## 📂 Project Structure

```
PyBingFetch/
│── fetch_image_urls.py   # Example for fetching URLs
│── download.py           # Example for downloading
│── download-square-bw.py # Example with filters
│── README.md             # Documentation
```

---

## 🧑‍💻 About

PyBingFetch is a **lightweight, multithreaded image scraper** for Bing.com. Perfect for:

* Training **AI/ML datasets**
* Collecting **domain-specific images**
* Quick **image research**

---

