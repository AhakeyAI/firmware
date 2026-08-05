# AhaKey Firmware

这里用于发布 AhaKey 官方固件版本说明、烧录教程和 GitHub Releases 下载入口。实际 HEX 文件请从 GitHub Releases 下载。

| 产品 | 当前推荐版本 | 老版本 | 烧录教程 |
|---|---|---|---|
| AhaKey X1 | v1.1.0：目前出厂会烧录的固件 / 当前推荐版本 | v1.0.0：之前的老版本 | [AhaKey-X1/docs/flash-guide.md](AhaKey-X1/docs/flash-guide.md) |

## 固件下载

| 版本 | 口径 | 适合谁 | 下载 |
|---|---|---|---|
| v1.1.0 | 目前出厂会烧录的固件 / 当前推荐版本 | 普通用户优先下载这个 | [AhaKey X1 Firmware v1.1.0](https://github.com/AhakeyAI/firmware/releases/tag/AhaKey-X1-v1.1.0) |
| v1.0.0 | 之前的老版本 | 需要回到旧版行为时使用 | [AhaKey X1 Firmware v1.0.0](https://github.com/AhakeyAI/firmware/releases#release-AhaKey-X1-v1.0.0) |

## 快速烧录步骤

1. 从 GitHub Releases 下载对应版本的 `.hex` 文件。
2. 下载并打开 WCHISPTool。
3. 让键盘关机。
4. 按住语音键，同时插入 Type-C。
5. 在 WCHISPTool 中选择 `.hex` 文件。
6. 点击 Download。
7. 烧录完成后重新连接蓝牙和 AhaKey 客户端。

详细教程：[AhaKey-X1/docs/flash-guide.md](AhaKey-X1/docs/flash-guide.md)

## GitHub Releases 与本仓库的关系

- GitHub Releases：正式保存和下载 HEX 固件。
- 本仓库文档：说明版本口径、烧录方法和发布规范。
- 从现在开始，仓库目录中不再重复保存 HEX 文件。

## License

This repository is licensed under the Apache License 2.0. See LICENSE for details.
