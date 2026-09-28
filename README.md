# Pisper 自定义组件

这是独立于 Pisper 安装包的可选自定义 UI 组件仓库。下载所需组件后，在 Pisper 的「设置 → 界面设置 → 独立组件」点击「导入文件夹」选择完整组件目录，或点击「导入 ZIP」选择包含组件目录的压缩包。导入后可以立即从组件详情打开；重启 Pisper 或重新加载界面后也会出现在「更多工具」。Pisper 不会自动访问或下载本仓库。

## 组件

| 组件 | 用途 | 权限 |
| --- | --- | --- |
| `pisper-game-asset-workbench` | 上传参考图、生成与手工调整动画帧、导出图集 | `game-assets.read`、`game-assets.write`、`game-assets.run` |

组件源文件位于 `components/<id>/`。导入时应保留目录结构：例如选择整个 `components/pisper-game-asset-workbench` 文件夹。不要只导入 HTML；工作台还需要 `manifest.json` 与 `frame-editor.js`。也可自行把完整文件夹放到设置页显示的 `custom-ui` 根目录，然后点击「重新扫描」。

游戏素材工作台由 Pisper 原内置组件迁出，使用 Pisper 提供的受限 `gameAssets` 桥；需要支持这些能力的 Pisper 版本。底层图像处理能力仍由 Pisper Runtime 提供。

## 贡献

新增组件需使用安全的目录 ID（小写字母、数字、`.`、`_`、`-`），将静态资源放在该目录中，并在 `manifest.json` 中只声明实际需要的桥接权限。组件不应依赖远程脚本、绝对资源路径或安装脚本。
