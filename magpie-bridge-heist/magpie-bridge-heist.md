# Magpie Bridge Heist · 鹊桥搞事现场

> **Tech Keywords:** three.js, webgl, orthographic camera, web audio api, branching interaction

<!-- WORK_META
  slug: magpie-bridge-heist
  render_engine: WebGL Three.js 0.185.1 (ESM import map)
  particle_count: 26 水花粒子池 + 8 涟漪池 + 48 远星
  particle_type: box splash particles / ripple rings / sparse star points
  shader_type: N/A
  interaction: touch / click / key 1·2·3（三选一分支）/ 3:4 PNG 本地保存
  audio: Web Audio API synthesis
  effects: 冷开场倒带、行动代号、角色反应气泡、桥砖预编排塌落、16 只多部件喜鹊组成单线鸟桥后从中心向两端飞散、三人依次落水、隐藏第四结局、祥云救援、七夕事故报告、合成音效
  use_cases: three.js, webgl, branching narrative, qixi festival, voxel diorama
  standalone: yes
  dependencies: 1 CDN (three.js, jsdelivr import map)
  file_size: ~59 KB, 1111 lines
  compatibility: Chrome/Edge/Firefox, Safari iOS 15+（需网络加载 three.js）
  WORK_META_END
-->

> 七夕夜路过鹊桥，撞上牛郎织女约会——其实，我当时有三个选择。

《Magpie Bridge Heist》是一出 8 秒一局的方块小人闹剧：冷开场里主角已经举起了锤子，画面倒带，把选择权交回给你——装狗混进去、一锤子解决、或者让桥自己飞。三种搞法，三种结局，每次行动先获得一本正经的代号，结尾再由「天庭事故管理局」出具可截图、可保存的 3:4 七夕事故报告。

无物理引擎：27 块桥砖的塌落、16 只喜鹊的出现与起飞全部由预编排时间线驱动。喜鹊由身体、头、金色鸟喙、白腹、双翼白斑和长尾等 9 组 InstancedMesh 组成；桥砖退场时喜鹊沿一条清晰拱线接力出现，短暂的金色拱线只在成桥确认时给出引导。鸟桥停留后从中心向两端疏朗飞散，三个人悬空愣半拍后依次落水，完成「我说的是桥会飞，没说你们会飞」的收尾。

三个普通结局全部集齐后，第三张报告会出现「查看下一年鹊桥」。进入后，天庭以“丰富鹊桥维护经验”为由把主角横着放进下一年的桥位；牛郎织女继续在他形成的桥上约会，喜鹊则下班飞走。第四张报告的核心句是「最终，我成了基础设施。」；事故图鉴依然记为 3 / 3，并标注隐藏结局已解锁。

视觉采用「Peachy Qixi」色板：清亮靛蓝夜空、紫罗兰云霞、桃红桥面与金色月光。河面由连续渐变纹理、18 道动态波纹和月光倒影组成，并向页面底部延伸，消除原先横向分割带。背景只保留少量远星，并用小模块组成带卷尾与金色底边的体素祥云，去掉悬浮纸屑与装饰爱心，让人物、桥和鸟群成为唯一视觉重点。牛郎织女保留方块体素结构，但增加交领、腰封、袍摆、宽袖、束发冠、高髻、金簪、步摇和飘带，使人物在手机尺寸下仍能读出古装轮廓。狗分支增加变身定格、共同爱犬项圈和约四秒绕场；拆桥分支的救援云增加公务警示灯；鸟桥分支在坠落前加入集体沉默气泡，让三个笑点都形成「动作—停顿—二次反转」。

## 🖼️ 预览

![Magpie Bridge Heist — animated branching scene](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/magpie-bridge-heist/v-dbbe54abf870/magpie-bridge-heist_1.gif)

![Choice screen with three branching options](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/magpie-bridge-heist/v-dbbe54abf870/magpie-bridge-heist_2.png)

![Magpie flock forming a single arched bridge over the river](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/magpie-bridge-heist/v-dbbe54abf870/magpie-bridge-heist_3.png)

![Disguised dog circling the couple on the bridge](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/magpie-bridge-heist/v-dbbe54abf870/magpie-bridge-heist_4.png)

![Bridge collapse with rescue clouds lifting the couple](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/magpie-bridge-heist/v-dbbe54abf870/magpie-bridge-heist_5.png)

![Hero lying horizontally as the next year's magpie bridge](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/magpie-bridge-heist/v-dbbe54abf870/magpie-bridge-heist_6.png)

![Qixi incident report card overlay](https://raw.githubusercontent.com/shasha1108/healing-visual-previews/main/magpie-bridge-heist/v-dbbe54abf870/magpie-bridge-heist_7.png)

## ✨ 本地运行与测试钩子

本地静态服务器打开 `magpie-bridge-heist.html`（three.js 走 jsdelivr ESM import map，需网络）。

测试钩子：`?nointro=1` 跳过冷开场；`?branch=dog|demolish|magpie|infrastructure` 自动播放指定分支；`?t=<秒>` 固定步进快进截图；`?shot=1` 停在收尾帧并直接显示事故报告。`infrastructure` URL 入口只供本地测试，普通用户必须集齐三个普通结局后从报告按钮进入。

本地渲染入口：`?render=1` 会禁止自动动画循环，并暴露 `window.__qixiRender.seek(branch, t, { step, shot })`。它只接受 `magpie` 或 `infrastructure`，每次调用都会重置世界、以默认 `1/60` 固定步长推进、渲染一帧后保持静止；`window.__qixiRender.render()` 可无推进地再渲染当前帧。移动端布局使用动态视口高度与安全区，重点适配 375×667、390×844、430×932 竖屏。

## 📂 文件说明

| 文件 | 说明 |
| --- | --- |
| `magpie-bridge-heist.html` | 完整可运行的 H5 互动作品，约 59KB |
| `magpie-bridge-heist.md` | 本说明文件 |
| 预览资源 | GIF/PNG 预览图存放于 healing-visual-previews 仓库，见上方作品预览 |

## 🖱️ 交互

- 冷开场（举锤 → 一块砖落水 → 倒带）后，点击三个按钮之一进入分支。
- 也可以点屏幕左/中/右三分之一，或按键盘 1 / 2 / 3。
- 每个结局会生成一张 3:4 的「七夕事故报告」，包括隐藏结局；点击「保存事故报告」即可下载 PNG 图片到本地，再点「再搞一次」回到选择。
- 三个普通结局会出现在本次打开页面的事故图鉴里；集齐 3 / 3 后，第三张普通报告会给出「查看下一年鹊桥」，解锁隐藏第四结局。刷新或重新打开页面会重新开始，图鉴分母始终是三个普通选择，并另标“隐藏结局已解锁”。
- 首次交互后启用 Web Audio 合成音效（锤击、落水、喜鹊振翅、狗爪步、倒带）。

## 🛠️ 技术栈

- Three.js 0.185.1（WebGL，OrthographicCamera，9 组 InstancedMesh 喜鹊群）
- Web Audio API
- Canvas 程序化纹理（夜空渐变）
- Playwright 逐帧取景 + FFmpeg H.264/AAC 成片（仅本地交付脚本）

## 🌱 创作背景

七夕的鹊桥向来是浪漫符号——这次让它变成一个可以被搞砸的现场。三个分支对应三种闯入「别人约会」的荒唐办法：装狗混入、暴力拆桥，以及一本正经地让桥自己飞。主视频优先推 C 分支：桥真的飞了，三个人却还留在半空，愣半拍后依次落水；笑点来自愿望被严格执行、后果却完全没被考虑。
