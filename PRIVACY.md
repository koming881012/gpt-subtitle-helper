# GPT 中文字幕助手隱私說明

適用版本：0.4.2 測試版 · 更新日期：2026 年 10 月 17 日

本工具為免費開源的獨立專案，支援 Windows x64 與 Chrome。尚未上架 Chrome Web Store。

## 登入與方案用量

登入在 OpenAI 官方頁面完成，工具不收集或保存 ChatGPT 密碼。需要使用者另外同意方案用量權限，帳號及模型資格由 OpenAI 決定。翻譯用量計入使用者原有方案限制，不是額外或無限額度。

擴充功能與本機連線助手本身免費。目前官方方案用量整合列出的適用對象為符合資格的 ChatGPT Plus／Pro 使用者；本專案尚未以 ChatGPT Free 免費帳號實測，不保證其可執行 AI 翻譯。程式不按方案名稱排除 Free 帳號，而是檢查實際授權及模型可用性。不提供共用帳號、開發者代付額度或 API 付費備援。登入成功與取得翻譯額度是不同的授權結果。

OpenAI 的登入憑證與更新憑證由 Windows DPAPI 加密保存在目前使用者的本機連線助手。瀏覽器插件儲存本機連接所需的配對碼；此碼不放進網址、影片頁面或診斷資料。登入流程透過一次性的本機連接要求自動配對，原生配對碼只作修復選項。

## 處理哪些資料

工具讀取支援網站的目前影片標題、影片識別、播放時間及可取得的英文字幕，用來翻譯與同步字幕。YouTube 音軌語言資訊只用於本機判斷是否自動翻譯，不擷取音訊或進行語音辨識。英文字幕及影片標題經本機助手傳送至 OpenAI 官方 Responses API；翻譯請求設為 `store:false`。OpenAI 對資料的處理仍依其條款與政策，這個設定不代表所有服務端記錄皆不存在。

開啟額外專有名詞搜尋時，會另送相關字幕上下文給 OpenAI 並增加用量；此功能預設關閉。

本工具不讀取 ChatGPT 對話或 cookies、不擷取影片音訊、不下載影片、不處理 DRM。沒有可取得的英文字幕時無法翻譯。

## 本機儲存與刪除

字幕、未完成翻譯、顯示偏好與快取保存在 Chrome 本機儲存，不提供開發者雲端同步或遙測收集。使用者主動匯出的字幕檔由使用者選擇儲存位置。

可在插件進階設定清除字幕快取。登出會清除目前帳號的本機登入憑證，並嘗試撤銷遠端授權；若撤銷未確認，請至 ChatGPT 設定移除應用連接。其他已儲存帳號需分別登出。

Windows 助手資料位於 `%LOCALAPPDATA%\YouTubeGPTSubtitle`。取消自動啟動可移除 Windows 啟動資料夾中的「YouTube GPT 字幕連線」捷徑，登出 Windows 後服務停止，再移除助手安裝資料夾。移除插件前可先清除字幕及登出帳號。匯出的字幕檔需自行刪除。

## 權限用途

- YouTube／Prime Video 網站：取得字幕及顯示中文字幕。
- 本機 127.0.0.1：連接 Windows 助手與完成登入配對；只接受指定連接埠及有效的一次性要求。
- activeTab：顯示目前影片狀態與操作。
- storage／unlimitedStorage：保留字幕、進度與偏好，避免重複翻譯。
- offscreen：關閉彈出視窗後繼續背景翻譯。
- downloads：使用者操作時另存字幕。

## 專案網站與聯絡

專案網站由 Sites 代管；提供者可能為傳送網頁與維護服務而處理 IP 位址、請求時間及瀏覽器資訊。網站不設置自訂追蹤、廣告或分析工具，也不要求登入即可閱讀隱私政策或下載檔案。下載檔案不會將本機字幕或 ChatGPT 憑證傳給網站。

支援與隱私問題可至 GitHub 問題回報頁聯絡維護者。GitHub 回報為公開內容，請勿貼上密碼、憑證、連線碼、私人影片、完整字幕或其他個人資料；GitHub 對回報及帳號資料的處理依其服務政策。

- 專案網站：https://gpt-subtitle-helper.justkodo.chatgpt.site/
- 原始碼：https://github.com/koming881012/gpt-subtitle-helper
- 支援與隱私問題：https://github.com/koming881012/gpt-subtitle-helper/issues
- 線上隱私政策：https://gpt-subtitle-helper.justkodo.chatgpt.site/privacy.html

本工具非 OpenAI、YouTube 或 Amazon 官方產品。
