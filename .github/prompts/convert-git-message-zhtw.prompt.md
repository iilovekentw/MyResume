---
agent: agent
model: Claude Sonnet 4.5
description: 'Git Commit 訊息繁體中文轉換: 將最後一次的 Git commit 訊息轉換為繁體中文,並保持原有的 Conventional Commits 格式規範。'
tools: ['execute/getTerminalOutput', 'execute/runInTerminal', 'read/terminalLastCommand', 'read/terminalSelection', 'fetch-mcp/fetch', 'web/fetch', 'web/githubRepo']
---

# Git Commit 訊息繁體中文轉換

## 目的
將最後一次的 Git commit 訊息轉換為繁體中文，專業術語請使用英文，並保持原有的 Conventional Commits 格式規範。

## 重要說明
原 Git commit 訊息是參考以下網頁的提示詞生成的:
- https://raw.githubusercontent.com/theorib/git-commit-message-ai-prompt/refs/heads/main/prompts/conventional-commit-with-gitmoji-ai-prompt.md

翻譯後的內容也必須遵守該提示詞的所有規範,包括:
- Conventional Commits 1.0.0 規範
- Gitmoji 使用規範
- 格式要求(emoji + type + scope + description)
- 100 字元行長度限制
- 特定的 type 定義(feat, fix, docs, style, refactor, test, chore, build, ci, perf, revert, i18n)
- Footer 格式(BREAKING CHANGE, Fixes, Closes, Co-authored-by 等)

## 執行步驟

### 1. 取得最後一次 commit 訊息
- 使用 `git log` 工具取得最後一次的 commit 訊息
- 檢查 commit 訊息的完整內容（包含標題、內文、footer）

### 2. 翻譯 commit 訊息
- 將 commit 訊息翻譯為繁體中文
- **保持 Conventional Commits 與 Gitmoji 格式**:
  - `<emoji> <type>(scope): subject`
  - emoji 必須保留(如:✨ 🐛 📝 💄 ♻️ ✅ 🔧 👷 ⚡️ ⏪️ 🌐)
  - type 保持英文小寫(如:feat, fix, docs, style, refactor, test, chore, build, ci, perf, revert, i18n)
  - scope 翻譯為中文(如果原本有的話)
  - subject 翻譯為中文
- 翻譯 commit body(如果有的話)
  - 使用項目符號「-」
  - 每行最多 100 字元
- 保留 footer 中的關鍵字(如:BREAKING CHANGE, Fixes, Closes, Co-authored-by, Reviewed-by 等)

### 3. 顯示翻譯結果
- 明確顯示翻譯後的完整 commit 訊息
- 讓使用者確認翻譯內容是否正確

### 4. 等待使用者確認
- **必須等待使用者按下確認按鈕或輸入 OK 後才能繼續**
- 不可自動執行下一步

### 5. 更新 commit 訊息
- 使用 `git commit --amend` 將翻譯後的訊息寫回
- 確認更新成功

## 範例

### 範例 1:功能新增
**原始訊息:**
```
✨ feat(user): add user profile page

- implement user profile page with avatar upload
- add profile picture preview functionality
```

**翻譯後:**
```
✨ feat(使用者): 新增使用者個人檔案頁面

- 實作使用者個人檔案頁面,包含頭像上傳功能
- 新增個人照片預覽功能
```

### 範例 2:錯誤修復
**原始訊息:**
```
🐛 fix(auth): resolve login session timeout issue

- fix session expiration not being properly handled
- update token refresh logic
```

**翻譯後:**
```
🐛 fix(驗證): 修正登入 session 逾時問題

- 修正 session 到期未正確處理的問題
- 更新 token 重新整理邏輯
```

### 範例 3:程式碼重構
**原始訊息:**
```
♻️ refactor(server): use environment variable for port configuration

- rename port variable from lowercase to uppercase (PORT)
- use process.env.PORT with fallback to PORT constant (7799)
```

**翻譯後:**
```
♻️ refactor(伺服器): 使用環境變數進行 port 設定

- 將 port 變數從小寫重新命名為大寫 (PORT)
- 使用 process.env.PORT 並回退至 PORT 常數 (7799)
```

## 翻譯規則

### 必須保留的元素
- emoji 符號(完全保留,不可移除或更改)
- type 類型(必須保持英文小寫)
- footer 關鍵字(如:BREAKING CHANGE, Fixes #123, Closes #456, Co-authored-by 等)
- 專有名詞(如:API, URL, JSON, HTTP, GitHub, token, session 等)

### 翻譯原則
- subject 和 body 翻譯為繁體中文
- scope 翻譯為中文(如:user → 使用者, auth → 驗證, server → 伺服器)
- 標點符號使用全形中文標點(如:,、。)
- 保持原有的項目符號格式(使用「-」)
- 每行最多 100 字元(包含空格和特殊字元)
- **專業術語請使用英文**(如:API, URL, JSON, HTTP, token, session, commit, repository 等)
- 確保翻譯後語意清晰、符合繁體中文習慣

### 特殊注意事項
- 如果 commit 已經推送到遠端,需要使用 `git push --force` 更新，否則不可強制推送
- 需等使用者確認翻譯內容無誤後再進行 commit 更新，切不可自動執行
- 翻譯時保持技術用語的準確性
- 對於混合中英文的句子,適當使用空格分隔