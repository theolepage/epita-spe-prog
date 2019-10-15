
#  EPITA - SPE - Coding style




## Introduction

This documents aims to provide a set of coding rules spitted in the following parts:
1. Name
2. File
3. Symbol
4. Declaration and expression
5. Function
6. Control structure
7. Documenting and comment
8. Header

To indicate the level of requirement, this document relies on the following key words:
- MUST = The definition is an absolute requirement.
- MUST NOT = The definition is an absolute prohibition.
- SHOULD: You are recommended to apply the definition.
- SHOULD NOT = You are not recommended to apply the definition.
- MAY = Applying the definition is optional.

These key words are described in the [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt).


## 1. Name

### 1.1 name.sep

Words composing entity names (variables, C functions and files) MUST be separated by underscores.

### 1.2 name.abbr

Names MAY be abbreviated but only when it allows for shorter code without loss of meaning.

### 1.3 name.lang

Names MUST be expressed in English. Names SHOULD be expressed in correct English, i.e. without spelling mistakes.

### 1.4 name.case

Entity names (variables, C functions and files) MAY be expressed using lower case letters, digits and underscores only. More precisely they SHOULD be matched by the regular expression below.
```
[a-z][a-z0-9_]*
```




## 2 File

### 2.1 file.deadcode

In order to disable large amounts of code, you SHOULD NOT use comments. Delivered project sources SHOULD NOT contain disabled code blocks.

### 2.2 file.dos

The DOS CR+LF line terminator MUST NOT be used.

### 2.3 file.terminate

The last line of this file MUST NOT be a single line feed.

### 2.4 file.indentation

Indentation MUST be done using whitespaces only, tabulations MUST NOT appear in your source code.

### 2.5 file.cols

Lines MUST NOT exceed 80 columns in width, excluding the trailing newline character.

### 2.6 file.spurious

There MUST NOT be any blank lines at the beginning or the end of the file.

### 2.7 file.trailing

There MUST NOT be any whitespace at the end of a line.




## 3 Symbol

### 3.1 braces

All braces MUST be on their own line.

### 3.2 comma

The comma MUST be followed by a single space, except when they separate arguments in function (or macro) calls and declarations and the argument list spans multiple lines: in such cases, there MUST NOT be any trailing whitespace at the end of each line.

### 3.3 semicolon

The semicolon MUST NOT be preceded by a whitespace, except if alone on its line. However, a semicolon SHOULD NOT be alone on its line. If the semicolon is followed by a non-empty statement, a single whitespace MUST follow the semicolon.

### 3.4 keyword

Keywords MUST be followed by a single whitespace, except the sizeof keyword which MUST NOT be followed by a whitespace. Keywords without arguments MUST NOT be separated from the following semicolon by a whitespace.




## 4 Declaration and expression 

### 4.1 decl.var

Variables SHOULD be initialized at the point of declaration.

### 4.2 decl.pointer

The pointer symbol (*) in declarations MUST appear next to the variable name, not next to the type.

```c
void func(const char *str);
```

### 4.3 decl.multiline

When initializing a local structure (a C99 feature) or a static array, the initializer value MAY start on the same line as the declaration.

If the initialization is too long and exceed the column limitation, the initializer value MUST start on the line after the declaration. In this case, each brace must be on their own line.

This rule is an exception of the braces rule.

```c
// Correct
int array[5] = { 1, 2, 3 };

// Incorrect
int array[5] =
{ 1, 2, 3 };

// Crrect
int array[5] =
{
	1, 2, 3
};
```

### 4.4 decl.type

When negative values are impossible, you MUST specify unsigned. Appropriate typedef (such as size_t) SHOULD be used when available.

### 4.5 exp.multiline

Expressions MAY span over multiple lines. When a line break occurs within an expression, it MUST appear just before a binary operator, in which case the binary operator MUST be indented with at least an extra indentation level.

```c
int very_long_var = 1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 + 9 
	+ 20 + 21;
```

### 4.6 exp.padding

All binary and ternary operators MUST be padded on the left and right by one space, including assignment operators. Prefix and suffix operators MUST NOT be padded, neither on the left nor on the right. When necessary, padding is done with a single whitespace.

### 4.7 exp.parentheses

There MUST NOT be any whitespace following an opening parenthesis nor any whitespace preceding a closing parenthesis. 






## 5 Function

### 5.1 fun.arg.count

Functions MUST NOT take more than 4 arguments.

### 5.2 fun.arg.space

There MUST NOT be any whitespace between the function or method name and the opening parenthesis for arguments, either in declarations or calls.

### 5.3 fun.prototype

Prototypes MUST specify both the return type and the arguments type.

### 5.4 fun.length

Functions’ body MUST NOT contain more than 25 lines. The enclosing braces, blank lines and comments are excluded from this count.

The following function would then have 4 counting lines:

```c
size_t array_min_index(const int *array, size_t length)
{
	size_t res = 0;
	for (size_t i = 0; i < length; i++)
	{
		res = (array[i] < array[res]) ? i : res;
	}
	return res;
}
```









## 6 Control structure

### 6.1 ctrl.switch

Incomplete switch constructs (that is, which do not cover all cases) MUST contain a default case, unless when used over an enumeration type, in which case it SHOULD NOT contain one.

### 6.2 ctrl.single

The conditional parts of if and while control structures, and the else keyword MUST be alone on their line.

### 6.3 ctrl.indentation

The code following a control structure MUST be indented. The number of whitespaces MUST be 4. If the code following a control structure is composed of only one expression, you MAY omit the braces.








## 7 Documenting and comment

### 7.1 doc.style

You SHOULD use the imperative when documenting, as if you were giving order to the function or entity you are describing.

### 7.2 comment.multi

The delimiters in multi-line comments MUST appear on their own line. Intermediary lines are aligned with the delimiters and start with **.

```c
/*
 * Incorrect
 */

/* Incorrect
 */

/*
** Correct
*/

/**
** Correct
*/

/* Correct */

// Correct
```

### 7.3 doc.obvious

You SHOULD NOT document the obvious.

### 7.4 comment.lang

Comments MUST be written in the English language. They SHOULD NOT contain spelling errors, whatever language they are written in. However, omitting comments is no substitute for poor spelling abilities.




## 8 Header

### 8.1 header.guard

Header files MUST be protected against multiple inclusions. You MAY use the format presented below.

```c
#ifndef FOO_H
#define FOO_H

//Content of foo++.h

#endif /* ! FOO_H */
```
