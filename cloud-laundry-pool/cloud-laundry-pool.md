# Cloud Laundry Pool · 晾云池

> **Tech Keywords:** p5.js, canvas 2d, touch interaction

<!-- WORK_META
  slug: cloud-laundry-pool
  render_engine: Canvas 2D p5.js 1.9.0
  particle_count: N/A
  particle_type: N/A
  shader_type: N/A
  interaction: touch / click
  audio: N/A
  effects: pixelated rendering, cloud compression, delayed rain, water ripples, splash particles
  use_cases: p5.js, canvas 2d, touch interaction
  standalone: yes
  dependencies: 1 CDN (p5)
  file_size: ~31 KB, 568 lines
  compatibility: Chrome/Edge/Firefox, Safari iOS 15+
  WORK_META_END
-->

![Cloud Laundry Pool - preview 1](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/cloud-laundry-pool/v-efe1196a4ed9/cloud-laundry-pool_1.gif)

> 把潮湿和心事挂起来，让它们慢慢落成一池雨。

《晾云池》把两朵潮湿的云挂在一方安静的庭院里。触摸云朵时，指尖会成为它的临时低点，云体向触点下陷，蓝色的雨水沿着新的重量方向落进石池。

作品用 p5.js 与 Canvas 2D 绘制像素化的云、晾衣绳、雨滴和水面反馈。固定种子让云朵纹理保持稳定，触摸状态机、有限雨滴池、延迟落雨与涟漪共同构成一次“触碰—排水—回静”的小型循环。

---

## ✨ 预览

直接用浏览器打开 `cloud-laundry-pool.html` 即可运行——单文件 H5，仅依赖 1 个 CDN（p5）。

## 📂 文件说明

| 文件 | 说明 |
| --- | --- |
| `cloud-laundry-pool.html` | 完整可运行的 H5 互动作品，约 31KB |
| [`cloud-laundry-pool_1.gif`](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/cloud-laundry-pool/v-efe1196a4ed9/cloud-laundry-pool_1.gif) | 预览图 1（外部资源仓库） |
| `cloud-laundry-pool.md` | 本说明文件 |

## 🖱️ 交互

- 触摸或点击任意一朵云，持续按住会让它逐渐下陷并开始落雨。
- 在云朵上拖动，触点会改变临时低点，雨水随之偏移。
- 松手后云朵缓慢回弹；延迟的一滴雨落入水池，随后画面回到安静状态。

## 🛠️ 技术栈

- p5.js
- Canvas 2D

## 🌱 创作背景

“晾云池”来自一个轻微的错觉：如果云也会吸水，也许它们需要被挂起来晾一会儿。这里没有要被解决的任务，只有把手指放在云上、让湿重暂时流走，再看水面替你收住余波的时间。
