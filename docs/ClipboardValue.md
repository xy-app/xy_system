# 读取/设置剪贴板内容 (ClipboardValue)

- **支持平台**：`Cross-Platform` (Windows / Linux / macOS)
- **需要管理员权限**：`否` (`requires_admin: false`)

## 功能描述
读取系统剪贴板中的文字内容，或将新文字写入系统剪贴板。

## 运行参数

* **写入内容 (留空则获取) (`value`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 待写入系统剪贴板的文本内容。如果保留为空，则表示从系统剪贴板中读取文本。

## 输出

* 类型: `string`
* 描述: 读取模式下返回当前系统剪贴板中的文本；写入模式下返回写入的内容。

## 使用示例

### 读取剪贴板
```json
{
  "tag": "ClipboardValue",
  "value": ""
}
```

### 写入剪贴板
```json
{
  "tag": "ClipboardValue",
  "value": "Hello, World!"
}
```
