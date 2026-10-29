# Codex 與 ChatGPT 協作起點

這是協作設定範本，尚未匯入「AI與你企業平台」原始碼，也尚未整合或測試 OCR。

## 使用方式
1. 在 ChatGPT 討論需求，整理成 `docs/HANDOFF.md` 的格式。
2. 在 Codex 開啟這個本機 Git 專案，請它讀取交接文件並實作。
3. 每個功能使用獨立分支，檢查變更與測試結果後，再透過 Pull Request 合併。
4. 把完成的 commit、Pull Request 網址及測試報告帶回 ChatGPT 討論。

GitHub 保存已提交的檔案與版本。ChatGPT 聊天內容不會因為連接 GitHub 就自動全部同步到 Codex；請明確提供交接文件、對話參照或 repo 連結。

## 目前狀態
- 已建立 GitHub 協作範本。
- 原始平台程式位置仍待確認。
- 未配置平台執行環境、部署或 OCR 模型。
- 此 repo 目前為公開倉庫，匯入業務程式或文件前應確認可見性；私密資料、密鑰與電子書不要提交。

## 日常 Git
```sh
git status
git switch -c feature/your-task
# 完成修改與相關測試後
git add <確認要提交的檔案>
git commit -m "說明具體修改"
git push -u origin HEAD
```

本機終端的推送需另有 GitHub 登入憑證。ChatGPT/Codex 的 GitHub 連接器授權不等於本機 Git 已登入。若 push 要求登入，使用 GitHub 官方支援的登入流程，不要將密碼或 token 貼到聊天。

## 回退
保留 main 的穩定版本。功能未合併時，先提交或另存目前修改，再切回 main；已合併的問題修改，以新的 revert commit 回退並重新驗證。不要使用破壞性的 reset 或強制推送。
