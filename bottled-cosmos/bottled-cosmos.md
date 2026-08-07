# Bottled Cosmos · 瓶装宇宙

> **Tech Keywords:** p5.js, canvas 2d, three.js, webgl, touch interaction

<!-- WORK_META
  slug: bottled-cosmos
  render_engine: Canvas 2D p5.js
  particle_count: N/A
  particle_type: N/A
  shader_type: N/A
  interaction: touch / click
  audio: N/A
  effects: 玻璃三 pass（底厚/菲涅尔/高光带）, 离屏 Three.js WebGL 星系层, TILT 倾斜渲染, 瓶塞开合+星辰逃逸, 光谱分类（B/G/M）恒星生命周期, 星尘粒子, 星卡 Canvas 合成
  use_cases: p5.js, canvas 2d, three.js, webgl, touch interaction
  standalone: yes
  dependencies: 2 CDN (p5, three)
  file_size: ~52 KB, 1382 lines
  compatibility: Chrome/Edge/Firefox, Safari iOS 15+
  WORK_META_END
-->

![Bottled Cosmos - preview 1](bottled-cosmos_1.gif)

> 把整个宇宙装进一只玻璃瓶——每颗恒星的一生，只有三十秒。

一只旧药剂瓶里，装着一个正在运转的宇宙。转动瓶身，银河盘在玻璃壁内缓缓倾斜旋转；点开瓶塞，星辰从瓶口逃逸，落进屏幕深处的夜空。

星系层由离屏 Three.js WebGL 渲染后逐帧合成进 p5.js 的玻璃剪裁区；恒星按光谱分为 B 型蓝白星、G 型黄矮星与 M 型红矮星，各有不同的光晕与寿命。按住瓶身搅动星尘、摩擦点燃新的恒星；长按一颗星，为它命名，它会带着这个名字继续燃烧，并生成一张可以保存的星卡。

创作想表达的是「尺度」：把一个比人更大的东西，装进一个比人更小的容器。玻璃瓶既是一层物理边界，也是一层心理边界——当瓶塞打开，原本属于瓶内的光，忽然拥有了整片夜空。

---

## ✨ 预览

直接用浏览器打开 `bottled-cosmos.html` 即可运行——单文件 H5，仅依赖 2 个 CDN（p5, three）。

## 📂 文件说明

| 文件 | 说明 |
| --- | --- |
| `bottled-cosmos.html` | 完整可运行的 H5 互动作品，约 52KB |
| `bottled-cosmos_1.gif` | 预览图 1 |
| `bottled-cosmos.md` | 本说明文件 |

## 🖱️ 交互

- 点按瓶塞开合瓶口——打开时星辰从瓶内逃逸，落进背景夜空
- 按住瓶身搅动星尘，摩擦点燃新的恒星
- 长按一颗恒星，为它命名，生成可保存的星卡
- 恒星按光谱呈现不同的颜色、光晕与寿命（每颗 30 秒）

## 🛠️ 技术栈

- p5.js
- Three.js
- Canvas 2D

## 🌱 创作背景

「瓶装宇宙」的起点是一次反问：如果宇宙可以被握在手里，会是什么感觉？作品延续了 drift-bottle 玻璃药剂瓶的曲线与渲染管线，把 falling-verse 的 3D 星系层压缩进一只瓶中——玻璃的边界既困住了光，也让光显得更亮。瓶塞的开合是作品唯一的叙事开关：合上是安静的收藏，打开是放逐，也是自由。
