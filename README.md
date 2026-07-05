# AhaKey Firmware

中文 | [English](#english)

## 中文

本仓库用于发布 AhaKey 硬件产品的官方可烧录固件、版本更新说明、校验信息和烧录文档。

当前已整理的产品线：

| 产品线 | 固件入口 | 状态 |
|---|---|---|
| AhaKey X1 | [products/AhaKey-X1/](products/AhaKey-X1/) | 已发布出厂版和 v1.1.0 |
| Future Products | 待添加 | 预留 |

## 这个仓库会放什么

- 官方可烧录 HEX 固件。
- 每个版本的更新说明和兼容性说明。
- 每个 HEX 的 SHA256 校验值。
- 面向用户和测试同事的烧录说明、回退说明和排障说明。

## 这个仓库不会放什么

本仓库不包含固件源码、SDK 源码、PCB、Gerber、BOM、生产测试资料或供应链资料。

## 快速入口

- AhaKey X1 出厂固件：[products/AhaKey-X1/releases/factory/](products/AhaKey-X1/releases/factory/)
- AhaKey X1 第一次大更新：[products/AhaKey-X1/releases/v1.1.0/](products/AhaKey-X1/releases/v1.1.0/)
- AhaKey X1 烧录说明：[products/AhaKey-X1/docs/flash-guide.md](products/AhaKey-X1/docs/flash-guide.md)
- 发布策略：[products/AhaKey-X1/docs/release-policy.md](products/AhaKey-X1/docs/release-policy.md)

## 版本边界

- `factory`：AhaKey X1 出厂固件，是蓝牙连接、基础键盘能力和默认体验的基石。
- `v1.1.0`：AhaKey X1 第一次大更新，来自本地 `obj_final` 构建产物。
- `drafts/`：准备中的下一版固件方向，只作为计划说明，不作为稳定固件下载入口。

## License

本仓库中的固件 HEX 仅用于正版 AhaKey 硬件的烧录、升级、测试和恢复。不得用于仿制硬件、竞争产品或逆向还原官方固件实现。

## English

This repository publishes official flashable firmware, release notes, checksums, and flashing documentation for AhaKey hardware products.

Current product lines:

| Product Line | Firmware Entry | Status |
|---|---|---|
| AhaKey X1 | [products/AhaKey-X1/](products/AhaKey-X1/) | Factory and v1.1.0 released |
| Future Products | To be added | Reserved |

## What This Repository Contains

- Official flashable HEX firmware files.
- Release notes and compatibility notes for each version.
- SHA256 checksums for each HEX file.
- Flashing, rollback, and troubleshooting documentation.

## What This Repository Does Not Contain

This repository does not include firmware source code, SDK source code, PCB, Gerber, BOM, production test materials, or supply-chain materials.

## Quick Links

- AhaKey X1 factory firmware: [products/AhaKey-X1/releases/factory/](products/AhaKey-X1/releases/factory/)
- AhaKey X1 first major update: [products/AhaKey-X1/releases/v1.1.0/](products/AhaKey-X1/releases/v1.1.0/)
- AhaKey X1 flashing guide: [products/AhaKey-X1/docs/flash-guide.md](products/AhaKey-X1/docs/flash-guide.md)
- Release policy: [products/AhaKey-X1/docs/release-policy.md](products/AhaKey-X1/docs/release-policy.md)
