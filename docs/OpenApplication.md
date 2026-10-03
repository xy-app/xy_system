# 打开应用 (OpenApplication)

启动指定的系统应用程序并可传入命令行参数与工作目录（非阻塞运行模式）。

## 运行参数

* **程序路径/名称 (`app`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 目标程序的可执行文件路径或名称（例如 `notepad.exe`、`calc.exe`）。
* **启动参数 (`command_line`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 启动时传递给应用程序的附加命令行参数。
* **工作目录 (`working_directory`)**
  * 类型: `FolderPicker`
  * 默认值: `""`
  * 描述: 应用程序启动运行所在的工作目录完整路径。
* **环境变量 (`env`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 启动时附带的环境变量配置（格式：`KEY=VALUE`）。

## 输出

* 类型: `None`
* 描述: 应用程序成功启动。

## 使用示例

```json
{
  "tag": "OpenApplication",
  "app": "notepad.exe",
  "command_line": "D:/notes.txt",
  "working_directory": "D:/",
  "env": ""
}
```