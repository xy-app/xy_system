# 本地用户管理 (ManageLocalUser)

- **支持平台**：`Cross-Platform` (Windows / Linux / macOS)
- **需要管理员权限**：部分操作需要（添加与删除用户需管理员权限，存在性检测通常无需管理员权限）

## 功能描述
统一管理操作系统本地电脑用户账户，支持账户存在性检测（`exists`）、新建本地用户（`add`）以及删除用户（`delete`）。

## 运行参数

* **操作类型 (`action`)**
  * 类型: `string`
  * 默认值: `"exists"`
  * 可选值: `"exists"` (检测存在), `"add"` (创建用户), `"delete"` (删除用户)
  * 描述: 要执行的本地账户管理动作。
* **账户名称 (`account`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 目标操作系统本地用户账户名称。
* **账户密码 (`password`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 新建账户时的密码（`add` 操作使用）。
* **家目录路径 (`home_dir`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 新建账户的主目录路径（`add` 操作使用，留空采用系统默认路径）。
* **同时删除家目录 (`delete_home_dir`)**
  * 类型: `boolean`
  * 默认值: `false`
  * 描述: 删除账户时是否同时物理清理其主文件夹（`delete` 操作使用）。

## 输出

* 检测存在 (`exists`): 返回布尔值 (`true` / `false`) 表示目标用户是否存在。
* 新建/删除用户 (`add`/`delete`): 返回执行结果提示信息。

## 使用示例

```json
{
  "tag": "ManageLocalUser",
  "action": "exists",
  "account": "guest_worker"
}
```
