# 在默认浏览器中打开网址 (OpenUrl)

使用操作系统默认网页浏览器打开指定的网址 URL 链接。

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