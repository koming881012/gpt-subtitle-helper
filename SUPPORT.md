# 使用支援

網站：https://gpt-subtitle-helper.justkodo.chatgpt.site/support.html

問題回報：https://github.com/koming881012/gpt-subtitle-helper/issues

## 回報內容

提供擴充功能版本、Chrome 版本、Windows 版本、重現步驟、預期與實際結果，以及去識別後的錯誤代碼。公開影片連結僅在你願意公開且確實與問題相關時提供。可從設定複製診斷，但送出前仍應檢查是否包含私人資訊。

不要提供密碼、一次性驗證碼、token、cookies、Authorization、授權回呼網址、本機連線碼、signed 字幕網址、完整字幕或私人影片資訊。GitHub Issue 是公開頁面。

## 常見狀況

- 未連接：先完成 Windows 助手安裝，再回插件按登入；更新後重新載入插件並重新整理影片頁面。
- 已登入但不能翻譯：確認另已授權方案用量，再看帳號可用模型與具體錯誤。登入成功不等於取得翻譯額度。
- ChatGPT Free：尚未實測，見 FREE_ACCOUNT_TEST.md。沒有依方案名稱直接封鎖，仍須 OpenAI 實際授權。
- 沒有英文來源：確認影片有可取得的原始英文字幕。工具不擷取音訊、不繞過平台限制。
- 429／額度限制：依提示等待或恢復未完成工作，不提供付費 API 回退。
- 移除：先登出及清除快取，再移除 Chrome 擴充功能；刪除 Windows 啟動資料夾內的「YouTube GPT 字幕連線」捷徑，登出 Windows 後移除 `%LOCALAPPDATA%\YouTubeGPTSubtitle`。匯出的字幕檔需自行刪除。

隱私問題亦可透過上述回報頁提出一般問題，勿在公開回報中提供個人資料。
