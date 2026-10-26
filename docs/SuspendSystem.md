# 系统电源与待机控制 (SuspendSystem)

- **支持平台**：`Cross-Platform` (Windows / Linux / macOS)
- **需要管理员权限**：`否` (`requires_admin: false`)

## 功能描述
控制计算机进入睡眠、休眠、锁屏、重启或关机状态。

## 运行参数

* **电源操作模式 (`option`)**
  * 类型: `string`
  * 默认值: `"Sleep"`
  * 描述: 目标电源控制操作。可选值：
    * `Sleep`: 进入睡眠待机状态
    * `Hibernate`: 进入深度休眠状态
    * `Lock`: 锁定当前用户屏幕
    * `Restart`: 重新启动操作系统
    * `Shutdown`: 正常关闭操作系统计算机

## 输出

* 类型: `bool`
* 描述: 是否成功发起系统电源控制请求。

## 使用示例

```json
{
  "tag": "SuspendSystem",
  "option": "Lock"
}
```
