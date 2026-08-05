# AhaKey Firmware

这里用于发布 AhaKey 官方固件版本说明、烧录教程和 GitHub Releases 下载入口。实际 HEX 文件请从 GitHub Releases 下载。

## 固件下载

| 版本 | 口径 | 适合谁 | 下载 |
|---|---|---|---|
| v1.1.0 | 目前出厂会烧录的固件 / 当前推荐版本 | 普通用户优先下载这个 | [AhaKey X1 Firmware v1.1.0](https://github.com/AhakeyAI/firmware/releases/tag/AhaKey-X1-v1.1.0) |
| v1.0.0 | 之前的老版本 | 需要回到旧版行为时使用 | [AhaKey X1 Firmware v1.0.0](https://github.com/AhakeyAI/firmware/releases#release-AhaKey-X1-v1.0.0) |

## 烧录教程（推荐windows烧录，mac烧录环境太复杂（可以让ai读这个文件来搞））

- Windows 图形化烧录：[AhaKey-X1/docs/flash-guide.md](AhaKey-X1/docs/flash-guide.md)
- macOS 命令行烧录：[AhaKey-X1/docs/flash-guide-macos.md](AhaKey-X1/docs/flash-guide-macos.md)

## 快速选择

- 使用 Windows，并且希望图形化操作：看 Windows 烧录教程，使用 WCHISPTool。
- 使用 macOS，只需要烧录已有 HEX：看 macOS 烧录教程中的“烧录已有 HEX”，使用 `wchisp`。
- 使用 macOS，还要从源码编译：看 macOS 烧录教程中的“在 Mac 上编译固件”。

## License

This repository is licensed under the Apache License 2.0. See LICENSE for details.
