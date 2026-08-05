# AhaKey X1 固件发布规范

本规范用于说明 AhaKey X1 官方固件的发布、下载和维护方式。

## 发布原则

- 每个正式固件版本都应该创建一个 GitHub Release。
- GitHub Releases 是官方 HEX 下载入口。
- 仓库内 README 和文档只负责说明版本口径、烧录方法和维护规则。
- 仓库内不再重复保存 HEX 文件。
- 不要把用户自定义 HEX 描述为官方固件。

## 当前版本口径

- `v1.0.0`：之前的老版本。
- `v1.1.0`：目前出厂会烧录的固件 / 当前推荐版本。

## GitHub Release tag 命名

推荐 tag：

- `AhaKey-X1-v1.0.0`
- `AhaKey-X1-v1.1.0`

## 每个 GitHub Release 应包含

- Release title
- Release notes
- `.hex` 文件
- SHA256 校验信息
- 烧录教程链接
- 版本口径说明

## 不要提交到仓库

- `.hex`
- `.o`
- `.elf`
- `.map`
- 构建缓存
- 固件源码
- SDK 源码
- PCB
- Gerber
- BOM
- 生产测试资料
- 供应链资料

## 下载入口

- [AhaKey X1 Firmware v1.1.0](https://github.com/AhakeyAI/firmware/releases/tag/AhaKey-X1-v1.1.0)
- [AhaKey X1 Firmware v1.0.0](https://github.com/AhakeyAI/firmware/releases#release-AhaKey-X1-v1.0.0)
