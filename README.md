# 芬达石森林 — 发布/管理工具

Tools for the [芬达石森林 blog](https://github.com/littlewonderland/fendashi-forest).

## 用法

打开 https://littlewonderland.github.io/fendashi-forest-tools/ 然后：

1. 在 [GitHub Settings → Developer settings → Personal access tokens](https://github.com/settings/tokens?type=beta) 签一条 fine-grained PAT
   - Repository access: All repositories (或者只勾 fendashi-forest)
   - Repository permissions: Contents + Administration 都是 Read and write
2. 在工具页面贴上 PAT
3. 勾「记住」存到浏览器 localStorage
4. 干你想干的事

## 文件

- `publish.html` — 发新文章
- `admin.html` — 管理、编辑、删除现有文章 + 改站点设置

## 怎么工作的

浏览器表单 → 直接调 GitHub Contents API (PUT/DELETE) → 触发 Pages 重建。30 秒后博客上就更新了。

PAT 只存在你的浏览器 localStorage，源码里不会有。

## 自己用

这些工具不绑 repo。要操作别的 blog/repo，只需 fork 改 `REPO` 常量（在两个 HTML 的 JS 顶部 `const REPO = ...`）。
