# 打开文件/文档 (LaunchFile)

- **支持平台**：`Cross-Platform` (Windows / Linux / macOS)
- **需要管理员权限**：`否` (`requires_admin: false`)

## 功能描述
使用操作系统默认关联程序打开指定的文档、表格、图片或脚本文件。

> **注意**：本动作仅用于打开本地文件系统路径，严格禁止传入 `http://` 或 `https://` 网页网址。若需在默认浏览器中打开网络链接，请使用 `OpenUrl` 动作。

## 运行参数

* **文件路径 (`file`)**
  * 类型: `FilePicker`
  * 默认值: `""`
  * 描述: 目标文件的完整文件系统绝对路径。

## 输出

* 类型: `bool`
* 描述: 是否成功唤起系统默认程序打开文件。

## 使用示例

```json
{
  "tag": "LaunchFile",
  "file": "D:/report.xlsx"
}
```
