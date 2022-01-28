`Tuples` are like inmutable arrays with static types.

|------------------------|----------------|
| Tuple construction     | `x = (1, 2.0, "3")` <br>`# Tuple{Int64, Float64, String}` |
| Access                 | `x[1] == 1`, `x[end] == "3"` |
| Unpack variables       | `a, b, c = x` |


`NamedTuples` are like `Tuples` but the elements have (static) names and allow access as data as fields.

|----------------------------|-----------------|
| Construction   | `nt = (; a = 10, b = 2.0, c = "3")` |
| Access         | `nt.a == 10`, `nt.c == "3"` |
| Unpack (by order)        | `(a,b,c) = nt` |
| Unpack (by variable names)        | `(;c,b,a) = nt` *(order does not matter)* |