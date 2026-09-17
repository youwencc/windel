# 删除助手 Windel

> 开源永久免费的 Windows 强制删除工具・删不掉的文件、解不开的占用、清不完的右键菜单、卸不掉的软件，一个工具全部搞定。

**当前版本：v1.12**・Windows 10 / 11 x64・单文件绿色免安装



***

## 截图预览

**强制删除** —— 文件 / 文件夹拖入即删，自动强制获取权限、解除占用：



![强制删除]([https://github.com/youwencc/windel/blob/main/assets/01.png)]

**右键菜单清理** —— 扫描全部右键菜单项，按第三方 / 系统 / 本软件分类清理，清理前自动备份可恢复：



![右键菜单清理](docs/screenshots/shot-context.png)

**软件卸载** —— 扫描已安装软件，常规卸载 / 强制卸载 / 注册表残留清理：



![软件卸载](docs/screenshots/shot-uninstall.png)



***

## 功能特性

### 1. 强制删除



* 支持**文件、文件夹批量拖放**删除，多路径同时处理

* 自动**强制获取权限**（takeown + icacls），只读、受保护文件也能删

* 自动**结束占用进程**，不再提示 "文件被占用"

* 删除失败自动**标记为重启后删除**，彻底清理不半途而废

* 删除全程操作记录可视化，支持勾选删除 / 清空列表

### 2. 右键菜单清理



* 一键扫描全部右键菜单项，按**第三方 / 系统 / 本软件**分类统计

* 勾选即可清理，也支持在列表项上右键直接清理单条

* **清理前自动备份**，按时间点一键恢复

* 支持注册「使用删除助手删除」到系统右键菜单

### 3. 软件卸载



* 扫描已安装软件，显示版本、**安装时间**、发布者、大小，支持按任意列排序与搜索

* **常规卸载**：调用官方卸载程序（自动处理 msiexec /X 参数）

* **强制卸载**：顽固软件一键清理 —— 备份并删除注册表键、结束相关进程、删除安装目录与快捷方式

* **清理注册表残留**：卸载后残余注册表项备份后清理，可追溯

## 系统要求



| 项目  | 要求                                          |
| --- | ------------------------------------------- |
| 系统  | Windows 10 / 11（64 位）                       |
| 权限  | 需要以**管理员身份**运行（用于强制删除与注册表操作）                |
| 运行时 | .NET 8 Desktop Runtime x64（如缺失，程序会自动弹出下载引导） |

## 下载与安装



* 前往 [GitHub Releases](https://github.com/youwencc/windel/releases) 下载最新 `Windel.exe`（约 1.1 MB）

* 单文件绿色软件：**免安装**，下载后双击即可运行

* 如提示缺少 .NET 环境，按弹窗引导一键下载安装 .NET 8 桌面运行时（x64）即可

## 快速上手



1. **强制删除**：把要删除的文件 / 文件夹拖入左侧拖放区 → 点击「删除选中」或「删除全部」

2. **右键菜单清理**：打开「右键菜单清理」→ 勾选目标项（或行内右键）→ 点击「清理选中」；误清可在底部备份区一键恢复

3. **软件卸载**：打开「软件卸载」→ 勾选软件 → 「卸载选中」（常规）或「强制卸载」（顽固软件）；卸载后可「清理注册表残留」

> 删除操作不可恢复，请谨慎确认。所有注册表与快捷方式清理前均自动备份。

## 开发与构建



```
\# 需要 .NET 8 SDK（Windows）

dotnet build ForceDelete.sln -c Release

\# 单文件自包含发布（免运行库，约 69 MB）

dotnet publish ForceDelete.sln -c Release -r win-x64 --self-contained true -p:PublishSingleFile=true

\# 单文件框架依赖发布（约 1.1 MB）

dotnet publish ForceDelete.sln -c Release -r win-x64 --self-contained false -p:PublishSingleFile=true
```

## 开源协议

本项目**开源永久免费**，采用 [MIT License](LICENSE)，欢迎自由使用、修改与分发；使用与分发时请保留作者信息。

## 作者与社区



* 出品：电脑小百科论坛・[weget.site](https://weget.site)

* B 站：[@电脑小百科](https://space.bilibili.com/595098830)

* 问题与建议：欢迎提交 [Issues](https://github.com/youwencc/windel/issues) 或 [Pull Requests](https://github.com/youwencc/windel/pulls)
