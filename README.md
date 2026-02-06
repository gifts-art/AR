# WebAR – видео върху маркер / Image marker video

**Безплатно WebAR приложение** с HTML, JavaScript, A-Frame и AR.js. При насочване на камерата към маркер/снимка автоматично се възпроизвежда видео върху него. Без мобилно приложение, без платени SDK, без лимити. Готово за безплатен хостинг в GitHub Pages.

---

## Варианти

| Файл           | Маркер                 | Как работи                                                                                                                                                 |
| -------------- | ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **index.html** | Pattern (Hiro)         | Отпечатайте [Hiro маркера](https://raw.githubusercontent.com/AR-js-org/AR.js/master/data/images/hiro.png), насочете камерата – видео се пуска автоматично. |
| **nft.html**   | Собствена снимка (NFT) | Качете снимка в [NFT Marker Creator](https://carnaux.github.io/NFT-Marker-Creator/), свалете `.fset`, `.fset3`, `.iset` и ги сложете в проекта.            |

И двата варианта използват **едно и също видео**: файлът `video.mp4` в корена на проекта.

---

## Стъпки за стартиране

### 1. Добавете видео

- Поставете вашето видео в папката на проекта като **`video.mp4`** (или сменете името в HTML на ваш файл).
- Препоръчително: кратко видео, формат MP4 (H.264), не твърде голям размер за по-бързо зареждане.

### 2. Вариант A – Pattern маркер (index.html)

- Отпечатайте маркера **Hiro**: [hiro.png](https://raw.githubusercontent.com/AR-js-org/AR.js/master/data/images/hiro.png).
- Отворете **index.html** през HTTPS (напр. чрез GitHub Pages или локален сървър с HTTPS).
- Разрешите достъп до камерата и насочете към отпечатания маркер – видео ще се пусне върху него.

### 3. Вариант B – Собствена снимка / NFT (nft.html)

1. Изберете **ясна снимка** с контраст и детайли (препоръчително висока разделителна способност).
2. Отворете [NFT Marker Creator (Web)](https://carnaux.github.io/NFT-Marker-Creator/).
3. Качете снимката и генерирайте маркера – ще свалите **3 файла**: `име.fset`, `име.fset3`, `име.iset`.
4. Копирайте тези 3 файла в папката на проекта. Ако името е например `mymarker`, файловете са `mymarker.fset`, `mymarker.fset3`, `mymarker.iset`.
5. В **nft.html** намерете реда с `url="marker"` и сменете на вашето име, напр. `url="mymarker"` (без разширение).
6. Отворете **nft.html** през HTTPS и насочете камерата към **същата снимка** (на екран или отпечатана) – видео ще се пусне върху нея.

---

## Хостинг в GitHub (безплатно)

1. Създайте нов репо в GitHub (напр. `my-webar`).
2. Качете в репото:
   - `index.html`
   - `nft.html` (ако ползвате NFT)
   - `video.mp4`
   - при NFT: трите файла `.fset`, `.fset3`, `.iset`
3. В репото: **Settings → Pages → Source**: изберете **GitHub Actions** или **Deploy from a branch**, branch **main**, папка **/ (root)**.
4. След няколко минути приложението ще е на адрес:  
   `https://<потребител>.github.io/<име-на-репо>/`  
   Напр. `https://username.github.io/my-webar/`

**Важно:** Камерата работи само при **HTTPS** (вкл. GitHub Pages). Локално тестване изисква HTTPS или `localhost`.

---

## Технологии

- **A-Frame** – WebGL сцена
- **AR.js** – маркер (pattern) и image tracking (NFT)
- Само HTML + JavaScript, без сървърна логика
- Всичко е безплатно и с отворен код

---

## Summary (EN)

Free WebAR app: point the camera at a printed **Hiro marker** (`index.html`) or at your **own image** (`nft.html`); video plays automatically on the marker. No app, no paid SDKs, no usage limits. Add `video.mp4` and (for NFT) the three descriptor files from [NFT Marker Creator](https://carnaux.github.io/NFT-Marker-Creator/). Host for free on GitHub Pages via repo Settings → Pages.

## Özet (TR)

Ücretsiz WebAR: kamerayı **Hiro marker**’a (`index.html`) veya **kendi görselinize** (`nft.html`) tutun; video otomatik oynar. Uygulama, ücretli SDK ve kullanım limiti yok. `video.mp4` ekleyin; NFT için [NFT Marker Creator](https://carnaux.github.io/NFT-Marker-Creator/) ile üretilen üç dosyayı projeye koyun. GitHub Pages ile ücretsiz yayınlayın (Settings → Pages).
