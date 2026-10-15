# Mission Control

面向 [MoltBot](https://github.com/0mlkrizzz655335v) 工作流的看板式任务面板：在浏览器里管理 Backlog / In Progress / Review / Done，并通过 GitHub 仓库里的 JSON 与 webhook 和 agent 协作。

## 在线面板

GitHub Pages：

**https://0mlkrizzz655335v.github.io/mission-control/**

打开后按页面引导连接本仓库（需有仓库读写权限的 GitHub 凭据）。**不要把 personal access token 写进 README、issue、截图或提交到 git**；只在浏览器本地连接流程中使用，并尽量用细粒度、可撤销的 token。

## 仓库结构

| 路径 | 用途 |
|------|------|
| `index.html` | 看板前端（单页应用） |
| `data/tasks.json` | 任务、项目、活动记录 |
| `data/crons.json` | 定时任务展示用数据 |
| `data/version.json` | 前端/数据版本元信息 |

面板会通过 GitHub Contents API 读写 `data/*.json`（提交到本仓库），因此需要已启用 Pages，且连接账号对该仓库有写权限。

## 本地预览

任意静态服务器即可，例如：

```bash
python3 -m http.server 8080
# 打开 http://localhost:8080
```

## 安全提示

- 不要在仓库、PR、评论里粘贴 GitHub classic / fine-grained token。
- 若曾泄露，立刻到 GitHub Settings → Developer settings 撤销并轮换。
- Webhook / Tailscale Funnel 等进阶集成见面板内置 Onboarding / Docs；对外暴露的 URL 务必带独立密钥，且不要提交密钥文件。

## License

MIT — 见 [LICENSE](LICENSE)。
