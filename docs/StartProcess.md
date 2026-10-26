# 启动应用/进程 (StartProcess)

- **支持平台**：`Cross-Platform` (Windows / Linux / macOS)
- **需要管理员权限**：`否` (`requires_admin: false`)

## 功能描述
在后台创建并启动指定的操作系统应用程序、独立进程或命令行任务。

## 运行参数

* **程序路径/命令 (`app`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 目标可执行文件路径、程序名称或系统命令。
* **命令行参数 (`command_line`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 启动时传递给进程的命令行参数。
* **隐藏窗口 (`no_window`)**
  * 类型: `string`
  * 默认值: `"false"`
  * 描述: 是否在无窗口后台模式下静默启动。可选值：`"false"`, `"true"`。
* **工作目录 (`working_directory`)**
  * 类型: `FolderPicker`
  * 默认值: `""`
  * 描述: 进程的工作目录完整路径。
* **环境变量 (`env`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 附加环境变量配置（格式：`KEY=VALUE`）。

## 输出

* 类型: `None`
* 描述: 进程成功启动。

## 使用示例

```json
{
  "tag": "StartProcess",
  "app": "cmd.exe",
  "command_line": "/c echo Task complete",
  "no_window": "true",
  "working_directory": "C:/",
  "env": ""
}
```
