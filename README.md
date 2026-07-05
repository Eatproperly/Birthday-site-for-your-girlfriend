# Birthday Web Template 🎂

一个可复用的生日祝福网页模板。

包含：

- 🎬 照片电影（自动播放幻灯片）
- 💌 打字情书（逐字打字机效果）
- 🎂 吹蜡烛互动（点亮 / 许愿 / 吹灭）
- 🎉 撒花动画
- 🎵 多段背景音乐（自动交叉淡入淡出）
- ✨ 隐藏彩蛋
- 📖 时间轴故事线
- 💕 对话框 + 头像合并动画

**无需修改业务代码，只需替换配置即可生成自己的生日网页。**

---

## 🚀 Quick Start

```
1. 下载项目（或 clone 仓库）
   ↓
2. 打开 example.html
   ↓
3. 找到 CONFIG 对象，修改里面的配置
   ↓
4. 替换图片和音乐文件
   ↓
5. 部署到 Vercel / GitHub Pages
   ↓
完成 ✅
```

> 如果你是完全不会编程的小白，也没关系——跟着下面的步骤一步步来就行。

---

## 📂 文件结构

```
project/
│
├── example.html      ← 模板文件（复制一份后修改 CONFIG 即可）
├── LICENSE           ← 开源协议
└── README.md         ← 你正在看的这个文件
```

> 整个项目只有一个 HTML 文件，所有 CSS 和 JS 都内联在里面，无需任何构建工具。

---

## 📖 使用方法

### 第一步：复制模板

把 `example.html` 复制一份，重命名为你想要的文件名，比如 `birthday.html`。

### 第二步：修改配置

打开文件，搜索 `const CONFIG = {`，你会看到一个配置对象。

**所有需要修改的内容都在这个 CONFIG 里面，后面的代码无需改动。**

### 第三步：替换图片和音乐

将你的图片、音乐文件放到合适的路径，然后更新 CONFIG 中的路径引用。

### 第四步：预览

用浏览器打开 HTML 文件预览效果（建议通过本地服务器访问，见下方「部署」章节）。

### 第五步：部署上线

推荐使用 Vercel，详见「部署」章节。

---

## 📸 图片要求

| 资源 | 建议尺寸 | 比例 | 格式 | 说明 |
|------|----------|------|------|------|
| 封面背景 (`cover.splash`) | 1920×1080+ | 16:9 | JPG | 首页全屏背景图 |
| 封面头像 (`cover.photo`) | 800×800+ | 1:1 | JPG | 首页圆形头像，会被裁切 |
| 时间轴配图 (`timeline[].img`) | 1000px+ | 4:3 | JPG | 时间线中的配图（可选） |
| 照片电影 (`film[].img`) | 1080×1920 | 竖图 9:16 | JPG | 自动播放的幻灯片 |
| 对话框头像 (`dialog.leftPhoto/rightPhoto`) | 400×400+ | 1:1 | JPG | "我们"合并动画中的头像 |
| 蛋糕四周照片 (`cake.photos`) | 600×600+ | 1:1 | JPG | 共 4 张，环绕蛋糕 |
| 蛋糕图片 (`cake.image`) | 600px+ | 不限 | PNG | 透明背景最佳 |

---

## 🎵 音乐要求

| 资源 | 格式 | 建议码率 | 说明 |
|------|------|----------|------|
| 许愿前背景音乐 (`audio.bgBeforeWish`) | MP3 | 128kbps+ | 浏览过程中的背景音乐 |
| 生日歌 (`audio.birthdaySong`) | MP3 | 128kbps+ | 许愿时播放（默认截取 84s~126s） |
| 许愿后背景音乐 (`audio.bgAfterWish`) | MP3 | 128kbps+ | 吹蜡烛后播放，循环 |

> **生日歌裁剪**：默认从第 84 秒播放到第 126 秒。如需修改，找到代码中的 `BIRTHDAY_SONG_START` 和 `BIRTHDAY_SONG_END`，改数字即可（单位：秒）。

---

## ⚙️ 配置说明

### ① 基本信息 (`profile`)

