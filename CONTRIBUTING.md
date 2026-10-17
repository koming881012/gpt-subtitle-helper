# 參與開發

先以 Issue 描述問題或預定修改，再提交範圍明確的 Pull Request。請保留 MIT 授權及第三方授權文件。

- 使用 Node.js 20 以上及 pnpm，執行 `pnpm install --ignore-scripts`。
- 修改內容腳本後執行 `pnpm build` 更新 content bundle。
- 提交前執行 `node scripts/check.js` 與 `node --test tests/*.test.js`；測試強度與修改風險成比例。
- 使用 fixture 或 mock 測試，避免測試消耗真實帳號額度。只有真實完成的驗證才能標記為實測。
- 不提交 `.env`、憑證、tokens、cookies、個人連線碼、私人字幕、執行記錄或個人操作報告。
- 不加入遠端可執行程式碼、共用帳號或未揭露的資料傳送。翻譯功能需維持使用者自行授權。

回報問題時遵循 SUPPORT.md；Free 帳號資格測試依 FREE_ACCOUNT_TEST.md 記錄。
