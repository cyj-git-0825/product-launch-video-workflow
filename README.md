# e2a Launch Video

用 [HyperFrames](https://hyperframes.heygen.com) 做的 **e2a 产品发布短片**(~55s,1080p,含配音 + BGM)。

一个关于 **"给 AI agent 一个真实的 email 地址,就是给它一个身份"** 的故事:agent 是你的新队友,但它没有地址、够不到任何人;e2a 给它地址后,它就能替你把对外的活干了,而你始终掌控。

**成片:** [`renders/e2a Launch.mp4`](renders/)

---

## 故事骨架(identity story)

```
Intro   遇见你的新 agent
Hook    你有一堆对外的活(客户 / 订单 / 会议 / 供应商)想甩给它
Pain    它能想、能起草,却够不到任何人 —— 它没有地址(团队花名册里唯一没邮箱的)
Reveal  e2a 给它一个真实地址:agent@agents.e2a.dev,身份点亮
Work    它替你把活干了 —— 四个业务分屏演真实邮件往来
        Support·Stripe / Scheduling·Google Meet / Commerce·Amazon / Reception·Slack
Trust   要群发 2,400 个客户?先 HELD,你点一下 Approve 才发出
Close   "你的 agent 不需要又一个 dashboard,它需要一个地址" + 一行命令安装
Brand   e2a · Give your agent an address.
```

核心隐喻:**Email address = identity**(而不是 email = 一个通信功能)。

---

## AI 视频工具选型:Remotion vs HyperFrames

两者不是替代关系,而是**分工互补**。

### Remotion —— 强,但改局部动效偏重
- 能做出很多**电影感镜头**,表现力强。
- 但做**局部动效微调**时"改起来有点重":动一个小效果往往要改 React 组件、跑整体编译,牵一发动全身。
- → 更适合 **总控 / 编排**。

### HyperFrames —— 改动效很直接,但不适合总控
- 一个 frame 就是一段 HTML + GSAP,**改动效所见即所得、seek-safe**,非常直接。
- 但**不适合做整片的总控 / 编排**。
- → 更适合 **把某一段画面 / 动效做得更高级**。

---

## 推荐分工:Remotion 总控 + HyperFrames 打磨

如果目标是产出**一套长期可复用的视频生产系统**(选题 → 脚本 → 镜头 → 字幕 → 画面 → 导出):

| 层 | 谁负责 | 干什么 |
|---|---|---|
| **总控 / 编排** | **Remotion** | 整条视频"怎么走":A-Roll / B-Roll、字幕、音频、镜头、时间轴、总控 |
| **单段打磨** | **HyperFrames** | 这一段"怎么更好看":单个镜头 / 动效 / B-roll 的高级感 |

- HyperFrames 配合 **`auto-motion` skill**:把动效分镜头拆成**独立的 project**,方便单独调整——改这一段动效不影响整片。
- 一句话:**Remotion 定"骨架和节奏",HyperFrames 把每块骨头打磨到高级。**

---

## 这支片的制作流水线(HyperFrames)

```
STORYBOARD.md  分镜(每帧一拍,含 transition / duration)
SCRIPT.md      锁定旁白
    ↓
compositions/frames/*.html   逐帧手写 HTML + GSAP(seek-safe 单时间轴)
    ↓
audio.mjs      Kokoro 本地 TTS 生成配音 + 时长对齐
assemble-index.mjs   组装成 index.html(帧 + 语音轨)
transitions.mjs      注入电影级 seam(zoom-through / blur-crossfade / push-slide)
    ↓
hyperframes render   → renders/*.mp4
    ↓
剪映 / CapCut        加 BGM、导出成片
```

---

## 设计要点

- **Committed 配色**(遵循设计法则,拒绝撞色卡 / clown palette):奶油纸 `#faf7f2` + 深墨绿 `#2b4033` + 和谐分类色(绿 / 蓝 / 金 / 紫)+ 电光青柠 `#d3fb52` 作能量点缀。
- **字体**:Fraunces(展示)+ Inter(正文)+ JetBrains Mono(地址 / 终端)。
- **视觉母题**:`agent@agents.e2a.dev` 这个地址贯穿全片——从空 `????` → 打字点亮 → 每个动作的签名。
- 逐业务**全屏真实场景**(不挤在一个看板)+ 超大 macOS 光标点击 Approve。

---

## 目录结构

```
renders/e2a Launch.mp4     最终成片
STORYBOARD.md / SCRIPT.md  分镜 + 旁白
frame.md                   设计系统(配色 / 字体 / 组件规范)
compositions/frames/       8 个逐帧 HTML(00-intro … 07-brand)
assets/fonts/              品牌字体(woff2)
capture/                   e2a.dev 抓取的品牌 token / 截图
index.html                 组装后的主合成
```
