# SamWaf Tools — 开发者工具集

面向开发者的**单页静态工具站**：打开浏览器即可使用，**所有逻辑在本地运行**，不依赖后端、不把业务数据上传到互联网。与 [SamWaf](https://github.com/samwafgo/SamWaf) 同属 SamWaf 生态，适合内网、离线或注重隐私的场景。

## 在线体验

<p align="center">
  <a href="https://samwaf.com/"><img src="https://img.shields.io/badge/在线体验-samwaf.com-2563eb?style=for-the-badge&logo=googlechrome&logoColor=white" alt="打开 samwaf.com 在线使用 SamWaf Tools"></a>
</p>

<p align="center"><strong><a href="https://samwaf.com/">https://samwaf.com/</a></strong></p>

<p align="center"><sub>无需下载仓库，浏览器打开即用；逻辑在本地浏览器执行，确保数据安全。</sub></p>

---

## 项目用途

- 在仓库首页或文档里一眼说明「这是干什么的」：本地 Web 工具合集。
- 直接双击或用任意静态服务器打开 `index.html` 即可使用（二维码功能需与 `js/` 同目录，见下文）。

## 内置工具一览

| 分类 | 工具 | 说明 |
|------|------|------|
| 图片 | 图片工具 | 压缩、合并、旋转，浏览器 Canvas 处理 |
| 编码 | JSON 格式化 | 格式化、压缩、校验、语法高亮、树形视图 |
| 编码 | Base64 | 编解码，支持中文（Unicode） |
| 编码 | URL | `encodeURIComponent` / 解码 |
| 编码 | 时间戳 | Unix 秒/毫秒与本地时间互转 |
| 安全 | Hash | MD5、SHA-1、SHA-256、SHA-512（Web Crypto + 内置 MD5） |
| 安全 | 密码生成器 | 随机密码、强度提示、批量生成 |
| 对比 | 代码对比 | 左右两侧逐行差异，LCS 比对、行内字符级高亮、可忽略空白 |
| 生成 | 二维码 | 本地生成，可调尺寸/颜色/纠错级别，导出 PNG |

## 本地运行方式

1. 克隆或下载本仓库到本地。
2. 用浏览器直接打开根目录下的 `index.html`，或通过任意静态文件服务托管该目录。

> **注意：** 若使用 `file://` 打开，个别浏览器对剪贴板、部分 API 可能有限制；如遇问题，可用 `npx serve .` 等方式以 `http://localhost` 访问。

## 第三方脚本：`js/qrcode.min.js`

二维码功能使用 **qrcodejs**（David Shim 维护的浏览器端二维码生成库），为保持**完全离线可用**，已将压缩版放到仓库的 `js/` 目录，由 `index.html` 通过相对路径引用：

```html
<script src="js/qrcode.min.js"></script>
```

### 下载来源（可核对 / 重新下载）

| 项 | 说明 |
|----|------|
| **库名** | qrcodejs |
| **版本** | 1.0.0 |
| **官方仓库** | [davidshimjs/qrcodejs](https://github.com/davidshimjs/qrcodejs) |
| **本仓库使用的 CDN 直链** | `https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js` |

重新下载示例（PowerShell）：

```powershell
Invoke-WebRequest -Uri "https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js" -OutFile "js/qrcode.min.js"
```

其余功能（图片、JSON、Base64、URL、时间戳、Hash、密码等）均为页面内联脚本实现，**无额外 npm 依赖**。

## 目录结构（简要）

```
SamWafToolIndex/
├── index.html      # 单页应用入口
├── js/
│   └── qrcode.min.js   # 二维码库（来源见上文）
└── README.md
```

## 许可证与关联

- 页面中展示的 SamWaf 相关链接与版权信息以 `index.html` 内为准。
- `qrcode.min.js` 遵循其上游项目许可证（见 [qrcodejs 仓库](https://github.com/davidshimjs/qrcodejs)）。

---

**一句话：** 这是 SamWaf 配套的**本地开发者工具箱**网页，方便在安全、离线环境下完成常见编解码与图片处理；仓库里唯一外置脚本为 `js/qrcode.min.js`，来源为 **cdnjs 上的 qrcodejs 1.0.0**。
