# GPT 中文字幕助手

免費、MIT 開源的 Chrome 擴充功能，將 YouTube 與 Prime Video 可取得的英文字幕翻成台灣繁體中文。支援雙語字幕、外觀設定、時間調整、本機快取、SRT／VTT 匯入與匯出。

- [專案網站](https://gpt-subtitle-helper.justkodo.chatgpt.site/)
- [下載與安裝](https://gpt-subtitle-helper.justkodo.chatgpt.site/download.html)
- [隱私政策](https://gpt-subtitle-helper.justkodo.chatgpt.site/privacy.html)
- [使用支援](https://gpt-subtitle-helper.justkodo.chatgpt.site/support.html)
- [問題回報](https://github.com/koming881012/gpt-subtitle-helper/issues)

## 使用條件

目前版本 0.4.2 為測試版，尚未上架 Chrome Web Store。需要 Windows x64 連線助手與 Chrome 116 以上；不需另外安裝 Node.js 或 Codex。

使用自己的 ChatGPT 帳號，在 OpenAI 官方頁面登入及授權；本工具不接收密碼，也不要求 API Key。翻譯使用該帳號可用的方案額度，不提供共用帳號、額度代付或付費 API 備援。

官方目前列出符合資格的 Plus／Pro 帳號可授權方案用量。**Free 帳號尚未實測**，不能承諾可用，也沒有實測證明不能用。程式依實際授權及模型可用性判斷，沒有依方案名稱阻擋 Free。參考 [測試紀錄](FREE_ACCOUNT_TEST.md) 與 [官方文件](https://developers.openai.com/siwc/quickstart)。

只處理可取得的英文字幕；沒有英文字幕時不能翻譯。不下載影音、不進行語音辨識、不處理 DRM 或繞過平台限制。YouTube 僅支援一般 watch 影片，不支援 Shorts、Music、嵌入頁及即時直播。平台介面改動可能影響字幕取得。

## 安裝

1. 到下載頁取得 Windows 連線助手及 Chrome 擴充功能 ZIP。
2. 解壓縮助手並執行「安裝連線助手.cmd」，會設定目前 Windows 使用者登入後自動啟動。
3. 將 Chrome ZIP 解壓縮到固定資料夾；在 `chrome://extensions` 開啟開發人員模式，按「載入未封裝項目」，選擇內含 manifest.json 的資料夾。
4. 開啟插件，按 Continue with ChatGPT，在 OpenAI 官方頁面登入及授權。
5. 重新整理影片頁面，開啟有英文字幕的支援影片。可在設定調整自動翻譯、顯示模式與外觀。

## 資料處理

英文字幕及影片標題經本機助手送至 OpenAI 官方 Responses API，使用 `store:false`；不代表服務端所有記錄都不存在。字幕及偏好保存在本機。OpenAI 憑證以 Windows DPAPI 加密，插件僅保存本機配對資料。不讀取 ChatGPT 對話或 cookies，沒有開發者遙測及字幕雲端同步。詳見 [PRIVACY.md](PRIVACY.md)。

## 從原始碼開發

需要 Node.js 20 以上及 pnpm：

```powershell
pnpm install --ignore-scripts
pnpm build
node scripts/check.js
node --test tests/*.test.js
```

Chrome 載入本專案目錄。Windows 原始碼開發版可執行根目錄「啟動Plus連線.cmd」啟動助手；檔名沿用既有版本，資格仍由實際授權決定。一般使用者請使用已包含執行環境的助手安裝包。

在 Windows x64 執行 `node scripts/package-release.js` 可產生測試安裝包。網站以 `node website/build.mjs` 建置；需先產生對應 release，下載頁才會包含可驗證的發行檔案。

## 回報與參與

閱讀 [SUPPORT.md](SUPPORT.md) 及 [CONTRIBUTING.md](CONTRIBUTING.md)。請勿公開憑證、配對碼、私人影片或完整字幕。

本專案使用 [MIT License](LICENSE)，第三方 Node.js 執行環境保留其授權文件。本工具非 OpenAI、YouTube 或 Amazon 官方產品。
