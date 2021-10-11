---
layout: two-cols
---

```typescript
let fa: (a: Animal) => void
let fc: (a: Cat) => void
let fd: (a: Dog) => void

fa = fc // Error
fc = fa // OK，contravariant
fc = fd // Error
```

```typescript
let fucd: (a: Cat | Dog) => void
let ficd: (a: Cat & Dog) => void

fucd = ficd // Error
ficd = fucd // OK

// union to intersection
type UnionToIntersection<T> = 
  (T extends any ? (x: T) => any : never) extends 
  (x: infer R) => any ? R : never
```

```typescript
abstract class AnimalShelter {
    abstract Animal getAnimalForAdoption();
    abstract void putAnimal(Animal animal);
}
```


::right::


```typescript
class CatShelter extends AnimalShelter {
    Cat getAnimalForAdoption() {
        return new Cat();
    }
}
```

```typescript
class CatShelter extends AnimalShelter {
    Cat getAnimalForAdoption() {
        return new Cat();
    }

    void putAnimal(Object animal) {
        // ...
    }
}
```

```dart
class CatShelter extends AnimalShelter {

    void putAnimal(covariant Cat animal) {
        // ...
    }
}
```