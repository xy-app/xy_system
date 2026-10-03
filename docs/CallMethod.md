# 调用方法 (CallMethod)

调用目标进程加载模块中的指定导出函数并获取执行结果。

## 运行参数

* **模块/会话对象 (`object`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 目标模块名称或会话标识。
* **方法名称 (`method`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 待调用的导出函数名称。
* **返回值类型 (`return_type`)**
  * 类型: `string`
  * 默认值: `"void"`
  * 描述: 函数返回值的数据解析类型。可选值：`int`, `uint`, `string`, `pointer`, `bool`, `void`, `float`。
* **调用约定 (`abi`)**
  * 类型: `string`
  * 默认值: `"default"`
  * 描述: 底层函数调用约定。可选值：`default`, `stdcall`, `fastcall`, `thiscall`。

## 输出

* 类型: `Mixed`
* 描述: 目标函数执行返回的结果值。

## 使用示例

```json
{
  "tag": "CallMethod",
  "object": "helper.dll",
  "method": "GetStatus",
  "return_type": "int",
  "abi": "stdcall"
}
```