# Glow Boat Bottle · 夜航瓶

> **Tech Keywords:** p5.js, canvas 2d, web audio api, touch interaction

<!-- WORK_META
  slug: glow-boat-bottle
  render_engine: Canvas 2D p5.js 1.9.0
  particle_count: N/A
  particle_type: N/A
  shader_type: N/A
  interaction: touch / click
  audio: Web Audio API synthesis
  effects: water ripples, boat bobbing, cork open-close, release flight, settle chime, seeded layout, glass refraction
  use_cases: p5.js, canvas 2d, web audio api, touch interaction
  standalone: yes
  dependencies: 1 CDN (p5)
  file_size: ~42 KB, 1012 lines
  compatibility: Chrome/Edge/Firefox, Safari iOS 15+
  WORK_META_END
-->

![Glow Boat Bottle - preview 1](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/glow-boat-bottle/v-1781aba67f02/glow-boat-bottle_1.gif)

> 玻璃瓶封着一小片夜海，发光的小船载着少年——拧开瓶塞，让它漂向真正的海。

玻璃瓶里封着一小片夜海。一只发光的白色小船载着少年剪影，在瓶内的水面缓缓起伏。

伸手触摸水面，涟漪会向四周荡开，船身随之轻轻晃动；点一下瓶塞，瓶口打开，小船驶出瓶口，化作背景夜海上的一盏灯。

整件作品是单个 p5.js HTML 文件。瓶形局部坐标系写死，innerR 是唯一边界；确定性随机让每次打开都是同一片海；声音由 Web Audio 实时合成（涟漪、开塞、定居风铃）。

---

## ✨ 预览

直接用浏览器打开 `glow-boat-bottle.html` 即可运行——单文件 H5，仅依赖 1 个 CDN（p5）。

## 📂 文件说明

| 文件 | 说明 |
| --- | --- |
| `glow-boat-bottle.html` | 完整可运行的 H5 互动作品，约 42KB |
| [`glow-boat-bottle_1.gif`](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/glow-boat-bottle/v-1781aba67f02/glow-boat-bottle_1.gif) | 预览图 1（外部资源仓库） |
| `glow-boat-bottle.md` | 本说明文件 |

## 🖱️ 交互

- 触摸瓶内水面 → 泛起涟漪，小船随涌起伏
- 点击瓶塞 → 瓶口开合，触发放行仪式
- 放行后 → 小船漂出瓶口，定居背景夜海，化作一盏灯
- URL 钩子：`?opencork=1` 直接开塞、`?seed=N` 固定布局、`?fast=N` 加速生命周期

## 🛠️ 技术栈

- p5.js
- Canvas 2D
- Web Audio API

## 🌱 创作背景

夜航瓶是一次关于「容器」的练习。药剂瓶、漂流瓶再到夜航瓶——瓶壁既是边界也是舞台，把一小片海封在玻璃里，让光在瓶内自己航行。创作时坚持克制：不动瓶身与背景的大结构，只保留涟漪、随涌这些微小自主行为，让船自己「活」起来。发光小船载着少年驶向真正的海，是这艘瓶留给海的一句晚安。
