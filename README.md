# 個人投影片

## Usage

### Package.json
- `npm run start`: 開啟本地伺服器測試環境。
- `npm run build`: 建立網頁靜態檔案。
- `npm run push`: 將專案推送到遠端儲存庫，預設是 Github，並且透過 `Github Action` 切換到分支 `gh-pages` 部屬網頁靜態檔案，

- `npm install --production`: 下載專案發布環境依賴套件，包含 `reveal-md`。
- `npm install`: 下載專案開發環境依賴套件，包含 `reveal-md`、`bootstrap`。

## Structure

- content: 投影片 markdown 檔案。
- static: 發布專案時要複製到專案內的檔案。
- theme: 網頁主題，使用 `sass` 編譯成 css。
  - all.scss: 投影片樣式表，使用 Tailwind。
  - listing.scss: 主頁樣式表，單獨使用 Bootstrap(_variables.scss)
- listing.html: 主頁模板
- reveal.html: 投影片頁面模板
- reveal.json: 投片片設定
- reveal-md.json: markdown 文檔設定

## 已知問題

- 提交版本時有可能修改到檔案的換行字元（CRLF/LF），導致在不同作業系統上，markdown 語法識別 `\n\n---\n\n` 相關的分頁法時，因為換行字元不同而導致渲染結果遭到破壞。

- 投影片頁面無法使用 `bootstrap` 套件，在開啟 `Overview Mode` 時會渲染失敗。因此投影片頁面改為使用 `Tailwind` 渲染，主頁面照舊使用 `bootstrap`。
