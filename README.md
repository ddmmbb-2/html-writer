# HTML Writer

**把文件和編輯器存成一個 HTML 檔。用瀏覽器開啟，就能離線編輯、閱讀與列印。**

HTML Writer 適合撰寫公告、操作手冊與課程講義。存檔後可把同一個 HTML 傳給其他人，對方開啟即可閱讀，需要修改時再切換到編輯模式。

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
- 插入或貼上圖片、調整圖片寬度，以及新增表格、增刪表格列欄。
- 把選取的段落套用「編號」，再用「上一層」或「下一層」調整層級。各層使用 `1. 2. 3.`、`a. b. c.`、`i. ii. iii.`。
- 可切換繁體中文、English、日本語，或依瀏覽器語言自動選擇介面。

## 列印與 PDF

點「列印預覽」查看 A4 分頁。列印和儲存 PDF 共用這些頁面。在瀏覽器的列印視窗選 **A4**、**實際大小（100%）**，並關閉頁首及頁尾。要產生 PDF 時，選擇「儲存為 PDF」作為目的地。

## 如何請 LLM 協助修改

把 `HTML-Writer.html` 交給 LLM，說明要從哪個按鈕或操作開始，以及預期畫面。檔案內有維護註解，可依功能找到對應程式：

| 功能 | 程式入口 |
| --- | --- |
| 介面翻譯 | `locale` 和 `data-i18n` |
| 多層編號 | `listLevels` |
| 正文復原與重做 | `editHistory` |
| A4 預覽、列印與 PDF 排版 | `paginator` |
| 另存可編輯的單檔 | `saveHTML()` |

例如可請 LLM「修改編號工具列的提示，並驗證選取多個子項後升層、降層、復原與列印預覽的結果」。

## HTML Office 系列專案

HTML Office 將以下五個開源專案集結成單一資料夾，可於 [https://office.ddmmbb.org/](https://office.ddmmbb.org/) 線上體驗或一次下載離線使用：

- **[html-writer](https://github.com/ddmmbb-2/html-writer)**（本專案）— 文件編輯器
- **[html-slidebook](https://github.com/ddmmbb-2/html-slidebook)** — 簡報編輯器
- **[html-image](https://github.com/ddmmbb-2/html-image)** — 圖片編輯器
- **[html-excel](https://github.com/ddmmbb-2/html-excel)** — 試算表編輯器
- **[html-keep](https://github.com/ddmmbb-2/html-keep)** — 口袋筆記 / 備忘錄

---

本專案由作者提出需求，由 AI 協助實作與測試。
