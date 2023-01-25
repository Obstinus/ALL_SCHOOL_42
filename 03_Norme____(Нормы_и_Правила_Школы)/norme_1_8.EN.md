![pageimage](src/page1image3852832-small-13.png)

# Standard 42 #

### Version 1.8 ###


#### Benny benny@42.fr ####

#### Thor thor@42.fr ####

#### marvin marvin@42.fr ####


#### Summary: This document describes the current C standard. The programming standard defines a set of rules governing code writing. The standard is mandatory. Follow it when writing C code. ####




## Contents ## 


I       [Foreword](#Foreword)

- I.1    [Why impose a standard?](#i1-why-impose-norm-)
- I.2    [Standard in your renderings](#i2-standard in your renderings)
- I.3    [Tip](#i3-Tip)

II.1   [Norm 42](#standard-42-1)

- II.1    [Naming convention](#ii1-agreement-about-names)
- II.2    [Formatting](#ii2-formatting)
- II.3    [Function parameters](#ii3-function-parameters)
- II.4    [Functions](#ii4--functions)
- II.5    [Typedef, struct, enum and union](#ii5definition-type-struct-enum- or-unit-structure-enum-or-unit-enum)
- II.6    [Headlines](#ii6eadlines)
- II.7    [Macros and preprocessor](#ii7-macros-and-processor)
- II.8    [Forbidden Things!](#ii8-forbiddenthings)
- II.9    [Comments Off on](#ii9-comments)
- II.10   [Files](#ii10files)
- II.11   [Makefile](#ii11makefile)

III.      [La Norminette]((#chapter-iii))


### Chapter I ### 

### Preface ### 

This document describes the current C standard. The programming standard defines a set of rules governing code writing. The standard is mandatory. Follow it when writing C code.


### I.1 Why impose a standard? ###

The standard has two main purposes:
* Standardize your codes so that everyone can read them easily, students and controllers.
* Write codes that are simple and easy to understand.



### I.2 Standard in your renderings ###

* All of your C code files must conform to `standard 42'. The standard will be checked by your proofreaders and even the slightest error in the standard will give a grade of 0 to your project or your exercise.

* The proofreading utility used in addition to your assignment defense will run a program called `Norminette'. `Norminette' will check a subset of the standard rules that it can check.

* Note that only the result of `Norminette' is to be taken into account. In this way everyone will be equal in the face of the standard. You will find a list of the standard rules that `Norminette' currently manages at the end of this document. This list will be updated regularly, so keep an eye on it.


### I.3 Tip ###

* As you will quickly realize, the standard is not a limitation. On the contrary, the standard is a safeguard to help you write simple and basic code in ``C''. This is why it is absolutely essential that you code directly from the standard, albeit coding more slowly in the early hours. A source file containing a standard error is just as bad as a file with ten. Be diligent and the standard will soon become something automatic for you.


### Chapter II ###

### Standard 42 ###


## II.1 Naming convention. ##

Mandatory part:

* The name of a structure `struct` must begin with `s_`.
* The name of the data type `typedef` must begin with `t_`.
* The name of a union `union` must begin with `u_`.
* The name of the enumerated data type `enum` must begin with `e_`.
* Global name must begin with `g_`.
* Variable names, function names must consist exclusively of lowercase letters,
numbers and `_` (Unix Case).
* File and directory names must start with lowercase letters, numbers
and `_` (Unix Case).
* Parts of compound names will be separated by `_` (underscore).

Recommended part:

* Syntactic objects (variables, functions, macros, types, files or directories) should have the most explicit or mnemonic names. Only `counters' can be named as you wish.
* Abbreviations are allowed because they allow you to greatly reduce the size of a name without losing its meaning.
* All identifiers (functions, macros, types, variables, etc.) must be in English.
* Any use of a global variable must be justified.

![1](src/001.png)





## II.2 Formatting ##

* All your files should start with the standard `header 42` from the first line. 

This header is available by default in the `emacs` and [`vim`](../Notes_to_help/vim.md) editors in dumps.

To create a header via the [[VSCode]](https://code.visualstudio.com/) editor, use the [[42 Header]](https://marketplace.visualstudio.com/items?itemName=kube.42header) extension.

![2](src/002.png)

* Each function must contain no more than 25 lines, not including curly brackets in the function block.

An example of a five-line function:

![3](src/003.png)

* You should indent your code using a tab of 4 spaces (this is not equivalent to 4 spaces, it really should be a tab). In its basic configuration your editor can insert spaces instead of tabs, be careful. Consult your publisher's documentation if in doubt.
* Each line can contain no more than 80 columns, including comments.

> Note: tabulation is not counted for a column, but for the `n` spaces it represents

* Only one declaration per line.
* Only one instruction per line.
* An empty string must not contain spaces or tabs.
* A string must never end with spaces or tabs.
* The opening or closing parenthesis must be one on its own line with the correct identification. A special case is `struct` / `union` / `enum` / `typedef`. They are discussed below.
* You must return to the line at the end of the control structure (`if`, `while`, etc.).
* You must put curly braces after the control structure if the block has more than one operator.

![4](src/004.png)

* Each comma or semicolon must be followed by a space unless we are at the end of a line.
* Each operator (binary or ternary) and its operands must be separated by a space, and only one. However, there should be no space between a unary operator and its operand.
* Every keyword in C must be followed by a space, except for type specifiers (such as `int`, `char`, `float`, `const`, etc.), and `sizeof`.
* An expression returned with the `return` keyword must be enclosed in parentheses.

![5](src/005.png)

* Each variable declaration must be indented in the same column. Pointer stars must be glued to the variable name and to each other.
* The variable type and its identifier must be separated by at least one tab.
* Only one variable declaration per line.
* No declaration and initialization on the same line, except for global variables, static variables, constants, and array initialization. In the latter case in particular, the array initialization expression must be standard (curly braces, commas, ...).

![6](src/006.png)

* Declarations must be at the beginning of a block and must be separated from the implementation by an empty line.
* There must be no blank lines in the middle of the declaration or implementation.

![7](src/007.png)

* You can return to the line during the same instruction or control structure, but you must add an indent on the parentheses or assignment operator. Operators must be at the beginning of the line. Line indentation affects the readability of your code, so be measured. More generally, if you have too long instructions or expressions, it's because you haven't considered your code enough.

![8](src/008.png)





## II.3 Function Parameters ##


* A function takes no more than 4 named parameters.
* A function that takes no arguments must be explicitly prototyped with the word `void` as an argument.

![9](src/009.png)





## II.4 Functions ##

* Function prototype parameters must have names.
* You can declare no more than 5 variables per block.
* Your function identifiers must be aligned in the same file(refers to header files).
* Each function definition must be separated by a blank line from the next.
* The return type of a function and the identifier of that function must be separated by at least one tab

![10](src/010.png)

* Remember that we always put a space after a comma or semicolon, but only if we are not at the end of a line.

![11](src/011.png)





## II.5 Definition of type `struct`, `enum` or `union` (structure, enumeration or union) ##

* Anonymous structures, unions and enumerations are forbidden.
* Declarations of `struct`, `enum` or `union` must be in the global scope.
* You must put a tab before the identifier when declaring `struct`, `enum` or `union`.

![12](src/012.png)

* When you declare a variable of type `struct`, `enum`, or `union`, you put only a space in the type.

![13](src/013.png)

* You must use a tab between the two `typedef` parameters.

![14](src/014.png)

* When you declare `struct`, `enum` or `union` with `typedef`, all rules apply, and you must map the name of `typedef` to the name of the structure, union or enumeration.
* In this particular case, the name `typedef` can be on the same line as the closing curly bracket.

![15](src/015.png)






## II.6 Headers ##

* Only header inclusions (system or not), data structure definitions, definitions, prototypes, and macros are allowed in header files.
* Any header inclusion must be justified in both `.c' and `.h'.
* All `.h' inclusions must be made at the beginning of the file (`.c' or `.h').
* The standard also applies to headers.
* Headers must be protected against double inclusion. If the file `foo.h`, the control macro is `FOO_H`.

![16](src/016.png)

* In the unique and specific case of a comment line to the right of `#endif`, the comment standard does not apply (see later in this document).
* The inclusion of the `.h' header, which is not used, is forbidden.
* Macros must reside exclusively in `.h' files. Only macros which activate functionalities (such as `BSD_SOURCE`) are allowed in `.c` files.





## II.7 Macros and Preprocessor ##

* Definitions that define code are forbidden.
* Multi-line macros are forbidden.
* Only macro names are capitalized.

![17](src/017.png)

* Characters following `#if`, `#ifdef` or `#ifndef` must be indented one space at each level.

![18](src/018.png)

* There must be no `#if`, `#ifdef` or `#ifndef` after the first function definition in `.c





## II.8 Prohibited things! ##


You are not allowed to use:

* `for`.
* `do . . . .while`
* `switch`
* `case`
* `goto
* Nested ternary operators `? 

![19](src/019.png)

* Ternary operators used for anything other than a destination.

![20](src/020.png)

* Variable size arrays (`VLA` variable Length Array)






## II.9 Comments ##


* Comments can be found in all source files.
* There should be no comments in the body of functions.
* Comments begin and end on the same line. All intermediate lines are lined up with them and start with `**`.
* No C++ comments `//`.
* Your comments must be in English and useful.
* A comment cannot justify a garbled function.

![21](src/021.png)






## II.10 Files ##

* You can't do `include' files `.c'. Ever. Even if someone told you to do it.
## You cannot have more than 5 function definitions in `.c'.





## II.11 Makefile ##

* The rules `$(NAME)`, `clean`, `fclean`, `re`(relink) and `all` are mandatory.
* A project is considered non-functional if `Makefile` `relink`.
* In the case of a multibinary project, in addition to the previous rules, you must have a `all` rule compiling all binaries as well as a rule specific to each compiled binary.
* In the case of a project that uses a function library (such as `libft`), your `Makefile` should automatically compile that library.
* The use of a wildcard (such as `*.c`) is prohibited.




# Chapter III

Norminette


In its current version, `Norminette' checks the rules in this section.
We will update this section regularly. Of course, all standard rules must be followed, including those that Norminette does not already check and those that are not automatically checked, but you should only check the following rules during mutual patching. Refer to the previous sections for the details of each rule.

* All your files must start with the standard `header 42' from the first line.
* Each function must contain no more than 25 lines without including curly braces in the function block.
* Each line may not contain more than 80 columns, including comments. (Note that a tab does not count for 1 column, but for the n spaces it represents).
* Only one instruction per line.
* An empty string must not contain spaces or tabs.
* A string must never end with spaces or tab characters.
* When you have the end of a control structure, you must return to the line.
* You must put a space after a keyword.
* You must put a space after a comma or semicolon if it is not the end of a line.
* You must put a space before and after a binary or ternary operator.
* You may not use : `for`, `do . . . while`, `switch`, `case` and `goto`.
* C++ comments `//` are not allowed.
* You can only make 5 function definitions per file.
* A function can only take 4 parameters.


 Translated with www.DeepL.com/Translator (free version)


