|                                   |                                             |
| --------------------------------- | ------------------------------------------- |
| Declaration                       | `arr = Float64[]` <br> `arr = []  # element type is Any`      |
| Pre-allocation                    | `sizehint!(arr, 10^4)`                      |
| Access and assignment             | `arr = [1,2]`<br>`x = arr[1] + arr[end]` <br> `arr[1] = 10`  |
| Array comprehension               | `arr = [i^2 for i in 1:10]` |
| Array comprehension (2D)              | `[i+j for i in 1:3, j in 1:3]` |
| Assigment | `a = [1,2,3]`<br>`b = a      # b and a bound to same array`<br>`a[1] = -99`<br>`a == b     # true` |
| Copy elements (not address)       | `b = copy(a) # shallow copy`<br>`b = deepcopy(a)`          |
| Length                            | `length(arr) # int`            | 
| Size                              | `size(arr)   # tuple` |
| Select subarray from m to n       | `arr[m:n]`                                  |
| n-element array with 0.0s         | `zeros(n)`                                  |
| n-element array with 1.0s         | `ones(n)`                                   |
| n-element array with #undefs      | `Vector{Type}(undef,n)`                     |
| n equally spaced numbers from start to stop | `range(start,stop=stop,length=n)` |
| Array with n random Int8 elements | `rand(Int8, n)`                             |
| Fill array with val               | `fill!(arr, val)`                           |
| Pop last element                  | `pop!(arr)`                                 |
| Pop first element                 | `popfirst!(a)`                              |
| Push val as last element          | `push!(arr, val)`                           |
| Push val as first element         | `pushfirst!(arr, val)`                      |
| Remove element at index idx       | `deleteat!(arr, idx)`                       |
| Sort                              | `sort!(arr)`                                |
| Append a with b                   | `append!(a,b)`                              |
| Check whether val is element      | `val in arr`                |
| Scalar product                    | `dot(a, b) == sum(a .* b)`                  |
| Change dimensions (if possible)   | `reshape(1:6, 3, 2)' == [1 2 3; 4 5 6]`     |
| To string (with delimiter del between elements) | `join(arr, del)`              |
| Iterate        | `arr = rand(100)`<br>`for x in arr`<br>`  # do something`<br> `end` |

