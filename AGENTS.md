# memory index
- [Development rules](.agents/memory/feedback-development-rules.md) — 只做最小改动、克制验证、把肉眼检查交回用户
- [User profile](.agents/memory/user-profile.md) — Windows 环境、vibe coder 协作方式、双层记忆技能

---

## Memory Operation Rules

- **Zero-Turn Context Perception**: 上面的记忆索引会在每一轮被加载。当任务涉及某个已索引主题时，先用读取工具打开对应的 `.agents/memory/<file>.md` 再下判断。
- **Epistemic Guardrail（"记忆说 X 存在 ≠ X 现在还存在"）**: 记忆记录的是写下时的状态。在依据记忆中的函数、文件或开关去推荐或修改代码前，先用读取工具（读文件、grep/glob）核实它们在当前代码树中是否仍然有效。
- **Associative Mesh**: 主题卡片之间用 `[[slug-name]]` 互相链接。探索相关领域上下文时，顺着这些锚点走。
- **Skills**:
  - `auto-memory`（自动）：当对话中出现持久偏好、行为反馈，或用户确认了某个非常规做法时，由模型自动调用。
  - `session-memory-distill`（手动）：仅在用户于会话/里程碑结束时明确要求时调用。模型绝不可自动调用。

---

## Gentle Nudge

当一次任务解决了非平凡的 bug、经历了多轮调试，或引入了重要的架构决策时，在最终交付回复的结尾附上这一句提醒：
`💡 A significant debugging/milestone experience was recorded. Would you like to run [session-memory-distill] to save it?`

---

# Project Guidelines & Rules

上游： https://github.com/HYXTPSP/BiliLite
我是一个学生,这个软件是我下载下来的个开源项目，我希望对它进行改进。它本身是一个专门用来学习的一个 B 站，它可以在里面选择 UP 主，然后上面就只会出现这个 UP 主的视频，不会被其他的杂七杂八的东西给干扰。现在因为我发现这个软件有些地方做的不好，所以我把它下载了下来，希望 AI 帮助我将它改的更好用。修改过程中，如果需要下载什么东西，比如说安卓开发的软件之类的。首先能在 GitHub 云端的话就用 GitHub 云端构建，不行的话就装在本项目文件夹内，不要装在 C 盘，我的 C 盘快爆了。