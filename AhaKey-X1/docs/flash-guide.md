# AhaKey X1 烧录教程

## 适用范围

本教程适用于 AhaKey X1 官方 HEX 固件的烧录、升级和回退。

## 准备材料

- AhaKey X1
- Windows 电脑
- 支持数据传输的 Type-C 数据线
- WCHISPTool
- 需要烧录的 `.hex` 文件

## 第 1 步：下载 WCHISPTool

请从沁恒官方页面下载 WCHISPTool：

[https://www.wch.cn/downloads/WCHISPTool_Setup_exe.html](https://www.wch.cn/downloads/WCHISPTool_Setup_exe.html)

下载后安装并打开 WCHISPTool。

## 第 2 步：从 GitHub Releases 下载 HEX

| 版本 | 口径 | 下载 |
|---|---|---|
| v1.1.0 | 目前出厂会烧录的固件 / 当前推荐版本 | [AhaKey X1 Firmware v1.1.0](https://github.com/AhakeyAI/firmware/releases/tag/AhaKey-X1-v1.1.0) |
| v1.0.0 | 之前的老版本 | [AhaKey X1 Firmware v1.0.0](https://github.com/AhakeyAI/firmware/releases#release-AhaKey-X1-v1.0.0) |

普通用户优先下载 `v1.1.0`。只有需要回到之前老版本行为时，才选择 `v1.0.0`。

## 第 3 步：进入烧录模式

1. 让键盘关机。
2. 打开 WCHISPTool。
3. 按住键盘语音键。
4. 保持按住语音键，同时插入 Type-C。
5. 等待 WCHISPTool 识别设备。

如果 WCHISPTool 没有识别设备，请确认 Type-C 线支持数据传输，然后换一个 USB 口重试。

## 第 4 步：选择 HEX 并点击 Download

1. 在 WCHISPTool 中点击 `...`。
2. 选择刚从 GitHub Releases 下载的 `.hex` 文件。
3. 点击 `Download` 开始烧录。

烧录时不要拔掉 Type-C 数据线，也不要关闭 WCHISPTool。

## 第 5 步：烧录完成后重新连接

烧录完成后：

1. 重新插拔 Type-C，或重新开关键盘。
2. 在系统蓝牙中删除旧的 AhaKey 配对记录。
3. 重新连接 AhaKey X1 蓝牙。
4. 打开 AhaKey 客户端并重新连接设备。
5. 测试按键、蓝牙连接和客户端识别是否正常。

## 视频教程

> 视频教程正在重新整理中。
> 当前请先参考本文图文步骤完成烧录。
> 后续我们会补入 B 站 / YouTube / 官网教程链接。

## 常见问题

### WCHISP 没有弹出选择固件窗口

- 确认键盘已经关机。
- 确认是先按住语音键，再插入 Type-C。
- 确认 Type-C 线支持数据传输，不是只能充电的线。
- 换一个 USB 口后重试。

### 电脑识别不到设备

- 换一根支持数据传输的 Type-C 线。
- 换一个电脑 USB 口。
- 关闭 WCHISPTool 后重新打开。
- 重新按住语音键并插入 Type-C。

### 烧录完成后蓝牙无法连接

- 在系统蓝牙设置里删除旧的 AhaKey 配对记录。
- 重新开关键盘。
- 重新搜索并连接 AhaKey X1。

### 烧录后 AhaKey 客户端无法连接

- 确认系统蓝牙已经连接 AhaKey X1。
- 关闭并重新打开 AhaKey 客户端。
- 在客户端中重新搜索设备。
- 如果仍然无法连接，重新开关键盘后再试。

### 不确定该烧录哪个版本

优先选择 `v1.1.0`。这是目前出厂会烧录的固件 / 当前推荐版本。
