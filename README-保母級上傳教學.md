# 婚禮網站保母級上傳教學（GitHub Pages + Google 表單）

這份資料夾已經幫你準備好：

- `index.html`：婚禮網站主程式
- `Fig1.png` ~ `Fig5.png`：文青復古風裝飾圖
- `.nojekyll`：避免 GitHub Pages 做額外處理
- `Google表單題目建議.md`：你建立 Google 表單時可以直接照抄的題目

---

## 先說最重要的事

你現在可以 **先把網站上線**，就算 Google 表單還沒建立也沒關係。  
因為 `index.html` 已經預留好表單位置，之後只要把兩個 Google 表單網址貼進去，再重新上傳一次就完成。

---

## 第 1 步：把這個資料夾解壓縮

你會看到至少這些檔案：

- `index.html`
- `Fig1.png`
- `Fig2.png`
- `Fig3.png`
- `Fig4.png`
- `Fig5.png`
- `.nojekyll`
- `Google表單題目建議.md`

---

## 第 2 步：建立 GitHub 帳號（如果你還沒有）

1. 打開 GitHub
2. 註冊 / 登入
3. 登入後，按右上角 `+`
4. 點 `New repository`

---

## 第 3 步：建立新的 Repo（倉庫）

建議你填這樣：

- Repository name：`wedding-website`
- Visibility：**Public**（公開，這樣 GitHub Free 可直接用 GitHub Pages）
- 勾選 / 不勾選 README 都可以；最簡單是不勾

按 `Create repository`

---

## 第 4 步：把網站檔案上傳到 GitHub

### 方法 A：最簡單（網頁拖拉上傳）

1. 進入你剛建立好的 repo
2. 點 `uploading an existing file`
3. 把整個資料夾裡的所有檔案拖進去
4. 下方 `Commit changes`
5. 可輸入：`first upload`
6. 按 `Commit changes`

### 注意
一定要把這些檔案都上傳：

- `index.html`
- `Fig1.png` ~ `Fig5.png`
- `.nojekyll`

---

## 第 5 步：開啟 GitHub Pages

1. 在 repo 頁面上方點 `Settings`
2. 左邊找到 `Pages`
3. 在 `Build and deployment` 區塊：
   - Source 選 `Deploy from a branch`
   - Branch 選 `main`
   - Folder 選 `/ (root)`
4. 按 `Save`

等 1～5 分鐘後，GitHub 會給你一個網址，通常像這樣：

`https://你的帳號.github.io/wedding-website/`

打開這個網址，你的網站就上線了。

---

## 第 6 步：建立 Google 表單（用你自己的 Google 帳號登入）

1. 打開 `forms.google.com`
2. 按 `空白表單`
3. 表單名稱可以填：
   `賴柏延＆馬琳 婚禮出席回覆`
4. 題目可以直接照抄 `Google表單題目建議.md`

### 建議設定
在 Google 表單裡面：
1. 點右上 `設定`
2. 看你要不要：
   - 收集電子郵件（可選）
   - 限制每人只能填一次（可選）
3. 如果你希望大家不用登入 Google 也能填：
   - 請把回覆權限設成「任何知道連結的人可填」
   - 不要限制必須登入特定網域帳號

---

## 第 7 步：拿到 Google 表單的兩個網址

建立完成後，按右上角的 **發布 / Publish** 或 **傳送 / Send**（介面可能依版本略有不同）。

### 你需要兩個東西：

#### A. 表單公開網址（給按鈕使用）
這會長得像：

`https://docs.google.com/forms/d/e/xxxxxxxxxxxxxxxx/viewform`

把它記下來，等等會貼進：

`FORM_VIEW_URL`

---

#### B. 表單嵌入網址（給網站 iframe 用）
在 Google 表單點：

- 傳送 / Send
- 選 `<>` 嵌入 HTML
- 複製 iframe 程式碼

你會拿到像這樣的內容：

```html
<iframe src="https://docs.google.com/forms/d/e/xxxxxxxxxxxxxxxx/viewform?embedded=true" width="640" height="1200" frameborder="0" marginheight="0" marginwidth="0">載入中…</iframe>
```

你只要把 `src="..."` 裡面的網址複製出來，貼進：

`FORM_EMBED_URL`

---

