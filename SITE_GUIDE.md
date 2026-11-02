# Zian Wang 学术主页维护说明

网站使用 AcademicPages 仓库中的 Jekyll 构建流程，主页沿用原版 AcademicPages 的导航、侧栏、字体、图标与主题，仅对论文和经历列表添加少量样式。

## 常用修改位置

| 内容 | 文件 |
| --- | --- |
| 姓名、邮箱、GitHub、Scholar、头像 | `_config.yml` 的 `author` 部分 |
| 英文简介与 News | `_pages/about.md` |
| 论文标题、作者顺序、会议、Paper / Code 链接 | `_data/research.yml` |
| 教育、科研经历与荣誉 | `_data/profile.yml` |
| 顶部导航 | `_data/navigation.yml` |
| 排版与手机适配 | `assets/css/academic.css` |
| 页面结构 | `_layouts/academic.html`（继承原版 `default` 布局） |

新增论文时复制 `_data/research.yml` 中的一条记录。`category` 为 `publication` 或 `preprint`；`paper`、`code` 留空时不会出现相应链接。作者顺序和 `*` 共同贡献标记需按正式论文核对。

头像放入 `images/`，然后设置 `author.avatar: "你的文件名.jpg"`。当前未使用占位人物照片。
Google Scholar 填入 `author.googlescholar`，LinkedIn 填入 `author.linkedin`（只填用户名部分）。

## 当前内容来源

个人经历、论文信息和荣誉来自提供的 CV。三个 Paper 链接提取自该 PDF 中的超链接；尚未另行验证这些外部页面的内容。简介和研究方向是基于这些经历起草的英文表述，可继续调整。

网站不提供 CV 入口或下载文件。Downloads 中的原始 CV 没有修改。

模板示例文件保留在源代码中，但通过 `_config.yml` 的 `exclude` 和关闭 collection 输出，避免生成示例博客、教学、演讲、假论文和模板 CV 页面。若以后启用这些栏目，需要先替换示例内容。

## 本地构建

使用 Ruby 3.3 和 Bundler：

```sh
bundle install
bundle exec jekyll serve --host 127.0.0.1 --port 4000
```

打开 `http://127.0.0.1:4000`。修改 `_config.yml` 后需要重启服务。静态构建命令为 `bundle exec jekyll build`，输出目录是 `_site/`，不要提交该目录。

主页使用原版主题 JavaScript 和 jQuery。Google Scholar 图标使用仓库内的 Academicons 字体，其他图标使用原版 Font Awesome。构建时可能出现 Sass 弃用提示，不影响当前主页。论文标题不带链接，使用下方的 Paper / Code 入口。

## GitHub Pages 发布

当前 Git remote 指向 `1663247/1663247.github.io`，对应配置地址为 `https://1663247.github.io`。Zian Wang 是页面显示姓名；如果实际迁移到另一个 GitHub 账号，需要同时更新 `url`、`repository` 和 `author.github`。

仓库保留 `.github/workflows/jekyll.yml` 的自动部署流程，推送到 `master` 时触发。首次上线时，在仓库的 Settings → Pages 中选择 GitHub Actions 作为发布来源，再检查 Actions 中的构建与部署结果。

本次仅修改本地文件，没有提交、推送或改变 GitHub Pages 设置。上线后需再检查正式网址、论文外链和 Google Scholar 链接。
