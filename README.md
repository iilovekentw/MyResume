# MyResume

這是一個以靜態網頁方式製作的個人履歷網站，主要用來展示個人簡介、工作經歷、技能、作品集、持續精進內容與教育背景。

## 畫面預覽

- 首頁主視覺：姓名、職涯定位、關鍵能力摘要與個人照片
- 工作經歷：以卡片與時間軸方式呈現主要任職經驗
- 作品集：展示近期參與或開發的代表專案
- 持續精進：展示自學筆記、課程進修與學習成果預覽
- 教育背景：整理學歷、訓練與補充資訊

## 專案使用到的程式語言

- HTML5
- CSS3
- JavaScript（原生 JavaScript / Vanilla JS）

## 專案使用到的技術

- 靜態網站架構
  - 以單一 `index.html` 作為主頁面，不依賴前端框架或後端服務。
- 語意化 HTML
  - 使用 `header`、`main`、`section`、`article`、`aside`、`footer` 等語意化標籤建立頁面結構。
- 響應式網頁設計（Responsive Web Design）
  - 透過 CSS Grid、Flexbox 與 `@media` 做桌機、平板、手機版面調整。
- CSS 自訂變數
  - 使用 `:root` 中的 CSS Variables 管理色彩、陰影、圓角與版面寬度。
- 平滑捲動與錨點導覽
  - 使用 `scroll-behavior: smooth`、`scroll-padding-top`、`scroll-margin-top` 實作頁面區塊導覽與回到頂部體驗。
- Sticky Header
  - 導覽列使用 `position: sticky`，讓頁面捲動時仍能快速切換區塊。
- Lightbox 圖片放大
  - 使用原生 `<dialog>` 元素搭配 JavaScript，實作筆記縮圖點擊放大檢視。
- 浮動回到頂部按鈕
  - 使用原生 JavaScript 監聽 `scroll` 事件，依捲動位置顯示或隱藏按鈕。
- 外部字型
  - 透過 Google Fonts 載入 `Noto Sans TC` 與 `Noto Serif TC`。

## 專案檔案結構

- `index.html`
  - 網站主頁面，包含所有內容結構與少量互動腳本。
- `css/style.css`
  - 全站樣式，包含版面、色彩、響應式設計與互動效果。
- `images/`
  - 履歷照片、筆記主題縮圖與 lightbox 展示圖片。
- `prompts/features/`
  - 功能需求說明文件，記錄此專案的功能開發需求。

## 功能特色

- 單頁式履歷網站，內容集中、閱讀動線明確
- 導覽列支援錨點跳轉與平滑捲動
- 首頁與重點區塊使用視覺強調樣式，提升閱讀聚焦效果
- 作品集可直接連到外部專案網站
- 持續精進區塊提供筆記主題縮圖與 lightbox 放大檢視
- 頁面捲動時會顯示浮動「回到頂部」按鈕
- 支援桌機、平板、手機等不同尺寸裝置

## 如何在本機開啟

這個專案不需要安裝額外套件，也不需要建置流程。

### 方式一：直接開啟

直接用瀏覽器開啟 `index.html` 即可。

### 方式二：使用編輯器的靜態伺服器

如果你使用 Visual Studio Code，可搭配 Live Server 類型工具啟動本機靜態頁面，方便即時預覽修改結果。

## 技術特點摘要

- 無框架、無建置流程，部署簡單。
- 以原生前端技術完成互動功能。
- 著重履歷展示、閱讀體驗與行動裝置相容性。