| 配置项 | 说明 | 示例 |
|--------|------|------|
| `recipientName` | 生日主角名字（收祝福的人） | `"小美"` |
| `senderName` | 送祝福的人 | `"小明"` |
| `birthdayDate` | 生日日期（显示在页面上） | `"2025 年 7 月 5 日"` |
| `pageTitle` | 浏览器标签页标题 | `"小美生日快乐"` |

### ② 音乐 (`audio`)

| 配置项 | 说明 |
|--------|------|
| `bgBeforeWish` | 许愿前背景音乐路径 |
| `birthdaySong` | 生日歌路径 |
| `bgAfterWish` | 许愿后背景音乐路径 |

### ③ 封面 (`cover`)

| 配置项 | 说明 |
|--------|------|
| `splash` | 首页全屏背景图路径 |
| `photo` | 首页圆形头像路径 |

### ④ 开场文案 (`intro`)

| 配置项 | 说明 |
|--------|------|
| `splashSub` | 封面副标题（名字下方） |
| `splashHint` | 封面底部提示文字 |
| `headline` | 第一页大标题 |
| `subText` | 第一页副标题 |
| `scrollHint` | 滚动提示文字 |

### ⑤ 时间轴 (`timeline`)

| 配置项 | 说明 |
|--------|------|
| `timelineTitle` | 时间轴标题 |
| `timeline[].date` | 日期 |
| `timeline[].title` | 标题 |
| `timeline[].desc` | 描述 |
| `timeline[].type` | `"text"` 纯文字 / `"image"` 带配图 |
| `timeline[].img` | 配图路径（type 为 "image" 时填写） |

> 可以增删条目，想写多少条就写多少条。

### ⑥ 照片电影 (`film`)

| 配置项 | 说明 |
|--------|------|
| `filmTitle` | 照片电影标题 |
| `filmInterval` | 每张幻灯片停留时间（毫秒），默认 5000 |
| `film[].img` | 图片路径 |
| `film[].caption` | 图片描述文字 |

### ⑦ 对话框 (`dialog`)

| 配置项 | 说明 |
|--------|------|
| `leftPhoto` | 左侧头像路径 |
| `rightPhoto` | 右侧头像路径 |
| `popups[].text` | 弹窗文字 |
| `popups[].sub` | 弹窗副标题（可选） |
| `popups[].duration` | 弹窗显示时长（毫秒） |
| `weTextEn` | 合并后英文文字 |
| `weTextCn` | 合并后中文文字 |

### ⑧ 信件 (`letter`)

| 配置项 | 说明 |
|--------|------|
| `letterTitle` | 信件区域标题 |
| `letter.salutation` | 称呼（留空自动用主角名字） |
| `letter.body` | 信件正文 |
| `letter.signature` | 签名（留空自动用送祝福者名字 + 日期） |

### ⑨ 蛋糕 (`cake`)

| 配置项 | 说明 |
|--------|------|
| `image` | 蛋糕主体图片路径（PNG 透明背景最佳） |
| `photos` | 蛋糕四周 4 张照片（数组：左上、右上、左下、右下） |
| `title` | 蛋糕区标题 |
| `wishText` | 吹灭蜡烛后显示的祝福文字（支持 HTML） |
| `hintLight` / `btnLight` | 初始状态提示 / 按钮文字 |
| `hintWish` / `btnWish` | 点亮后提示 / 按钮文字 |
| `hintBlow` / `btnBlow` | 许愿中提示 / 按钮文字 |
| `hintRelight` / `btnRelight` | 吹灭后提示 / 按钮文字 |

### ⑩ 彩蛋 (`hiddenEgg`)

| 配置项 | 说明 |
|--------|------|
| `icon` | 彩蛋图标（默认 ✨） |
| `text1` | 点击后第一段文字 |
| `text2` | 点击后第二段文字 |

---

## 🖼️ 如何替换图片

### 如果你的图片文件就在同目录下：

直接在 CONFIG 中填写文件名即可：

```js
cover: {
  splash: "background.jpg",    // 同目录下的 background.jpg
  photo: "avatar.jpg",         // 同目录下的 avatar.jpg
}
```

