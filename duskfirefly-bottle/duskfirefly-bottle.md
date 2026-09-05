# Hand the Unquenched to the Night · 把未熄的交给夜

> **Tech Keywords:** p5.js, canvas 2d, web audio api, touch interaction

<!-- WORK_META
  slug: duskfirefly-bottle
  render_engine: Canvas 2D p5.js 1.9.0
  particle_count: N/A
  particle_type: N/A
  shader_type: N/A
  interaction: touch / click
  audio: Web Audio API synthesis
  effects: deterministic seeded firefly swarm, three-pass pixel-glass refraction, additive-glow firefly rendering, procedural Web Audio tide/cork pop/wind chimes
  use_cases: p5.js, canvas 2d, web audio api, touch interaction
  standalone: yes
  dependencies: 1 CDN (p5)
  file_size: ~36 KB, 124 lines
  compatibility: Chrome/Edge/Firefox, Safari iOS 15+
  WORK_META_END
-->

![Hand the Unquenched to the Night - preview 1](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/duskfirefly-bottle/v-3b97fc312354/duskfirefly-bottle_1.gif)

> 海退回时，把一只漂流瓶留在湿沙上——瓶里还有没熄的萤火，交给夜来认领。

潮水退去，把一只细长的玻璃漂流瓶留在湿沙上，瓶里装着 96 只仍亮着的萤火虫。轻触瓶塞（键盘 Enter / 空格亦可），拔塞的瞬间，光点一只接一只沿瓶口涌出，散进靛紫的暮色，直到夜空把它们全部认领。

整支画面由确定性 seeded 虫群驱动：深靛紫压住"静"，地平线一道珊瑚色做转折，暖金、黄绿、浅青绿三种光只留给萤火。玻璃瓶以三分层折射叠出半透明质感，全场景无任何图片素材，海潮、瓶塞摩擦与稀疏的风铃都由 Web Audio 程序化合成。

作品名本身就是一次交付动作——把还没熄掉的东西，放心地交给夜。释放之后，你仍可以轻点夜空，给仍在飞舞的萤火一点点推力。

---

## ✨ 预览

直接用浏览器打开 `duskfirefly-bottle.html` 即可运行——单文件 H5，仅依赖 1 个 CDN（p5）。

## 📂 文件说明

| 文件 | 说明 |
| --- | --- |
| `duskfirefly-bottle.html` | 完整可运行的 H5 互动作品，约 36KB |
| [`duskfirefly-bottle_1.gif`](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/duskfirefly-bottle/v-3b97fc312354/duskfirefly-bottle_1.gif) | 预览图 1（外部资源仓库） |
| `duskfirefly-bottle.md` | 本说明文件 |

## 🖱️ 交互

- 轻触瓶塞开启漂流瓶；键盘 Enter / 空格也可释放
- 萤火散开后，轻点夜空给最近的萤火一点推力（能量回升并轻轻散开）
- URL 参数：`?seed=` 换一版虫群分布、`?fast=` 调速、`?demo=idle|release|open` 直达各阶段

## 🛠️ 技术栈

- p5.js
- Canvas 2D
- Web Audio API

## 🌱 创作背景

作为 pixel-bloom 的一支独立 motion-study，先把"瓶里的光是主角"这件事做对：湿沙、海面与云都被按进低饱和低对比，暖色几乎只出现在萤火本身，星与远屿只作点缀。暮色六段色场经作者授权，自原稿迁入后在本作中继续独立重构，云层、水面、瓶体与虫群的运动各自迭代。

整支动画由确定性 seeded 随机驱动：同一 `?seed` 必然得到同一版释放轨迹，便于逐帧回放与 QA 核验。音频以一段程序化低噪流做海潮底，拔塞时的摩擦、软性的 pop 与四枚稀疏风铃错落排布——声音只在需要你注意的瞬间出现。
