# CS-Flash 💻

> 记录日常盲点，溯源 CS 基础底层原理，构建知识闭环

**个人技术笔记：计算机系统底层知识**

## 📋 目录

- [为什么做这个](#为什么做这个)
- [实验记录](#实验记录)
- [工作方法](#工作方法)
- [环境配置](#环境配置)
- [项目结构](#项目结构)

---

## 🎯 为什么做这个

从工程问题出发，通过代码实验深入底层，顺便补齐薄弱的理论知识。不从零啃理论书。

**工作流程**：遇到性能问题 → 写代码实验（60%）→ 用工具验证 → 回溯原理（40%）→ 记录下来

**特点**：
- 问题驱动，从真实痛点出发（如数据拷贝瓶颈）
- Python + C++ 对比实验
- 三端通用（Linux/macOS/Windows）
- 用系统工具抓证据
- 理论来源不限（书/博客/论文/源码等）

---

## 🔧 工作方法

### 1. 双向实现

| 语言 | 职责 |
|------|------|
| C++ | 底层操作、内存申请、机器级控制 |
| Python | 逻辑调度、数据解析、协议对接 |

### 2. 系统工具验证

不同平台的工具：

| 功能 | Linux | macOS | Windows |
|------|-------|-------|---------|
| 系统调用追踪 | `strace` | `dtruss` (需 sudo) | Process Monitor (Procmon) |
| 进程内存映射 | `pmap` | `vmmap` | VMMap (Sysinternals) |
| IPC 资源查看 | `ipcs` | `ipcs` | PowerShell 命令 |
| 调试与内存分析 | `gdb` | `lldb` | WinDbg / VS Debugger |

### 3. 原理溯源

实验完成后回溯底层理论（占比 40%）：
- 从多个来源补充理论：书籍、博客、论文、官方文档、源码等
- 记录在每个实验的 README 中

---

## 💻 环境配置

### 操作系统

| 平台 | 环境 |
|------|------|
| Linux | Ubuntu 20.04+ / Debian / CentOS |
| macOS | macOS 11+ |
| Windows | Windows 10/11 + WSL2 或原生 |

### 编译器

| 工具 | 版本 | 平台 |
|------|------|------|
| GCC/G++ | 11.0+ | Linux |
| Clang/LLVM | 13.0+ | macOS |
| MSVC | VS 2022+ | Windows |
| Python | 3.10+ | 全平台 |

### 原则

- 不用高度封装的第三方库，直接用系统调用（如 `mmap`, `shm_open`）
- 目标：理解底层机制

---

## 📂 项目结构

```
cs-flash/
├── 1_Shared_Memory_IPC/          # 共享内存 IPC
│   ├── README.md                  # 实验笔记
│   ├── lab1_basic_handshake/
│   ├── lab2_memory_layout/
│   └── lab3_numpy_zerocopy/
│
├── 2_Memory_Layout_Overhead/     # 内存布局
└── 3_Concurrency_Primitives/     # 并发原语
```