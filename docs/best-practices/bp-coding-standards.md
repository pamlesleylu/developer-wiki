---
layout: page
title: Best Practices
permalink: /best-practices/coding-standards
---

## Coding Standards

### Indention
1. Use **2 spaces** for each indention. Install VSCode extension https://github.com/editorconfig/editorconfig-vscode to read .editorconfig file


### Whitepsaces

#### Typescript
1. Use 1 space before leading brace after function name (use `functionName() {` instead of `functionName(){`)
1. 1 space before opening parenthesis of condition (use `if (true) {` instead of `if(true) {`)
1. No space between function name and opening parenthesis (use `functionName() {` instead of `functionName () {`)
1. No spaces inside parentheses (use `console.log(name)` instead of `console.log( name )`)
1. No spaces inside square brackets (use `[1, 2, 3]` instead of `[ 1, 2, 3 ]`)
1. Add space inside curly brackets (use `{ sum: 10 }` instead of `{sum: 10}`)
1. 1 space after colon of property name and value (use `{ sum: 10 }` instead of `{ sum:10 }`)
1. Spaces between operators (use `sum = first + second` instead of `sum=first+second`)

#### CSS
1. Use 1 space before leading brace (use `.css-class {` instead of `.css-class{`)
1. 1 space after colon and before style value (use `color: red` instead of `color:red`)

### Naming Convention

1. Avoid single-character names. Make variable names and function names descriptive.

#### TypeScript
1. Class names must be in PascalCase
2. Variable names must be in camelCase
3. Prefix private class variables with `_` (e.g., `_camelCase`)

#### CSS
1. Class names must be in kebab-case

#### Python
1. Variables must be in snake_case
2. Function names must be in snake_case

### Strings

#### Typescript
1. Use single quotes for strings
2. Use interpolation instead of concatenation (e.g., use ``Hi, my name is ${name}`` instead of `'Hi, my name is ' + name`)

#### HTML 
1. Use double quotes to enclose attribute values

#### CSS
1. Use double quotes

#### Python
1. Use single quotes unless there's a single quote within the string value, then use double quote

