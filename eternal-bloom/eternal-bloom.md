# Eternal Bloom · 永生花工坊

> **Tech Keywords:** p5.js, canvas 2d, web audio api, touch interaction

<!-- WORK_META
  slug: eternal-bloom
  render_engine: Canvas 2D p5.js 1.9.0
  particle_count: N/A
  particle_type: N/A
  shader_type: N/A
  interaction: touch / click
  audio: Web Audio API synthesis
  effects: matrix 3D projection, painter's algorithm depth sort, parametric petal ruffle/reflex geometry, pointer-flinch spring physics, bezier glass dome + clip + screen-blend highlight, Web Audio bell synthesis, drifting spores & fireflies
  use_cases: p5.js, canvas 2d, web audio api, touch interaction
  standalone: yes
  dependencies: 1 CDN (p5)
  file_size: ~57 KB, 1449 lines
  compatibility: Chrome/Edge/Firefox, Safari iOS 15+
  WORK_META_END
-->

![Parametric 3D flowers sealed under glass cloches on a shelf — p5.js Canvas 2D eternal-bloom preview](eternal-bloom_1.gif)

> 调好一朵花的每个参数，封进玻璃钟罩，它就替你一直开着。

一座开在浏览器里的永生花工坊。四个品种——玫瑰、牡丹、彼岸花、牵牛花——都由同一个参数化 3D 花卉引擎实时生成：花冠尺寸、瓣宽、褶皱、翻卷、开放度逐参数可调，每个品种还有自己的一套配色谱系（卡罗拉红、赵粉、魏紫、曼珠沙华、朝颜蓝……）。

花是"活"的：整株上下浮沉、花瓣微微脉冲，指尖靠近时花瓣会沿着弹簧物理轻轻躲开。调满意之后按下「封存为永生花」，花朵会缩成一颗光球、伴着一声合成铃声落进木质花架上的玻璃钟罩，铭牌刻下品种与封存日期。

钟罩不是终点。点击花架上任何一朵永生花，就能把它的完整配方取回工坊，继续改。

---

## ✨ 预览

直接用浏览器打开 `eternal-bloom.html` 即可运行——单文件 H5，仅依赖 1 个 CDN（p5）。

## 📂 文件说明

| 文件 | 说明 |
| --- | --- |
| `eternal-bloom.html` | 完整可运行的 H5 互动作品，约 57KB |
| `eternal-bloom_1.gif` | 预览图 1 |
| `eternal-bloom.md` | 本说明文件 |

## 🖱️ 交互

- 滑杆调参：花冠尺寸 / 花瓣宽度 / 褶皱度 / 翻卷度 / 开放姿态 / 躲避灵敏
- 下拉切换品种（玫瑰 / 牡丹 / 彼岸花 / 牵牛花）与专属配色
- 🎲 随机品种：一键换一组参数组合
- 指尖/鼠标靠近花瓣，花瓣会实时躲开（flinch 物理）
- 🏺 封存为永生花：光球动画 + 铃声，收入玻璃钟罩并刻上日期铭牌
- 点击花架上的钟罩，取回那朵花的配方继续编辑

## 🛠️ 技术栈

- p5.js
- Canvas 2D
- Web Audio API

## 🌱 创作背景

这件作品是三条旧管线的汇合：3D 矩阵投影 + 画家算法的引擎骨架、分层错位带顶端褶皱的有机花瓣逻辑，以及来自 tidal-moon-moss 的玻璃渲染管线（bezier 穹顶、clip 裁切、screen 混合高光、亚克力底座）。前两者让花"长出来"，第三者让花"留下来"——于是有了工坊与收藏架这对结构：一边不断生成，一边替你保存。

渲染上坚持固定正面视角，不做相机旋转；呼吸感完全交给整花浮沉、花瓣脉冲与开放度微振荡。永生花的意思大概就在这里：它被参数完整地描述着，所以随时可以被取回、被重新打开。
