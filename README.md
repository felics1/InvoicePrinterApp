# 电子发票拼版打印工具

一个简单的 Windows 发票排版与打印工具。可一次选择多张 PDF 或图片发票，自动在 A4 页面中按每页 2、3 或 4 张排列，预览确认后调用系统打印。

## 功能

- 支持多选 PDF、JPG、JPEG、PNG 文件
- 每页 2 张、3 张或 4 张发票的 A4 拼版
- 单张发票向右旋转 90°
- 从当前排版中删除单张发票
- 可开关裁剪辅助线
- 记忆上次选择的布局和辅助线设置
- 使用 Windows 系统打印对话框选择打印机和份数

## 下载和使用

1. 在仓库的 [Releases](https://github.com/felics1/InvoicePrinterApp/releases) 页面下载 `InvoicePrinterApp-v1.0.0-win-x64.zip`。
2. 解压全部文件，不要只单独拖出 EXE。
3. 双击 `InvoicePrinterApp.exe`。
4. 选择或拖入发票文件，调整每页张数、旋转方向和辅助线。
5. 点击“立即打印”，在 Windows 打印窗口中选择打印机。

程序需要 Windows 10/11 和 Microsoft Edge WebView2 Runtime。多数 Windows 10/11 电脑已经安装 WebView2 Runtime。

## 隐私说明

发票文件由本机页面读取并用于本地预览、打印，当前页面代码没有上传发票的接口。不过，PDF 预览库 `pdf.js` 当前从 cdnjs 加载，所以首次使用 PDF 功能时需要联网访问该 CDN。涉及敏感票据信息时，请根据自己的网络与合规要求使用。

程序运行后会自动创建 `InvoicePrinterApp.exe.WebView2` 用户数据目录，其中可能包含缓存、浏览记录和本地设置。该目录不属于程序发布包，也不应上传或分享。

## 源码说明

当前保留下来的可编辑页面源码位于 [`wwwroot/index.html`](./wwwroot/index.html)，包含界面、发票预览、拼版和打印样式。

原目录中没有 C# 项目文件或 C# 源码，因此本仓库不宣称包含完整桌面外壳源码。Windows 可执行文件通过 Release 单独提供。

## 构建与安全状态

- 应用版本：`1.0.0`
- 平台：Windows x64
- 发布形式：便携版 ZIP
- 数字签名：未签名，Windows 可能显示“未知发布者”提示
- 发票打印前请先核对预览、纸张方向、缩放比例和实际打印机设置

## 许可证

仓库中自行编写的页面源码和文档采用 [MIT License](./LICENSE)。可执行文件中包含的 .NET、WebView2 及其他第三方组件仍受各自许可条款约束，详见 [`THIRD_PARTY_NOTICES.md`](./THIRD_PARTY_NOTICES.md)。
