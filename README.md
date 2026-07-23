# MediaSlim

**图片更小，隐私留在你的 Mac。**

MediaSlim 是一款 macOS 本地图片压缩工具，在兼顾画质的同时减小 PNG 与 JPEG 文件体积。无需上传，拖入图片或文件夹即可开始。

[下载最新版本](https://github.com/jojoTechWorkshop/MediaCompressRelease/releases/latest) · [查看更新日志](CHANGELOG.md)

## 主要功能

- 支持 PNG、JPG 与 JPEG，可一次添加多张图片。
- 支持拖入整个文件夹，并自动查找其中可压缩的图片。
- **所有处理均在本机完成，图片不会上传到云端。**
- 不修改或覆盖原图；只有压缩结果更小时才会生成副本。
- 实时展示处理进度、压缩前后体积与节省比例。
- 可随时取消批处理，并在 Finder 中快速定位输出文件。
- 支持简体中文和英文界面，以及应用内自动更新。

## 压缩效果:与 TinyPNG 的对比

我们用 79 张 PNG + 94 张 JPEG 的真实与公开语料,对 MediaSlim 和 TinyPNG 做了
逐图配对测量(SSIMULACRA2 / SSIM / PSNR + 人工盲测),并公开全部逐图原始数据:

- **JPEG**:每张图保证感知质量下限(SSIMULACRA2 ≥ 72),同质量下限下比 TinyPNG 省 15%;
- **PNG**:可比样本下体积持平、质量配对中位略优,最差 5% 画质下限更好;
- 短板同样如实公开:文字/UI 类 PNG 截屏画质小幅落后 TinyPNG。

完整报告(含方法论、放大对比图与逐图 CSV 数据):
**[中文版](docs/comparison-vs-tinypng.zh-CN.md)** · **[English](docs/comparison-vs-tinypng.en.md)**

## 系统要求

- macOS 13 Ventura 或更高版本。

## 安装与使用

1. 前往 [Releases](https://github.com/jojoTechWorkshop/MediaCompressRelease/releases/latest) 下载最新版 DMG。
2. 打开 DMG，将 MediaSlim 拖入“应用程序”文件夹。
3. 启动应用，然后拖入图片或文件夹；也可以使用“文件”菜单添加内容。
4. 压缩完成后，点击“在 Finder 中显示”查看结果。

应用会在每张原图所在目录创建 `Compressed` 文件夹。若同名文件已经存在，会自动使用新的文件名，避免覆盖已有结果；若压缩后没有变小，则保留原图且不生成无意义的副本。

## 隐私与安全

### 图片不上传，只在本机处理

**MediaSlim 不会将任何图片上传到远端服务器。** 图片的读取、压缩和写入全部在你的 Mac 上完成，原始图片始终留在本机。

### 通过 Apple 安全校验

正式发布的 DMG 与应用均使用 Apple Developer ID 签名并完成 Apple 公证。发布包经过 Apple 的已知恶意软件检查；安装和首次启动时，macOS Gatekeeper 还会验证开发者身份、代码签名与文件完整性。应用内更新另由 Sparkle 签名校验，确保更新包来自可信发布源且未被篡改。

## 更新

MediaSlim 会通过 Sparkle 检查正式版本。你也可以从应用菜单选择“检查更新…”，或直接访问 [Releases](https://github.com/jojoTechWorkshop/MediaCompressRelease/releases)。完整版本记录见 [CHANGELOG.md](CHANGELOG.md)。

## 关于本仓库

本仓库仅用于发布 MediaSlim 安装包、版本日志和应用内更新，不包含应用源代码。