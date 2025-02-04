See [Julia Manual - Performance tips](https://docs.julialang.org/en/v1/manual/performance-tips/).

- Performance critical code should be inside a function.
- Avoid global variables.
- Measure performance with `@time` or `@btime` and pay attention to memory allocation.
- Use Profiling or other analysis tools. (e.g. `Juno.@profiler` and `@code_warntype`)
- Avoid containers with abstract type parameters
- Type declarations are only needed when the compiler cannot predict the type.
- Use immutable types where possible.
- Avoid `Any` in collections.
- Avoid abstract types in collections.
- Write *type-stable* functions.
- Separate kernel functions (aka, function barriers)
- Use `sizehint!` for large arrays.
- Access arrays along columns, because multi-dimensional arrays are stored in column-major order.
- Pre-allocate outputs.
- Use `@.` to fuse vectorized operations.
- Consider using `@view` for slices.
- Avoid the splat (`...`) operator for keyword arguments.
- Use mutating APIs (i.e. functions with `!` to avoid copying data structures.
- Avoid `try`-`catch` in (computation-intensive) loops.
- Avoid string interpolation in I/O.
- Vectorizing does often not improve speed (unlike R, MATLAB or Python).
- Avoid `eval` at run-time.
