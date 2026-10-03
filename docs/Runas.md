# 以管理员身份提权运行 (Runas)

使用管理员权限（UAC提权）启动指定程序或执行特权命令。

## 运行参数

* **程序路径/命令 (`app`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 可执行程序路径或系统命令（例如 `cmd.exe`、`powershell.exe`）。
* **指定账户 (`account`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 指定运行的用户账户名称（留空表示使用当前管理员提权执行）。
* **账户密码 (`password`)**
  * 类型: `Password`
  * 默认值: `""`
  * 描述: 用户账户密码（若指定特定账户时填写）。
* **工作目录 (`working_directory`)**
  * 类型: `FolderPicker`
  * 默认值: `""`
  * 描述: 程序运行的工作目录路径。
* **命令行参数 (`command_line`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 附加命令行运行参数。
* **环境变量 (`env`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 附加环境变量配置。

## 输出

* 类型: `None`
* 描述: 提权程序成功唤起运行。

## 使用示例

```json
{
  "tag": "Runas",
  "app": "powershell.exe",
  "account": "",
  "password": "",
  "working_directory": "C:/",
  "command_line": "-NoExit -Command Get-Service",
  "env": ""
}
```