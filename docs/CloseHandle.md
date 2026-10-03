# 关闭系统句柄 (CloseHandle)

释放已打开的系统资源句柄，保证系统资源的正常回收与稳定运行。

## 运行参数

* **句柄类型 (`type`)**
  * 类型: `string`
  * 默认值: `"Process"`
  * 描述: 系统句柄资源类型。可选值：`Process`, `Thread`, `File`, `Event`, `Mutex`, `Semaphore`, `Key`, `All`。
* **句柄名称或关键字 (`name`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 待释放句柄的名称、标识或过滤匹配关键字。
* **关联进程文件 (`exe_file`)**
  * 类型: `FilePicker`
  * 默认值: `""`
  * 描述: 关联的可执行程序文件（可选），用于过滤特定程序占用的句柄。

## 输出

* 类型: `bool`
* 描述: 是否成功关闭并释放目标句柄资源。

## 使用示例

```json
{
  "tag": "CloseHandle",
  "type": "File",
  "name": "data.lock",
  "exe_file": ""
}
```