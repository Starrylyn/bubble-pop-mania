# 🫧 泡泡大作战 · Bubble Pop Mania

> 一款基于 HTML5 Canvas 的休闲气泡消除游戏，单局 60 秒，支持桌面端和移动端。

## 🎮 在线游玩

**公开 URL**: https://starrylyn.github.io/bubble-pop-mania/

直接在浏览器中打开即可游玩，无需安装。

## 🎯 玩法

| 泡泡类型 | 图标 | 分数 | 效果 |
|---------|------|------|------|
| 普通泡泡 | 🫧 | +10 | 基础得分 |
| 金色泡泡 | ⭐ | +50 | 高分奖励 |
| 炸弹泡泡 | 💥 | -15 | 扣分，避开！ |
| 冰冻泡泡 | ❄️ | +5 | 减速全场 3 秒 |

- **连击系统**: 连续点中 3 个以上泡泡触发连击奖励，连击数 × 5 = 额外加分
- **时间限制**: 60 秒倒计时
- **最高分**: 自动保存在浏览器本地存储中

## 🛠 技术栈

- **渲染**: HTML5 Canvas 2D API
- **音频**: Web Audio API（程序化生成音效，无外部音频文件）
- **存储**: localStorage（最高分持久化）
- **框架**: 零依赖，纯原生 JavaScript 单文件
- **部署**: GitHub Pages 静态托管

## 📁 项目结构

```
bubble-pop/
├── index.html      # 游戏主文件（含全部 HTML/CSS/JS）
├── README.md       # 本文档
└── screenshot-live.png  # 菜单截图
```

## 🚀 本地运行

```bash
cd bubble-pop
python3 -m http.server 8765
# 浏览器打开 http://localhost:8765
```

或直接用浏览器打开 `index.html`。

## 🎮 操作方式

| 平台 | 操作 |
|------|------|
| 桌面端 | 鼠标点击泡泡；ESC/P 键暂停；Enter/空格开始 |
| 移动端 | 手指触摸泡泡；触摸暂停按钮暂停 |

## 🏗 架构说明

### 状态机
```
MENU → PLAYING → PAUSED → OVER → (重新开始) → PLAYING
```

### 核心系统
1. **Bubble 系统**: 4 种类型，随机生成，上浮 + 摆动动画
2. **Particle 系统**: 爆破粒子效果，12-20 粒/次
3. **Combo 系统**: 1.2 秒窗口内连续消除累加倍率
4. **Audio 系统**: Web Audio API 程序化生成 pop/combo/gameover 音效
5. **FloatingBg 系统**: 菜单和游戏中的浮动背景气泡
6. **响应式**: 自动适配窗口大小，移动端全屏

### 设计风格
参考 **08 Resn** 风格（趣味互动）：
- 温暖的珊瑚色调（#FF8C69 / #E8784A）
- 奶油色背景（#FDF6F0）
- 插画式角色（气泡小人）
- 情感化 UI（表情、连击特效）

## ⚠️ 已知限制

1. **无云端排行榜**: 分数仅保存在本地 localStorage，换设备/浏览器不同步
2. **无音效开关**: 音效默认开启，暂无静音按钮
3. **无难度选择**: 60 秒固定时长，难度随时间递增但不可调
4. **emoji 渲染差异**: 不同平台 emoji 样式可能略有不同
5. **无离线缓存**: 需要网络连接才能加载（GitHub Pages 托管）

## 🔄 回滚方案

```bash
# 查看历史版本
git log --oneline

# 回滚到上一版本
git revert HEAD
git push origin main

# GitHub Pages 会自动重新部署
```

## 🔮 后续扩展建议

- [ ] 云端排行榜（需后端服务）
- [ ] 多种游戏模式（无尽模式、挑战模式）
- [ ] 道具系统（时间加成、分数翻倍）
- [ ] 成就系统
- [ ] PWA 离线支持
- [ ] 多语言切换

## 📜 许可证

MIT License

## 🔗 链接

- **源代码**: https://github.com/Starrylyn/bubble-pop-mania
- **在线游玩**: https://starrylyn.github.io/bubble-pop-mania/
