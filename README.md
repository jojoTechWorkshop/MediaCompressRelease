# MediaSlim

MediaSlim（简体中文显示为“清压图片”）是一款轻量、私密的 macOS 图片压缩工具。把 PNG、JPEG 图片或整个文件夹拖入应用，MediaSlim 会在本机完成压缩，并把更小的副本保存到原文件旁的 `Compressed` 文件夹中。

[下载最新版本](https://github.com/jojoTechWorkshop/MediaCompressRelease/releases/latest) · [查看更新日志](CHANGELOG.md)

## 主要功能

- 支持 PNG、JPG 与 JPEG，可一次添加多张图片。
- 支持拖入整个文件夹，并自动查找其中可压缩的图片。
- 所有处理均在本机完成，图片不会上传到云端。
- 不修改或覆盖原图；只有压缩结果更小时才会生成副本。
- 实时展示处理进度、压缩前后体积与节省比例。
- 可随时取消批处理，并在 Finder 中快速定位输出文件。
- 支持简体中文和英文界面，以及应用内自动更新。

## 系统要求

- macOS 13 Ventura 或更高版本。

## 安装与使用

1. 前往 [Releases](https://github.com/jojoTechWorkshop/MediaCompressRelease/releases/latest) 下载最新版 DMG。
2. 打开 DMG，将 MediaSlim 拖入“应用程序”文件夹。
3. 启动应用，然后拖入图片或文件夹；也可以使用“文件”菜单添加内容。
4. 压缩完成后，点击“在 Finder 中显示”查看结果。

应用会在每张原图所在目录创建 `Compressed` 文件夹。若同名文件已经存在，会自动使用新的文件名，避免覆盖已有结果；若压缩后没有变小，则保留原图且不生成无意义的副本。

## 隐私与安全

MediaSlim 不需要把图片发送到服务器，读取、编码和写入均在本机完成。正式发布的 DMG 与应用已使用 Apple Developer ID 签名并完成公证，应用更新由 Sparkle 签名校验。

## 更新

MediaSlim 会通过 Sparkle 检查正式版本。你也可以从应用菜单选择“检查更新…”，或直接访问 [Releases](https://github.com/jojoTechWorkshop/MediaCompressRelease/releases)。完整版本记录见 [CHANGELOG.md](CHANGELOG.md)。

## 关于本仓库

本仓库是 MediaSlim 的公开下载与自动更新发布仓库，不包含应用源代码。应用使用以下稳定地址获取更新信息：

`https://github.com/jojoTechWorkshop/MediaCompressRelease/releases/latest/download/appcast.xml`

每个正式 GitHub Release 至少需要包含：

- `appcast.xml`；
- 已公证并由 Sparkle EdDSA 签名的 `<应用名>-<版本>.zip`；
- 已签名并完成公证、用于首次安装的 `<应用名>-<版本>.dmg`；
- `appcast.xml` 中引用的所有 delta 文件（如有）。

Release 标签应与版本号一致，例如 `v1.1.0`。发布新版本时还应同步更新 [CHANGELOG.md](CHANGELOG.md)，并确保 GitHub Release 的说明与日志一致。更新文件必须作为 Release assets 上传；仅提交到 `main` 分支不会触发客户端更新。
