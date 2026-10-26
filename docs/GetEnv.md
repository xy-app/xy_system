# 获取环境变量 (GetEnv)

- **支持平台**：`Cross-Platform` (Windows / Linux / macOS)
- **需要管理员权限**：`否` (`requires_admin: false`)

## 功能描述
读取当前进程、用户级或系统级的环境变量数值。

## 参数说明

| 参数名称 | 类型 | 必填 | 默认值 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| `name` | String | 是 | `""` | 环境变量键名（如 `PATH`, `TEMP`, `JAVA_HOME`） |
| `scope` | String | 否 | `"process"` | 作用域（`process`, `user`, `system`） |

## 返回值
返回环境变量对应值的字符串。

## JSON 配置示例
```json
{
  "tag": "GetEnv",
  "data": {
    "name": "PATH",
    "scope": "process"
  }
}
```
