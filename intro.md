# 代码

是一种**非结构化**的数据，通过语法指定它的结构。

编译器通过词法分析（lexical analysis），语法分析（syntax analysis）等，将具体的语法转换为抽象语法树（AST）。到这里统一称为**编译器的前端**。

对于静态类型语言，类型检查器会基于语义做类型检查，提前发现一些可能导致运行时错误的代码，动态类型语言则跳过这一步。除了类型检查，编译器还会做一些优化和分析以提升性能和可靠性。这一阶段被称为**编译器的中端**。

最后基于优化后的代码中间表示形式（Intermediate Representation)，编译器会生成特定CPU指令集的机器码，也就是**编译器的后端**。


<div style="background: #fff">
 <img src="https://upload.wikimedia.org/wikipedia/commons/c/cc/Compiler_design.svg" />
</div>

