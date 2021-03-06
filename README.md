# MetaTools

[![Build Status](https://travis-ci.org/burrowsa/MetaTools.jl.png?branch=master)](https://travis-ci.org/burrowsa/MetaTools.jl)

`MetaTools.jl` makes it simpler to write Julia macros that work on functions. When developing a macro in Julia the developer must take into account all the possible forms of AST that could be passed to the macro. The code to do this can be complicated and obscures the real logic the macro is designed to implement making the code harder to understand and maintain. Also all the possible forms of AST must be tested adding further the effort required to develop a macro. The approach `MetaTools.jl` takes is to convert the AST into a standardized format, an object of type `ParsedFunction`. This object is mutable and can be manipulated then the final form converted back to AST using the `emit` function. The `MetaTools.jl` functions to parse and emit AST are thoroughly tested so you only need test the core functionality of your macro not all the corner cases relating to obscure AST.

As well as the tools described above for writing macros `MetaTools.jl` also includes some handy macros implemented using the package. They serve both as examples of how to use the package and also as useful tools in their own right. The following macros are included:

 * `@commutative`