|                   |                                                                                 |
| ----------------- | ------------------------------------------------------------------------------- |
| Read stream       | `stream = stdin`<br>`for line in eachline(stream)`<br>`    # do stuff`<br>`end` |
| Read file         | `open(filename) do file`<br>`    for line in eachline(file)`<br>`        # do stuff`<br>`    end`<br>`end` |
| Read CSV file     | `using CSV`<br>`data = CSV.read(filename)`                                      |
| Write CSV file    | `using CSV`<br>`CSV.write(filename, data)`                                      |
| Save HDF5         | `using HDF5`<br>`h5write(filename, "key", object)`                              |
| Load HDF5         | `using HDF5`<br>`h5read(filename, "key")`                                       |
