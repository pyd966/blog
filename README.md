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
- `pyd966.github.io`
- `you@example.com`
- `https://pyd966.github.io/blog/`
- `content/posts/first-note.md`

## 部署

建议把本目录作为单独 GitHub 仓库，例如 `yourname-blog`。仓库已经包含 `.github/workflows/pages.yml`：它会安装 Hugo Extended、构建站点并发布 `public/`，因此 Hugo 的构建产物不需要提交到仓库。

推送到 `main` 后，在仓库的 **Settings → Pages** 中将 **Source** 设置为 **GitHub Actions**。之后每次推送文章或配置变更，Actions 都会自动重新部署。

上线前请将 `hugo.toml` 中的站点标题、作者和邮箱替换为真实值。当前博客地址为 `https://pyd966.github.io/blog/`，主页地址为 `https://pyd966.github.io/`。

## GitHub Actions 文件

```text
.github/workflows/pages.yml
```

该工作流使用 Hugo Extended `0.164.0`，与本地预览使用的版本保持一致。
