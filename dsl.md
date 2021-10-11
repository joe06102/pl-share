# DSL

小程序核心是 JS + React Native，只在语法层面做了一些包装，整体模式还是和RN相同，采用了MV*模式，分为了**模板**和**逻辑**。

## 模板

整体基于 XML + 指令来实现，解析上直接采用了 `vue-template-compiler`，通过最基本的 LL 算法实现AST的解析。并在AST之上添加了一套指令的解析，例如 `pp:for` `pp:if` `slot` 等。

## 逻辑

逻辑上考虑到逻辑复用的问题，小程序常见的方式是`mixins`，而新版React体系中则使用 `Render-Props`, `HOC`, `Hooks`为主，所以采用了React已经不推荐的`createReactClass` 去创建实例，相比通过 `class` 去复用逻辑，createReactClass 有一些优势：自定绑定this，自动生命周期的合并，mixins形式上的一致等。
