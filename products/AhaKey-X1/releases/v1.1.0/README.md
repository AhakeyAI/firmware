# AhaKey X1 Firmware v1.1.0

## 中文

这是 AhaKey X1 的第一次大更新固件，HEX 来自本地 `obj_final` 构建产物。

文件：

- `AhaKey-X1-firmware-v1.1.0.hex`

主要变化：

- 增加 USB HID 有线输入能力。
- 增加 USB / HID / 充电状态的屏幕显示逻辑。
- 优化蓝牙 HID 未连接时的蓝灯提示逻辑。
- 优化蓝牙重置、蓝牙名称递增和重连状态处理。
- 三个主要模式的第 4 个键默认改为 Backspace。
- 调整默认灯光亮度。
- 增加 AI 状态灯效协议和亮度配置协议。
- 支持上位机通过 BLE / USB 进行关键配置同步。
- 更新默认 OLED 和灯光相关行为。

注意：

- 这是官方可烧录更新固件，不是用户自定义 HEX。
- 如果需要恢复最初出厂体验，请使用 `../factory/AhaKey-X1-factory.hex`。

SHA256：

```text
09F4B60751C0BFCB374E5C62F6BE5A2B4FA180F6D7DC623B8E8CA46D1D34205A  AhaKey-X1-firmware-v1.1.0.hex
```

## English

This is the first major firmware update for AhaKey X1. The HEX file is from the local `obj_final` build output.

Highlights:

- Added USB HID wired input.
- Added USB / HID / charging status display behavior.
- Improved Bluetooth HID disconnected blue-light indication.
- Improved Bluetooth reset, Bluetooth name increment, and reconnect handling.
- Changed the fourth key in the three main modes to Backspace by default.
- Adjusted default LED brightness.
- Added AI status light protocol and brightness configuration protocol.
- Added key configuration sync support over BLE / USB.
- Updated default OLED and lighting behavior.
