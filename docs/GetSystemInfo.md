# 获取系统与硬件信息 (GetSystemInfo)

- **支持平台**：`Cross-Platform` (Windows / Linux / macOS)
- **需要管理员权限**：`否` (`requires_admin: false`)

## 功能描述
获取计算机 CPU 核心数、物理内存容量、可用空间、主机名及操作系统架构等硬件/系统指标。

## 参数说明

| 参数名称 | 类型 | 必填 | 默认值 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| `category` | String | 否 | `"all"` | 查询分类（`all`, `cpu`, `memory`, `os`） |

## 返回值
返回包含硬件指标的 JSON 对象：
`{"os": "windows", "arch": "x86_64", "hostname": "PC-01", "cpu_cores": 8, "memory": {"total_mb": 16384, "available_mb": 8192}}`

## JSON 配置示例
```json
{
  "tag": "GetSystemInfo",
  "data": {
    "category": "all"
  }
}
```
