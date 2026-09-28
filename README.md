# Pisper 自定义组件

这是独立于 Pisper 安装包的可选自定义 UI 组件仓库。用户手动下载所需组件，把完整目录放入 Pisper 显示的 `custom-ui` 根目录，再到「设置 → 界面设置 → 独立组件」点击「重新扫描」。Pisper 不会自动访问或下载本仓库。

## 组件

| 组件 | 用途 | 权限 |
| --- | --- | --- |
| `pisper-game-asset-workbench` | 上传参考图、生成与手工调整动画帧、导出图集 | `game-assets.read`、`game-assets.write`、`game-assets.run` |

组件源文件位于 `components/<id>/`。下载时应保留目录结构：例如将 `components/pisper-game-asset-workbench` 整个文件夹放进 `custom-ui`，使 `custom-ui/pisper-game-asset-workbench/manifest.json` 与 `index.html` 位于同一目录层级。不要只复制 HTML；工作台还需要 `frame-editor.js`。

游戏素材工作台由 Pisper 原内置组件迁出，使用 Pisper 提供的受限 `gameAssets` 桥；需要支持这些能力的 Pisper 版本。底层图像处理能力仍由 Pisper Runtime 提供。

## 贡献

新增组件需使用安全的目录 ID（小写字母、数字、`.`、`_`、`-`），将静态资源放在该目录中，并在 `manifest.json` 中只声明实际需要的桥接权限。组件不应依赖远程脚本、绝对资源路径或安装脚本。
