# AhaKey X1 macOS 烧录指南

本文档用于在 macOS 上给 AhaKey X1 烧录固件。当前验证过的 Mac 路线不是 WCHISPTool 图形界面，也不是 `wch-web-isp` 网页烧录，而是使用 `wchisp` 命令行工具。

如果只是烧录官方发布的 `.hex` 文件，可以只看“烧录已有 HEX”。如果需要在 Mac 上从源码编译固件，再看“在 Mac 上编译固件”。

## 适用范围

- 设备：AhaKey X1 / CH582 系列固件流程
- 系统：macOS，包含 Apple Silicon / arm64
- 烧录方式：USB ISP
- 固件格式：`.hex`
- 推荐烧录工具：`wchisp 0.3.0`

不建议在 Mac 上使用 WCHISPTool Studio GUI。它在 Windows 上更成熟，Mac 上容易遇到驱动和兼容性问题。

## 前期准备

### 硬件准备

- AhaKey X1
- Mac 电脑
- 支持数据传输的 Type-C 数据线
- 要烧录的 `.hex` 固件

不要使用只能充电的 Type-C 线。如果 Mac 通过扩展坞连接失败，建议直接接 Mac 的 USB-C 口，或换一个扩展坞/转接头。

### macOS 环境

建议先安装 Homebrew 和 Apple Command Line Tools：

```bash
xcode-select --install
```

如果使用 Cargo 安装 `wchisp`，需要 Rust 环境：

```bash
brew install rust libusb
cargo install wchisp --version 0.3.0
```

安装后确认：

```bash
wchisp --version
```

如果项目已经把 `wchisp` 放在本地目录，也可以不走 Cargo，全程使用：

```bash
firmware-dev/tools/wchisp/bin/wchisp
```

### 下载固件

普通用户优先从 GitHub Releases 下载官方 `.hex` 固件，不需要在 Mac 上编译源码。

## 开发工具链

| 用途 | 工具 | 来源 | 建议本地路径 | 备注 |
|---|---|---|---|---|
| C 编译 | xPack RISC-V GCC 12.2.0-3 | `github.com/xpack-dev-tools/riscv-none-elf-gcc-xpack`，版本 `v12.2.0-3` | `firmware-dev/toolchains/xpack-riscv-none-elf-gcc-12.2.0-3/` | macOS arm64 native；不要用 WCH 自带的 `riscv-none-embed-gcc` |
| BLE 库和 HAL | openwch-ch583 SDK | `github.com/openwch/ch583`，建议固定 commit `bd508ad` | `firmware-dev/sdk/openwch-ch583/` | 项目只保留 `APP` 和 `Profile`，其余从 SDK 拉取 |
| 烧录 | wchisp 0.3.0 | `github.com/ch32-rs/wchisp`，建议固定 commit `cefd870` | `firmware-dev/tools/wchisp/bin/` | 不用 WCHISPTool Studio GUI |
| 构建 | GNU Make | macOS 系统自带或开发工具提供 | `firmware-dev/scripts/firmware.mk` | 使用项目自己的 Makefile，不依赖 MounRiver |

## 烧录已有 HEX

### 1. 准备文件

准备好要烧录的 `.hex` 文件。普通用户优先使用 GitHub Releases 中发布的正式固件，不需要自己编译。

### 2. 确认 `wchisp`

在项目目录下确认 `wchisp` 可以运行：

```bash
firmware-dev/tools/wchisp/bin/wchisp --version
```

如果是自己用 Cargo 安装，也可以直接使用：

```bash
wchisp --version
```

如果 macOS 提示二进制来自互联网、无法运行，可以对下载目录解除 quarantine：

```bash
xattr -dr com.apple.quarantine firmware-dev/tools/wchisp/
```

### 3. 进入 USB ISP 模式

这个步骤顺序很关键，顺序错了通常会失败。

1. 先让板子关机。如果固件已经卡死，建议断电，必要时拆电池。
2. 先运行烧录命令，让 `wchisp` 进入等待设备的状态。
3. 按住 `KEY0` 不放。
4. 保持按住 `KEY0`，插入 USB。
5. 一直按住，直到终端里出现 `Erasing` 或已经开始烧录，再松开。

如果先插 USB 再按 `KEY0`，或者没有先让板子关机，失败概率很高。

### 4. 执行烧录

如果项目已经提供脚本，优先使用脚本：

```bash
firmware-dev/scripts/flash-firmware.sh path/to/firmware.hex
```

如果直接使用 `wchisp`，可以执行：

```bash
wchisp flash path/to/firmware.hex
```

或者使用项目本地版本：

```bash
firmware-dev/tools/wchisp/bin/wchisp flash path/to/firmware.hex
```

烧录时不要拔 USB，也不要关闭终端。

### 5. 判断是否进入 ISP

CH582 USB ISP 设备的识别号通常是：

- VID：`0x4348`
- PID：`0x55e0`

可以用项目脚本观察 USB 设备：

```bash
firmware-dev/scripts/watch-usb.sh
```

也可以在 macOS 的“系统信息”里查看 USB 设备列表，确认是否出现对应 VID/PID。

### 6. 烧录完成后

1. 拔掉 USB。
2. 退出 ISP 模式。
3. 重新上电或重新插入 USB。
4. 如果蓝牙连接异常，在 macOS 蓝牙设置里删除旧的 AhaKey 配对记录后重新配对。

## 兜底进入 Bootloader

如果 `KEY0 + USB` 始终无法进入 ISP，说明软件入口可能走不通。硬件级兜底方式是：

