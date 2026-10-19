# 收费单据生成器 Android 项目

## 第一步：放入你的 HTML
把你发来的完整 HTML 页面复制到 `app/src/main/assets/index.html`，覆盖示例提示页。

## 第二步：上传 GitHub
把解压后的项目文件上传到 GitHub 仓库根目录。仓库默认分支建议使用 `main`。

## 第三步：自动编译
打开仓库的 Actions 页面，选择 `Build Android APK`，点击 `Run workflow`。成功后打开运行记录，在 Artifacts 区域下载 `shoufei-danju-debug-apk`，解压即可得到 `app-debug.apk`。

## 已配置
- Android WebView 加载本地 HTML。
- 启用 JavaScript 和 DOM Storage，供页面脚本与 localStorage 使用。
- 原生打印接口：`AndroidApp.printPage()`。
- 原生文件保存接口：`AndroidApp.saveFile(fileName, mimeType, base64Data)`。

## 重要说明
`index.html` 目前是占位示例，必须替换成你发来的完整 HTML 才是你的应用。
WebView 中 `window.print()` 和通过 Blob 生成下载文件的方式可能无法像浏览器那样正常工作。若要让“打印”和 CSV/JSON 导出按钮在 APK 内稳定工作，需要把 HTML 中这几个按钮改为调用上面的 AndroidApp 接口。其他单据生成、商品计算、localStorage 历史记录功能可以继续使用。

APK 输出路径：`app/build/outputs/apk/debug/app-debug.apk`
