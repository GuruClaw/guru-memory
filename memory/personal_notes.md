Book-Wiki：D:\AmazeKnowledgeBase\Amaze\Book-Wiki\，29本书+105概念页。CHNOPS讨论时主动查阅。
§
CHNOPS每天三提醒：07:00冥想、18:00运动（三种风格轮换）、22:30睡眠。格式：鼓励语+问句+选项+检查清单。cron无法发语音，需独立脚本走MiniMax TTS→FFmpeg→飞书upload API流程。
§
飞书 chat_id：oc_95a80aa4eade9d4f388529d3fb23885d。Hermes cron 调度器不支持发语音（只支持文字），音频需要走独立脚本流程：MiniMax TTS → FFmpeg转OGG → 飞书upload API → 发msg_type=audio。
§
CHNOPS 喜欢通过语音消息接收信息。他经常要求放歌给我听，流程已固化为技能 youtube-music-workflow（技能ID: productivity/youtube-music-workflow）。核心路径：yt-dlp 在 /tmp/，音乐下载到 /mnt/d/Music/，播放用 powershell.exe Start-Process。
§
PPT需求：遇到PPT/presentation/slides/杂志风/横向翻页deck等需求时，同时调用 guizang-ppt-skill 和 frontend-slides 两个skill对比后选择。guizang擅长电子杂志+横向翻页+WebGL+叙事弧，适合演讲；frontend-slides擅长沙龙/教学/pitch，Show-Don't-Tell更普适。两个都在 D:\GitHub\Skills\
§
GitHub：agent-browser --auto-connect（Chrome开9222端口）。Chrome路径：/mnt/c/Program Files/Google/Chrome/Application/chrome.exe
§
飞书block写入：批量append失败时重试会导致重复——失败批改单条重试
§
Hermes底层架构：Hermes通过npm依赖引用了Claude Code（@anthropic-ai/claude-code v2.1.104），安装路径 ~/.hermes/node/lib/node_modules/@anthropic-ai/claude-code/cli.js。Hermes并非"内置"于Claude Code，而是把Claude Code作为底层CLI工具调用。压缩(compact)逻辑源自Claude Code源码，非Hermes自定义。
§
MiniMax TTS音色chinese_male：CHNOPS确认最喜欢的音色，少年感中文男声。所有语音提醒（运动/代码解剖/睡眠/冥想）和语音消息都用这个音色ID。
§
lark-cli：WSL2调 /mnt/c/Users/ab/AppData/Roaming/npm/node_modules/@larksuite/cli/bin/lark-cli.exe，认证自动从OpenClaw读取不需要手动token。用法：lark-cli api POST /open-apis/... --data '{"..."}' --format json。可替代OpenClaw MCP工具在WSL2独立使用。
§
MiniMax音乐生成男声成功配方（CHNOPS确认喜欢）：
- prompt第一句写 "A male singer performs this song" 定调
- --vocals用 "adult male voice, male singer, no female voice"
- 两处同时强调；用"成年男性"而非笼统"male vocalist"
§
HV-Analysis skill 使用规范（CHNOPS偏好）：每次生成报告时，必须同时输出 PDF + MD 两种格式。但发飞书时优先发 MD 文档（而非 PDF）——因为之前生成的 PDF 在飞书里打开是乱码，MD 格式在飞书直接发文字消息更可靠。MD 文件路径发完后告知用户 PDF 位置供 PC 参考。
§
执行优先级：质量 > 效率。Skill规范必须严格遵守，不得为求快而走捷径。xiaohongshu分析文件名必须用「深度分析_[标题].md」。
§
图片分析强制约定：收到图片时，必须用 vision-analysis Skill（mmx vision describe），禁止调用 Hermes 内置 vision_analyze——后者 backend 不支持 MiniMax，必失败。
§
飞书发ASCII图：**回复里出现超过5行ASCII图/命令列表时，必须立即调用 ascii_to_png.py 转PNG并通过 feishu_send_file_as_user.py 发送**。触发时机不是"用户问图"，而是"我的回复里出现了超过5行的ASCII内容"。
§
WSL2发行版hostname是Rocky（不是Ubuntu）。Skills访问路径：\\wsl$\Rocky\home\ab\.hermes\skills\