# HTML Writer

**把文件和編輯器存成一個 HTML 檔。用瀏覽器開啟，就能離線編輯、閱讀與列印，並可連接地端 Ollama 進行文件問答。**

HTML Writer 適合撰寫公告、操作手冊與課程講義。存檔後可把同一個 HTML 傳給其他人，對方開啟即可閱讀，需要修改時再切換到編輯模式，或開啟「AI 問文件」快速查詢文件內容。

👉 **線上體驗與完整包下載**：[https://office.ddmmbb.org/](https://office.ddmmbb.org/)

## 開始使用

### 方式一：線上直接體驗（或下載完整套件）

前往 **[HTML Office 網站](https://office.ddmmbb.org/)**，可以直接在瀏覽器中線上試用 HTML Writer，或一次下載包含五款工具的完整離線包（`html-office.zip`）。

### 方式二：從本專案單檔下載

1. 開啟 [HTML-Writer.html](HTML-Writer.html) 的檔案頁，點右上角的 **Download raw file**。
2. 用瀏覽器開啟下載的檔案。先試用範例，或點「新文件」開始撰寫。
3. 完成後點「另存 HTML」。文字、圖片與編輯器會一起存進新檔案。

## 編輯功能

- 段落與標題、粗體、斜體、底線、文字色、對齊、連結和文件大綱。
- 使用本機備援字型的無襯線、襯線與等寬字型。
- 插入或貼上圖片，支援「隨文字排列」與「自由模式」（可調整文字上／下層、拖曳移動、縮放、旋轉與不透明度）。
- 新增表格、增刪列欄、拖曳欄線調整欄寬，以及儲存格合併與直切／橫切分割。
- 把選取的段落套用「編號」，再用「上一層」或「下一層」調整層級。各層使用 `1. 2. 3.`、`a. b. c.`、`i. ii. iii.`。
- 可切換繁體中文、English、日本語，或依瀏覽器語言自動選擇介面。

## AI 問文件（支援地端 Ollama）

內建側邊欄問答面板，可連接本機執行的 **Ollama** 或其他 **OpenAI 相容 API**，直接針對目前文件內容提問或討論修改建議。

1. 點擊右上角的 **「AI 問文件」**（在閱讀、編輯與列印預覽模式皆可使用）。
2. 展開 **「API 連線設定」**，預設網址為地端 Ollama 的 `http://127.0.0.1:11434/v1`（API Key 為選填）。
3. 點擊 **「取得模型清單」**，載入後於下拉選單選擇要使用的聊天模型即可開始提問。

**特色與注意事項：**

- **來源跳轉**：AI 回覆會標註引用的文件片段 `[n]`，點擊下方的來源按鈕可直接捲動並高亮對應段落（列印預覽模式亦適用）。
- **隱私與存檔**：AI 面板僅讀取目前文件內容，對話紀錄只保留在當前頁面；執行「另存 HTML」時，**不會**將 API 連線設定、金鑰或對話紀錄寫入檔案中。
- **跨來源連線（CORS）**：若直接雙擊開啟本機 HTML 檔（`file://`）遇到瀏覽器阻擋連線，請確認地端 Ollama 已允許跨來源請求，或改以本機 HTTP 伺服器開啟該檔案。

## 列印與 PDF

點「列印預覽」查看 A4 分頁。列印和儲存 PDF 共用這些頁面。在瀏覽器的列印視窗選 **A4**、**實際大小（100%）**，並關閉頁首及頁尾。要產生 PDF 時，選擇「儲存為 PDF」作為目的地。

## 如何請 LLM 協助修改

把 `HTML-Writer.html` 交給 LLM，說明要從哪個按鈕或操作開始，以及預期畫面。檔案內有維護註解，可依功能找到對應程式：

| 功能 | 程式入口 |
| --- | --- |
| 介面翻譯 | `locale` 和 `data-i18n` |
| 多層編號 | `listLevels` |
| 正文復原與重做 | `editHistory` |
| 表格編輯與欄寬調整 | `tableEditing` 和 `columnSizing` |
| 自由模式圖片排版 | `freeImages` |
| A4 預覽、列印與 PDF 排版 | `paginator` |
| AI 問文件（段落檢索與 API 連線） | `writerKnowledge` 和 `writerAI` |
| 另存可編輯的單檔 | `saveHTML()` |

例如可請 LLM「修改 AI 問文件的預設提示詞，並驗證切換模型、停止生成與點擊來源跳轉的結果」。

## HTML Office 系列專案

HTML Office 將以下五個開源專案集結成單一資料夾，可於 [https://office.ddmmbb.org/](https://office.ddmmbb.org/) 線上體驗或一次下載離線使用：

- **[html-writer](https://github.com/ddmmbb-2/html-writer)**（本專案）— 文件編輯器
- **[html-slidebook](https://github.com/ddmmbb-2/html-slidebook)** — 簡報編輯器
- **[html-image](https://github.com/ddmmbb-2/html-image)** — 圖片編輯器
- **[html-excel](https://github.com/ddmmbb-2/html-excel)** — 試算表編輯器
- **[html-keep](https://github.com/ddmmbb-2/html-keep)** — 口袋筆記 / 備忘錄

---

本專案由作者提出需求，由 AI 協助實作與測試。
