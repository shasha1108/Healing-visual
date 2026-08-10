# Tide-Keeping Station · 潮汐保管处

> **Tech Keywords:** canvas 2d, three.js, webgl, web audio api, touch interaction, glsl shader

<!-- WORK_META
  slug: tide-keeping-station
  render_engine: WebGL (Three.js)
  particle_count: N/A
  particle_type: N/A
  shader_type: custom ShaderMaterial / GLSL
  interaction: touch / click
  audio: Web Audio API synthesis
  effects: Gerstner wave displacement, Canvas 2D thread-field simulation, GLSL ShaderMaterial ocean, pink-noise audio synthesis, 216/432Hz binaural response tone, deterministic seed rendering
  use_cases: canvas 2d, three.js, webgl, web audio api, touch interaction, glsl shader
  standalone: yes
  dependencies: 1 CDN (three)
  file_size: ~49 KB, 1416 lines
  compatibility: Chrome/Edge/Firefox, Safari iOS 15+
  WORK_META_END
-->

![Tide-Keeping Station - preview 1](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/tide-keeping-station/tide-keeping-station_1.gif)

> 把缠成一团的事交给潮汐，它会替你拆开、带走，并留下回应。

「潮汐保管处」是一场单次的交接仪式。画面中央悬着一团由未完成感缠成的暗结——那些说不出口、也放不下的事，在这里被具象成一片缠绕的线场。你只需要按住它，感受它在掌心的重量；松手的那一刻，交接完成，剩下的事交给海。

海面由 Gerstner 波实时位移生成，潮汐有自己的节奏，不催促、不旁观。暗结落进水里后，会被波浪一层层拆开、带走，随后海面回以一段 216/432Hz 的泛音回应——像一个"已收到"的回执。Canvas 2D 的线场悬浮在 WebGL 海面之上，两个渲染层各管各的事：一层负责纠缠，一层负责释怀。

整件作品只依赖一个 CDN（Three.js），音频全部由 Web Audio API 现场合成（粉噪潮汐 + 因果回应音），无任何音频文件。按住与松手之间，是你唯一需要做的决定。

---

## ✨ 预览

直接用浏览器打开 `tide-keeping-station.html` 即可运行——单文件 H5，仅依赖 1 个 CDN（three）。

## 📂 文件说明

| 文件 | 说明 |
| --- | --- |
| `tide-keeping-station.html` | 完整可运行的 H5 互动作品，约 49KB |
| [`tide-keeping-station_1.gif`](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/tide-keeping-station/tide-keeping-station_1.gif) | 预览图 1 |
| `tide-keeping-station.md` | 本说明文件 |

## 🖱️ 交互

- **按住**画面中央的暗结，感受线场在掌心收紧
- **松手**，把暗结交给潮汐，海会替你拆开、带走
- 等待海面的**回应音**（216/432Hz 泛音），那是"已收到"的回执
- 音频为可选体验，首次交互后按提示开启

## 🛠️ 技术栈

- Three.js
- Canvas 2D
- WebGL
- Web Audio API

## 🌱 创作背景

人总有些事，既不想继续攥着，也做不到随手丢掉。「保管处」是第三种去处——不解决，也不遗忘，只是暂时交给一个比自己大的节律。潮汐从不说教，它只负责带走。这件作品想提供的正是这样一个中转站：你完成松手的动作，世界负责完成剩下的释放。
