# risc_v-core

当前仓库还没有可运行的源码（仅有占位文件 `.gitkeep`），所以现在**不能直接运行项目**。

## 这个程序应该在什么环境下运行？

对于 RISC-V 项目，一般是下面两类运行环境：

1. **本机交叉编译 + 仿真运行（最常见）**
   - 在 Windows 上用 RISC-V 交叉编译器生成目标程序
   - 用 QEMU 等仿真器运行
2. **本机交叉编译 + 真机运行（开发板）**
   - 在 Windows 上编译
   - 下载到 RISC-V 开发板运行

> 结论：**Windows 64 位可以做开发与运行（仿真）**，但需要先安装对应工具链。

## 在 VS Code 上面可以运行吗？

**可以。** 但准确说法是：

- VS Code 是编辑器/IDE；
- 真正执行编译和运行的是终端里的工具（`gcc`/`make`/`cmake`/`qemu` 等）。

你可以在 VS Code 里通过这几种方式运行：

- 打开集成终端执行命令（推荐）
- 配置 `tasks.json` 一键构建
- 配置 `launch.json` 调试（如接 GDB/QEMU）

## Windows 64 位建议先准备的环境

1. **Git for Windows**（拉代码）
2. **VS Code**（推荐）
3. **Python 3.10+**（很多脚本/构建工具会用到）
4. **C/C++ 编译环境**（二选一）
   - Visual Studio Build Tools（MSVC）
   - 或 MSYS2 + mingw-w64（GCC）
5. **RISC-V 工具链**（按目标选择）
   - 裸机/固件常用：`riscv64-unknown-elf-gcc`
   - Linux 用户态常用：`riscv64-linux-gnu-gcc`
6. （可选）**仿真器**
   - QEMU（`qemu-system-riscv64` / `qemu-riscv64`）

## 后续有源码时的通用运行流程

1. 拉取仓库：`git clone <repo-url>`
2. 进入目录：`cd risc_v-core`
3. 查看构建说明：`README.md` / `docs/` / `Makefile` / `CMakeLists.txt`
4. 安装依赖（按项目脚本）
5. 构建与运行（常见命令）：
   - `make`
   - `cmake -S . -B build && cmake --build build`
   - `python run.py`（如果项目提供脚本）

---

如果你把实际源码（例如 `Makefile` 或 `CMakeLists.txt`）提交上来，我可以再给你一份**Windows + VS Code 可直接复制执行的完整步骤**。
