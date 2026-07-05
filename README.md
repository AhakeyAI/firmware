<a id="top"></a>

<p align="center">
  <a href="#zh-cn"><strong>简体中文</strong></a> ·
  <a href="#en"><strong>English</strong></a>
</p>

---

<a id="zh-cn"></a>

<h1 align="center">🧩 AhaKey Firmware</h1>

<p align="center">
  <strong>AhaKey 官方可烧录固件、版本说明、校验信息与烧录文档</strong>
</p>

<p align="center">
  Official HEX · Release Notes · Checksums · Flash Guide · Compatibility
</p>

<p align="center">
  <a href="./products/AhaKey-X1/"><img alt="AhaKey X1" src="https://img.shields.io/badge/Product-AhaKey%20X1-5C6BC0"></a>
  <a href="./products/AhaKey-X1/releases/factory/"><img alt="factory" src="https://img.shields.io/badge/Firmware-Factory-26A69A"></a>
  <a href="./products/AhaKey-X1/releases/v1.1.0/"><img alt="v1.1.0" src="https://img.shields.io/badge/Release-v1.1.0-43A047"></a>
  <a href="./products/AhaKey-X1/docs/flash-guide.md"><img alt="flash guide" src="https://img.shields.io/badge/Guide-Flashing-orange"></a>
</p>

---

## AhaKey Firmware 是什么？

`firmware` 仓库用于发布 AhaKey 硬件产品的**官方可烧录固件、版本更新说明、校验信息和烧录文档**。

这个仓库面向：

* 普通用户：下载官方固件、查看升级说明
* 测试同事：验证固件版本、核对 SHA256 校验值
* 售后和维护人员：按官方文档进行烧录、回退和排障
* 开发者：了解官方固件版本边界和兼容性说明

如果你想基于公开 SDK 自定义按键、拨杆、灯光、OLED 或构建自己的 HEX，请查看：

