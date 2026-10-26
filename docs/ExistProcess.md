# 检测进程 (ExistProcess)

- **支持平台**：`Cross-Platform` (Windows / Linux / macOS)
- **需要管理员权限**：`否` (`requires_admin: false`)

## 功能描述
检查指定的应用程序或进程当前是否正在操作系统后台运行。

## 运行参数

* **目标进程 (`app`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 进程名称、完整路径或通配符表达式（例如 `notepad.exe`、`*chrome*`）。

## 输出

* 类型: `bool`
* 描述: `true` 表示目标进程当前正在运行，`false` 表示未检测到该进程。

## 使用示例

```json
{
  "tag": "ExistProcess",
  "app": "notepad.exe"
}
```
