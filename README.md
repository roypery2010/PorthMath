# PorthMath

PorthMath is a tiny collection of integer-focused helpers for [tsoding’s Porth](https://gitlab.com/tsoding/porth). The module stays within the core instruction set so it can be included directly in any project that already brings in `std.porth`.

## What’s inside

- `abs int -- int` – absolute value.
- `sign int -- int` – sign (`1`, `0`, or `-1`).
- `gcd int int -- int` – Euclidean greatest common divisor (handles negatives).
- `lcm int int -- int` – least common multiple (zero when either argument is zero).
- `pow int int -- int` – exponentiation with non-negative exponents.
- `factorial int -- int` – factorial for `n ≥ 0` (returns `0` for negative inputs).
- `is-prime int -- bool` – simple trial-division primer (returns `true` for `2`, `false` for `n < 2`).

Each proc is defined with clear stack signatures so you can read the code as documentation.

## Usage

Place `PorthMath.porth` somewhere the compiler can see it (for example next to your game scripts) and then:

```porth
include "std.porth"
include "PorthMath.porth"

proc main in
  48 180 gcd putu "\n" puts
  3 4 pow putu "\n" puts
end
```

Build the example with the usual compiler workflow (you just need the runtime and `std/` near the sources):

```bash
./porth -I . com PorthMath/examples/demo.porth
./demo
```

`examples/demo.porth` shows how to combine several helpers and can be used as a reference to see the exact stack order the library expects.
