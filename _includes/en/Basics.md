|                      |                                                       |
| -------------------- | ----------------------------------------------------- |
| Assignment | `answer = 42`<br>`x, y, z = 1, [1.0, 2.0, 3.0], "A string"` |
| Swap | `x, y = y, x  # swap x and y` |
| Constant declaration | `const DATE_OF_BIRTH = 2012`                          |
| End-of-line comment  | `i = 1 # This is a comment`                           |
| Delimited comment    | `#= This is a ` <br> `multiline comment =#`                       |
| Chaining | `x = y = z = 1  # right-to-left`<br>`0 < x < 3      # true`<br>`5 < x != y < 5 # false` |
| Function definition  | `function add_one(i)`<br>`    return i + 1`<br>`end`  |
| Insert LaTeX symbols | `\delta` + [Tab]                                      |

A variable, in Julia, is a name associated (or bound) to a value. 
Notice that for most complex types, it will not copy the underlying data! For example
```
x = [1,2,3]
y = x 
y[1] = 10
x[1] == 10  # this is true, since x and y are associated to the same array
```