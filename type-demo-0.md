# 子类型 Subtyping

子类型表示在某种上下文下，一个类型A可以安全的替换类型B。对于OO类型的PL，多态就是子类型的一种表现形式。

除了常见的继承表示子类型，还存在其他复杂的子类型，例如 函数子类型，泛型子类型等。

而不同的子类型所处的上下文不同，所以最后类型之间替换的规则也不同。

```typescript
interface Animal {
    cry(): void
}
interface Cat extends Animal {
    furry: boolean
}
interface Dog extends Animal {
    naughty: boolean
}
```

```typescript
let a: Animal
let c: Cat
let d: Dog

a = c // OK，covariant
c = a // Error
c = d // Error
```
