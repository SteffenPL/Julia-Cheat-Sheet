|                   |                                                          |
| ----------------- | -------------------------------------------------------- |
| Conditional <br> `if`, `else`, `elseif`, `end`   | `if 10 == 11`<br>`    println("Error in the matrix.")`<br>`else`<br>`    println("All good.")`<br>`end`|                                     |
| Simple `for` loop | `for i in 1:10`<br>`    println(i)`<br>`end`             |
| Unnested for loop | `for i in 1:10, j = 1:5`<br>`    println(i*j)`<br>`end`  |
| Enumeration       | `for (idx, val) in enumerate(arr)`<br>`    println("the $idx-th element is $val")`<br>`end` |
| `while` loop      | `while bool_expr`<br>`    # do stuff`<br>`end`           |
| Exit loop         | `break`                                                  |
| Skip current iteration    | `continue`                                               |