1. 断电。
2. 将 CH582 的 `PB22` 拉到 `GND`。在板上通常对应 `CN1` 排针的 `BOOT` 网络。
3. 保持 `PB22` 接地后重新上电。
4. 再执行烧录。

这是 CH582 ROM 自带的硬件 boot 入口，可以绕过当前固件。

## 在 Mac 上编译固件

只有需要自己改固件时才需要这一部分。只是烧录官方 HEX 的用户可以跳过。

### 1. 解除 macOS quarantine

xPack 工具链通常来自 GitHub Releases，是未签名二进制。macOS Gatekeeper 可能会拦截 `cc1`、`libisl.23.dylib` 等内部组件，表现为编译时直接 `SIGKILL`，没有明确报错。

下载工具链后执行：

```bash
xattr -dr com.apple.quarantine firmware-dev/toolchains/xpack-riscv-none-elf-gcc-12.2.0-3/
```

如果 `wchisp` 也是下载的未签名二进制，也可以对它所在目录执行同样处理：

```bash
xattr -dr com.apple.quarantine firmware-dev/tools/wchisp/
```

### 2. 使用 GCC 12 的中断写法

xPack GCC 12 不认识 WCH 私有写法 `WCH-Interrupt-fast`。如果不改，编出来的固件可能表面上烧录成功，但 BLE 跑不起来，原因是中断函数被当作普通 C 函数编译，没有正确保存 caller-saved 寄存器。

需要把 WCH 私有写法改成标准 RISC-V machine interrupt 写法。

在 `firmware-dev/sdk/openwch-ch583/EVT/EXAM/SRC/StdPeriphDriver/inc/CH58x_common.h` 中：

```c
#define __INTERRUPT __attribute__((interrupt("machine")))
```

原始写法通常类似：

```c
// #define __INTERRUPT __attribute__((interrupt("WCH-Interrupt-fast")))
```

另外，项目里的 `TMR3_IRQHandler` 也要同步使用：

```c
__attribute__((interrupt("machine")))
```

截图中的位置是：

```text
CH582m_vibe_coding_BLE_keyboard/APP/sub_main/psk_ws2812.c:294
```

### 3. ST7735 屏幕偏移补丁

如果使用 ST7735 屏幕，截图中的经验是把硬编码的 `(x+1, y+26)` 改成根据 `USE_HORIZONTAL` 切换 `IPS_X_OFFSET` / `IPS_Y_OFFSET`。

位置：

```text
CH582m_vibe_coding_BLE_keyboard/APP/hardware/ips096_st7735.c
```

这个补丁只影响屏幕坐标方向，不是烧录成功的必要条件。

### 4. 编译关键参数

`firmware-dev/scripts/firmware.mk` 中建议使用：

```make
-march=rv32imac_zicsr_zifencei
-mabi=ilp32
-mcmodel=medany
-Os
-ffunction-sections
-fdata-sections
-Wl,--gc-sections
-T Link.ld
--specs=nano.specs
--specs=nosys.specs
```

宏定义建议：

```make
-DDEBUG=3
-DBLE_BUFF_MAX_LEN=80
-DCENTRAL_MAX_CONNECTION=0
```

BLE 配置使用 SDK 自带的：

```text
BLE/HAL/include/config.h
```

### 5. 编译

项目如果已经提供脚本，优先使用：

```bash
firmware-dev/scripts/build-firmware.sh
```

编译成功后，再使用“烧录已有 HEX”的流程烧录生成的 `.hex`。

## 常见失败原因

### 烧录显示成功，但固件启动后 BLE 跑不起来

最常见原因是没有应用 `WCH-Interrupt-fast` 到 `interrupt("machine")` 的补丁。这个问题看起来像“刷机失败”，但实际是固件已经写进去了，只是运行时中断上下文损坏。

优先检查：

1. 是否使用 MounRiver Studio 或系统默认工具链编译。
2. 是否使用了 xPack GCC 12.2.0-3。
3. 是否已经修改 `CH58x_common.h` 和 `TMR3_IRQHandler`。

### macOS 编译时 `cc1` 被系统杀掉

通常是没有执行：

```bash
xattr -dr com.apple.quarantine firmware-dev/toolchains/xpack-riscv-none-elf-gcc-12.2.0-3/
```

执行后重新编译。

### `wchisp` 一直等不到设备

按这个顺序重试：

1. 关机或彻底断电。
2. 先运行烧录命令，让 `wchisp` 等待设备。
3. 按住 `KEY0`。
4. 插 USB。
5. 等到出现 `Erasing` 后再松开。

仍然不行就用 `PB22` 拉 `GND` 的硬件 boot 方式。

### WCHISPTool GUI 在 Mac 上不好用

不要优先排查 GUI。这个流程验证的是 `wchisp CLI`，不是 WCHISPTool Studio GUI。Mac 上 GUI 可能因为驱动或架构问题识别不到设备。

### xPack GCC 版本不对

建议固定 `12.2.0-3`。更老版本可能不支持需要的写法；更新版本可能对 `-march` 或中断属性行为有变化，复现成本更高。

## 推荐排查顺序

1. 先确认是否能识别到 USB ISP：VID `0x4348` / PID `0x55e0`。
2. 再确认 `wchisp` 是否开始 `Erasing`。
3. 如果能烧录但固件不运行，优先查中断属性补丁。
4. 如果 Mac 上编译直接异常退出，优先查 `xattr -dr com.apple.quarantine`。
5. 如果始终进不了 ISP，用 `PB22` 拉 `GND` 的硬件 boot 入口。
