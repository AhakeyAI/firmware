# AhaKey X1 Flash Guide

中文 | [English](#english)

## 中文

本说明用于 AhaKey X1 固件 HEX 的烧录、升级和回退。

## 准备

- AhaKey X1 键盘。
- USB Type-C 数据线。
- Windows 电脑。
- 固件 `.hex` 文件。
- 沁恒官方烧录工具：`WCHISP Studio` / `WCHISPTool`。

下载地址：

[WCHISP 烧录软件工具](https://www.wch.cn/downloads/WCHISPTool_Setup_exe.html)

## 选择固件

- 恢复出厂体验：`products/AhaKey-X1/releases/factory/AhaKey-X1-factory.hex`
- 使用第一次大更新：`products/AhaKey-X1/releases/v1.1.0/AhaKey-X1-firmware-v1.1.0.hex`

如果你是开发者，也可以先生成自己的 HEX 烧录文件；普通用户建议直接使用本仓库 releases 目录下已经发布的 `.hex` 文件。

## 烧录教程

1. 准备 `.hex` 固件文件。

   如果下载的是压缩包，请先解压，然后找到后缀为 `.hex` 的文件。

2. 下载并安装 `WCHISP Studio` / `WCHISPTool`。

   下载地址：

   [https://www.wch.cn/downloads/WCHISPTool_Setup_exe.html](https://www.wch.cn/downloads/WCHISPTool_Setup_exe.html)

3. 打开 WCHISP 软件，并让键盘进入烧录模式。

   操作方式：

   - 先让键盘关机。
   - 保持 WCHISP 软件处于打开状态。
   - 长按住键盘的语音键。
   - 在继续按住语音键的同时，把 Type-C 数据线插入键盘。
   - WCHISP 软件会弹出选择固件的窗口。
   - 点击 `...`，选择 `.hex` 文件。
   - 点击下载 / Download 开始烧录。

   选择固件示意图：

   ![选择固件](https://github.com/user-attachments/assets/a54f5e05-101d-4b2d-9dc3-a51870f19dbb)

   视频演示：

   [https://github.com/user-attachments/assets/61aaab35-1b08-4eaa-a504-ec1168348d65](https://github.com/user-attachments/assets/61aaab35-1b08-4eaa-a504-ec1168348d65)

   其他选项界面参考：

   <img width="2473" height="1511" alt="WCHISP options" src="https://github.com/user-attachments/assets/9a80de0c-fdd8-400e-9fc7-5bd23b5f3b77" />

4. 烧录完成后重新连接键盘。

   正常情况下，下载完成后键盘会重新启动，并弹出蓝牙连接。

   之后请：

   - 在电脑系统蓝牙中连接 AhaKey 键盘。
   - 打开 AhaKey 软件客户端。
   - 在客户端中连接键盘并测试按键、屏幕、灯光和模式切换。

## 烧录后建议测试

- 键盘能正常开机。
- 屏幕能正常显示。
- 蓝牙能正常连接。
- 三个主要模式能正常切换。
- USB 连接时能显示 USB / HID 状态。
- 第 4 个键行为符合当前固件版本说明。
- AhaKey 软件客户端能正常连接键盘。

## 常见问题

### WCHISP 没有弹出选择固件窗口

- 确认键盘处于关机状态。
- 确认先打开 WCHISP 软件，再按住语音键插入 Type-C。
- 确认使用的是支持数据传输的 Type-C 数据线，不是只能充电的线。
- 换一个 USB 口后重试。

### 烧录完成后电脑没有弹出蓝牙连接

- 先在系统蓝牙里删除旧的 AhaKey 配对记录。
- 重新开关键盘。
- 如果仍然无法连接，可以重新烧录出厂固件或当前稳定固件后再测试。

## English

This guide covers flashing, upgrading, and rolling back AhaKey X1 HEX firmware.

## Preparation

- AhaKey X1 keyboard.
- USB Type-C data cable.
- Windows PC.
- A firmware `.hex` file.
- WCH's official flashing tool: `WCHISP Studio` / `WCHISPTool`.

Download:

[WCHISP flashing tool](https://www.wch.cn/downloads/WCHISPTool_Setup_exe.html)

## Firmware Files

- Factory firmware: `products/AhaKey-X1/releases/factory/AhaKey-X1-factory.hex`
- First major update: `products/AhaKey-X1/releases/v1.1.0/AhaKey-X1-firmware-v1.1.0.hex`

## Flashing Steps

1. Prepare the `.hex` firmware file.
2. Install and open `WCHISP Studio` / `WCHISPTool`.
3. Power off the keyboard.
4. Hold the voice key, then plug in the Type-C cable while still holding the key.
5. WCHISP should open a firmware selection dialog.
6. Click `...`, choose the `.hex` file, and start Download.
7. After flashing, reconnect the keyboard through system Bluetooth and AhaKey Studio.
