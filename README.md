# Personal blog

这是与 `personal-homepage` 分离的 Hugo + PaperMod 博客。文章使用 Markdown 编写，博客通过 GitHub Pages 独立部署，主页只负责介绍个人信息和跳转入口。

## 本地预览

项目需要 Hugo Extended。当前开发环境使用 `D:\project\tools\hugo-0.164.0\hugo.exe`。

```powershell
& D:\project\tools\hugo-0.164.0\hugo.exe server --buildDrafts
```

然后打开 `http://localhost:1313/`。

## 写新文章

```powershell
& D:\project\tools\hugo-0.164.0\hugo.exe new posts/my-first-post.md
```

文章会出现在 `content/posts/`，默认使用 `archetypes/posts.md` 的 front matter 模板。

## 需要替换的占位内容

- `Your Name`
- `yourname.github.io`
- `you@example.com`
- `https://blog.example.com/`
- `content/posts/first-note.md`

## 部署

建议把本目录作为单独 GitHub 仓库，例如 `yourname-blog`，然后在 GitHub Pages 中选择 GitHub Actions。Hugo 的构建产物不需要提交到仓库，推送文章后由 Actions 自动构建和发布。
