# 退出 (Exit)

- **支持平台**：`Cross-Platform` (Windows / Linux / macOS)
- **需要管理员权限**：`否` (`requires_admin: false`)

## 功能描述
直接终止当前自动化工作流程的执行。

## 运行参数

本动作无配置参数，执行时将立即终止流程引擎的后续动作执行。

## 输出

* 类型: `None`
* 描述: 流程结束。

## 使用示例

```json
{
  "tag": "Exit"
}
```
