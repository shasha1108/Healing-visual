# The Sealed Four O'Clock · 封存的四点钟

> **Tech Keywords:** p5.js, canvas 2d, web audio api, touch interaction

<!-- WORK_META
  slug: sealed-summer-jar
  render_engine: Canvas 2D p5.js 1.9.0
  particle_count: N/A
  particle_type: N/A
  shader_type: N/A
  interaction: touch / click
  audio: Web Audio API synthesis
  effects: pixel-art canvas rendering, Frutiger Aero glass gradients, procedural wind noise (lowpass white noise + LFO), cap-release gust animation, interactive cat and wind chimes
  use_cases: p5.js, canvas 2d, web audio api, touch interaction
  standalone: yes
  dependencies: 1 CDN (p5)
  file_size: ~26 KB, 574 lines
  compatibility: Chrome/Edge/Firefox, Safari iOS 15+
  WORK_META_END
-->

![The Sealed Four O'Clock - preview 1](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/sealed-summer-jar/sealed-summer-jar_1.gif)

> 一只玻璃罐，把一个不会结束的夏日下午四点钟封存了起来。

这是一座像素风的玻璃罐微景：罐子里封着一个永不结束的夏日午后——风扇在转，窗帘在鼓，树影在呼吸，小猫趴在原地打盹。画面采用 Frutiger Aero 风格的青蓝玻璃色调，配合罐头边缘的环境光反射，整个场景像泡在清凉的水里。

静置时，罐内的一切持续缓慢地「呼吸」；所有音效都由 Web Audio API 实时合成——白噪声经低通滤波加上 LFO 起伏，生成一阵极轻的背景微风，无需任何外部音频文件。

互动从罐盖的卡扣开始：碰一下，封住的风会被短暂放出来，灌满整个罐子；罐子里的小猫和三只风铃也各自等着被点醒。

---

## ✨ 预览

直接用浏览器打开 `sealed-summer-jar.html` 即可运行——单文件 H5，仅依赖 1 个 CDN（p5）。

## 📂 文件说明

| 文件 | 说明 |
| --- | --- |
| `sealed-summer-jar.html` | 完整可运行的 H5 互动作品，约 26KB |
| [`sealed-summer-jar_1.gif`](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/sealed-summer-jar/sealed-summer-jar_1.gif) | 预览图 1 |
| `sealed-summer-jar.md` | 本说明文件 |

## 🖱️ 交互

- 触碰罐盖卡扣：释放封存的风，罐内气流短暂涌动
- 点击小猫：触发猫咪互动反应
- 点击三只风铃：各自发出合成铃音
- 静置观赏：风扇、窗帘与树影持续缓慢摆动，伴随微风底噪

## 🛠️ 技术栈

- p5.js
- Canvas 2D
- Web Audio API

## 🌱 创作背景

作品的概念写在源码注释里：「一只玻璃罐把一个不会结束的夏日下午封存了起来。」下午四点是一日里最倦怠、也最适合发呆的时刻——把它封进罐子，就可以随时拧开卡扣，放一点风出来。
