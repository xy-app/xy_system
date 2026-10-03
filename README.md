# ⚙️ 系统与软件进程管理套件 (System & Process Management Suite)

[![Plugin Version](https://img.shields.io/badge/version-0.50.5-blue.svg)](manifest.json)
[![Group](https://img.shields.io/badge/group-System-slate.svg)](#)
[![Platform](https://img.shields.io/badge/platform-All-green.svg)](#)
[![License](https://img.shields.io/badge/license-Freeware-brightgreen.svg)](#)

专为系统级自动化、桌面程序调度、辅助测试及操作系统管控设计的旗舰套件。提供软件进程生命周期管理（启动/附加/查杀/探测）、系统句柄释放、进程内存高精度读写与特征码扫描、结构化对象构建、系统剪贴板存取、毫秒级高精度延时等待及系统电源状态管理（睡眠/休眠/锁屏/重启/关机）。

---

## 📖 简介 (Overview)

`xy_system` 提供了跨平台的操作系统与运行时交互能力：
- **进程生命周期管控**：支持普通与管理员提权启动（`StartProcess`、`Runas`）、根据 PID 或进程名附加（`AttachProcess`）、运行状态探测（`ExistProcess`）以及进程终止（`KillProcess`）。
- **内存读写与特征码扫描**：提供针对目标进程地址空间的数据读取（`ReadMemory`，支持 i32/i64/f32/f64/bytes/string 等）、数据写入（`WriteMemory`）以及带通配符的十六进制特征码扫描定位（`SearchMemory`，如 `48 8B 05 ?? ?? ?? ??`）。
- **系统句柄与对象交互**：支持系统资源句柄的安全释放（`CloseHandle`），以及结构化实体构造与模块导出函数调用（`CreateObject`、`CallMethod`）。
- **桌面环境与系统电源**：提供系统剪贴板的双向读写（`ClipboardValue`）、默认关联程序/文件拉起（`LaunchFile`）、浏览器快捷打开网页（`OpenUrl`）、精准挂起等待（`Wait`）及整机电源策略控制（`SuspendSystem`，支持 Sleep/Hibernate/Lock/Restart/Shutdown）。
- **工作流分支跳转与账号管理**：支持基于标签的流程跳转（`Jump`）、显式流程退出（`Exit`）、随机数生成（`Random`）及系统本地用户创建（`UserAdd`）。

---

## ✨ 核心特性 (Features)

- **原生系统级直连**：高效调用操作系统底层服务，执行速度极快，响应稳定。
- **带通配符特征码扫描**：支持字节级模糊匹配（`??`），能够自适应软件版本变动与动态基址寻址。
- **结构化实体与方法调用**：支持根据模板在内存中创建结构化数据实体，并灵活传递参数调用模块导出方法。
- **特权操作支持**：原生支持管理员提权执行通道（`Runas`）与进程管理能力。
- **高精度调度与剪贴板管道**：内置低资源占用的精准休眠等待（`Wait`）与跨应用文本传输管道。

---

## 🛠️ 动作指令全景速查 (Action Catalog)

| 动作标识 (Tag) | 功能名称 | 描述 | 输出类型 |
| :--- | :--- | :--- | :--- |
| `StartProcess` | 启动新进程 | 在后台创建并启动指定的独立操作系统进程或命令行任务 | `None` |
| `OpenApplication` | 打开应用 | 启动指定的系统应用程序并可传入命令行参数与工作目录（非阻塞运行） | `None` |
| `Runas` | 以管理员身份提权运行 | 使用管理员权限（UAC提权）启动指定程序或执行特权命令 | `None` |
| `AttachProcess` | 附加进程 | 连接并附加到目标软件进程，支持动态加载扩展模块与执行初始化逻辑 | `None` |
| `ExistProcess` | 检测进程 | 检查指定的应用程序或进程当前是否正在系统后台运行 | `bool` |
| `KillProcess` | 终止进程 | 根据进程名称、路径或表达式结束指定的系统进程 | `bool` |
| `ReadMemory` | 读取内存 | 读取目标软件进程或模块内存地址中的数据，支持多种数据类型与偏移链解析 | `Mixed` |
| `WriteMemory` | 写入内存 | 向目标软件进程或模块内存地址写入数据，支持自动解除写保护 | `bool` |
| `SearchMemory` | 搜索内存 | 在目标软件进程或模块内存中检索特定的特征码或字节序列 | `Array` |
| `CloseHandle` | 关闭系统句柄 | 释放已打开的系统资源句柄，保证系统稳定运行 | `bool` |
| `CreateObject` | 创建对象 | 在内存中创建结构化数据实体（支持Point、Rect、Size、Color、Range、DateTime等） | `Mixed` |
| `CallMethod` | 调用方法 | 调用目标进程加载模块中的指定导出函数并获取执行结果 | `Mixed` |
| `ClipboardValue` | 读取/设置剪贴板内容 | 读取系统剪贴板中的文字内容，或将新文字写入剪贴板 | `string` |
| `LaunchFile` | 打开关联文件 | 使用操作系统默认关联程序打开指定的文档、表格、图片或脚本 | `bool` |
| `OpenUrl` | 在默认浏览器中打开网址 | 使用操作系统默认浏览器打开指定的网页网址 URL | `bool` |
| `SuspendSystem` | 系统电源与待机控制 | 控制计算机进入睡眠、休眠、锁屏、重启或关机状态 | `bool` |
| `Wait` | 延时等待 | 暂停执行等待指定时间（支持秒数或毫秒数） | `None` |
| `Random` | 随机数 | 生成指定区间范围 [min, max] 内的随机整数 | `number` |
| `UserAdd` | 添加系统本地用户 | 在当前操作系统中创建新的本地电脑用户账户 | `bool` |
| `Jump` | 跳转 | 跳转到指定的工作流动作步骤或标签处继续执行 | `None` |
| `Exit` | 退出 | 直接终止当前自动化工作流程的执行 | `None` |

---

## 📚 详细参数说明与使用参考 (Detailed Reference)

### 1. 进程生命周期管理 (Process Management)

#### `StartProcess` 与 `OpenApplication`
- **`StartProcess`**：在后台创建并启动指定的独立操作系统进程。
  - `app` (*string*): 目标可执行文件路径或系统命令。
  - `command_line` (*string*): 命令行启动参数。
  - `no_window` (*string*, 默认 `"false"`): 是否在无窗口后台模式下静默启动。
  - `working_directory` (*FolderPicker*): 进程的工作目录完整路径。
  - `env` (*string*): 附加环境变量配置 (`KEY=VALUE`)。
- **`OpenApplication`**：启动指定的系统应用程序（非阻塞模式）。
  - `app` (*string*): 目标程序路径或名称（如 `notepad.exe`, `calc.exe`）。
  - `command_line` (*string*): 启动参数。
  - `working_directory` (*FolderPicker*): 工作目录路径。
  - `env` (*string*): 环境变量。

#### `Runas` - 以管理员身份提权运行
通过系统 UAC 提权运行程序。
- **参数：** `app`（程序路径/命令）、`account`（指定用户，可选）、`password`（密码，可选）、`working_directory`（工作目录）、`command_line`（运行参数）、`env`（环境变量）。

#### `AttachProcess`、`ExistProcess` 与 `KillProcess`
- **`AttachProcess`**：连接并附加到目标软件进程。参数：`app`（目标进程）、`dy`（动态库路径）、`entrypoint`（入口函数）、`data`（初始化数据）、`command_line`（命令行参数）。
- **`ExistProcess`**：传入 `app`（进程名或通配符），返回布尔值指示目标进程是否在线。
- **`KillProcess`**：传入 `app`，结束指定的运行中进程。

---

### 2. 进程内存分析与修改 (Memory Inspection & Scanning)

#### `ReadMemory` - 读取内存数据
- **输入参数：**
  - `app`: 目标进程标识或名称。
  - `backend`: 驱动模式，默认 `"auto"`。
  - `address`: 十六进制内存地址（如 `0x7FF710000000`）。
  - `data_type`: 解析的数据格式（`i32`, `i64`, `u32`, `u64`, `f32`, `f64`, `string_utf8`, `string_utf16`, `bytes`, `hex`）。
  - `size`: 读取字节数（适用于 bytes/hex/string）。
  - `offsets`: 多级指针偏移链（例如 `0x10,0x28`）。
  - `memflow_connector`: 硬件连接通道配置（可选）。
- **输出类型：** `Mixed`

#### `WriteMemory` - 写入内存数据
- **输入参数：**
  - `app`: 目标进程标识。
  - `backend`: 驱动模式，默认 `"auto"`。
  - `address`: 十六进制内存地址。
  - `data_type`: 写入数据格式。
  - `value`: 准备写入的数值、文本或十六进制字节串。
  - `offsets`: 多级指针偏移链。
  - `unprotect`: 是否自动解除页面写保护（`"true"`, `"false"`）。
  - `memflow_connector`: 硬件连接通道配置（可选）。
- **输出类型：** `bool`

#### `SearchMemory` - 搜索内存特征码
- **输入参数：**
  - `app`: 目标进程标识。
  - `backend`: 驱动模式，默认 `"auto"`。
  - `pattern`: 十六进制特征码字符串，支持 `??` 通配符（例如 `48 8B 05 ?? ?? ?? ??`）。
  - `module`: 限定搜索的动态链接库模块名称（可选）。
  - `rip_offset`: 相对寻址偏移计算位置（可选）。
  - `instruction_len`: 指令长度（可选）。
  - `match_all`: 是否返回全部匹配地址（`"false"`, `"true"`）。
  - `memflow_connector`: 硬件连接通道配置（可选）。
- **输出类型：** `Array`

---

### 3. 对象与系统句柄管理 (Objects & System Handles)

#### `CreateObject` 与 `CallMethod`
- **`CreateObject`**：在内存中创建结构化数据实体。
  - `value`: 数据载荷/模板（如 `{"x": 0, "y": 0}`, `{"width": 1920, "height": 1080}`, `0..100`, `now`）。
  - **输出**：`Mixed`
- **`CallMethod`**：调用目标模块中的导出方法。
  - `object`: 目标模块名称或会话标识。
  - `method`: 待调用的导出函数名称。
  - `return_type`: 返回值类型（`int`, `uint`, `string`, `pointer`, `bool`, `void`, `float`）。
  - `abi`: 调用约定（`default`, `stdcall`, `fastcall`, `thiscall`）。
  - **输出**：`Mixed`

#### `CloseHandle` - 关闭系统句柄
- **输入参数：**
  - `type`: 句柄类型（`Process`, `Thread`, `File`, `Event`, `Mutex`, `Semaphore`, `Key`, `All`）。
  - `name`: 句柄名称或过滤关键字。
  - `exe_file`: 关联的可执行程序文件（可选）。
- **输出类型：** `bool`

---

### 4. 桌面环境、电源与系统交互 (Desktop & System Environment)

#### `ClipboardValue` - 读写剪贴板
- **输入参数：**
  - `value`: 准备写入剪贴板的纯文本。**留空则执行读取操作**，获取当前剪贴板文本。
- **输出类型：** `string`

#### `SuspendSystem` - 系统电源与待机控制
- **输入参数：**
  - `option`: 电源操作模式（`Sleep`, `Hibernate`, `Lock`, `Restart`, `Shutdown`）。
- **输出类型：** `bool`

#### `LaunchFile` 与 `OpenUrl`
- **`LaunchFile`**：传入 `file`（目标文件完整路径），使用系统默认关联应用直接启动。
- **`OpenUrl`**：传入目标 `url`（如 `https://www.google.com`），直接在默认网页浏览器中打开。

---

### 5. 控制流、时间与用户管理 (Control & Utility)

- **`Wait`**：暂停执行等待指定时间，参数 `value`（支持浮点秒数或毫秒）。
- **`Random`**：在 `min` 到 `max` 之间生成均匀随机整数。
- **`UserAdd`**：指定 `account`、`password` 和 `home_dir`，在本地操作系统中添加新的用户账户。
- **`Jump`**：跳转至流程中指定的 `target` 步骤标签。
- **`Exit`**：直接终止当前自动化工作流程的执行。

---

## 📦 插件清单定义 (Manifest Reference)

```json
{
  "plugin_id": "xy_system",
  "name": "系统与软件进程管理 (System & Process)",
  "version": "0.50.5",
  "group": "System",
  "group_icon": "⚙",
  "description": "提供启动与关闭软件、读写剪贴板、检测系统运行状态、高精度延时等待与电脑关机休眠等功能",
  "actions": [...]
}
```

---

## 📄 许可证 (License)

本插件遵循免费专有许可协议 (Freeware)。供 小友+ 用户免费下载与使用，未经官方书面授权，严禁对二进制文件进行逆向工程、反编译或二次打包转售。
