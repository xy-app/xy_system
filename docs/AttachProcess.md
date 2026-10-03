# 附加进程 (AttachProcess)

连接并附加到目标软件进程，支持动态加载扩展模块与执行初始化逻辑。

## 运行参数

* **目标进程 (`app`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 目标进程名称、PID 或可执行文件完整路径。
* **模块动态库 (`dy`)**
  * 类型: `FilePicker`
  * 默认值: `""`
  * 描述: 待注入或加载的动态链接库文件完整路径。
* **入口函数 (`entrypoint`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 动态库导出入口执行函数名称。
* **初始化数据 (`data`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 传递给入口函数的初始化配置或载荷字符串。
* **命令行参数 (`command_line`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 可选的附加启动参数。

## 输出

* 类型: `None`
* 描述: 操作执行完成，若失败则抛出相应错误提示。

## 使用示例

```json
{
  "tag": "AttachProcess",
  "app": "target_app.exe",
  "dy": "C:/plugins/helper.dll",
  "entrypoint": "InitializePlugin",
  "data": "config_payload"
}
```