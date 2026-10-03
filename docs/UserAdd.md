# 添加系统本地用户 (UserAdd)

在当前操作系统中创建新的本地电脑用户账户。

## 运行参数

* **用户名/账号 (`account`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 新创建的系统本地用户账户名称。
* **初始密码 (`password`)**
  * 类型: `Password`
  * 默认值: `""`
  * 描述: 用户账户初始密码。
* **主目录路径 (`home_dir`)**
  * 类型: `FolderPicker`
  * 默认值: `""`
  * 描述: 用户的主目录存储路径（留空表示使用系统默认用户目录）。

## 输出

* 类型: `bool`
* 描述: 是否成功创建系统本地用户。

## 使用示例

```json
{
  "tag": "UserAdd",
  "account": "operator",
  "password": "SecurePassword123!",
  "home_dir": ""
}
```