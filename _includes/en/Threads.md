Multithreading is provided by the `Threads` standard package.

|----------------------------------------|---------------------------------|
| Launch Julia with threads  | `julia  --threads 4` |
| Number of threads | `Threads.nthreads()` |
| Multithreaded `for` loop | `Threads.@threads for i = 1:10`<br>  `a[i] = i^2` <br>      `end` |
| Data-race freedom | use `lock(x)` (and `unlock(x)`),e.g. <br> `lock(lk) do`<br>`    use(a)` <br>     `end`|