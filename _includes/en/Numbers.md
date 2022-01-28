|                                    |                                                                    |
| ---------------------------------- | ------------------------------------------------------------------ |
| Integer types                      | `IntN` and `UIntN`, with `N ∈ {8, 16, 32, 64, 128}`, `BigInt` <br> `x = 1` -> `typeof(x) `     |
| Floating-point types               | `FloatN` with `N ∈ {16, 32, 64}`<br>`BigFloat`                     |
| Type detection                     | `n = 100; x = 3.14` <br> `typeof(n) == Int64`, `typeof(x) == Float64` |
| Minimum and maximum values by type | `typemin(Int8)`<br>`typemax(Int64)`                                |
| Complex types                      | `Complex{T}`, e.g. `Complex{Float64}`                                                       |
| Imaginary unit                     | `im`, e.g. `z = 1.0 - 2.0im`                                                               |
| Real and imaginary parts           | `real(z) == 1.0` and `imag( z ) == -2.0`                                                               |
| Machine precision                  | `eps(1.0) # Float64 precision around x = 1.0`                                     |
| Rounding                           | `round(x)        # returns floating-point`<br>`round(Int64, x) # returns 64-bit integer`      |
| Floor (round down)                 | `floor(x)` resp. `floor(Int64, x)`      |
| Ceiling (round up)                 | `ceil(x)` resp. `ceil(Int64, x)`      |
| Type conversions                   | `convert(T, val) # for T numbertype`  e.g. `convert(UInt8, 42)`<br>`Float64(val)           # calls convert` |
| Parse string (to number)           | `parse(Float64, "3.14")`|
| Global constants                   | `pi # 3.1415...`<br>`π  # 3.1415...`<br>`im # real(im * im) == -1` |
| More constants                     | `using Base.MathConstants`                                         |

Julia does not automatically check for numerical overflow. Use package
[SaferIntegers](https://github.com/JeffreySarnoff/SaferIntegers.jl) for ints
with overflow checking.
