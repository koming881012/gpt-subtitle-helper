# GPT 中文字幕助手

免費、MIT 開源的 Chrome 擴充功能，將 YouTube 英文、日文字幕與 Prime Video 英文字幕翻成台灣繁體中文。支援雙語字幕、外觀設定、時間調整、本機快取、SRT／VTT 匯入與匯出。

- [隱私政策](PRIVACY.md)
- [使用支援](SUPPORT.md)
- [問題回報](https://github.com/koming881012/gpt-subtitle-helper/issues)

## 使用條件

目前版本 0.6.0。只需要 Chrome 116 以上，**不需要安裝任何其他程式**（0.4.x 的 Windows 連線助手已不再需要）。只在 Windows 實測，其他作業系統尚未實測。

使用自己的 ChatGPT 帳號，在 OpenAI 官方頁面登入及授權；本工具不接收密碼，也不要求 API Key。翻譯使用該帳號可用的方案額度，不提供共用帳號、額度代付或付費 API 備援。

官方目前列出符合資格的 Plus／Pro 帳號可授權方案用量。**Free 帳號尚未實測**，不能承諾可用，也沒有實測證明不能用。程式依實際授權及模型可用性判斷，沒有依方案名稱阻擋 Free。參考 [測試紀錄](FREE_ACCOUNT_TEST.md) 與 [官方文件](https://developers.openai.com/siwc/quickstart)。

只處理可取得的字幕：YouTube 英文或日文、Prime Video 英文；沒有這些字幕時不能翻譯。日文影片依原音音軌與字幕內容判斷語言，會避開 YouTube 自動配音音軌的字幕。不下載影音、不進行語音辨識、不處理 DRM 或繞過平台限制。YouTube 僅支援一般 watch 影片，不支援 Shorts、Music、嵌入頁及即時直播。平台介面改動可能影響字幕取得。

## 安裝

1. 從 Chrome 線上應用程式商店安裝「YouTube GPT 中文字幕助手」。
2. 開啟插件，按「用 ChatGPT 登入」，在 OpenAI 官方頁面登入及授權。
3. 重新整理影片頁面，開啟有英文或日文字幕的支援影片。可在設定調整自動翻譯、顯示模式與外觀。

## 資料處理

原文字幕及影片標題由插件直接送至 OpenAI 官方 Responses API，使用 `store:false`；不代表服務端所有記錄都不存在。字幕、偏好與登入憑證保存在 Chrome 擴充功能本機儲存。不讀取 ChatGPT 對話或 cookies，沒有開發者遙測及字幕雲端同步。詳見 [PRIVACY.md](PRIVACY.md)。

## 從原始碼開發

原始碼在 `gpt-subtitle-<版本>-source.zip`。需要 Node.js 20 以上及 pnpm：

```powershell
pnpm install --ignore-scripts
pnpm build
node scripts/check.js
node --test tests/*.test.js
```

在 `chrome://extensions` 開啟開發人員模式，按「載入未封裝項目」選擇原始碼目錄。`node scripts/package-release.js` 產生商店上傳用 ZIP。

## 回報與參與

閱讀 [SUPPORT.md](SUPPORT.md) 及 [CONTRIBUTING.md](CONTRIBUTING.md)。請勿公開憑證、私人影片或完整字幕。

本專案使用 [MIT License](LICENSE)。本工具非 OpenAI、YouTube 或 Amazon 官方產品。
