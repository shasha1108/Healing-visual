# Tang Sancai Fire · Luoyang Kiln Chronicle · 三彩釉火 · 洛阳窑记

> **Tech Keywords:** canvas 2d, three.js, webgl, web audio api, touch interaction, localstorage persistence, glsl shader

<!-- WORK_META
  slug: tang-sancai-fire
  render_engine: WebGL (Three.js)
  particle_count: N/A
  particle_type: N/A
  shader_type: custom ShaderMaterial / GLSL
  interaction: touch / click
  audio: Web Audio API synthesis
  effects: Three.js scene, ShaderMaterial/GLSL glaze, Web Audio API kiln cues, Canvas 2D export, localStorage persistence
  use_cases: canvas 2d, three.js, webgl, web audio api, touch interaction, localstorage persistence, glsl shader
  standalone: yes
  dependencies: 1 CDN (three)
  file_size: ~1.6 MB, 209 lines
  compatibility: Chrome/Edge/Firefox, Safari iOS 15+
  WORK_META_END
-->

![Tang Sancai Fire · Luoyang Kiln Chronicle - preview 1](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/tang-sancai-fire/v-7045a7066d41/tang-sancai-fire_1.gif)

> 从白胎到窑火：在一匹唐三彩马身上，留下你的釉色与一则窑记。

《三彩釉火 · 洛阳窑记》是一件可触摸的 WebGL 三维互动作品。访客从四种基础施釉环境开始，在陶马与饰件上补色，并可拖动转台从不同角度审视火后流彩。

完成施釉后，作品将进入可调节火候与风箱的烧制流程，并生成一张 3:4「窑记」图像。三维场景由 Three.js 驱动，釉色效果使用 ShaderMaterial / GLSL 实现；操作进度和结果会保存在本地浏览器中。

---

## ✨ 预览

直接用浏览器打开 `tang-sancai-fire.html` 即可运行——单文件 H5，仅依赖 1 个 CDN（three）。

## 📂 文件说明

| 文件 | 说明 |
| --- | --- |
| `tang-sancai-fire.html` | 完整可运行的 H5 互动作品，约 1.6MB（本地陶马资源已内联） |
| [`tang-sancai-fire_1.gif`](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/tang-sancai-fire/v-7045a7066d41/tang-sancai-fire_1.gif) | 预览图 1（外部资源仓库） |
| `tang-sancai-fire.md` | 本说明文件 |

## 🖱️ 交互

- 选择「洛阳经典」「黄绿交融」「留白轻彩」或「空白胎」作为基础施釉环境。
- 选择蜜黄、孔雀绿或白浅釉，在陶马可施釉区域上触摸或点击补色。
- 拖动陶台进行 360° 审视；选择火候并拉动风箱后启动烧制。
- 将完成的窑记导出为 3:4 PNG 图像；浏览器会保存本地创作状态。

## 🛠️ 技术栈

- Three.js
- Canvas 2D
- WebGL
- Web Audio API
- localStorage

## 🌱 创作背景

pending（未提供创作背景）
