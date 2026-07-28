# 旧信号 · The Old Signal

> **Tech Keywords:** p5.js, canvas 2d, web audio api, touch interaction, localstorage persistence

<!-- WORK_META
  slug: the-old-signal
  render_engine: Canvas 2D p5.js 1.9.4
  particle_count: N/A
  particle_type: N/A
  shader_type: N/A
  interaction: touch / click
  audio: Web Audio API synthesis
  effects: anaglyph misregistration (lighter composite), deterministic hash glitch, scanlines + rolling band, pregenerated noise frames, riso paper grain, spring-physics knobs, screen spill glow, ambient env-glow transition, Web Audio CRT hum + power-down pitch drop
  use_cases: p5.js, canvas 2d, web audio api, touch interaction, localstorage persistence
  standalone: yes
  dependencies: 1 CDN (p5)
  file_size: ~31 KB, 810 lines
  compatibility: Chrome/Edge/Firefox, Safari iOS 15+
  WORK_META_END
-->

![The Old Signal - preview 1](the-old-signal_1.gif)

> 一台信号不好的旧电视，红青两个色版错开着呼吸；你每碰它一次，它就调准一点——直到屏幕里那个旧日的自己，回头看你一眼。

一台落灰的 90 年代奶油白 CRT 电视，立在暗室里。屏幕信号不好：青与橙两个色版错开着呼吸，噪点拍打，扫描线缓缓滚过——那是现在与过去叠不齐的影子。每拍一次机身，旋钮就进一格，画面就向清晰逼近一步；进度快满时信号会进入「风暴带」，画面抗拒地弹开、闪白，像记忆在最后一刻的挣扎。

完全调准的瞬间，50Hz 的 CRT 低鸣 pitch down 到 18Hz 后彻底切断，暖垫音隔一秒才漫进来；屏幕里的旧日午后变得可辨认——窗、落日、地毯，还有那个背对你坐着的小孩。随后，他会回头看你一眼：时间定格，暖光洪水漫过整个房间。触碰次数与旋钮格位被 localStorage 记住，下次打开时信号保持在你离开的样子。

技术上，错版由青橙双色版在 `lighter` 混合模式下对称叠合而成（叠合即亮白，是错版美学的根基）；所有毛刺与噪点都是时间的确定性函数（hash 驱动，draw 内无 random）；像素世界以 2px 格为原子单位，整数渲染保证每个像素干净。

---

## ✨ 预览

直接用浏览器打开 `the-old-signal.html` 即可运行——单文件 H5，仅依赖 1 个 CDN（p5）。

## 📂 文件说明

| 文件 | 说明 |
| --- | --- |
| `the-old-signal.html` | 完整可运行的 H5 互动作品，约 31KB |
| `the-old-signal_1.gif` | 预览图 1 |
| `the-old-signal.md` | 本说明文件 |

## 🖱️ 交互

- **拍击电视机身**（含天线范围）：调准信号——旋钮步进一格，色版对齐推进一拍（非线性节拍，越到后面步长越小）
- **反复拍击直至调准**：触发「回头」事件——小孩回头看你，首次伴随时间定格与暖光洪水
- **调准后静置**：每约 8 秒小孩会周期性回头一次
- **进度自动存档**：localStorage 记住对齐进度 / 旋钮格位 / 触碰次数，重开页面续上

## 🛠️ 技术栈

- p5.js
- Canvas 2D
- Web Audio API
- localStorage

## 🌱 创作背景

每个人都有一台这样的旧电视。不是某台具体的机器，而是那种「信号不好」的感觉——过去明明就在那里，却隔着噪点和错位，怎么也对不齐。拍打机身是大人教我们的第一个巫术：不讲道理，但有时真的有用。

这件作品把那个巫术做成了真的。你拍，它就好一点。而当你终于把信号调准，看清那个坐在旧日午后里的小孩时，他会回头看你——原来一直被注视的，是你。

## 🎛️ 演示 / 拍摄参数

在 URL 后追加查询参数，可直接定格到需要的画面状态（可任意组合，用 `&` 连接）：

| 参数 | 取值 | 效果 |
| --- | --- | --- |
| `align` | `0` ~ `1` | 直接设定初始对齐进度。`0.12` 为默认开局（严重错版）；`0.9` 进入风暴带；`1` 完全调准 |
| `turn` | `1` | 直接取景「回头看你」状态（需配合 `align=1` 才有清晰画面） |
| `shot` | `1` | 跳过开机阶段，首帧即稳定画面（拍封面/录屏必加） |
| `fresh` | `1` | 清除 localStorage 存档，从零开始（演示完整调准流程前必加） |
| `clean` | `1` | 隐藏底部「旧 信 号」标题文字（纯净画面） |

常用组合：

- 封面定格（回头瞬间）：`?align=1&turn=1&shot=1&clean=1`
- 错版开局（演示起点）：`?fresh=1&shot=1`
- 风暴带（记忆抗拒的挣扎态）：`?align=0.9&shot=1&clean=1`
- 完整演示流程：先 `?fresh=1` 清零，再连续拍击机身直至调准

> 注意：交互会写入存档。演示/拍摄结束后，用一次 `?fresh=1` 即可恢复出厂状态。