### 如果使用网络图片（URL）：

直接粘贴图片链接：

```js
cover: {
  splash: "https://example.com/bg.jpg",
  photo: "https://example.com/avatar.jpg",
}
```

### 替换照片电影：

```js
film: [
  { img: "photo1.jpg", caption: "第一次见面的那天" },
  { img: "photo2.jpg", caption: "一起去看的演唱会" },
  { img: "photo3.jpg", caption: "生日惊喜" },
]
```

> 保持路径一致即可，图片路径和 `img` 字段的值对应。

---

## 🎶 如何替换音乐

```js
audio: {
  bgBeforeWish: "music1.mp3",     // 同目录下的 music1.mp3
  birthdaySong: "birthday.mp3",   // 同目录下的 birthday.mp3
  bgAfterWish: "music2.mp3",      // 同目录下的 music2.mp3
}
```

也可以直接使用网络链接：

```js
audio: {
  bgBeforeWish: "https://example.com/music1.mp3",
  birthdaySong: "https://example.com/birthday.mp3",
  bgAfterWish: "https://example.com/music2.mp3",
}
```

---

## 🚀 部署

### 方式一：Vercel（推荐）

1. 将项目上传到 GitHub
2. 打开 [vercel.com](https://vercel.com)
3. 点击 **Import Project**，选择你的仓库
4. 点击 **Deploy**，等待部署完成
5. 获得一个 `xxx.vercel.app` 的链接，发给 TA 即可

### 方式二：GitHub Pages

1. 将项目上传到 GitHub 仓库
2. 进入仓库 **Settings → Pages**
3. Source 选择 **main branch**
4. 保存，等待部署完成
5. 访问 `https://你的用户名.github.io/仓库名/birthday.html`

### 方式三：Netlify

1. 打开 [netlify.com](https://netlify.com)
2. 把项目文件夹直接拖到页面上
3. 等待部署完成

> ⚠️ 请不要直接用浏览器双击 HTML 文件打开——由于浏览器安全策略，音乐和部分功能可能无法正常工作。请通过部署后的链接访问。

---

## ❓ FAQ

**Q：为什么音乐不能播放？**

A：浏览器需要用户先与页面交互（点击、触摸）后才能播放音乐。这是浏览器的安全策略，不是 bug。用户点击「✦ 点击进入 ✦」后音乐就会自动播放。

**Q：图片为什么变形 / 模糊？**

A：请遵循上方的图片要求。封面头像需要 1:1 正方形，照片电影建议竖图 9:16，时间轴配图建议 4:3。图片尺寸不要太小，建议 800px 以上。

**Q：怎么增加 / 减少时间轴的条目？**

A：在 CONFIG 的 `timeline` 数组中增删对象即可。每个对象是一个条目，格式和其他条目保持一致就行。

**Q：怎么增加 / 减少照片电影的张数？**

A：在 CONFIG 的 `film` 数组中增删对象即可。

**Q：蛋糕的蜡烛位置怎么调？**

A：蜡烛位置在代码中由 `FLAME_POS` 控制（相对图片的百分比位置）。如果你换了不同的蛋糕图片，可能需要微调。搜索 `FLAME_POS` 修改两个坐标值即可。

**Q：为什么直接双击 HTML 打开效果不对？**

A：浏览器的本地文件安全策略会限制音乐播放和部分功能。建议部署后通过链接访问，或者使用 VS Code 的 Live Server 插件进行本地预览。

**Q：手机端效果怎么样？**

A：完美适配移动端，已针对 iPhone 安全区域做了适配（包括刘海屏、底部横条等）。

---

## 📝 更新日志

| 版本 | 内容 |
|------|------|
| v1.0 | 完成生日网页基础版 |
| v1.1 | 新增照片电影、对话框合并动画 |
| v1.2 | 新增蛋糕互动、隐藏彩蛋 |
| v1.3 | 优化移动端适配、资源预加载 |

---

## 📄 License

[MIT](./LICENSE) — 自由使用，欢迎 Star ⭐
