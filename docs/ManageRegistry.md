# 注册表管理 (ManageRegistry)

- **支持平台**：`Windows`
- **需要管理员权限**：部分操作需要（写入系统关键路径或删除系统项需管理员权限，读取通常无需管理员权限）

## 功能描述
统一管理 Windows 操作系统注册表，支持键值读取（`read`）、数据写入（`write`）、项/值删除（`delete`）以及键值存在性检测（`exists`）。

## 运行参数

* **操作类型 (`action`)**
  * 类型: `string`
  * 默认值: `"read"`
  * 可选值: `"read"` (读取), `"write"` (写入), `"delete"` (删除), `"exists"` (检测存在)
  * 描述: 要执行的注册表管理动作。
* **根键 (`hive`)**
  * 类型: `string`
  * 默认值: `"HKEY_CURRENT_USER"`
  * 可选值: `"HKEY_CURRENT_USER"`, `"HKEY_LOCAL_MACHINE"`, `"HKEY_CLASSES_ROOT"`, `"HKEY_USERS"`, `"HKEY_CURRENT_CONFIG"`
  * 描述: 注册表根配置项。
* **项路径 (`key_path`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 注册表项路径（如 `"Software\\MyApp"`）。
* **值名称 (`value_name`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 键值名称，留空表示操作默认值或整个键项。
* **值类型 (`value_type`)**
  * 类型: `string`
  * 默认值: `"REG_SZ"`
  * 可选值: `"REG_SZ"`, `"REG_DWORD"`, `"REG_BINARY"`, `"REG_EXPAND_SZ"`, `"REG_MULTI_SZ"`, `"REG_QWORD"`
  * 描述: 写入操作时的数据类型。
* **写入数据 (`data`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 写入操作的具体内容。

## 输出

* 读取操作 (`read`): 返回读取到的注册表键值内容。
* 检测存在 (`exists`): 返回布尔值 (`true` / `false`) 表示目标是否存在。
* 写入/删除操作 (`write`/`delete`): 执行成功后继续下一动作。

## 使用示例

```json
{
  "tag": "ManageRegistry",
  "action": "read",
  "hive": "HKEY_CURRENT_USER",
  "key_path": "Software\\Microsoft\\Windows\\CurrentVersion",
  "value_name": "ProgramFilesDir"
}
```
