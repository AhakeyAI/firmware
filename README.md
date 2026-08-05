# AhaKey Firmware

这里用于发布 AhaKey 官方 HEX 固件、更新历史、校验值和烧录教程。

## 固件入口

| 产品 | 当前推荐版本 | 老版本 | 烧录教程 | GitHub Releases |
|---|---|---|---|---|
| AhaKey X1 | v1.1.0，目前出厂会烧录的固件 | v1.0.0，之前的老版本 | [AhaKey-X1/docs/flash-guide.md](AhaKey-X1/docs/flash-guide.md) | [GitHub Releases](https://github.com/AhakeyAI/firmware/releases) |

## 直接下载

| 版本 | 口径 | 适合谁 | 仓库内 HEX | GitHub Release |
|---|---|---|---|---|
| v1.1.0 | 目前出厂会烧录的固件 / 当前推荐版本 | 普通用户优先下载这个 | [AhaKey-X1/releases/v1.1.0/AhaKey-X1-firmware-v1.1.0.hex](AhaKey-X1/releases/v1.1.0/AhaKey-X1-firmware-v1.1.0.hex) | [对应 GitHub Release](https://github.com/AhakeyAI/firmware/releases) |
| v1.0.0 | 之前的老版本 | 需要回到旧版行为时使用 | [AhaKey-X1/releases/v1.0.0/AhaKey-X1-firmware-v1.0.0.hex](AhaKey-X1/releases/v1.0.0/AhaKey-X1-firmware-v1.0.0.hex) | [对应 GitHub Release](https://github.com/AhakeyAI/firmware/releases) |

如果还没有创建具体版本的 GitHub Release，请先使用 [Releases 总页](https://github.com/AhakeyAI/firmware/releases)。后续 GitHub Release 会与仓库内 `AhaKey-X1/releases/` 目录保持同步。

## 快速烧录步骤

1. 下载对应版本 HEX。
2. 下载并打开 WCHISPTool。
3. 让键盘关机。
4. 按住语音键，同时插入 Type-C。
5. 在 WCHISPTool 中选择 HEX。
6. 点击 Download。
7. 烧录完成后重新连接蓝牙和 AhaKey 客户端。

详细步骤见 [AhaKey-X1/docs/flash-guide.md](AhaKey-X1/docs/flash-guide.md)。

## GitHub Releases 和仓库目录的关系

1. 仓库内目录，例如 `AhaKey-X1/releases/v1.1.0/`，用于长期保存该版本的 HEX、README、SHA256SUMS.txt。
2. [GitHub Releases](https://github.com/AhakeyAI/firmware/releases) 用于对外展示版本更新、提供下载入口和发布说明。
3. 每个正式版本应该尽量两边都有：仓库目录里有对应文件，GitHub Releases 里有对应 tag / release，仓库目录 README 链接到 GitHub Release，GitHub Release 描述里链接回仓库目录。

推荐 tag 命名：

```text
AhaKey-X1-v1.0.0
AhaKey-X1-v1.1.0
```

## 仓库结构

```text
firmware/
├── README.md
└── AhaKey-X1/
    ├── README.md
    ├── assets/
    ├── docs/
    │   ├── flash-guide.md
    │   └── release-policy.md
    └── releases/
        ├── v1.0.0/
        │   ├── README.md
        │   ├── AhaKey-X1-firmware-v1.0.0.hex
        │   └── SHA256SUMS.txt
        └── v1.1.0/
            ├── README.md
            ├── AhaKey-X1-firmware-v1.1.0.hex
            └── SHA256SUMS.txt
```
