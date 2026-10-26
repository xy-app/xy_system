# 执行命令并获取输出 (ExecuteCommand)

- **支持平台**：`Cross-Platform` (Windows / Linux / macOS)
- **需要管理员权限**：`否` (`requires_admin: false`)

## 功能描述
同步运行 CMD / PowerShell / Shell 命令行脚本，捕获控制台标准输出（`stdout`）、错误输出（`stderr`）以及进程退出代码（`exit_code`）。

## 参数说明

| 参数名称 | 类型 | 必填 | 默认值 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| `command` | String | 是 | `""` | 待执行的命令行或脚本内容 |
| `shell` | String | 否 | `"auto"` | 解释器选择（`auto`, `cmd`, `powershell`, `bash`, `sh`） |
| `working_directory` | FolderPicker | 否 | `""` | 执行命令的工作路径 |
| `timeout` | Number | 否 | `30` | 允许运行的最长超时秒数 |
| `env` | String | 否 | `""` | 环境变量配置（`KEY=VALUE`） |

## 返回值
返回包含控制台输出的 JSON 对象：
`{"output": "...", "stdout": "...", "stderr": "...", "exit_code": 0, "success": true}`

## JSON 配置示例
```json
{
  "tag": "ExecuteCommand",
  "data": {
    "command": "ipconfig /all",
    "shell": "cmd",
    "timeout": 30
  }
}
```
