# WebAR – видео върху маркер / Image marker video

**Безплатно WebAR приложение** с HTML, JavaScript, A-Frame и AR.js. При насочване на камерата към маркер/снимка автоматично се възпроизвежда видео върху него. Без мобилно приложение, без платени SDK, без лимити. Готово за безплатен хостинг в GitHub Pages.

---

## Къде задавам снимката (маркера) и видеото?

| Какво искате | Къде го задавате |
|--------------|------------------|
| **Кое видео да се пуска** | Файл **`video.mp4`** в папката на проекта. Или в **index.html** и **nft.html** сменете `src="video.mp4"` на името на вашия файл (напр. `src="moeto-video.mp4"`). |
| **Коя снимка да е маркер (index.html)** | Снимката е **фиксирана** – това е маркерът Hiro. Отпечатайте [hiro.png](https://raw.githubusercontent.com/AR-js-org/AR.js/master/data/images/hiro.png) и насочете камерата към него. Не променяте нищо в кода. |
| **Коя снимка да е маркер (nft.html)** | 1) Изберете **ваша снимка**. 2) Генерирайте маркер чрез [NFT Marker Creator (уеб)](https://ar-js-org.github.io/NFT-Marker-Creator/) или **локално с Node.js** (вижте по-долу „Ако уеб сайтът крашва“). 3) Сложете 3-те файла (`.fset`, `.fset3`, `.iset`) в папката на проекта. 4) В **nft.html** сменете `MARKER_NAME` на името на маркера. |

**Обобтено:** Видео = файл `video.mp4` (или сменете `src` в HTML). Маркер при **index.html** = отпечатан Hiro; при **nft.html** = вашата снимка чрез NFT Marker Creator + трите файла + `MARKER_NAME` в nft.html.

В проекта вече има готова снимка за маркер: **`marker-image.png`** (Sonsuz Rota). За **nft.html** генерирайте от нея 3-те файла (вижте **MARKER-INSTRUCTIONS.txt**).

---

## Варианти

| Файл           | Маркер                 | Как работи                                                                                                                                                 |
| -------------- | ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **index.html** | Pattern (Hiro)         | Отпечатайте [Hiro маркера](https://raw.githubusercontent.com/AR-js-org/AR.js/master/data/images/hiro.png), насочете камерата – видео се пуска автоматично. |
| **nft.html**   | Собствена снимка (NFT) | Генерирайте маркер от снимка с [NFT Marker Creator](https://ar-js-org.github.io/NFT-Marker-Creator/) или локално с Node.js (вижте по-долу). Сложете `.fset`, `.fset3`, `.iset` в проекта. |

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

1. Изберете **ясна снимка** с контраст и детайли.
2. Генерирайте маркера по един от следните начини:
   - **Уеб:** [NFT Marker Creator (AR-js-org)](https://ar-js-org.github.io/NFT-Marker-Creator/) – качете снимката и свалете 3-те файла. Ако сайтът крашва, вижте секцията по-долу.
   - **Локално (Node.js):** вижте „Ако уеб сайтът крашва“.
3. Сложете файловете `име.fset`, `име.fset3`, `име.iset` в папката на проекта.
4. В **nft.html** сменете `MARKER_NAME = 'marker'` на вашето име (напр. `'mylogo'`).
5. Отворете **nft.html** през HTTPS и насочете камерата към същата снимка – видео ще се пусне върху нея.

#### Ако уеб NFT Marker Creator не отваря или крашва

Уеб линковете понякога не работят (блокирани, сриване). Използвайте **локално генериране** (без уебсайт):

- **Скрипт в проекта (най-лесно):** От папката на проекта стартирайте в PowerShell:
  ```powershell
  .\generate-marker.ps1
  ```
  Скриптът изисква [Node.js](https://nodejs.org/). Той ще свали генератора, ще генерира 3-те файла от `marker-image.png` и ще ги копира в проекта. Вижте **MARKER-INSTRUCTIONS.txt**.

- **Ръчно с Node.js:** Клонирайте [NFT-Marker-Creator](https://github.com/AR-js-org/NFT-Marker-Creator), `npm install`, после `node app.js -i marker-image.png`. Файловете са в `output/` – копирайте ги в папката на WebAR.

- **Уеб алтернативи** (ако при вас отварят): [ar-js-org](https://ar-js-org.github.io/NFT-Marker-Creator/) · [carnaux](https://carnaux.github.io/NFT-Marker-Creator/) · [webarkit](https://www.webarkit.org/tools/NFT_Marker_Creator/). Намалете снимката до 800 px ако крашва.

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

Free WebAR app: point the camera at a printed **Hiro marker** (`index.html`) or at your **own image** (`nft.html`); video plays automatically on the marker. No app, no paid SDKs, no usage limits. Add `video.mp4` and (for NFT) the three descriptor files from [NFT Marker Creator](https://ar-js-org.github.io/NFT-Marker-Creator/) or generate them locally with the Node.js version if the web app crashes. Host for free on GitHub Pages via repo Settings → Pages.

## Özet (TR)

Ücretsiz WebAR: kamerayı **Hiro marker**’a (`index.html`) veya **kendi görselinize** (`nft.html`) tutun; video otomatik oynar. Uygulama, ücretli SDK ve kullanım limiti yok. `video.mp4` ekleyin; NFT için [NFT Marker Creator](https://ar-js-org.github.io/NFT-Marker-Creator/) ile üretilen üç dosyayı projeye koyun. GitHub Pages ile ücretsiz yayınlayın (Settings → Pages).
