# Jellyfin Plugin Repository

自动同步第三方 Jellyfin 插件的仓库 manifest，通过 GitHub Actions 每日检查上游更新。

## 包含的插件

| 插件 | 上游仓库 | 说明 |
|------|---------|------|
| StrmTool | [jinlin-teck/StrmTool](https://github.com/jinlin-teck/StrmTool/tree/jellyfin) | 从 strm 文件中提取媒体信息，加速起播速度 |

## 使用方法

在 Jellyfin 中添加此插件仓库：

1. 进入 **控制台 → 插件 → 存储库**
2. 点击 **+** 添加
3. 名称填 `NaUuuu Plugins`（随意）
4. URL 填：
   ```
   https://raw.githubusercontent.com/NaUuuu/jellyfin-plugin-repo/main/manifest.json
   ```
5. 保存

之后在 **插件 → 目录** 中即可看到并安装/更新插件。

## 自动更新

GitHub Actions 每天 UTC 04:00（北京/台湾时间 12:00）自动检查上游新版本。如需手动触发，可在 Actions 页面运行 `Update StrmTool Manifest` workflow。
