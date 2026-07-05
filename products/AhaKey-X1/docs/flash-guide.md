# AhaKey X1 Flash Guide

## 中文

本说明用于 AhaKey X1 固件 HEX 的烧录和回退。

## 准备

- AhaKey X1 键盘。
- USB 数据线。
- Windows 电脑。
- 沁恒官方下载烧录工具，例如 WCHISPTool。
- 需要烧录的 `.hex` 文件。

## 选择固件

- 恢复出厂体验：`products/AhaKey-X1/releases/factory/AhaKey-X1-factory.hex`
- 使用第一次大更新：`products/AhaKey-X1/releases/v1.1.0/AhaKey-X1-firmware-v1.1.0.hex`

## 基本流程

1. 关闭键盘。
2. 让键盘进入下载 / 烧录模式。
3. 打开 WCHISPTool。
4. 选择对应芯片和 HEX 文件。
5. 建议按测试要求选择 Data-Flash 擦除策略。
6. 开始下载。
7. 烧录完成后重启键盘。
8. 测试蓝牙连接、按键输入、模式切换、屏幕显示和灯光状态。

## 烧录后建议测试

- 键盘能正常开机。
- 屏幕能正常显示。
- 蓝牙能正常连接。
- 三个主要模式能正常切换。
- USB 连接时能显示 USB / HID 状态。
- 第 4 个键行为符合当前固件版本说明。

## English

This guide covers flashing and rollback for AhaKey X1 HEX firmware.

Use WCH's official flashing tool, such as WCHISPTool, select the target HEX file, flash it, restart the keyboard, and then verify Bluetooth, key input, mode switching, display, and lighting behavior.
