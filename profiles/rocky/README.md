# Rocky Profile 备份

本目录包含 Rocky（Guru 的第二个 Hermes Agent）的关键配置文件。

## 文件说明

| 文件 | 内容 | 备注 |
|------|------|------|
| `config.yaml` | Rocky 的 Agent 配置 | MiniMax-M2.7 模型 |
| `.env` | 飞书 Bot 凭证 | App ID 直接可见，App Secret 已脱敏 |
| `auth.json` | MiniMax API Key | Key 已脱敏为 `<MINIMAX_API_KEY_PLACEHOLDER>` |
| `cron/jobs.json.bak` | Rocky 建好时的原始 cron jobs | 11个 jobs（Guru 同步过来的，已清空） |

## 恢复说明

恢复时需要替换以下占位符：
- `<MINIMAX_API_KEY_PLACEHOLDER>` → 真实的 MiniMax API Key
- `<REDACTED>` → 真实的飞书 App Secret（从 `D:\OpenClawAccount\` 读取）

## 相关文档

- 搭建实录：`~/.hermes/cron/output/Hermes-Profile-Rocky-搭建实录.md`
- hermes-profile-builder Skill：`~/.hermes/skills/hermes/hermes-profile-builder/SKILL.md`
