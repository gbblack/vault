## Zero Initialization

Prefer ZII (Zero Is Initialization).

```c++
template <typename T> struct Array {
private:
  T *m_buffer = nullptr;
  i32 m_size = 0;
  i32 m_capacity = 0;
};
```

> Easy to reason with struct data if most types are initialized the same way. It's also common to recieve zero initalized memory from custom memory allocators.
> 
> The name of a boolean may be flipped to support ZII. For example, instead of `bool alive = true`, use `bool dead = false`.


## Struct Initialization

Zero initialize structs and C style arrays with `= {}`.

```c++
Image m_white = {};
Value m_stack[STACK_MAX] = {};
```

## Sized Enums

Set an explicit size for enums.

> This is so that the enum type can be stored in a struct with a known size.

```c++
enum EnemyState : i32 {
  EnemyState_Idle,
  EnemyState_Alert,
  EnemyState_Chase,
  EnemyState_Dead,
};
```

(is this like the names integers thing from xig devlog) -> [[The Unreasonable Effectiveness of Naming Integers]]