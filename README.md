# 俊泰工程有限公司 (Juntai Engineering Co., Ltd.) - 企業官方網站

這是一個基於 Vue.js 3 與 Nuxt.js 所建構的企業官方網站專案，專為「俊泰工程有限公司」所設計。網站主打「工業科技風 (Industrial Tech)」，採用深色系主題（Slate / Blue），並結合了工程圖面、儀表板元素的 UI 設計，旨在展示其在 EPOXY 樹脂地坪、耐酸鹼 FRP 地坪防護及高科技無塵室地坪工程的專業形象。

## 🛠 技術堆疊 (Tech Stack)

*   **框架**: [Nuxt 3](https://nuxt.com/) (Vue.js 框架)
*   **語言**: HTML, CSS, TypeScript / JavaScript
*   **樣式與排版**: [Tailwind CSS](https://tailwindcss.com/) (Utility-first CSS framework)
*   **圖示庫**: [Lucide Vue Next](https://lucide.dev/) (開源 SVG Icon 集合)
*   **字體**: 系統預設黑體、襯線字搭配 Monospace (等寬字體) 營造工程儀表感
*   **部署環境**: Node.js (開發與伺服器渲染 SSR)

## 📁 專案主要結構

*   `app.vue` / `nuxt.config.ts`: Nuxt 應用程式進入點與核心配置檔。
*   `layouts/`
    *   `default.vue`: 全站共用版型（包含頂部導覽列、頁尾聯絡資訊與版權宣告）。
*   `pages/`
    *   `index.vue`: 首頁（品牌形象Hero區塊、核心優勢、標準化施工流程）。
    *   `about.vue`: 關於我們（公司簡介、廠房實景、核心理念）。
    *   `services.vue`: 服務項目（各種工業地坪解決方案與技術規格）。
    *   `projects.vue`: 工程實績（作品集展示，具備動態分類過濾功能）。
    *   `contact.vue`: 聯絡我們（包含詢問表單、聯絡資訊及地圖示意）。
    *   `privacy.vue`: 隱私權政策。
    *   `terms.vue`: 服務條款。
*   `assets/`
    *   `/logo.jpg`: 俊泰工程公司商標圖檔。

## 🎨 設計系統 (Design System)

本專案採用客製化的 **Industrial Tech (工業科技風)**，捨棄了常見的現代極簡風，強調耐用、穩固與高精密的工程質感：

*   **色彩計畫**: 
    *   主色：深海藍灰 (`slate-900`, `slate-950`) - 作為穩重的基底。
    *   強調色：科技藍 (`blue-600`, `blue-500`) - 用於按鈕、連結與視覺亮點。
    *   輔助色：冷灰色系 (`slate-400`, `slate-500`) - 用於次要文字與邊框。
*   **視覺元素**:
    *   大量採用銳利的直角 (`rounded-sm`, 甚至直接切角) 來取代溫和的圓角。
    *   背景圖樣結合 `radial-gradient` (點陣化) 或 `linear-gradient` (網格線條)，模仿藍圖或施工透視圖。
    *   將部分英文標籤使用全大寫與等寬字型 (`font-mono tracking-widest uppercase`)，模仿工業機具或 HUD 介面的標示。

## 🚀 本地開發與運行 (Development)

請確認您已安裝 Node.js (建議版本 18.x 或以上)。

1. **安裝依賴套件 (Install dependencies)**:
   ```bash
   npm install
   # 或是使用 yarn install / pnpm install
   ```

2. **啟動開發伺服器 (Start development server)**:
   ```bash
   npm run dev
   # 預設會在 http://localhost:3000 上執行
   ```

3. **建置正式環境檔案 (Build for production)**:
   ```bash
   npm run build
   ```

4. **預覽正式環境 (Preview production build)**:
   ```bash
   npm run preview
   ```

## 📧 聯絡資訊

若有任何網頁前端或設計系統相關問題，請聯繫前端開發團隊。
* **Client**: 俊泰工程有限公司 (Juntai Engineering Co., Ltd.)
* **Email**: juntai.wu01@gmail.com
* **Tel**: 07-726-1010
