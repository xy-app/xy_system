# 设置环境变量 (SetEnv)

- **支持平台**：`Cross-Platform` (Windows / Linux / macOS)
- **需要管理员权限**：`否` (`requires_admin: false`；注：修改系统级 scope 需要管理员权限)

## 功能描述
设置当前进程、用户级或系统级的环境变量数值。

## 参数说明

| 参数名称 | 类型 | 必填 | 默认值 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| `name` | String | 是 | `""` | 环境变量键名 |
| `value` | String | 是 | `""` | 准备设置的变量数值 |
| `scope` | String | 否 | `"process"` | 作用域（`process`, `user`, `system`） |

## JSON 配置示例
```json
{
  "tag": "SetEnv",
  "data": {
    "name": "MY_APP_VAR",
    "value": "12345",
    "scope": "process"
  }
}
```
