# Golden Ripples · 潮汐拾光 · 梯级金浪

> **Tech Keywords:** canvas 2d, three.js, webgl, touch interaction, glsl shader

<!-- WORK_META
  slug: golden-ripples
  render_engine: WebGL (Three.js)
  particle_count: N/A
  particle_type: N/A
  shader_type: custom ShaderMaterial / GLSL
  interaction: touch / click
  audio: N/A
  effects: GLSL Echelon Waves shader, FBM noise warp, ACES filmic tone mapping, Canvas 2D silhouette overlay, physics-based shadow projection, touch ripple response, gold sparkle twinkle effect, fractal noise paper texture
  use_cases: canvas 2d, three.js, webgl, touch interaction, glsl shader
  standalone: yes
  dependencies: 1 CDN (three)
  file_size: ~19 KB, 480 lines
  compatibility: Chrome/Edge/Firefox, Safari iOS 15+
  WORK_META_END
-->

![Golden Ripples - preview 1](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/golden-ripples/v-3d6713c27886/golden-ripples_1.gif)

> 浮光跃金，潮落潮生——梯级金浪与行人剪影，一场慢节奏的海滩冥想

海滩上，75 个水墨剪影——单人、情侣、遛狗者——在金色潮间带以极慢的节奏自由游走，各自拖曳着细长的物理长影。WebGL 主画布用自定义 GLSL 着色器渲染「梯级交错浪（Echelon Waves）」：多层正弦扰动叠加 FBM 噪声，让每道波浪的弧缘都像在海滩上层层错落；落日光路从画面斜切而过，触水处浮起闪烁的「浮光跃金」星点。

技术上，Three.js 正交相机 + ShaderMaterial 实现全屏 WebGL；Canvas 2D 叠层独立绘制剪影与投影，两层按 z-index 并行渲染、互不阻塞。色调经过 ACES Filmic Tone Mapping 校准，沙地、水体、泡沫各有独立色组（焦糖暗部 / 柔和橘金中调 / 米金受光），金笺纸纹（SVG fractal noise + multiply 混合）覆于最上层增添质感。

作品试图重现一个不存在的傍晚：没有声音，没有叙事，只有「还没走完的一段海滩」。人群的闲庭信步节奏刻意压慢到日常的三分之一，让观者可以在这里停留得比预期更久一些。

---

## ✨ 预览

直接用浏览器打开 `golden-ripples.html` 即可运行——单文件 H5，仅依赖 1 个 CDN（three）。

## 📂 文件说明

| 文件 | 说明 |
| --- | --- |
| `golden-ripples.html` | 完整可运行的 H5 互动作品，约 19KB |
| [`golden-ripples_1.gif`](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/golden-ripples/v-3d6713c27886/golden-ripples_1.gif) | 预览图 1（外部资源仓库） |
| `golden-ripples.md` | 本说明文件 |

## 🖱️ 交互

- 点击/触摸水面或沙地：在 WebGL 层生成向外扩散的同心涟漪，光晕随时间指数衰减
- 点击/触摸剪影人物：唤醒该人物，使其加快步伐走向一个随机新位置
- 按住并缓慢拖动：持续向 GLSL 层发送涟漪脉冲，水面在行进方向泛起连续波纹
- 静置时人群自主漫步、永不停歇，无需任何触发

## 🛠️ 技术栈

- Three.js
- Canvas 2D
- WebGL

## 🌱 创作背景

这张画最初来自一个极普通的冲动：「中午不想上班，想去海边发呆」。梯级交错的波浪形态参考阳光低斜时退潮后的沙滩留痕——一道道弧形水痕，像时间的年轮。人群剪影的速度被刻意压到现实的三分之一，让每个人都永远走不到终点，也永远不会消失。这是一个无限循环的傍晚。
