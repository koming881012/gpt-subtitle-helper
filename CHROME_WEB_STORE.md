# Chrome Web Store 上架準備

核對日期：2026-10-17。套件版本：0.4.2。狀態：本機準備，尚未上傳或送審。

## 發行條件

目標為免費公開發行，使用者各自登入 ChatGPT。專案使用 MIT 授權，公開原始碼位於 https://github.com/koming881012/gpt-subtitle-helper 。

官方目前列出符合資格的 ChatGPT Plus／Pro 使用者可授權此類開源工具使用方案額度。Free 帳號尚未實測，不能宣稱可用或已有實測證明不可用。程式依實際授權與可用模型判斷，不按方案名稱阻擋 Free；測試流程與結果見 FREE_ACCOUNT_TEST.md。送審文案需保留此區分。

使用者只在 OpenAI 官方頁面輸入帳密並授權，不在擴充功能內填寫密碼。插件與助手不收費；OpenAI 帳號方案、模型、地區、額度與服務資格由 OpenAI 決定。

現版需要 Windows x64 本機連線助手與 Chrome 116 以上。商店安裝擴充功能後仍須另外安裝助手，不能宣稱安裝插件即可在所有作業系統使用。

## 可供填寫的商店資料草稿

以下依現版功能整理；實際上架前須完成安裝驗收與必填素材。Free 帳號測試不以文件推測代替。

名稱：YouTube GPT 中文字幕助手

簡短說明：將 YouTube 與 Prime Video 英文字幕翻成台灣繁體中文，支援雙語字幕與本機快取。

詳細說明：

> 將 YouTube 與 Prime Video 可取得的英文字幕翻成台灣繁體中文，支援雙語顯示、自訂字幕外觀、調整時間、本機快取及 SRT／VTT 匯出。
>
> 擴充功能與 Windows 連線助手免費。AI 翻譯需以自己的 ChatGPT 帳號在 OpenAI 官方頁面授權方案用量；官方目前列出符合資格的 Plus／Pro 帳號。Free 帳號尚未實測，不保證可用，用量仍受原方案限制。
>
> 使用前需另行安裝 Windows x64 連線助手，無需安裝 Node.js 或 Codex。下載：https://gpt-subtitle-helper.justkodo.chatgpt.site/download.html 。原始碼：https://github.com/koming881012/gpt-subtitle-helper 。
>
> 只處理網站已提供且工具可取得的英文字幕，不下載影片、不擷取音訊、不進行語音辨識；沒有可取得的英文字幕時無法翻譯。YouTube 支援一般 watch 影片，不支援 Shorts、Music、嵌入頁或即時直播。
>
> 登入密碼只在 OpenAI 官方網站輸入。英文字幕及影片標題經本機助手傳送給 OpenAI；字幕、進度與偏好保存在本機。沒有開發者遙測、廣告或字幕雲端同步。
>
> 本工具由獨立開發者提供，非 OpenAI、YouTube 或 Amazon 官方產品。

專案首頁：https://gpt-subtitle-helper.justkodo.chatgpt.site/

支援頁：https://gpt-subtitle-helper.justkodo.chatgpt.site/support.html

隱私政策：https://gpt-subtitle-helper.justkodo.chatgpt.site/privacy.html

單一用途：將支援影片網站可取得的英文字幕翻譯及同步顯示為繁體中文字幕，提供相關外觀設定、本機快取、字幕匯入及匯出。

建議分類：依開發者後台可用選項選擇影片／觀看輔助相關分類。主要語言：繁體中文。

發行設定：Public；依帳號實際可用地區與助手支援範圍確認發行地區。免費提供插件不代表所有地區都能使用 OpenAI。

## 隱私與權限欄位

隱私政策來源為 `PRIVACY.md`；由 `website/build.mjs` 產生 privacy.html，公開發布後以上述 HTTPS 網址填入後台。套件內的檔案不等同商店要求的政策網址。

