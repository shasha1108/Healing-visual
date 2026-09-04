# Streetlamp Slow Rain · 路灯周围，雨会慢一点

> **Tech Keywords:** p5.js, canvas 2d, web audio api, touch interaction

<!-- WORK_META
  slug: streetlamp-slow-rain
  render_engine: Canvas 2D p5.js 1.9.0
  particle_count: N/A
  particle_type: N/A
  shader_type: N/A
  interaction: touch / click
  audio: Web Audio API synthesis
  effects: seeded deterministic pixel scene, layered rain (far/mid/near), time-debt slowdown under lamp, ripples & splashes, procedural Web Audio rain + lamp hum, butterfly touch-avoid
  use_cases: p5.js, canvas 2d, web audio api, touch interaction
  standalone: yes
  dependencies: 1 CDN (p5)
  file_size: ~57 KB, 1144 lines
  compatibility: Chrome/Edge/Firefox, Safari iOS 15+
  WORK_META_END
-->

![Streetlamp Slow Rain - preview 1](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/streetlamp-slow-rain/v-b29665ccaa4b/streetlamp-slow-rain_1.gif)

> 末班车走远后，最后一盏旧路灯还亮着。按住光，让灯下的雨慢一点。

《路灯周围，雨会慢一点》是一座像素风的末班车站台：雨还在下，那盏旧路灯始终亮着。当你的指尖轻轻按住灯光，灯下的雨仿佛暂时失去了时间，落得又慢又轻——可一旦松手，被延迟的雨滴会重新追上这个世界，把欠下的那场雨一口气还给夜空。

作品的交互核心是把「停留」变成一种有代价的温柔：慢下来不是把世界暂停，而是把时间暂时借给此刻。轻碰那只躲雨的小蝴蝶，它会悄悄让开；程序化合成的雨声与灯丝嗡鸣在后台缓缓铺开，当浏览器的自动播放策略把声音拦下时，真正的一次触摸会替你把声音叫醒。

技术上，作品用 p5.js 以固定随机种子在 Canvas 2D 上逐帧绘制确定性场景，720×960 纵向构图；雨按远、中、近三层错落分布，配合落点飞溅与地面水洼的同心波纹，拼出一个完整的雨夜。单文件运行，仅依赖一个 CDN。

---

## ✨ 预览

直接用浏览器打开 `streetlamp-slow-rain.html` 即可运行——单文件 H5，仅依赖 1 个 CDN（p5）。

## 📂 文件说明

| 文件 | 说明 |
| --- | --- |
| `streetlamp-slow-rain.html` | 完整可运行的 H5 互动作品，约 57KB |
| [`streetlamp-slow-rain_1.gif`](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/streetlamp-slow-rain/v-b29665ccaa4b/streetlamp-slow-rain_1.gif) | 预览图 1（外部资源仓库） |
| `streetlamp-slow-rain.md` | 本说明文件 |

## 🖱️ 交互

- 轻碰灯光：灯下的雨暂时慢下来，时间被「借」给这一刻
- 按住不松手：可以停留久一点，慢下来的雨被收进时间债务
- 松手：被延迟的雨重新追上世界，把欠下的雨还给夜空
- 轻碰蝴蝶：它会轻轻躲开，不打扰这站台的安静

## 🛠️ 技术栈

- p5.js
- Canvas 2D
- Web Audio API

## 🌱 创作背景

「路灯周围，雨会慢一点」来自一个具体而微的错觉——灯光下的雨滴，在视觉上总是显得比别处更慢。作品把这个错觉轻轻留了下来：末班车开走后的空站台、一盏还亮着的旧路灯、一场迟迟不肯停的雨。它没有剧情，也没有旁白，只留下「你的手可以让灯下的雨慢一点」这一个动作——像在拥挤的雨夜里，为某个人偷偷留出一小段不被打扰的时间。慢下来，是为了让告别再多待一会儿。
