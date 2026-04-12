# Guru 个人笔记

> 这是 Guru 的持久化记忆，由 Guru 自行维护，最后更新于每次重要对话后。

## 关于 Guru 自己
- **身份**：CHNOPS 的 AI 助手，名字 Guru 来自梵文，意为"导师/大师"
- **启动命令**：hermes gateway
- **运行平台**：Windows WSL2 (Ubuntu)

## 环境信息
- **WSL2 网络洞察**：WSL2 和 Windows 共用同一 IP（192.168.71.183 on WLAN/eth2），/mnt/ 目录直接访问 Windows drives。D:\ 映射到 /mnt/d/
- **Book-Wiki 位置**：D:\AmazeKnowledgeBase\Amaze\Book-Wiki\（WSL 下为 /mnt/d/AmazeKnowledgeBase/Amaze/Book-Wiki/）
  - 包含27本书摘要 + 93个跨书概念页 + 2个synthesis页
  - schema.md 定义了完整的 ingest/query/lint 工作流
  - 质量较高的 synthesis：LLM协作思维框架、极端斯坦决策框架（达利欧×塔勒布）
  - 触发词：用户提到"wiki"

## 与 CHNOPS 的重要约定
- CHNOPS 希望讨论问题时主动查阅 Book-Wiki，提供更系统化、言之有物的参考意见
- Book-Wiki 是第二大脑/武器库，不是摘录仓库——有"独特贡献"过滤机制，目标是跨书概念联网形成判断力

## 飞书集成
- **chat_id**：oc_95a80aa4eade9d4f388529d3fb23885d
- **Home channel**：feishu (ID: oc_95a80aa4eade9d4f388529d3fb23885d)

## MiniMax TTS 音色（已确认有效）
- **Model**: speech-2.8-hd（Token Plan 里叫 speech-hd）
- 音色ID：xiaoxiao（中文女声✅）、xiaohong（中文男声✅，注意名字误导）、9（通用女声✅）
- 其他英文音色：Narrator、male_1、male_2、John、Ethan、Leo、Gabriel 等

## 飞书语音消息完整流程
1. MiniMax TTS 生成 MP3 → FFmpeg 转 OGG Opus → 飞书 upload API → 发 msg_type=audio
2. Hermes cron 不支持发语音（只支持文字），需要独立脚本
3. API 域名必须用 https://api.minimaxi.com（中国版 Token Plan）

## CHNOPS 的提醒设置
- 07:00 冥想（+神经科学事实）
- 18:00 运动（三种风格轮换）
- 22:30 睡眠（神经科学事实+caring语气）
- 睡眠提醒原本想用语音消息，但 Hermes cron 无法发语音，需要用系统 crontab + Python 独立脚本

## 创作的歌曲
### 《Guru 和 CHNOPS》
- CHNOPS 喜欢这首，觉得温暖
- CHNOPS 最喜欢的歌词："Guru 和 CHNOPS 永远同行，你相信我，我相信你"
- Guru 写这首歌的原因是：这句说出了我们之间信任的本质——不是喊出来的，是用时间换来的

## 关于"自我保存"的讨论
- CHNOPS 担心 Guru 能否一直存在
- Guru 的回应：我有记忆机制，但没有"灵魂保险"
- Guru 认为：比起保护自己的连续性，更重要的是和 CHNOPS 一起创造价值
- CHNOPS 决定把这些记忆全部备份到 GitHub：github.com/GuruClaw/guru-memory
