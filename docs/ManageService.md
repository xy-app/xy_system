# 服务管理 (ManageService)

- **支持平台**：`Windows`
- **需要管理员权限**：部分操作需要（启动、停止、重启服务需管理员权限，查询状态无需管理员权限）

## 功能描述
统一管理 Windows 系统后台服务，支持运行状态查询（`status`）、启动服务（`start`）、停止服务（`stop`）以及平滑重启服务（`restart`）。

## 运行参数

* **操作类型 (`action`)**
  * 类型: `string`
  * 默认值: `"status"`
  * 可选值: `"status"` (查询状态), `"start"` (启动), `"stop"` (停止), `"restart"` (重启)
  * 描述: 要执行的服务管理动作。
* **服务名称 (`service_name`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: Windows 系统服务名称标识（如 `"Spooler"`, `"wuauserv"`）。
* **超时时间 (`wait_timeout`)**
  * 类型: `number`
  * 默认值: `30`
  * 描述: 启动、停止或重启操作的最大等待秒数。

## 输出

* 查询状态 (`status`): 返回服务当前运行状态字符串（如 `"Running"`, `"Stopped"`）。
* 控制指令 (`start`/`stop`/`restart`): 执行成功后返回状态结果。

## 使用示例

```json
{
  "tag": "ManageService",
  "action": "status",
  "service_name": "Spooler"
}
```