## 第 8 步：修改 index.html 裡的兩個網址

打開 `index.html`，往下找這段：

```js
const SITE_CONFIG = {
  FORM_VIEW_URL: "PASTE_GOOGLE_FORM_VIEW_URL_HERE",
  FORM_EMBED_URL: "PASTE_GOOGLE_FORM_EMBED_URL_HERE",
  MAP_QUERY: "台中旌旗教會 408台中市南屯區文心南五路三段160號"
};
```

把它改成像這樣：

```js
const SITE_CONFIG = {
  FORM_VIEW_URL: "https://docs.google.com/forms/d/e/你的表單ID/viewform",
  FORM_EMBED_URL: "https://docs.google.com/forms/d/e/你的表單ID/viewform?embedded=true",
  MAP_QUERY: "台中旌旗教會 408台中市南屯區文心南五路三段160號"
};
```

存檔。

---

## 第 9 步：把改好的 index.html 再上傳一次

回到 GitHub repo：

1. 打開 `index.html`
2. 右上角點鉛筆 `Edit`
3. 把改好的內容貼上去
4. 按 `Commit changes`

等 1～2 分鐘重新整理網站，你就會看到 Google 表單直接嵌進婚禮網站裡。

---

## 第 10 步：確認網站有沒有成功

請檢查 4 件事：

1. 首頁人名是否正確：**賴柏延 ＆ 馬琳**
2. 日期是否正確：**2026/05/30**
3. 地圖是否正常顯示：**台中旌旗教會**
4. RSVP 區塊是否能看到 Google 表單

---

## 想換自己的照片怎麼做？

現在網站裡放的是文青風示意裝飾圖：

- `Fig1.png`
- `Fig2.png`
- `Fig3.png`
- `Fig4.png`
- `Fig5.png`

### 你之後如果想換成自己的婚紗照：
做法最簡單的是：

1. 把你的照片改成同檔名
2. 例如新的照片命名成 `Fig1.png`
3. 直接覆蓋原本檔案
4. 上傳到 GitHub 取代舊檔

這樣網站程式不用改。

---

## 想改文字怎麼做？

打開 `index.html`，搜尋這些文字就能直接改：

- `賴柏延`
- `馬琳`
- `2026 / 05 / 30`
- `台中旌旗教會`

---

## 想讓 LINE / Facebook 分享預覽更漂亮？

打開 `index.html`，在最上方 `<head>` 找到這兩行：

```html
<meta property="og:url" content="https://YOUR_GITHUB_PAGES_URL/" />
<meta property="og:image" content="https://YOUR_GITHUB_PAGES_URL/Fig1.png" />
```

把 `YOUR_GITHUB_PAGES_URL` 改成你真正的 GitHub Pages 網址，例如：

```html
<meta property="og:url" content="https://yourname.github.io/wedding-website/" />
<meta property="og:image" content="https://yourname.github.io/wedding-website/Fig1.png" />
```

再上傳一次即可。

---

## 如果你完全不會改 HTML，最少只要改哪裡？

只改這兩個地方就好：

### 1. Google 表單網址
在 `index.html` 搜尋：

- `PASTE_GOOGLE_FORM_VIEW_URL_HERE`
- `PASTE_GOOGLE_FORM_EMBED_URL_HERE`

### 2. GitHub Pages 網址（可選）
在 `index.html` 搜尋：

- `YOUR_GITHUB_PAGES_URL`

---

## 常見問題

### Q1：一定要會寫程式嗎？
不用。你只需要會：
- 建立 GitHub repo
- 拖拉上傳檔案
- 複製貼上 Google 表單網址

### Q2：Google 表單可以免費用嗎？
一般個人 Google 帳號就可以使用 Google 表單。

### Q3：GitHub Pages 可以免費用嗎？
可以。公開 repo 在 GitHub Free 就能使用 GitHub Pages。

### Q4：手機看會不會跑版？
不會。這份 `index.html` 已做響應式排版（RWD），手機與電腦都能自動調整。

---

## 最後提醒

我沒有把你的 Gmail 寫進網站檔案裡，避免日後你把 repo 設成公開時，個人 email 被直接曝光在網站程式碼中。  
你只要用自己的 Google 帳號登入 Google Forms 建立表單就好。
