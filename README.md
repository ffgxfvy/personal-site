# 个人网站（GitHub Pages）

多方向求职与学术科研展示个人主页（纯静态 HTML/CSS + 轻量原生 JS，**无构建步骤**）。
支持按 **全部方向 / 🤖 具身智能与 RL / ⚙️ 控制与嵌入式 / 📊 数据科学与建模 / 💻 软件与全栈开发** 实时筛选项目卡片，支持 URL 参数直达（例如 `?track=ai`、`?track=control`），并内置深/浅色视图切换与本地脱敏简历 `assets/resume.pdf`。

## 已本地化的资产

- `assets/resume.pdf`：1 页排版完整、已主动移除手机号与学号的公开脱敏简历（仅留邮箱与 GitHub）。
- `assets/img/`：已全部从各仓库本地拷贝成果封面图（真实部署实拍图、RL 三代演进箱线图、2025 电赛框图、全栈系统看板截图、论文雷达图/三维轨迹图、统计建模预测图、P2P SVG 架构图），无外链占位图。

## 部署到 GitHub Pages

### 方式 A：作为独立仓库 `personal-site`（推荐，与上传脚本一致）

推送后在仓库 **Settings → Pages → Source** 选 `Deploy from a branch`，分支选 `main`，目录选 `/ (root)`，保存后访问：
`https://ffgxfvy.github.io/personal-site/`

### 方式 B：作为用户根主页 `ffgxfvy.github.io`

若希望短域名 `https://ffgxfvy.github.io/`，在 GitHub 新建名为 `ffgxfvy.github.io` 的 Public 仓库并将本目录文件推送至其 `main` 分支即可。

## 本地预览

```powershell
cd "D:\桌面\实习\作品集\personal-site"
python -m http.server 8000
# 浏览器访问 http://localhost:8000  或  http://localhost:8000/?track=ai
```
