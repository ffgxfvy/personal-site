# 个人网站（GitHub Pages）

单页静态站点，**无构建步骤**：`index.html` + 一个 CSS 文件。
推到 GitHub 后在仓库设置里选一下发布分支即可上线。

## 上线前必做

### 1. 占位符已填好 ✅

`index.html` 里的 `YOUR_GITHUB_USERNAME` 和 `YOUR_EMAIL` 已经替换成
`ffgxfvy` / `ffgxfvy5562@163.com`。

> 如果你不想公开这个邮箱，把 `index.html` 里两处 `mailto:` 改成
> "邮件索取" 之类的文字即可（搜索 `mailto:` 就能定位）。

### 2. 放入脱敏后的简历 PDF

站点里有一个「简历 PDF」按钮指向 `assets/resume.pdf`，**这个文件目前不存在**，需要你自己放进去。

**放之前必须脱敏**：

- [ ] 删除手机号（或改成只留邮箱）
- [ ] 删除学号、身份证号、家庭住址
- [ ] 确认没有 AutoDL / Hugging Face 等平台的 token
- [ ] 照片可保留（求职场景下需要）

简历源文件在 `D:\桌面\实习\简历.pdf`，导出前记得先改掉手机号。

## 部署到 GitHub Pages

### 方式 A：作为独立仓库（推荐）

```powershell
cd "D:\桌面\实习\作品集\personal-site"
git init -b main
git add .
git commit -m "feat: personal portfolio site"
# 先在 GitHub 上建一个空仓库，名字随意（如 personal-site）
git remote add origin git@github.com:ffgxfvy/personal-site.git
git push -u origin main
```

然后：仓库 **Settings → Pages → Source** 选 `Deploy from a branch`，
分支选 `main`，目录选 `/ (root)`，保存。等 1~2 分钟，访问
`https://ffgxfvy.github.io/personal-site/`。

### 方式 B：作为用户主页（URL 更短）

把仓库名改成 `ffgxfvy.github.io`，推送后直接访问
`https://ffgxfvy.github.io/`。

```powershell
cd "D:\桌面\实习\作品集\personal-site"
git init -b main
git add .
git commit -m "feat: personal portfolio site"
git remote add origin git@github.com:ffgxfvy/ffgxfvy.github.io.git
git push -u origin main
```

> ⚠️ 方式 B 的仓库名必须与用户名**完全一致**，否则不会生效。

### 方式 C：放在作品集仓库的 docs/ 目录

在任意仓库里把站点放进 `docs/`，Pages 的目录选 `/docs`。

## 已经在代码里做好的事

| 事项 | 说明 |
|---|---|
| **响应式** | 手机 / 平板 / 桌面三档，项目卡片在 760px 以上变成三列 |
| **深/浅色自适应** | 用 `prefers-color-scheme` 跟随系统，无需手动切换 |
| **无外部依赖** | 不用 CDN、不加载字体文件、无 JS。断网也能正常显示，加载快 |
| **`.nojekyll`** | 已放置，避免 GitHub Pages 的 Jekyll 处理忽略特定文件 |
| **图片已本地化** | 从各项目仓库复制了 `rl-evolution.png`（三代得分对比）与 `lerobot-cover.png`（项目海报），不依赖外链 |
| **无障碍** | 语义化标签（`header` / `section` / `article` / `footer`）、图片有 `alt` 描述 |

## 内容结构

```
index.html
├── hero           一句话定位 + GitHub / 邮箱 / 简历 三个入口
├── #projects      3 个项目卡片（含指标数据）+ 其他 6 个仓库的清单
├── #publications  论文与荣誉时间线（按年份倒序）
├── #skills        4 组技能（ML/RL、控制优化、嵌入式、软件工程）
└── #contact       联系方式 + 折叠的"课程基础与综合素质"
```

**为什么项目卡片里放了指标数字**（`6.22 → 30.44`、`201 episodes`、`1.2 mm`）：
招聘方扫一眼页面只有几秒钟，"提升了 4.9 倍""201 条数据"这种具体数字比形容词有效得多。

## 后续可以加的东西

- **演示视频**：机械臂项目的 30 秒 GIF 放在 lerobot 卡片的 `thumb` 位置；
  视频文件传到 B 站/YouTube 后外链，不要放进仓库
- **英文版**：复制成 `en/index.html`，在 nav 加语言切换链接（面向外企时可加）
- **博客**：如果开始写技术文章，可以挂到 `/blog/`，用纯静态 Markdown→HTML
  或换成 Astro/Jekyll 主题

## 本地预览

```powershell
# 方式一：直接双击 index.html（file:// 协议能正常显示）
# 方式二：起个本地服务（更接近真实部署环境）
cd "D:\桌面\实习\作品集\personal-site"
python -m http.server 8000
# 然后浏览器打开 http://localhost:8000
```
