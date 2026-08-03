# Waiting for the Moon · 等月亮

> **Tech Keywords:** p5.js, canvas 2d, web audio api, touch interaction, localstorage persistence

<!-- WORK_META
  slug: moon-cat
  render_engine: Canvas 2D p5.js 1.9.0
  particle_count: N/A
  particle_type: N/A
  shader_type: N/A
  interaction: touch / click
  audio: Web Audio API synthesis
  effects: pixel-art rendering, animated moon phases, procedural stars, rain streaks, meteor trails, bird silhouettes, synthesized purr, lo-fi pad, localStorage persistence
  use_cases: p5.js, canvas 2d, web audio api, touch interaction, localstorage persistence
  standalone: yes
  dependencies: 1 CDN (p5)
  file_size: ~36 KB, 825 lines
  compatibility: Chrome/Edge/Firefox, Safari iOS 15+
  WORK_META_END
-->

![Waiting for the Moon - preview 1](moon-cat_1.gif)

> A quiet moonlit window where a cat slowly falls asleep.

《等月亮》是一段竖屏像素窗景：一只橘猫在窗台上自主呼吸、甩尾、动耳、调姿，夜空中的星星、流星、飞鸟和玻璃上的雨滴以低频事件缓慢经过。画面不设置提示文字，观者只需停留，让场景自己展开；约一分钟后，猫完全睡着，月光成为最后的留白。

按住屏幕或鼠标时，窗台的光影会略微变暖，并静默解锁由 Web Audio API 合成的呼噜与 E♭ 调 lo-fi pad；松手即止。月相通过 localStorage 持久化，重访时有低概率前进一档，保留变化感而不做签到式任务。作品保持单 HTML 结构，使用 p5.js Canvas 2D 绘制，并为手机竖屏与触摸交互设计。

---

## ✨ 预览

直接用浏览器打开 `moon-cat.html` 即可运行——单文件 H5，仅依赖 1 个 CDN（p5）。

### 🎬 演示参数 · Demo Parameters

`等月亮 / Waiting for the Moon` 支持以下 URL 参数。多个参数可以用 `&` 连接。

| 参数 | 示例 | 作用 |
| --- | --- | --- |
| `shot=1` | [`?shot=1`](https://shasha1108.github.io/healing-visual-lab/moon-cat/moon-cat.html?shot=1) | 开启 30 秒可复现录制时间线：流星 ×5、夜鸟 ×3、雨 ×2、猫的生命事件 ×6 |
| `fast=1` | [`?fast=1`](https://shasha1108.github.io/healing-visual-lab/moon-cat/moon-cat.html?fast=1) | 时间流速 ×3，约 20 秒可录到猫入睡的结尾 |
| `days=N` | [`?days=2`](https://shasha1108.github.io/healing-visual-lab/moon-cat/moon-cat.html?days=2) | 月相前进 `N` 步，用于演示重访变化，不写回存储 |

例如，使用 `?shot=1&fast=1` 可以同时开启录制时间线和加速播放。

## 📂 文件说明

| 文件 | 说明 |
| --- | --- |
| `moon-cat.html` | 完整可运行的 H5 互动作品，约 36KB |
| `moon-cat_1.gif` | 预览图 1 |
| `moon-cat.md` | 本说明文件 |

## 🖱️ 交互

- 按住屏幕或鼠标：光影变暖并播放合成呼噜与 lo-fi pad，松手停止
- 点击或触摸：首次交互静默解锁音频；无需操作也可观看场景自行演变
- 重新打开页面：月相可能低概率前进一档，状态保存在 localStorage

## 🛠️ 技术栈

- p5.js
- Canvas 2D
- Web Audio API
- localStorage

## 🌱 创作背景

pending：创作者尚未提供独立的创作背景说明；公开页面不从代码或画面推断个人动机。
