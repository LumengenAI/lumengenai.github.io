# Henry Xing 的个人网站

基于 GitHub Pages 原生 Jekyll 构建。网站包含技术专题、笔记、课程和关于页；页面结构见 [设计稿](docs/DESIGN.md)。

## 更新内容

- 写笔记：在 `_posts/` 新增 `YYYY-MM-DD-english-slug.md`，填写标题、摘要、专题和 permalink。首页最近更新、笔记列表、专题页及 RSS 会自动收录。
- 写课程：在 `courses/` 新增一个 Markdown 页面，使用 `layout: course`，在正文手工排列章节和课时；课程列表自动收录。
- 修改方向：先调整 `_data/topics.yml`，再同步调整 `topics/` 中对应页面和已有文章的 `topic` 值。
- 修改个人介绍：编辑 `about.md`；首页简短介绍位于 `index.html`。

完整 front matter 与示例见 [内容维护指南](docs/CONTENT.md)。不要发布示例内容；只填已经公开且核实的信息。

## 首次发布前

1. 核实并修改 `index.html` 的一句话介绍、`about.md` 的经历/兴趣与公开联系方式。
2. 按 [内容维护指南](docs/CONTENT.md) 添加第一篇真实笔记和第一门公开课程；不要发布示例内容。
3. 本地构建后逐页检查首页、四个专题、笔记、课程、404、RSS 与 sitemap；手机宽度也要检查导航和代码块。
4. 在 GitHub 仓库 Settings → Pages 选择 `main` 分支根目录，推送后确认 Pages 构建日志及线上页面。

## 本地预览

需要 Ruby、Bundler 和本机可用的原生扩展编译环境。安装依赖后运行：

```sh
bundle install
bundle exec jekyll serve
```

访问 <http://127.0.0.1:4000/>。在 Windows 上需使用 RubyInstaller 的 MSYS2/UCRT64 工具链。如果原生扩展编译时 GCC 无法启动汇编器，可在当前 PowerShell 会话中设置：

```powershell
$env:PATH = "C:\Ruby33-x64\msys64\ucrt64\bin;C:\Ruby33-x64\msys64\usr\bin;$env:PATH"
$env:COMPILER_PATH = 'C:\Ruby33-x64\msys64\ucrt64\bin'
bundle install
```

将 `C:\Ruby33-x64` 换成实际 RubyInstaller 安装目录。若 `eventmachine` 的 C++ 扩展仍编译失败，可先运行 `gem install eventmachine -v 1.2.7 -- --with-cxxflags=-BC:/Ruby33-x64/msys64/ucrt64/bin/`，再运行 `bundle install`。之后运行 `bundle exec jekyll serve` 即可。

部署使用 GitHub Pages 的 `main` 分支根目录。请在仓库 Settings → Pages 中确认该设置。`docs/`、`README.md` 和 Gemfile 不会被发布到站点。
