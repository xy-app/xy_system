# 读取内存 (ReadMemory)

读取目标软件进程或模块内存地址中的数据，支持多种数据类型与多级偏移链解析。

## 运行参数

* **目标进程 (`app`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 目标进程名称、PID 或标识。
* **驱动模式 (`backend`)**
  * 类型: `string`
  * 默认值: `"auto"`
  * 描述: 内存访问驱动模式。支持 `"auto"`（推荐自动模式）。
* **内存地址 (`address`)**
  * 类型: `string`
  * 默认值: `"0x0"`
  * 描述: 十六进制内存地址或基址（例如 `0x7FF710000000`）。
* **数据类型 (`data_type`)**
  * 类型: `string`
  * 默认值: `"i32"`
  * 描述: 读取解析的数据格式。可选值：`i32`, `i64`, `u32`, `u64`, `f32`, `f64`, `string_utf8`, `string_utf16`, `bytes`, `hex`。
* **读取长度 (`size`)**
  * 类型: `string`
  * 默认值: `"4"`
  * 描述: 读取字节数（适用于 bytes/hex/string）。
* **指针偏移 (`offsets`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 多级指针偏移链（例如 `0x10,0x28`，留空为直接寻址）。
* **通道连接配置 (`memflow_connector`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 外部直连或通道配置（高级可选参数，普通场景保留为空即可）。

## 输出

* 类型: `Mixed`
* 描述: 解析后得到的数值、字符串或十六进制字节数据。

## 使用示例

```json
{
  "tag": "ReadMemory",
  "app": "game.exe",
  "backend": "auto",
  "address": "0x7FF700100000",
  "data_type": "i32",
  "size": "4",
  "offsets": "0x48,0x10",
  "memflow_connector": ""
}
```