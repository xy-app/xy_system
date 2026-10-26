# 终止进程 (KillProcess)

- **支持平台**：`Cross-Platform` (Windows / Linux / macOS)
- **需要管理员权限**：`否` (`requires_admin: false`)

## 功能描述
根据进程名称、完整路径或通配符表达式结束指定的系统进程。

## 运行参数

* **目标进程 (`app`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 待结束的目标进程名称、路径或通配符表达式（例如 `calc.exe`）。

## 输出

* 类型: `bool`
* 描述: 是否成功结束目标进程。

## 使用示例

```json
{
  "tag": "KillProcess",
  "app": "calc.exe"
}
```
