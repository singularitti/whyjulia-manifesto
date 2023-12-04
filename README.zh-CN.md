# 为什么选择Julia —— 一份宣言

[![DOI](https://zenodo.org/badge/720188322.svg)](https://zenodo.org/doi/10.5281/zenodo.10252526)

这个仓库的目的是提供一个易于获取且阐述清晰的总结，解释为什么学术界应该使用 [Julia编程语言](https://julialang.org)进行科学计算 / 计算科学 / 数据分析 / 研究软件工程。  
如有遇到问及“为什么选择Julia？”的人，请随意分享此内容。

_(显然，这篇文章是表达了此GitHub仓库贡献者的观点；尽管如此，这些观点都是基于后续章节明确提供的事实信息)_

## 什么是编程语言？

编程语言是科学家完成工作的工具，同时它们支持科学家的工作被其他科学家进一步复用和扩展。

## 编程语言最重要的是什么？

保持简单并考虑到学术界的需求，一个编程语言最基础的重要方面包括：

1. **编写速度。** 科学家将其想法从纸上/大脑中转化为计算机上的可运行原型的速度有多快。
2. **执行速度。** 编写的代码被计算机运行的速度。
3. **可用库。** 有多少提供现成功能并且文档齐全的优秀包/扩展程序？
4. **扩展性/组合性。** 在不同编程语言中复用、扩展或与现有库组合的难易程度。
5. **易用性/可分享性/可再现性。** 初学者上手语言的难易程度（安装和学习最初的步骤），以及与其他科学家分享工作的方便程度，使得他们也能轻松复现共享的工作。

现在我们可能会问自己：_“理想的编程语言是什么？”_

它应该是在所有上述基本方面表现最好的语言。但这样的语言并不存在，因为在现实世界中优缺点是不可分割的一部分。因此，最佳的_真实_语言是在探究这些基本方面时整体质量最高的那个。

## Julia是最佳的语言（用于科学）

在比较上述几个基本方面后，**Julia显现为总体赢家**，因为它在所有方面的表现都非常出色。详细内容和参考资料将在“详情”章节提供。总结如下：

### 编写速度

Julia是一种动态语言，允许交互式灵活的代码创作和探索。Julia的语法与数学尽可能接近，同时也是现代的（高级别）。它还包括自动理解语句结尾或允许使用Unicode这样的创新进展。这些进展使得通常Julia代码与其实现的科学论文有1对1的映射关系。Julia也不需要显式地注明类型（尽管可以这么做），进一步提高了编写代码的效率。

多重分派是一种与科学思维最相似的编程范式，因为它将进程从数据类型中剥离出来。这加速了将科学想法转换成可运行代码的过程。

### 执行速度

Julia编译成的机器代码因其智能类型推断系统而常常与C/FORTRAN一样快。这意味着，标准用户编写的Julia代码被编译为高效的机器代码 - 不需要任意的语言扩展（例如Numba、Cython等）。Julia对并行和分布式计算的支持天生在内。这些方面也易于使用。Julia对GPU的支持通过易用的包来实现，而Julia的包生态系统还包括了许多用于代码性能加速的包，如[Transducers.jl](https://github.com/JuliaFolds/Transducers.jl)、[ThreadsX.jl](https://github.com/tkf/ThreadsX.jl)、[FLoops.jl](https://github.com/JuliaFolds/FLoops.jl)、[MultiThreadedCaches.jl](https://github.com/JuliaConcurrent/MultiThreadedCaches.jl)、[ParallelAccelerator.jl](https://github.com/IntelLabs/ParallelAccelerator.jl)、[Dagger.jl](https://github.com/JuliaParallel/Dagger.jl)等更多包。

### 可用库

Julia已经在几乎每个科学领域都有软件组织。从高能物理到经济学，很有可能你正在工作的领域已经有一个_开发者_（不仅仅是用户）社区，他们使用本土Julia软件，而这些软件能与其他语言中的替代品匹敌。此外，这些组织中已经包含了一些最优秀的软件，也就是说，对于特定任务而言，它们是最具功能、最高性能并且最易于获取的工具。例如[DifferentialEquations.jl](https://github.com/SciML/DifferentialEquations.jl)、[DynamicalSystems.jl](https://github.com/JuliaDynamics/DynamicalSystems.jl)、[Turing.jl](https://github.com/TuringLang/Turing.jl)、[NeuralPDEs.jl](https://github.com/SciML/NeuralPDE.jl)、[Distributions.jl](https://github.com/JuliaStats/Distributions.jl)、[Makie.jl](https://github.com/MakieOrg/Makie.jl)、[JuMP.jl](https://github.com/jump-dev/JuMP.jl)等等。此外，即使有些你需要的工具在Julia中不可用，这也不是问题，因为其与其他语言的组合性（见下文）。

_我们应该指出这一点是多么令人惊讶。Julia是一门较新的编程语言，用户更少，接受的大规模资金也更少，与目前科学家使用最广泛的Python相比。Julia的库生态系统与Python匹敌，在许多领域甚至超过Python，这证明了1）在Julia中开发或贡献软件有多容易，以及2）Julia吸引了多少软件工程人才。_

### 扩展性/组合性

尽管这个方面在编程语言讨论中常被忽视，它在学术界至关重要。它能使科学工作成为被硬盘永久遗忘的神秘脚本，或者成为一个完整的包（或者是另一个已建立包的一部分），使得其他科学家可以复用和延续，加快他们自己的研究。此外，良好的扩展性和组合性通常也意味着良好的代码复用，这本身就意味着良好的维护性（这意味着长期维护代码库是容易的）。

在科学代码的扩展性和组合性方面，Julia是市场上最好的工具之一。当谈到与其他语言软件的组合性时，Julia允许_原生地_调用C/FORTRAN代码。诸如[PythonCall.jl](https://github.com/cjdoris/PythonCall.jl)或[RCall.jl](https://github.com/JuliaInterop/RCall.jl)等包允许直接调用各自语言的代码（实际上，PythonCall.jl允许在Julia中使用典型的面向对象语法）。

但Julia真正的强项在于Julia包之间的组合性和扩展性。Julia带来了前所未有的代码复用量，使包可以轻松地相互通信和扩展彼此，而不需要冗余的代码和命名空间问题，这在像Python这样的语言中是会遇到的。这就是Julia在几乎每一个科学领域中的可用包数量激增的部分原因。而这一切组合性的基础都是Julia的多重分派系统。

（主张的证据：https://www.youtube.com/watch?v=kc9HwsxE1OY 和 https://www.youtube.com/watch?v=2MBD10lqWp8 和 https://github.com/Datseris/Zero2Hero-JuliaWorkshop 用于展示组合性的实操演示）

### 易用性/可分享性/可再现性

开始使用Julia很简单！
为每个操作系统安装核心语言是一个简单的下载并点击安装过程。Julia拥有一个叫做[`juliaup`](https://github.com/JuliaLang/juliaup)的版本多路复用器，使得管理多个Julia版本变得非常简单。
为语言安装包同样简单。
Julia拥有一个强大的[包管理器](https://github.com/JuliaLang/Pkg.jl)（它本身就是语言的一个包）。由于大多数的Julia包都是用纯Julia编写的，因此安装它们也是一个简单的一行命令。在涉及二进制依赖时，Julia拥有先进的预构建二进制系统：为任何系统和平台组合构建、编译和存储二进制文件，并在安装有二进制依赖的包时自动安装这些文件。再也不用花费数周时间来安装软件了！

与其他科学家分享Julia项目同样简单，因为强大的包管理器。一个Julia环境（即两个文本文件）包含了所有使用过的包以及它们的依赖，直至具体使用包的准确git提交记录。人们可以分享这个环境和相关的脚本，接收者则可以实例化它们，复现同样的环境。这样就能运行相同的代码，得到相同的输出，进而实现同样的结果。

## Julia的详细优势

该部分通过项目清单详细阐述了Julia的具体优势。它还提供了参考资料并提供了进一步阅读的资源。

1. **解决了双语言问题**：它是动态和交互的语言，允许像Python这样的解释型语言一样进行实时的科学探索，但同时还提供了C这样的静态低级语言的性能。Julia通过编译机器级代码运行，因此所有基本的编程概念，如迭代、广播、函数作为参数，都是快速的。因此，你永远不必“重写”一个Julia代码到另一种语言中以使之运行得更快！这意味着你将花费更少的时间编写（或重写代码），花更多时间推进你的工作。它还意味着你不必精通两种编程语言就能参与到一个库的开发中。
2. **占据了高性能和简单代码的“甜蜜点”**：在所有编程语言的全球比较中：<img src="speed_vs_codesize_comparison.png" alt="speed vs codesize language comparison" width=500>

   这个图像是由[Chapel Language](https://chapel-lang.org/)的开发者创建的，后者并没有特别针对学术用途。此图像取自他们的公开推文：https://twitter.com/ChapelLanguage/status/1623389242822111232 。
3. **它的语法直观且尽可能贴近数学**：高级别的语法结合Unicode，以及易于推理的代码，让代码编写和阅读速度变得更快。此外，现代Julia语法解析器消除了使用许多“修饰符”的需要，例如用`;`结束行或要求缩进来表示代码块，因为它能自动理解命令的开始和结束。
4. **多重分派**：是Julia的核心编程范式，并与函数式编程结合使用。我们认为，它是 [将科学思想实现为代码最合适的范式](https://www.youtube.com/watch?v=7y-ahkUsIrY)，因为它使科学思考并行化：“过程”（函数）不属于任何特定的数据结构。多重分派以及它带来的指数级表达能力在[Stefan Karpinski的这次演讲](https://www.youtube.com/watch?v=kc9HwsxE1OY)中表现得很好。
5. **空前的代码复用和包之间的交流**。这是多重分派的直接后果，是Julia这种编程语言所独有的特性，其他语言从未有过。总之，在Julia中，包可以非常容易地使用和扩展其他包（大多数时候免费！），无需编写冗余或粘合代码。因此，大多数包都重用了现有的代码，并与其他包有共同的接口。例如，在[Chris Rackauckas的这次演讲中](https://youtu.be/tynmTkpdAME?si=44MRCVQtW4sQ5JFI&t=1879)，他强调了Julia如何发展机器学习与开发其他标准情况一样，这是Julia科学机器学习开放社区能与Python的PyTorch等相媲美，并在微分方程方面大大超越Python的一个重要原因。为了进一步阐明这一点，请看[Kristoffer Carlsson和Fredrik Bagge Carlson的这场演讲](https://youtu.be/2MBD10lqWp8?si=cst_gfNXyWs0hH7z&t=624)，显示了多重分派系统的力量，展示了用户如何**免费**获得对实数、矩阵、误差传播、符号动力学和自动微分的三角函数支持，所有这些都是基于`sin`函数，并且只有10行代码，同时还能解决一个包含这些所有可能类型的`sin`函数的微分方程。
6. **Julia由Julia编写**：（[从一个实际学术角度看](https://discourse.julialang.org/t/how-is-julia-written-in-julia/50918/8?u=datseris)）这就是Julia解决双语言问题的原因，它还具有更多的优势。  
   * 典型的用户代码实际上与Julia自己的基础代码类似，一直到基本算术运算。这意味着，理解其他包的源代码，甚至Julia本身的代码，是直截了当的。因此，通过代码贡献来改进现有代码库也是简单的。  
   * 上述情况自然导致，典型的Julia用户已经接近成
