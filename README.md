# 四枝鉛筆作文營靜態網站

這是一個無需建置流程的靜態宣傳網站，可直接部署到 GitHub Pages、Netlify、Cloudflare Pages 或 Vercel。

## 本機預覽

在專案根目錄執行：

```powershell
python -m http.server 8000
```

然後開啟 `http://127.0.0.1:8000/`。

## 替換圖片

目前倉庫沒有提供正式圖片，因此 `assets/` 內放的是清楚標示的佔位圖。

- 將正式標誌替換為 `assets/logo.svg`，或改用 `assets/logo.png` 後同步更新 `index.html`。
- 將正式海報替換為 `assets/poster.svg`，或改用 `assets/poster.png` 後同步更新 `index.html` 的海報與 Open Graph 圖片。
- 將原始報名 QR Code 放入 `assets/registration-qr.png`，再把 `index.html` 中的 `assets/registration-qr-placeholder.svg` 改成該檔名。不要重新繪製、裁切、壓縮或加濾鏡。
- 將 Tony 照片放入 `assets/tony.jpg`，並更新講師照片路徑。
- 將松本照片放入 `assets/matsumoto.jpg`，並更新講師照片路徑。

## 更新講師簡介

在 `index.html` 搜尋：

```html
<!-- EDIT: Instructor biographies -->
```

只填入已確認的學經歷與介紹，不要加入未確認的學位、證照、機構、獎項、出版或年資。

## 新增 LINE 群組連結

在 `index.html` 搜尋：

```html
<!-- EDIT: LINE group link -->
```

若日後有公開 LINE 連結，可新增按鈕或文字。若仍需完成報名後邀請，維持目前文字即可。

## 更新活動地點

在 `index.html` 搜尋：

```html
<!-- EDIT: Confirmed activity location -->
```

確認可公開後再加入地址。若加入地址，也請同步更新 Event JSON-LD 的 `location`。

## 修改費用與日期

在 `index.html` 搜尋「報名費用」、「活動資訊」與 JSON-LD 的 `startDate`、`endDate`、`offers`。可同時更新頁面顯示文字與結構化資料。

## 部署到 GitHub Pages

1. 將 `index.html`、`styles.css`、`script.js`、`assets/`、`README.md` 推送到 GitHub repository。
2. 到 repository 的 Settings -> Pages。
3. Source 選擇主要分支與根目錄。
4. 發布後，把 `index.html` 的 canonical URL 和 JSON-LD `url` 改成正式網址。

## 部署到 Netlify

1. 在 Netlify 新增 site 並連接 Git repository。
2. Build command 留空。
3. Publish directory 設為專案根目錄。
4. 部署後更新 canonical URL。

## 測試報名連結與 QR Code

- 搜尋 `https://forms.gle/HjCH9zStH4BdLYuB7`，確認所有報名 CTA 都使用同一個網址。
- 正式 QR Code 補上後，用手機掃描確認會開啟同一個 Google Form。
- QR Code 必須維持白底、清楚、未變形，且不要套用濾鏡或重新繪製。
