---
id: FreeGroup
title: Module FreeGroup
---

[← Back](.)

[Source](https://github.com/gcanti/fp-ts/blob/master/src/FreeGroup.ts)

# FreeGroup

```ts
constructor(readonly value: Array<Either<A, A>>) {}
```

Added in v1.13.0 (data)

The free group generated by elements of `A`, up to equality. Note that the `Setoid` and `Monoid` instances differ
from the standard such instances for `Array<Either<A, A>>`; two elements of the free group are equal iff they are equal
after being reduced to "canonical form", i.e., cancelling adjacent inverses.

## ap

```ts
<B>(fab: FreeGroup<(a: A) => B>): FreeGroup<B>
```

Added in v1.13.0 (method)

## ap\_

```ts
<B, C>(this: FreeGroup<(b: B) => C>, fb: FreeGroup<B>): FreeGroup<C>
```

Added in v1.13.0 (method)

## chain

```ts
<B>(f: (a: A) => FreeGroup<B>): FreeGroup<B>
```

Added in v1.13.0 (method)

## map

```ts
<B>(f: (a: A) => B): FreeGroup<B>
```

Added in v1.13.0 (method)

## empty

```ts
const empty: FreeGroup<never>
```

Added in v1.13.0 (constant)

## fromArray

```ts
<A>(S: Setoid<A>): ((as: Array<Either<A, A>>) => FreeGroup<A>)
```

Added in v1.13.0 (function)

Smart constructor which normalizes an array

## getGroup

```ts
<A>(S: Setoid<A>): Group<FreeGroup<A>>
```

Added in v1.13.0 (function)

## getSetoid

```ts
<A>(S: Setoid<A>): Setoid<FreeGroup<A>>
```

Added in v1.13.0 (function)

## normalize

```ts
<A>(S: Setoid<A>) => (g: Array<Either<A, A>>): Array<Either<A, A>>
```

Added in v1.13.0 (function)

Reduce a term of a free group to canonical form, i.e. cancelling adjacent inverses.