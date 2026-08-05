# AhaKey X1 固件发布规范

本规范用于说明 AhaKey X1 官方 HEX 固件在仓库目录和 GitHub Releases 中如何发布、对应和维护。

## 版本口径

| 版本 | 口径 | 默认推荐 |
|---|---|---|
| v1.1.0 | 目前出厂会烧录的固件 / 当前推荐版本 | 是 |
| v1.0.0 | 之前的老版本 | 否 |

不要再把 `v1.0.0` 叫做 `factory`、恢复出厂或出厂固件。

## GitHub Releases 和仓库目录的关系

1. 仓库内目录：

   ```text
   AhaKey-X1/releases/v1.1.0/
   ```

   用于长期保存该版本的 HEX、README、SHA256SUMS.txt。

2. GitHub Releases：

   [https://github.com/AhakeyAI/firmware/releases](https://github.com/AhakeyAI/firmware/releases)

   用于对外展示版本更新、提供下载入口和发布说明。

3. 每个正式版本应该尽量两边都有：

   - 仓库目录里有对应文件。
   - GitHub Releases 里有对应 tag / release。
   - 仓库目录 README 链接到 GitHub Release。
   - GitHub Release 描述里链接回仓库目录。

## 推荐 tag 命名

```text
AhaKey-X1-v1.0.0
AhaKey-X1-v1.1.0
```

如果当前还没有这些 GitHub Release，不要创建无效的具体 tag 链接。可以先链接到 Releases 总页：

[https://github.com/AhakeyAI/firmware/releases](https://github.com/AhakeyAI/firmware/releases)

## 每个版本目录应包含什么

每个正式版本目录应包含：

```text
README.md
AhaKey-X1-firmware-vX.Y.Z.hex
SHA256SUMS.txt
```

其中：

- `README.md` 说明该版本定位、适合谁使用、下载入口和校验方式。
- `.hex` 是官方可烧录固件文件。
- `SHA256SUMS.txt` 记录该目录中 HEX 文件的 SHA256 校验值。

## 发布步骤

1. 新建或更新 `AhaKey-X1/releases/vX.Y.Z/` 目录。
2. 放入对应的官方 HEX 文件。
3. 生成或更新 `SHA256SUMS.txt`。
4. 更新该版本目录的 `README.md`。
5. 更新根目录 `README.md` 和 `AhaKey-X1/README.md`。
6. 创建 GitHub Release，并使用推荐 tag 命名。
7. 在 GitHub Release 描述中链接回仓库内版本目录。
8. 在仓库内版本 README 中链接到 GitHub Releases 总页或具体 release。

## 不应放入本仓库的内容

- SDK 源码
- 固件源码
- `.o`、`.elf`、构建缓存等中间产物
- PCB、BOM、Gerber
- 生产测试资料
- 供应链资料
- 未经确认的第三方 HEX
