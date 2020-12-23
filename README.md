# proj5-fuxi-full-system-with-cpu-compiler-os

### 项目描述

作为计算机系的学生，掌握 CPU、Compiler、OS 是一种必须的专业技能；但同时，作为一个本科生，很难将这三者有机整合，融会贯通。伏羲致力于从零开始，构建一个以 RISC-V 处理器为核心的软硬件全系统，包括 CPU、SoC、Compiler 和 OS，借此锻炼本科生的系统能力，并且在相关方向上做出更多的探索和创新。

学习和扩展伏羲系统，可以帮助有一定能力的同学吃透 CPU、Compiler、OS，自底向上建立计算机体系结构、组成原理、编译原理和操作系统等课程之间的内在联系，学习和理解大型软硬件工程的设计、实现和测试方法，锻炼工程能力和系统能力，在计算机系统的道路上更上层楼。

得益于 RISC-V 指令集架构灵活的扩展性，同学们还可根据实际需要，在系统中实现针对诸如高性能计算、异构计算、可信计算等方向的扩展。由于整个伏羲系统均为自行构建，我们可以针对这套体系，快速实现一个包含指令集扩展、编程语言语法/标准库支持、编译后端特殊优化、操作系统提供接口的完整的软硬件解决方案。

### 已有源代码

- [CPU: Fuxi (伏羲), 32-bit pipelined RISC-V processor written in Chisel3](https://github.com/MaxXSoft/Fuxi)
- [Compiler: Yu (羽), a simple system programming language](https://github.com/MaxXSoft/YuLang)
- [OS: GeeOS (寂), a lightweight, UNIX like operating system written in YuLang](https://github.com/MaxXSoft/GeeOS)

### 所属赛道

2021 全国大学生操作系统比赛的 “OS功能设计” 赛道

### 参赛要求

- 以小组为单位参赛，最多三人一个小组，且小组成员是来自同一所高校的本科生（2021 年春季学期或之后本科毕业的大一 ~ 大四的学生）
- 如学生参加了多个项目，参赛学生选择一个自己参加的项目参与评奖
- 请遵循 “2021 全国大学生操作系统比赛” 的章程和技术方案要求

### 项目导师

邢其正 (MaxXing)

- github https://github.com/MaxXSoft
- email x@MaxXSoft.net
- web http://MaxXSoft.net/

### 难度

初等 ~ 中等 ~ 高等

### 特征

- 自己设计 CPU (伏羲 CPU)
- 设计一种编程语言 (羽语言)，并实现这种编程语言的编译器，可以把编译出的代码运行在自己设计的 CPU 上
- 用自己设计的编程语言编写 OS (寂 OS)，通过自己写的编译器生成机器码，并最终运行在自己设计的 CPU 上

### License

- GPLv3

## 预期目标

### 注意：下面的内容是建议内容，不要求必须全部完成。选择本项目的同学也可与导师联系，提出自己的新想法，如导师认可，可加入预期目标

### 第一题: 大自然的搬运工

* 挑选合适的 FPGA 开发板, 将伏羲 SoC 移植到其上.
* 在第一步的基础上, 为伏羲 SoC 移植各类系统软件, 如 `u-boot`, `open-sbi`, `xv6`, `rCore` 等.
* 在进行第二步时, 您可能需要微调伏羲 CPU 的实现.

### 第二题: 扩展寂 OS

使用羽语言, 为寂 OS 实现更多的功能, 例如:

* 支持基于优先级的线程调度.
* 支持基于伙伴分配器的内存管理.
* 支持 `mmap`, `fork`, `execve` 等系统调用.
* 支持更丰富的文件系统.
* 支持 GUI.

### 第三题: Make YuLang Great Again!

以下三点为平行关系, 您只需完成其中的一点 (或几点):

* 为羽语言添加更多的功能, 例如:
  * 支持 RAII, 即: 编译器负责在某个 “对象” (`struct` 的一个实例) 的生命周期结束后, 自动调用其 `del` 方法.
  * 支持基于模式匹配和 AST 生成的宏.
  * 支持泛型.
  * 支持生成调试信息.
* 使用 Rust 或其他语言, 重新实现羽语言的编译器.
* 使用羽语言, 实现羽语言的编译器.

### 第四题: 伏羲的 RVC 支持

* 修改伏羲 CPU 的硬件实现, 使其支持 RISC-V 的 RVC (压缩指令) 扩展.
* 修改寂 OS 的相关部分, 使其支持这一变更, 并能正常运行于修改后的伏羲 CPU 上.

### 第五题: 伏羲的自定义扩展

* 为伏羲添加一个硬件加速器, 例如针对矩阵运算, 编解码, 神经网络推理的硬件实现.
* 如果您对指令集做出了扩展, 您需要修改羽语言编译器的后端 (目前是 LLVM), 使其支持在必要的情况下, 生成相关的指令.
* 修改寂 OS, 使其适配相关更改.
* 设计一个可运行于伏羲 SoC/寂 OS, 并利用该自定义扩展的应用, 以展示您所做的更改.
