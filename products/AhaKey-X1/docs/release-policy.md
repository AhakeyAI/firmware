# AhaKey X1 Firmware Release Policy

## 中文

本目录只发布 AhaKey X1 官方可烧录固件。

版本划分：

- `factory`：最初出厂固件，作为恢复和对照测试基线。
- `v1.x.x`：经过测试确认的稳定更新。
- `drafts/`：准备中的功能说明，不作为正式固件发布。

发布原则：

- 每个正式版本必须包含 HEX、README 和 SHA256 校验值。
- 不提交 `.o`、`.elf`、构建缓存或其他中间产物。
- 不提交完整固件源码、PCB、BOM、Gerber、生产测试资料或供应链资料。
- 不把用户自定义 HEX 描述为官方固件。
- 新产品线应放入独立目录，例如 `products/AhaKey-X2/`。

## English

This directory publishes official flashable firmware for AhaKey X1 only.

Each stable release should include a HEX file, README, and SHA256 checksum. Build intermediates, source code, PCB, BOM, Gerber, production test materials, and supply-chain materials should not be committed here.
