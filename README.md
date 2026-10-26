# ⚙️ 系统与软件进程管理套件 (System & Process Management Suite)

[![Plugin Version](https://img.shields.io/badge/version-0.53.0-blue.svg)](manifest.json)
[![Group](https://img.shields.io/badge/group-System-slate.svg)](#)
[![Platform](https://img.shields.io/badge/platform-All-green.svg)](#)
[![License](https://img.shields.io/badge/license-Freeware-brightgreen.svg)](#)
[![Discord](https://img.shields.io/discord/832082456727257118?label=Discord&logo=discord&logoColor=white&color=5865F2)](https://discord.gg/g5Fh3FtfGx)

专为系统级自动化、桌面程序调度、辅助测试及操作系统管控设计的旗舰套件。提供软件进程生命周期管理（启动/查杀/探测/枚举/同步等待）、原生注册表管理（读/写/删/查）、系统服务集中管控（状态/启/停/重启）、控制台命令同步捕获、系统/硬件信息感知、环境变量读写、系统剪贴板带冲突指数退避存取、系统电源休眠以及本地用户账户闭环管理。

---

## 📖 简介 (Overview)

`xy_system` 提供了跨平台的操作系统与运行时交互能力，包含 16 项高内聚核心动作：
- **进程生命周期调度**：支持普通与管理员提权启动（`StartProcess`）、运行状态探测（`ExistProcess`）、终止进程树（`KillProcess`）、当前运行进程列表枚举过滤（`GetProcesses`）以及同步等待进程出现或退出（`WaitForProcess`）。
- **命令行与环境感知**：CMD/PowerShell/Shell 同步执行与输出高精度捕获（`ExecuteCommand`）、进程/系统级环境变量读写（`GetEnv`、`SetEnv`），以及 CPU 核心数、可用物理内存、主机名与操作系统版本等指标采集（`GetSystemInfo`）。
- **注册表与系统服务集中管控**：统一 Windows 注册表管理（`ManageRegistry`：支持 read、write、delete、exists 四合一操作）；统一 Windows 系统服务管理（`ManageService`：支持 status、start、stop、restart 四合一操作）。
- **桌面、文件与剪贴板交互**：提供带 OS 锁竞争指数退避重试的系统剪贴板读写（`ClipboardValue`）、默认关联程序打开本地文档（`LaunchFile`）、默认浏览器快捷打开网络协议链接（`OpenUrl`）以及计算机睡眠/休眠/锁屏/关机控制（`SuspendSystem`）。
- **本地账户安全管理**：统一操作系统本地用户账户闭环管控（`ManageLocalUser`：支持 exists 检测、add 创建、delete 删除）。

---

## 🛠️ 动作指令全景速查 (Action Catalog)

| 动作标识 (Tag) | 功能名称 | 描述 | 支持平台 | 提权需求 |
| :--- | :--- | :--- | :--- | :--- |
| `ClipboardValue` | 读取/设置剪贴板内容 | 读写系统剪贴板文字，内置 5 次指数退避防并发锁冲突机制 | `Cross-Platform` | `false` |
| `ExecuteCommand` | 执行命令并获取输出 | 同步运行 CMD / PowerShell / Shell 命令行脚本并捕获输出与退出码 | `Cross-Platform` | `false` |
| `ExistProcess` | 检测进程 | 检查指定的应用程序或进程当前是否正在系统后台运行 | `Cross-Platform` | `false` |
| `GetEnv` | 获取环境变量 | 获取当前进程、用户或系统级的环境变量数值 | `Cross-Platform` | `false` |
| `GetProcesses` | 获取进程列表 | 检索当前系统正在运行的所有进程列表，支持名称与通配符过滤 | `Cross-Platform` | `false` |
| `GetSystemInfo` | 获取系统与硬件信息 | 获取计算机 CPU 核心数、内存可用空间、主机名及操作系统版本等指标 | `Cross-Platform` | `false` |
| `KillProcess` | 终止进程 | 根据进程 PID、进程名称或路径通配符结束指定的系统进程及子树 | `Cross-Platform` | `false` |
| `LaunchFile` | 打开文件/文档 | 使用操作系统默认关联程序打开指定的文档、表格、图片或脚本（仅限本地文件） | `Cross-Platform` | `false` |
| `ManageLocalUser` | 本地用户管理 | 统一管理操作系统本地用户账户：支持 exists (判断存在)、add (创建账户)、delete (删除账户) | `Cross-Platform` | `依操作而定` |
| `ManageRegistry` | 注册表管理 | 统一管理 Windows 注册表：支持 read (读取)、write (写入)、delete (删除)、exists (判断存在) | `Windows` | `依操作而定` |
| `ManageService` | 服务管理 | 统一管理系统服务：支持 status (状态查询)、start (启动)、stop (停止)、restart (平滑重启) | `Windows` | `依操作而定` |
| `OpenUrl` | 在默认浏览器中打开网址 | 使用操作系统默认浏览器打开指定的网络链接（支持 http/https，防误传本地路径） | `Cross-Platform` | `false` |
| `SetEnv` | 设置环境变量 | 设置当前进程、用户或系统级的环境变量数值 | `Cross-Platform` | `false` |
| `StartProcess` | 启动应用/进程 | 在后台创建并启动指定的操作系统应用程序、进程或命令行任务 | `Cross-Platform` | `false` |
| `SuspendSystem` | 系统电源与待机控制 | 控制计算机进入睡眠、休眠、锁屏、重启或关机状态 | `Cross-Platform` | `false` |
| `WaitForProcess` | 等待进程状态 | 阻塞同步等待目标进程启动出现或退出结束，支持超时与周期轮询 | `Cross-Platform` | `false` |

---

## 📄 许可证 (License)

本插件遵循免费专有许可协议 (Freeware)。供 小友+ 用户免费下载与使用，未经官方书面授权，严禁对二进制文件进行逆向工程、反编译或二次打包转售。
