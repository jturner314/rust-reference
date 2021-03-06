# Slice types

> **<sup>Syntax</sup>**\
> _SliceType_ :\
> &nbsp;&nbsp; `[` [_Type_] `]`

A slice is a [dynamically sized type] representing a 'view' into a sequence of
elements of type `T`. The slice type is written as `[T]`.

To use a slice type it generally has to be used behind a pointer for example
as:

* `&[T]`, a 'shared slice', often just called a 'slice', it doesn't own the
  data it points to, it borrows it.
* `&mut [T]`, a 'mutable slice', mutably borrows the data it points to.
* `Box<[T]>`, a 'boxed slice'

Examples:

```rust
// A heap-allocated array, coerced to a slice
let boxed_array: Box<[i32]> = Box::new([1, 2, 3]);

// A (shared) slice into an array
let slice: &[i32] = &boxed_array[..];
```

All elements of slices are always initialized, and access to a slice is always
bounds-checked in safe methods and operators.

[_Type_]: types.html#type-expressions
[dynamically sized type]: dynamically-sized-types.html
