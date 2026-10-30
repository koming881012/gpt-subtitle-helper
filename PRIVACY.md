# GPT 中文字幕助手隱私說明

適用版本：0.6.0 · 更新日期：2026 年 10 月 30 日

本工具為免費開源的獨立專案，是 Chrome 擴充功能，不需要另外安裝電腦程式。

## 登入與方案用量

登入在 OpenAI 官方頁面完成，工具不收集或保存 ChatGPT 密碼。需要使用者另外同意方案用量權限，帳號及模型資格由 OpenAI 決定。翻譯用量計入使用者原有方案限制，不是額外或無限額度。

目前官方方案用量整合列出的適用對象為符合資格的 ChatGPT Plus／Pro 使用者；本專案尚未以 ChatGPT Free 免費帳號實測，不保證其可執行 AI 翻譯。程式不按方案名稱排除 Free 帳號，而是檢查實際授權及模型可用性。不提供共用帳號、開發者代付額度或 API 付費備援。

OpenAI 授權完成後會導回 `http://127.0.0.1:8766/auth/callback`；插件在瀏覽器內攔截這個網址取得一次性授權碼，直接向 OpenAI 換發登入憑證，這個網址不會連到任何本機或外部伺服器。登入憑證與更新憑證保存在 Chrome 的擴充功能本機儲存，只有本擴充功能自己的頁面能讀取，不放進網址、影片頁面或診斷資料，也不傳送到 OpenAI 以外的地方。

## 處理哪些資料

工具讀取支援網站的目前影片標題、影片識別、播放時間及可取得的字幕（YouTube 英文或日文、Prime Video 英文），用來翻譯與同步字幕。YouTube 音軌語言資訊只用於本機判斷影片原音語言、選擇字幕軌及是否自動翻譯，不擷取音訊或進行語音辨識。原文字幕及影片標題直接傳送至 OpenAI 官方 Responses API；翻譯請求設為 `store:false`。OpenAI 對資料的處理仍依其條款與政策，這個設定不代表所有服務端記錄皆不存在。

插件會在本機記錄自己送出的請求次數與 token 數（不含字幕內容），用來在小視窗顯示「今天／近 7 天用量」。OpenAI 目前不提供第三方插件讀取方案剩餘額度；剩餘額度與重置時間請在 ChatGPT 用量頁查看。

開啟額外專有名詞搜尋時，會另送相關字幕上下文給 OpenAI 並增加用量；此功能預設關閉。

本工具不讀取 ChatGPT 對話或 cookies、不擷取影片音訊、不下載影片、不處理 DRM。沒有可取得的英文或日文字幕時無法翻譯。

## 本機儲存與刪除

字幕、未完成翻譯、顯示偏好、用量統計與快取保存在 Chrome 本機儲存，不提供開發者雲端同步或遙測收集。使用者主動匯出的字幕檔由使用者選擇儲存位置。

可在插件設定清除字幕快取。登出會清除目前帳號的本機登入憑證，並嘗試撤銷遠端授權；若撤銷未確認，請至 ChatGPT 設定移除應用連接。其他已儲存帳號需分別登出。移除插件時，Chrome 會一併刪除插件的本機儲存。匯出的字幕檔需自行刪除。

0.4.x 版使用的 Windows 連線助手已不再需要。若曾安裝，可刪除 Windows 啟動資料夾中的「YouTube GPT 字幕連線」捷徑與 `%LOCALAPPDATA%\YouTubeGPTSubtitle` 資料夾。

## 權限用途

- YouTube／Prime Video 網站：取得字幕及顯示中文字幕。
- api.openai.com：用你的 ChatGPT 授權送出翻譯請求、讀取帳號可用模型。
- auth.openai.com：完成 ChatGPT 登入、更新與撤銷登入憑證。
- 127.0.0.1:8766 與 declarativeNetRequestWithHostAccess：只用來攔截 OpenAI 授權完成後的導回網址，轉到插件自己的登入完成頁；不連線到本機任何程式。
- activeTab：顯示目前影片狀態與操作。
- storage／unlimitedStorage：保留字幕、進度、偏好與登入狀態，避免重複翻譯。
- offscreen：關閉彈出視窗後繼續背景翻譯。
- downloads：使用者操作時另存字幕。

## 專案網站與聯絡

隱私政策與原始碼放在 GitHub 公開專案，不需登入即可閱讀；GitHub 對瀏覽資料的處理依其服務政策。本專案不設置自訂追蹤、廣告或分析工具。

支援與隱私問題可至 GitHub 問題回報頁聯絡維護者。GitHub 回報為公開內容，請勿貼上密碼、憑證、私人影片、完整字幕或其他個人資料；GitHub 對回報及帳號資料的處理依其服務政策。

- 原始碼：https://github.com/koming881012/gpt-subtitle-helper
- 支援與隱私問題：https://github.com/koming881012/gpt-subtitle-helper/issues
- 線上隱私政策：https://github.com/koming881012/gpt-subtitle-helper/blob/main/PRIVACY.md

本工具非 OpenAI、YouTube 或 Amazon 官方產品。
