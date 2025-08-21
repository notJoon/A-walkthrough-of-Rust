# For Once and For All: Bound Regions and the Universe Hierarchy

## Regions in the compiler's model

The compiler represents lifetime as **regions**. Some regions correspond to concrete program scopes. For example, the lifetime of a local variable, some are named parameters like `'a` that you write in a signature; some are inference variables inserted by the compiler while it is still fighting things out. Some are special "placeholder" regions used to reason about higher-ranked bounds.

...

## Outlives, variance and constraints

## Region things

TODO: need to explain region lattice things that already explained in `region_kind.rs` file.

```text
// PATH: compiler/rustc_type_ir/src/region_kind.rs
// The Region lattice within a given function

static ----------+-----...------+       (greatest)
|                |              |
param regions    |              |
|                |              |
|                |              |
|                |              |
empty(root)   placeholder(U1)   |
|            /                  |
|           /         placeholder(Un)
empty(U1) --         /
|                   /
...                /
|                 /
empty(Un) --------                      (smallest)
```

## Leak checking

Once placeholder are in play, the compiler proceeds to relate the two sides by generating the usual type and outlives constraints.

TODO: Should I need to explain HRTB comparison things in this post?

## Region Solver

---

## Further Reading