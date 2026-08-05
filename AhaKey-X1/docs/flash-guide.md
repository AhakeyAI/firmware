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

## 第 2 步：下载 HEX

- 普通用户优先下载 `v1.1.0`。
- `v1.1.0` 是目前出厂会烧录的固件，也是当前推荐版本。
- `v1.0.0` 是之前的老版本，只在需要回到旧版行为时使用。

下载入口：

| 版本 | HEX |
|---|---|
| v1.1.0 | [../releases/v1.1.0/AhaKey-X1-firmware-v1.1.0.hex](../releases/v1.1.0/AhaKey-X1-firmware-v1.1.0.hex) |
| v1.0.0 | [../releases/v1.0.0/AhaKey-X1-firmware-v1.0.0.hex](../releases/v1.0.0/AhaKey-X1-firmware-v1.0.0.hex) |

## 第 3 步：进入烧录模式

1. 让键盘关机。
2. 打开 WCHISPTool。
3. 按住键盘语音键。
4. 保持按住语音键，同时插入 Type-C。
5. WCHISPTool 识别设备后选择 HEX 文件。

如果 WCHISPTool 没有识别设备，请确认 Type-C 线支持数据传输，然后换一个 USB 口重试。

## 第 4 步：选择 HEX 并点击 Download

在 WCHISPTool 中点击 `...`，选择刚下载的 `.hex` 文件，然后点击 `Download` 开始烧录。

烧录时不要拔掉 Type-C 数据线，也不要关闭 WCHISPTool。

## 第 5 步：烧录完成后重新连接

烧录完成后：

1. 重新插拔 Type-C，或重新开关键盘。
2. 在系统蓝牙中删除旧的 AhaKey 配对记录。
3. 重新连接 AhaKey X1 蓝牙。
4. 打开 AhaKey 客户端并重新连接设备。
5. 测试按键、蓝牙连接和客户端识别是否正常。

## 常见问题

### WCHISPTool 没有识别设备

- 确认键盘已经关机。
- 确认是先按住语音键，再插入 Type-C。
- 确认 Type-C 线支持数据传输，不是只能充电的线。
- 换一个 USB 口后重试。

### 烧录完成后蓝牙连不上

- 在系统蓝牙设置里删除旧的 AhaKey 配对记录。
- 重新开关键盘。
- 重新搜索并连接 AhaKey X1。
- 打开 AhaKey 客户端重新连接设备。

### 视频教程 404 怎么办？

如果旧的视频教程链接显示 404，请先按本页面的文字步骤操作。

临时处理方式：

- 不再依赖旧的视频链接作为唯一教程入口。
- 以本仓库的 `AhaKey-X1/docs/flash-guide.md` 作为当前正式教程。
- 后续如果重新上传视频，应在本页面补充新的可访问链接。
- 对外分享教程时，优先分享本页面链接，而不是旧的视频链接。

## GitHub Releases 和仓库目录的关系

1. 仓库内目录，例如 `AhaKey-X1/releases/v1.1.0/`，用于长期保存该版本的 HEX、README、SHA256SUMS.txt。
2. [GitHub Releases](https://github.com/AhakeyAI/firmware/releases) 用于对外展示版本更新、提供下载入口和发布说明。
3. 每个正式版本应该尽量两边都有：仓库目录里有对应文件，GitHub Releases 里有对应 tag / release，仓库目录 README 链接到 GitHub Release，GitHub Release 描述里链接回仓库目录。
