Packages must be [registered](https://pkg.julialang.org) before they are visible to the
package manager. In Julia, there are two ways to work with the package manager:
either with `using Pkg` and using `Pkg` functions, or by typing `]` in the REPL to
enter the special interactive package management mode. *(To return to regular REPL, just
hit `BACKSPACE` on an empty line in package management mode).*

## In Interactive Package Mode

|                                                          |                                       |
| -------------------------------------------------------- | ------------------------------------- |
| Add `PackageName`                                        | `add PackageName`                     |
| Remove `PackageName`                                     | `rm PackageName`                      |
| Update `PackageName`                                     | `update PackageName`                  |
| Use development version                                  | `dev PackageName` or `dev GitRepoUrl` |
| Stop using development version, revert to public release | `free PackageName`                    |

## Using `Pkg` in Julia session

|                                            |                            |
| ------------------------------------------ | -------------------------- |
| List installed packages (human-readable)   | `Pkg.status()`             |
| Update all packages                        | `Pkg.update()`             |
| Install `PackageName`                      | `Pkg.add("PackageName")`   |
| Rebuild `PackageName`                      | `Pkg.build("PackageName")` |
| Use `PackageName` (after install)          | `using PackageName`        |
| Remove `PackageName`                       | `Pkg.rm("PackageName")`    |