👉 [`protocol / AhaKey Developer Kit`](https://github.com/AhakeyAI/protocol)

---

## 当前产品线

| 产品线             | 固件入口                                         | 状态               |
| --------------- | -------------------------------------------- | ---------------- |
| AhaKey X1       | [`products/AhaKey-X1/`](products/AhaKey-X1/) | 已发布出厂版和 `v1.1.0` |
| Future Products | 待添加                                          | 预留               |

---

## 这个仓库会放什么？

本仓库会放：

* 官方可烧录 HEX 固件
* 每个版本的 release notes
* 每个版本的兼容性说明
* 每个 HEX 的 SHA256 校验值
* 面向用户和测试同事的烧录说明
* 回退说明
* 排障说明
* 官方固件发布策略

---

## 这个仓库不会放什么？

本仓库不包含：

* 固件源码
* SDK 源码
* PCB layout
* Gerber
* BOM
* 生产测试资料
* 供应链资料
* 官方完整固件内部实现
* 可用于仿制、打板、量产或竞争性硬件开发的生产级资料

如果你想做开发者二创、SDK demo 或自定义 HEX，请优先使用：

👉 [`protocol / AhaKey Developer Kit`](https://github.com/AhakeyAI/protocol)

如果你希望进一步参与固件代码完善、硬件产品技术开发、底层调试、生产级资料评估或更深度的产品共创，请提交：

👉 [`Hardware Source Access Program`](https://ahakey.com/cn/hardware-source)

---

## 快速入口

| 内容             | 链接                                                                                       | 说明                    |
| -------------- | ---------------------------------------------------------------------------------------- | --------------------- |
| AhaKey X1 固件入口 | [`products/AhaKey-X1/`](products/AhaKey-X1/)                                             | AhaKey X1 官方固件目录      |
| 出厂固件           | [`products/AhaKey-X1/releases/factory/`](products/AhaKey-X1/releases/factory/)           | AhaKey X1 出厂固件        |
| 第一次大更新         | [`products/AhaKey-X1/releases/v1.1.0/`](products/AhaKey-X1/releases/v1.1.0/)             | AhaKey X1 `v1.1.0` 固件 |
| 烧录说明           | [`products/AhaKey-X1/docs/flash-guide.md`](products/AhaKey-X1/docs/flash-guide.md)       | 面向用户和测试同事的烧录文档        |
| 发布策略           | [`products/AhaKey-X1/docs/release-policy.md`](products/AhaKey-X1/docs/release-policy.md) | 官方固件发布、回退和版本管理策略      |

---

## 推荐使用路径

### 1）我想下载或恢复官方固件

```text
进入 products/AhaKey-X1/
→ 选择 factory 或指定 release
→ 核对版本说明和 SHA256
→ 按 flash-guide.md 烧录
→ 验证设备功能
```

适合：

* 恢复出厂固件
* 重新烧录官方固件
* 排查设备异常
* 按售后说明恢复设备

---

### 2）我想升级到最新官方版本

```text
进入 products/AhaKey-X1/releases/
→ 查看最新 release
→ 阅读 release notes
→ 确认兼容性
→ 核对 SHA256
→ 按官方烧录说明升级
```

适合：

* 升级官方固件
* 查看版本变化
* 确认官方支持范围
* 测试新版本稳定性

---

### 3）我想自己做 SDK 二创或构建自定义 HEX

```text
进入 protocol
→ 阅读 AhaKey Developer Kit
→ 查看 sdk/README.md
→ 参考 examples
→ 构建自己的 HEX
→ 本地烧录到正版 AhaKey X1 硬件
```

入口：

👉 [`protocol / AhaKey Developer Kit`](https://github.com/AhakeyAI/protocol)

> 用户自己构建的 HEX 是自定义开发者固件，不等同于 AhaKey 官方固件。
> 请不要将自定义 HEX 描述为官方固件，也不要冒充官方发布版本。

---

## 版本边界

| 版本 / 目录   | 含义                                     | 状态          |
| --------- | -------------------------------------- | ----------- |
| `factory` | AhaKey X1 出厂固件，是蓝牙连接、基础键盘能力和默认体验的基石    | 官方稳定版本      |
| `v1.1.0`  | AhaKey X1 第一次大更新，来自本地 `obj_final` 构建产物 | 官方发布版本      |
| `drafts/` | 准备中的下一版固件方向，只作为计划说明                    | 不作为稳定固件下载入口 |

说明：

* `factory` 和正式 release 目录用于官方确认过的可烧录固件。
* `drafts/` 只用于规划、草案或准备中的版本说明。
* 用户自定义 HEX 不会作为本仓库的官方 release 发布。
* 未经 AhaKey 团队确认的第三方 HEX 不应被描述为官方固件。

---

## 固件校验

本仓库中的官方 HEX 应尽量提供 SHA256 校验值。

建议烧录前确认：

```text
1. 固件版本是否正确
2. 设备型号是否匹配
3. SHA256 是否一致
4. 是否阅读对应 release notes
5. 是否按 flash-guide.md 操作
```

如果校验值不一致，请不要继续烧录，并优先检查：

* 文件是否下载完整
* 是否下载了错误版本
* 是否被浏览器或网盘改名 / 修改
* 是否使用了非官方来源的固件文件

---

## 仓库结构

```text
firmware/
├── README.md
└── products/
    └── AhaKey-X1/
        ├── README.md
        ├── releases/
        │   ├── factory/
        │   └── v1.1.0/
        └── docs/
            ├── flash-guide.md
            └── release-policy.md
```

---

## 和其他仓库的关系

| 仓库                                                             | 用途                   | 适合什么内容                                |
| -------------------------------------------------------------- | -------------------- | ------------------------------------- |
| [`desktop`](https://github.com/AhakeyAI/desktop)               | 官方桌面客户端              | 设备连接、配置、AI 状态同步、语音输入、桌面工作流            |
| [`protocol`](https://github.com/AhakeyAI/protocol)             | AhaKey Developer Kit | BLE 协议、硬件 SDK、examples、自定义 HEX 构建说明   |
| [`awesome-ahakey`](https://github.com/AhakeyAI/awesome-ahakey) | 社区项目展示               | 第三方项目、workflow、SDK demo、自定义 HEX 玩法、教程 |
| [`firmware`](https://github.com/AhakeyAI/firmware)             | 官方固件说明与发布            | 官方可烧录 HEX、release notes、校验信息、烧录文档     |
| [`Discussions`](https://github.com/orgs/AhakeyAI/discussions)  | 想法讨论                 | 不确定问题、玩法讨论、社区共创方向                     |

简单理解：

```text
官方桌面客户端 → desktop
协议 / SDK / examples / 自定义 HEX 构建 → protocol
社区项目 / SDK demo / 自定义 HEX 展示 → awesome-ahakey
官方可烧录固件 / 版本说明 / 烧录文档 → firmware
不确定 → Discussions
```

---

## License

本仓库中的官方固件 HEX 仅用于正版 AhaKey 硬件的烧录、升级、测试和恢复。

不得将本仓库中的固件文件、说明或校验信息用于：

* 仿制硬件
* 非正版 AhaKey 硬件
* 竞争产品
* 绕过正版硬件使用边界
* 逆向还原官方固件实现
* 冒充 AhaKey 官方固件或官方发布版本

本仓库中的文档、说明和元数据以仓库 `LICENSE` 文件为准。
第三方工具链、芯片厂商 SDK、烧录工具和供应商库继续适用其原始授权条款。

---

<p align="right"><a href="#top">↑ Back to top</a></p>

---

<a id="en"></a>

<h1 align="center">🧩 AhaKey Firmware</h1>

<p align="center">
  <strong>Official flashable firmware, release notes, checksums, and flashing documentation for AhaKey hardware</strong>
</p>

<p align="center">
  Official HEX · Release Notes · Checksums · Flash Guide · Compatibility
</p>

<p align="center">
  <a href="./products/AhaKey-X1/"><img alt="AhaKey X1" src="https://img.shields.io/badge/Product-AhaKey%20X1-5C6BC0"></a>
  <a href="./products/AhaKey-X1/releases/factory/"><img alt="factory" src="https://img.shields.io/badge/Firmware-Factory-26A69A"></a>
  <a href="./products/AhaKey-X1/releases/v1.1.0/"><img alt="v1.1.0" src="https://img.shields.io/badge/Release-v1.1.0-43A047"></a>
  <a href="./products/AhaKey-X1/docs/flash-guide.md"><img alt="flash guide" src="https://img.shields.io/badge/Guide-Flashing-orange"></a>
</p>

---

## What is AhaKey Firmware?

The `firmware` repository publishes **official flashable firmware, release notes, checksums, and flashing documentation** for AhaKey hardware products.

This repository is for:

* users who need official firmware downloads or recovery files
* testers who need to verify firmware versions and SHA256 checksums
* support and maintenance teams who need flashing, rollback, and troubleshooting docs
* developers who need to understand official firmware version boundaries and compatibility notes

If you want to customize buttons, toggle behavior, lights, OLED display, or build your own HEX using the public SDK, please start with:

👉 [`protocol / AhaKey Developer Kit`](https://github.com/AhakeyAI/protocol)

---

## Current product lines

| Product Line    | Firmware Entry                               | Status                        |
| --------------- | -------------------------------------------- | ----------------------------- |
| AhaKey X1       | [`products/AhaKey-X1/`](products/AhaKey-X1/) | Factory and `v1.1.0` released |
| Future Products | To be added                                  | Reserved                      |

---

## What this repository contains

This repository contains:

* official flashable HEX firmware files
* release notes for each version
* compatibility notes for each version
* SHA256 checksums for each HEX file
* flashing documentation for users and testers
* rollback instructions
* troubleshooting documentation
* official firmware release policy

---

## What this repository does not contain

This repository does not include:

* firmware source code
* SDK source code
* PCB layout
* Gerber
* BOM
* production test materials
* supply-chain materials
* full official firmware internals
* production-grade materials that can be used for cloning, board reproduction, mass production, or competing hardware development

If you want to build SDK demos, custom developer firmware, or your own HEX files, please start with:

👉 [`protocol / AhaKey Developer Kit`](https://github.com/AhakeyAI/protocol)

If you want to help improve firmware code, fill technical gaps in hardware product development, join low-level debugging, request production-grade material evaluation, or explore deeper product collaboration, please submit:

👉 [`Hardware Source Access Program`](https://ahakey.com/cn/hardware-source)

---

## Quick links

| Content                  | Link                                                                                     | Notes                                                   |
| ------------------------ | ---------------------------------------------------------------------------------------- | ------------------------------------------------------- |
| AhaKey X1 firmware entry | [`products/AhaKey-X1/`](products/AhaKey-X1/)                                             | Official firmware directory for AhaKey X1               |
| Factory firmware         | [`products/AhaKey-X1/releases/factory/`](products/AhaKey-X1/releases/factory/)           | AhaKey X1 factory firmware                              |
| First major update       | [`products/AhaKey-X1/releases/v1.1.0/`](products/AhaKey-X1/releases/v1.1.0/)             | AhaKey X1 `v1.1.0` firmware                             |
| Flashing guide           | [`products/AhaKey-X1/docs/flash-guide.md`](products/AhaKey-X1/docs/flash-guide.md)       | Flashing documentation for users and testers            |
| Release policy           | [`products/AhaKey-X1/docs/release-policy.md`](products/AhaKey-X1/docs/release-policy.md) | Official firmware release, rollback, and version policy |

---

## Recommended paths

### 1) I want to download or restore official firmware

```text
Go to products/AhaKey-X1/
→ Choose factory or a specific release
→ Check release notes and SHA256
→ Follow flash-guide.md
→ Verify device behavior
```

Best for:

* restoring factory firmware
* reflashing official firmware
* troubleshooting device issues
* recovering the device according to support instructions

---

### 2) I want to upgrade to the latest official version

```text
Go to products/AhaKey-X1/releases/
→ Read the latest release notes
→ Check compatibility
→ Verify SHA256
→ Follow the official flashing guide
```

Best for:

* upgrading official firmware
* checking version changes
* confirming official support scope
* testing new official versions

---

### 3) I want to build SDK demos or custom HEX files

```text
Go to protocol
→ Read AhaKey Developer Kit
→ Check sdk/README.md
→ Follow examples
→ Build your own HEX
→ Flash it locally to genuine AhaKey X1 hardware
```

Entry:

👉 [`protocol / AhaKey Developer Kit`](https://github.com/AhakeyAI/protocol)

> User-built HEX files are custom developer firmware and are not official AhaKey firmware.
> Please do not describe custom HEX files as official firmware or use them to impersonate official releases.

---

## Version boundaries

| Version / Directory | Meaning                                                                                                      | Status                               |
| ------------------- | ------------------------------------------------------------------------------------------------------------ | ------------------------------------ |
| `factory`           | AhaKey X1 factory firmware, the baseline for BLE connection, basic keyboard behavior, and default experience | Official stable version              |
| `v1.1.0`            | AhaKey X1 first major update, built from local `obj_final` output                                            | Official release                     |
| `drafts/`           | Planned future firmware direction                                                                            | Not a stable firmware download entry |

Notes:

* `factory` and formal release directories are for AhaKey-confirmed flashable firmware.
* `drafts/` is only for planning, drafts, or upcoming version notes.
* User-built custom HEX files are not published as official releases in this repository.
* Third-party HEX files not confirmed by AhaKey should not be described as official firmware.

---

## Firmware verification

Official HEX files in this repository should provide SHA256 checksums whenever possible.

Before flashing, please verify:

```text
1. The firmware version is correct
2. The hardware model matches
3. The SHA256 checksum matches
4. You have read the release notes
5. You are following flash-guide.md
```

If the checksum does not match, do not flash the file. Check whether:

* the file was downloaded completely
* you downloaded the wrong version
* the file was renamed or modified by the browser or storage service
* the file came from an unofficial source

---

## Repository layout

```text
firmware/
├── README.md
└── products/
    └── AhaKey-X1/
        ├── README.md
        ├── releases/
        │   ├── factory/
        │   └── v1.1.0/
        └── docs/
            ├── flash-guide.md
            └── release-policy.md
```

---

## Relationship with other repositories

| Repository                                                     | Purpose                             | Best for                                                                         |
| -------------------------------------------------------------- | ----------------------------------- | -------------------------------------------------------------------------------- |
| [`desktop`](https://github.com/AhakeyAI/desktop)               | Official desktop client             | Device connection, configuration, AI status sync, voice input, desktop workflows |
| [`protocol`](https://github.com/AhakeyAI/protocol)             | AhaKey Developer Kit                | BLE protocol, Hardware SDK, examples, and custom HEX build docs                  |
| [`awesome-ahakey`](https://github.com/AhakeyAI/awesome-ahakey) | Community project showcase          | Third-party projects, workflows, SDK demos, custom HEX showcases, tutorials      |
| [`firmware`](https://github.com/AhakeyAI/firmware)             | Official firmware docs and releases | Official flashable HEX files, release notes, checksums, flashing docs            |
| [`Discussions`](https://github.com/orgs/AhakeyAI/discussions)  | Idea discussion                     | Start here if you are not sure where your issue or idea belongs                  |

Simple rule:

```text
Official desktop client → desktop
Protocol / SDK / examples / custom HEX build docs → protocol
Community projects / SDK demos / custom HEX showcases → awesome-ahakey
Official flashable firmware / release notes / flashing docs → firmware
Not sure → Discussions
```

---

## License

Official firmware HEX files in this repository are provided only for flashing, upgrading, testing, and recovering genuine AhaKey hardware.

You may not use firmware files, documentation, or checksums in this repository for:

* clone hardware
* non-genuine AhaKey hardware
* competing products
* bypassing the intended genuine hardware boundary
* reverse engineering the official firmware implementation
* impersonating official AhaKey firmware or official releases

Documentation and metadata in this repository follow the repository `LICENSE` file.
Third-party toolchains, chip vendor SDKs, flashing tools, and vendor libraries remain under their original license terms.

---

<p align="right"><a href="#top">↑ Back to top</a></p>