| 權限／網站 | 現版用途 |
| --- | --- |
| storage | 保留設定、目前影片偏好與本機助手配對資料 |
| unlimitedStorage | 保存長影片字幕快取及翻譯進度，避免重複翻譯 |
| offscreen | 執行翻譯 Worker，關閉 Popup 後仍可處理工作 |
| activeTab | 使用者操作時取得目前影片分頁並控制字幕 |
| downloads | 使用者主動另存字幕檔 |
| https://www.youtube.com/* | 讀取支援影片的英文字幕與播放資訊，顯示字幕 |
| https://www.primevideo.com/*、https://primevideo.com/* | 讀取播放器可取得的字幕與播放資訊，顯示字幕 |
| http://127.0.0.1:8766/* | 連接本機助手，完成配對、帳號狀態查詢與翻譯 |
| 本機連線內容腳本 http://127.0.0.1/* | 配對橋接；執行時再核對助手的指定連接埠與一次性要求 |

資料揭露需反映實際處理及傳送，不能因沒有開發者伺服器就一律勾選「不處理資料」。帳號識別／Email、登入授權憑證、支援網站的影片識別與標題、英文字幕及翻譯結果，應依後台當時的資料類別逐項核對。OpenAI 憑證保存在 Windows DPAPI 加密檔，不進入瀏覽器儲存；配對碼保存在 Chrome 本機儲存。

OpenAI 是翻譯資料接收方。網站觀看資訊僅用於字幕功能，不收集一般瀏覽歷史；不販售資料、不用於廣告。依 `PRIVACY.md` 填寫保留、刪除與登出方式。程式隨套件打包，不下載遠端 JavaScript 執行；外部 OpenAI 呼叫由另外安裝的本機助手進行，須在審查說明中揭露此相依性。

## 尚缺的公開發行資料與驗收

- 驗證上述公開原始碼、下載、支援與隱私網址不需登入即可使用。
- Chrome 開發者帳號所需的聯絡 Email 及身分資料，僅由使用者在官方後台提供；公開支援管道採 GitHub Issues，不代為捏造個人 Email。
- Chrome 商店開發者帳號完成註冊、驗證與一次性註冊費；不要將插件免費誤寫為開發者註冊也免費。
- 真實操作截圖：以無私人資料的影片展示中文字幕、雙語顯示與設定；截圖不能用模擬預覽冒充已完成翻譯。現有套件有 128 px 圖示，仍須依商店圖片規格準備截圖及其他必填素材。
- 乾淨 Windows 電腦安裝助手、商店型安裝流程、新帳號授權、字幕顯示與匯出、取消及續翻、登出與撤銷的實測。
- 確認「免費帳號可用」是否為必要條件；現有自動化測試不代表已驗證 ChatGPT Free 翻譯資格。

## 審查測試說明草稿

1. 在 Windows x64 安裝正式公開下載的連線助手，使用 Chrome 116 以上載入待審插件。下載連結需先補齊。
2. 開啟 Popup，按 Continue with ChatGPT，於 OpenAI 官方頁面登入符合資格的測試帳號並授權方案用量。不要在公開欄位填入私人帳密或憑證；若審查需要專用測試帳號，另以後台的審查專用方式提供。
3. 重新整理有可取得英文 CC 的 YouTube watch 影片，開始翻譯並核對繁中及雙語字幕；用量計入該測試帳號。影片範例需在送審時重新確認可用。
4. 調整字幕外觀／時間，關閉並重開 Popup，確認工作與字幕狀態；完成整片後測試 SRT／VTT 匯出。
5. 測試登出與清除快取。Prime Video 另需審查者具備合法觀看權限及有英文字幕的影片，不提供繞過存取限制的流程。

## 套件與提交步驟

本機打包指令：`node scripts/package-release.js`。輸出位於 `release/0.4.2/`，Chrome ZIP 僅含插件；Windows ZIP 為另外提供的助手，不上傳為 Chrome 擴充功能。

填妥資料並完成實測後，到 Chrome Developer Dashboard 建立項目，上傳 `GPT字幕助手-0.4.2-Chrome.zip`，填寫商店說明、隱私、發行及審查說明，再提交審查。通過審查前不能稱為已上架。

## 官方依據

- [OpenAI Sign in with ChatGPT：資格及登入與方案權限的差異](https://developers.openai.com/siwc/quickstart)
- [OpenAI：開源與本機應用的方案用量整合](https://developers.openai.com/siwc/token-sharing-open-source)
- [Chrome：開發者註冊](https://developer.chrome.com/docs/webstore/register/)
- [Chrome：首次發布流程](https://developer.chrome.com/docs/webstore/publish)
- [Chrome：使用者資料與權限政策](https://developer.chrome.com/docs/webstore/program-policies/policies)
- [Chrome：商店圖片規格](https://developer.chrome.com/docs/webstore/images)
