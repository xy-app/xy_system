# 在默认浏览器中打开网址 (OpenUrl)

- **支持平台**：`Cross-Platform` (Windows / Linux / macOS)
- **需要管理员权限**：`否` (`requires_admin: false`)

## 功能描述
使用操作系统默认网页浏览器打开指定的网址 URL 链接。

> **注意**：本动作仅用于在浏览器中打开网络链接（以 `http://` 或 `https://` 开头），严禁传入本地磁盘路径（如 `C:\...`）。若需打开本地文件，请使用 `LaunchFile` 动作。

## 运行参数

* **目标网址 (`url`)**
  * 类型: `string`
  * 默认值: `"https://"`
  * 描述: 待访问的 HTTP 或 HTTPS 网页完整链接地址。

## 输出

* 类型: `bool`
* 描述: 是否成功调用默认浏览器打开链接。

## 使用示例

```json
{
  "tag": "OpenUrl",
  "url": "https://www.google.com"
}
```
