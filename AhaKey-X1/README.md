# AhaKey X1 Firmware

这里存放 AhaKey X1 的官方可烧录 HEX 固件、版本说明、校验值和烧录教程。

## 固件版本

| 版本 | 口径 | 推荐程度 | HEX | 说明 |
|---|---|---|---|---|
| v1.1.0 | 目前出厂会烧录的固件 | 推荐 | [releases/v1.1.0/AhaKey-X1-firmware-v1.1.0.hex](releases/v1.1.0/AhaKey-X1-firmware-v1.1.0.hex) | 当前出厂和普通用户推荐版本 |
| v1.0.0 | 之前的老版本 | 仅旧版需要时使用 | [releases/v1.0.0/AhaKey-X1-firmware-v1.0.0.hex](releases/v1.0.0/AhaKey-X1-firmware-v1.0.0.hex) | 早期版本，不再作为默认推荐 |

## 如何选择？

- 普通用户：选择 `v1.1.0`。
- 当前新出厂设备：使用 `v1.1.0`。
- 需要回到之前老版本行为：选择 `v1.0.0`。
- 不确定：优先选择 `v1.1.0`。

## 烧录教程

[docs/flash-guide.md](docs/flash-guide.md)

## GitHub Releases

[https://github.com/AhakeyAI/firmware/releases](https://github.com/AhakeyAI/firmware/releases)

仓库内 `AhaKey-X1/releases/` 用于长期保存 HEX 文件和文档。
GitHub Releases 用于对外发布版本、展示更新记录和下载附件。
两者应该互相跳转，保持口径一致。

## GitHub Releases 和仓库目录的关系

1. 仓库内目录，例如 `AhaKey-X1/releases/v1.1.0/`，用于长期保存该版本的 HEX、README、SHA256SUMS.txt。
2. [GitHub Releases](https://github.com/AhakeyAI/firmware/releases) 用于对外展示版本更新、提供下载入口和发布说明。
3. 每个正式版本应该尽量两边都有：仓库目录里有对应文件，GitHub Releases 里有对应 tag / release，仓库目录 README 链接到 GitHub Release，GitHub Release 描述里链接回仓库目录。

推荐 tag 命名：

```text
AhaKey-X1-v1.0.0
AhaKey-X1-v1.1.0
```
