# Paper Boat Release · 纸船放行

> **Tech Keywords:** p5.js, canvas 2d, web audio api, touch interaction

<!-- WORK_META
  slug: paper-boat-release
  render_engine: Canvas 2D p5.js 1.9.0
  particle_count: N/A
  particle_type: N/A
  shader_type: N/A
  interaction: touch / click
  audio: Web Audio API synthesis
  effects: bottle physics, water slosh, paper boat release, seagull morph, generative sound
  use_cases: p5.js, canvas 2d, web audio api, touch interaction
  standalone: yes
  dependencies: 1 CDN (p5)
  file_size: ~63 KB, 1651 lines
  compatibility: Chrome/Edge/Firefox, Safari iOS 15+
  WORK_META_END
-->

![Paper Boat Release - preview 1](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/paper-boat-release/v-2ebea3e84f4d/paper-boat-release_1.gif)

> 点开瓶塞，让一只纸船替你把难以言说的心事带向海面。

《Paper Boat Release》把一次轻触变成一段可停留的放行仪式。画面中央的漂流瓶里，纸船、鱼群与水面保持各自的节奏；触碰瓶塞，纸船便有了通向海面的出口。

点击纸船或河灯，会展开一张随机寄语的羊皮纸。你可以让它回到大海继续漂流，或化为海鸥飞离瓶中；水面的点击与拖动则会留下涟漪，并以合成音色回应每次触碰。

作品以单文件 p5.js Canvas 绘制，结合 Web Audio API 在桌面和触屏设备上保留同一份可亲手完成的静谧体验。

---

## ✨ 预览

直接用浏览器打开 `paper-boat-release.html` 即可运行——单文件 H5，仅依赖 1 个 CDN（p5）。

## 📂 文件说明

| 文件 | 说明 |
| --- | --- |
| `paper-boat-release.html` | 完整可运行的 H5 互动作品，约 63KB |
| [`paper-boat-release_1.gif`](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/paper-boat-release/v-2ebea3e84f4d/paper-boat-release_1.gif) | 预览图 1（外部资源仓库） |
| `paper-boat-release.md` | 本说明文件 |

## 🖱️ 交互

- 点击瓶塞，打开或合上纸船离开漂流瓶的出口。
- 点击瓶内纸船、海上的纸船或河灯，阅读一则随机寄语；选择让它回归大海，或化作海鸥。
- 点击或拖动瓶中水面，搅动水波与鱼群，并触发对应的合成音效。

## 🛠️ 技术栈

- p5.js
- Canvas 2D
- Web Audio API

## 🌱 创作背景

有些念头不需要立刻得到答案，也不必被用力地遗忘。纸船放行把它们折成一艘能漂向远方的小船：先在玻璃瓶里安静停靠，等到准备好了，再把瓶塞轻轻打开。
