# 功能需求：新增「持續精進」區塊

## 目標

在 `index.html` 的現有 `<main>` 區域內，於 `#projects`（作品集）區塊之後、`#education`（學歷）區塊之前，新增一個 `id="growth"` 的 `<section>`，用來展示本人如何持續精進個人程式開發能力。

同時在 `<nav class="site-nav">` 內新增對應的導覽連結。

---

## 版面結構

此區塊包含三個子項目，依序排列：

### 1. 個人自學筆記 Repo

- 標題：「個人自學筆記 Repo」
- 說明文字：
  > 建立私人 GitHub Repo（Self-Learn-Notes）系統性記錄學習過程中遇到的問題與解決方案，包含程式碼片段、工具使用心得、學習資源整理等。目前為 private，以保護部分具敏感性的內容，但可於面試時實際展示。
- 顯示一個「查看 Repo」按鈕，樣式使用現有的 `.button.button-secondary`，連結為 `https://github.com/iilovekentw/Self-Learn-Notes`，加上 `target="_blank" rel="noopener noreferrer"`

### 2. 筆記主題圖片展示

- 標題：「學習筆記主題預覽」
- 說明文字：
  > 以下是筆記 Repo 中部分主題的縮圖，每張圖代表一個實務上遇到並解決的問題，點擊可放大查看筆記內容。
- 以 CSS Grid（2 欄或 4 欄響應式）排列四張主題縮圖：
  - `images/主題_1.png`
  - `images/主題_2.png`
  - `images/主題_3.png`
  - `images/主題_4.png`
- 每張圖點擊後，以 lightbox 方式放大顯示 `images/內容.png`（即點進主題後的筆記內容示意圖）
- Lightbox 實作使用純 HTML + CSS + 少量原生 JavaScript（`<dialog>` 元素或自製 overlay），不引入第三方套件

### 3. 參加課程進修

- 標題：「課程進修」
- 說明文字：
  > 參加保哥（Will保哥）在多奇教育訓練網開設的課程「GitHub Copilot 全方位實戰：協作×進階×代理人（共三堂）」，將課堂所學實際應用於工作中，包含使用 GitHub Copilot 協助程式碼撰寫、問題分析與解決，並在日常開發流程中導入 AI 工具以提升效率與品質。

---

## 樣式規範

- 沿用 `css/style.css` 現有設計語言（CSS 變數、圓角、陰影、色彩）
- 區塊 heading 使用現有 `.section-heading` 結構（含 `.eyebrow` 副標題與 `<h2>`）
- `eyebrow` 建議文字：`Growth`
- `<h2>` 標題文字：`持續精進`
- 三個子項目可使用 card 樣式（白底、圓角、`var(--shadow)`），排列方式：
  - 桌機：三欄並排（`grid-template-columns: repeat(3, 1fr)`）
  - 手機（< 768px）：單欄堆疊
- 圖片縮圖 hover 時加上輕微放大效果（`transform: scale(1.03)`，`transition: 0.25s ease`）

---

## 導覽列更新

在 `<nav class="site-nav">` 中，於「作品集」連結之後加入：

```html
<a href="#growth">持續精進</a>
```

---

## 注意事項

- 不修改現有任何區塊的 HTML 結構或 CSS
- 所有文字使用繁體中文
- 圖片 `alt` 屬性要有描述性文字
- Lightbox 關閉方式：點擊遮罩或按 `Escape` 鍵均可關閉


