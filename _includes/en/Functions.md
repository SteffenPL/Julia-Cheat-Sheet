All arguments to functions are passed by reference.

**Convention**: Functions with `!` at the end of the name change at least one argument, typically the first, e.g.
`sort!(arr)`.

There are three kinds of arguments:

 - **Required arguments** are separated with a comma and use the positional notation.
 - **Optional arguments** come after required arguments and have a default value, defined with `=`.
 - **Keyword arguments** use the named notation and are listed in the function's
signature after the semicolon.

````
function func(req1, req2, opt1 = 1; key1="x", key2=0)
    # do stuff
end
````

The semicolon is *not* required in the call to a function that accepts keyword arguments.

The `return` statement is optional but highly recommended. *(Without return, the function returns the value of the last line.)*

Multiple variables can be returned as a tuple in a single `return` statement.


Functions can have explicit input and return types
```
# take any Number subtype and return it as a String
function stringifynumber(num::Number)::String
    return "$num"
end
```

*Multiple dispatch:* Functions can have multiple definitions for different input types. 
At each call, the most spezialized definition will be used, e.g.
```
intbyfloat(x,y) = NaN
intbyfloat(x::Int64,y::Float64) = x/y
intbyfloat(x::Float64,y::Int64) = y/x

intbyfloat(1,2.0) == 1/2.0  # calls second definition
intbyfloat(3.0,2) == 2/3.0  # calls third definition
isnan( intbyfloat(3.0, 3.0) ) # calls first definition
```

Functions can be
[vectorized](https://docs.julialang.org/en/v1/manual/functions/#man-vectorized-1)
by using the Dot Syntax

```
# here we broadcast the addition and the call of f(x)
A = rand(3, 4)
B = A .- randn(3,4)  # broadcast '-'

f(x) = 2x-1
C = f.(B)            # broadcast 'f'
```

Alternative ways to define functions are one line functions and anonymous functions.

One line functions use `=` instead of return
```
f(x,y=1;z=2) = x+y*z
```

Anonymous functions do not have a function name and use `->` instead of return
```
(x,y=1;z=2) -> x+y*z 
```
They can be used for example in collection functions or list comprehension, e.g.
```
sort([1,2,3], by = (x) -> 1/sin(x)) 
map((x,y) -> x/y^2, 1:10, 2:11)
```


Anonymous functions can best be used in collection functions or list comprehensions:
`x -> x^2`.

Functions can accept a variable number of arguments:

```
function func(a...)
    println(a)
end

func(1, 2, [3:5]) # tuple: (1, 2, UnitRange{Int64}[3:5])
```

Functions can be nested:

```
function outerfunction()
    # do some outer stuff
    function innerfunction()
        # do inner stuff
        # can access prior outer definitions
    end
    # do more outer stuff
end
```


Parametric functions 


Julia generates <a class="tooltip" href="#">specialized versions<span> Multiple dispatch a type of
polymorphism that dynamically determines which version of a function to
call. In this context, dynamic means that it is resolved at run-time,
whereas method overloading is resolved at compile time. Julia manages
multiple dispatch completely in the background. Of course, you can
provide custom function overloadings with type annotations. </span></a>
of functions based on data types. When a function is called with the
same argument types again, Julia can look up the native machine code and
skip the compilation process.

The existence of potential ambiguities is acceptable, 
but actually calling an ambiguous method is an **immediate error**.

Stack overflow is possible when recursive functions nest many levels
deep.
```