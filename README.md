# Cross Rules

跨平台规则集合仓库，用于存放和管理各类规则配置。

## 简介

本仓库用于集中管理和维护各种规则集，方便跨项目、跨平台复用。

## 目录结构

```
cross-rules/
├── README.md              # 项目说明文档
└── mihomo/                # mihomo (Clash.Meta) 规则集
    ├── ai.list            # AI 网站与工具规则
    └── developer.list     # 程序员常用网站规则
```

## 规则列表

| 文件 | 说明 | 包含内容 |
|------|------|----------|
| `mihomo/ai.list` | AI 网站与工具 | OpenAI, Claude, Gemini, Midjourney, Cursor, GitHub Copilot 等 |
| `mihomo/developer.list` | 程序员常用网站 | GitHub, npm, Docker Hub, Stack Overflow, Vercel 等 |

## 使用方式

### mihomo 配置示例

```yaml
rule-providers:
  ai:
    type: http
    behavior: classical
    url: "https://raw.githubusercontent.com/Ashbaer/cross-rules/main/mihomo/ai.list"
    path: ./ruleset/ai.list
    interval: 86400
  developer:
    type: http
    behavior: classical
    url: "https://raw.githubusercontent.com/Ashbaer/cross-rules/main/mihomo/developer.list"
    path: ./ruleset/developer.list
    interval: 86400

rules:
  - RULE-SET,ai,🤖 AI服务
  - RULE-SET,developer,💻 开发者服务
```

或直接复制规则文件到本地使用。

## 贡献

欢迎提交 Issue 或 Pull Request 来完善规则集。

## 许可证

MIT License
