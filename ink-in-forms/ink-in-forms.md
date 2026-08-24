# Ink In Forms · 墨中有相

> **Tech Keywords:** three.js, touch interaction, glsl shader

<!-- WORK_META
  slug: ink-in-forms
  render_engine: WebGL (Three.js)
  particle_count: 30K-62K
  particle_type: procedural + canvas-mask sampled points
  shader_type: custom ShaderMaterial / GLSL
  interaction: touch / click
  audio: N/A
  effects: procedural taichi topology, layered landscape particle field, canvas mask sampling for crane/peony, custom ShaderMaterial ink diffusion, GPU pointer displacement, breathing motion, four-stage press-and-hold state machine
  use_cases: three.js, touch interaction, glsl shader
  standalone: yes
  dependencies: 1 CDN (three r128)
  file_size: ~41 KB
  compatibility: Chrome/Edge/Firefox, Safari iOS 15+
  WORK_META_END
-->

![Ink In Forms - preview 1](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/ink-in-forms/v-2d04b3a1c0ee/ink-in-forms_1.gif)

> 长按，把浮水中的彩墨交给一枚心印——太极、鹤影、山水、牡丹，成形后仍会呼吸，也仍会被指尖拨散。

这是一件把「按」当作笔的作品。底栏摆着四枚国风心印，太极、鹤影、山水、牡丹；选中一枚，长按，浮在水中漂游的彩墨粒子会随你的停留逐渐凝成那枚图案——先归位，再成形，成形后带着水墨独有的呼吸感轻轻浮动。松手不是终点：墨印安放之后，鼠标或手指轻触仍能把墨推开，它让开，又慢慢回来。

技术上，粒子在 Three.js 双场景 WebGL 中运行：太极用程序化拓扑直接铺出阴阳盘面，山水用分层目标场堆出远山与流水，鹤影与牡丹则先由 Canvas 蒙版采样墨稿轮廓，再映射为粒子目标场——三种构造方式各得其所。所有形变都在自定义 ShaderMaterial 的 GLSL 里完成，粒子尺寸、湿度、墨色与边缘随机扰动随按压状态分四个阶段平滑过渡（recognize → handoff → release → respond），粒子数按设备触屏能力在 30K–62K 间自适应。

「墨中有相」想说的是：相不是预先画好的，是墨在自己走完这一程之后显现的。长按的动作被拉得很慢，慢到你能感到墨粒一枚枚归位的过程——这枚印，是你和它一起按出来的。

---

## ✨ 预览

直接用浏览器打开 `ink-in-forms.html` 即可运行——单文件 H5，仅依赖 1 个 CDN（three r128）。

## 📂 文件说明

| 文件 | 说明 |
| --- | --- |
| `ink-in-forms.html` | 完整可运行的 H5 互动作品，约 41KB |
| [`ink-in-forms_1.gif`](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/ink-in-forms/v-2d04b3a1c0ee/ink-in-forms_1.gif) | 预览图 1（外部资源仓库） |
| `ink-in-forms.md` | 本说明文件 |

## 🖱️ 交互

- 选择一枚心印：太极、鹤影、山水、牡丹
- 长按，让浮水中的彩墨逐渐聚成所选图案
- 松手，墨粒凝为会呼吸的国风心印，静置时自行浮动
- 成形后轻触拨动，墨仍会散开、再缓缓归位

## 🛠️ 技术栈

- Three.js
- WebGL ShaderMaterial
- Canvas 蒙版采样

## 🌱 创作背景

水墨画里藏着一个常识：落墨之前，纸上什么都没有；笔下去，相才显出来。「墨中有相」把这件事交还给观众的手指——你按住的那一刻，就是那一笔。太极、鹤影、山水、牡丹，都从同一片浮水里长出来，像是同一种墨在不同念想下凝成的样子。
