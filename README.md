# dev in local
hugo server -D

# deploy
push new posts to github

# visit
https://trust2065.github.io/blog/posts/

# 私密文章 (Private Posts) 功能
- **路徑**: 所有的私密文章請統一放在 `content/posts/private/` 目錄底下。
- **預設設定**: 放在該目錄下的文章會被 `content/posts/private/_index.md` 隱藏，不會出現在部落格的任何首頁、分類列表、或是 RSS 中。
- **自動加密**: 每次推送到 GitHub 時，GitHub Actions 腳本會自動抓取 `public/posts/private/` 下的所有 `.html` 檔案，因為安全性考量，這裡我們使用了 StatiCrypt 加密
- **解鎖方式**: 請確保你在 GitHub Repo 的 **Settings -> Secrets and variables -> Actions** 裡面已經新增了一組名為 `PRIVATE_POST_PASSWORD` 的密碼。如果別人取得你的文章直接連結（例如 `https://trust2065.github.io/cursor_playground/posts/private/test/`），必須輸入這個密碼才能看到內容。
