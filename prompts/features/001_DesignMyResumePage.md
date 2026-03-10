# 任務：建立個人履歷頁面

## 目標
請讀取以下兩份參考資料，擷取履歷相關內容，然後**覆寫 `index.html`**，建立一個完整的個人履歷靜態網頁，並使用 `MCP Tool-Pencil工具去設計頁面`。

## 參考資料來源

1. **Word 履歷文件**：`docs/環資公司的個人履歷.docx`
   - 使用 `pandoc docs/環資公司的個人履歷.docx -t plain` 或 `python3 -c "import docx; ..."` 等方式讀取內容
2. **104 人力銀行線上履歷**：https://pda.104.com.tw/profile/share/5g1gwLympb9xVVwwpF9ZqbOQ4aPxxHxm

## 頁面必須包含的區塊

1. **頭像照片** — 圖片路徑：`images/履歷大頭照.jpg`
2. **姓名**
3. **職稱**
4. **聯絡資訊**：電話、電子郵件
5. **自我介紹**
6. **工作經歷**：每筆包含公司名稱、職位、工作期間、工作內容摘要
7. **教育背景**：學校名稱、學位、畢業年份
8. **技能清單**
9. **作品集 / 專案連結**（若資料中有提及）

## 技術規格

- 輸出檔案：`index.html`（單一 HTML 檔，CSS 另外建立外部檔案 `style.css`並放在資料夾 `css` 中）
- **RWD**：需支援手機、平板、桌機（使用 CSS Flexbox 或 Grid，並加入 `@media` breakpoints）
- 字型：使用 Google Fonts（如 Noto Sans TC），確保中文顯示正常
- 配色：專業簡潔風格，主色調自行決定，背景白色或淺灰
- 使用任何 JavaScript 框架或外部 JS 函式庫時，檔案要放在資料夾 `js` 中
