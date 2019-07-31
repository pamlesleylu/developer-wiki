# Directory Structure, Filenames and Imports

- Filenames should be in lowercase. It should then be followed by the type of file (e.g., dto, controller, service, etc.) and then file extension. Some examples are `accounts.controller.ts` and `create-account.dto.ts`  

- Use absolute paths when importing.  
    
	Instead of `import { DatabaseModule } from '../../database/database.module';`, use `import { DatabaseModule } from '@api/database/database.module';`
         
	The absolute paths are: 
	+  `@app` - `apps/lead-generation/src/app`
	+ `@env` - `apps/lead-generation/src/environments`
	+ `@api-interface` - `libs/api-interface/src/lib/`
	+ `@api` = `apps/api/src/app`

- Frontend Directory Structure    
      
	Application codes are in the `src/app` subdirectory. `@app` has been set up as an alias and can be used in import statements (e.g., `import { Account, SearchResponse } from '@app/shared/models';`).      
       

```
@app/
+-- modules/
|   +-- accounts-manager/
|       +-- details/
|       +-- relationship-map/
|       +-- account-details.resolver.ts
|       +-- account-manager.component.html
|       +-- account-manager.component.less
|       +-- account-manager.component.spec.ts
|       +-- account-manager.component.ts
|       +-- account-manager.datasource.ts
|       +-- account-manager.module.ts
|   +-- dashaboard/
|       +-- charts/
|           +-- chart-containers/
|                     .
|                     .
|                     .
|           +-- dashboard-revenue/
|       +-- dashboard.component.html
|       +-- dashboard.component.less
|       +-- dashboard.component.spec.ts
|       +-- dashboard.component.ts
|       +-- dashboard.module.ts
+-- shared/
|   +-- components/
|   +-- data/
|   +-- models/
|   +-- services/
+-- assets/
+-- environments/
+-- theme/
+-- app.component.html
+-- app.component.less
+-- app.component.ts
+-- app.module.ts
```

> 	- modules/: Angular modules are heavily used to group togehter common blocks of codes. This also allows the usage of lazy loading to break up the download of client-side codes. Some examples of modules are the `account-manaager.module.ts` and the `dashboard.module.ts`
> 	- shared/: where shared codes like common directives and components, models and services are placed
> 	- assets/: where static files like images and fonts are stored


# Best Practices

## General

1. Make code expressive such that it can be easily understood by people. With this, comments can be optional. Comments are still code that need to be maintained. If code is littered with comments, every time the code changes, the corresponding comment needs to be updated. Comment the code to explain a very complicated algorithm (only if code can't be simplified) or to document the reason why the logic is as it is.


## CSS

1. Never hard code font sizes. Either use `em`, `rem` or the variable from variables.less
1. Never hard code colors. Use a variable from `variables.less`

# Coding Standards

## Indention
1. Use **2 spaces** for each indention. Install VSCode extension https://github.com/editorconfig/editorconfig-vscode to read .editorconfig file


## Whitepsaces

### Typescript
1. Use 1 space before leading brace after function name (use `functionName() {` instead of `functionName(){`)
1. 1 space before opening parenthesis of condition (use `if (true) {` instead of `if(true) {`)
1. No space between function name and opening parenthesis (use `functionName() {` instead of `functionName () {`)
1. No spaces inside parentheses (use `console.log(name)` instead of `console.log( name )`)
1. No spaces inside square brackets (use `[1, 2, 3]` instead of `[ 1, 2, 3 ]`)
1. Add space inside curly brackets (use `{ sum: 10 }` instead of `{sum: 10}`)
1. 1 space after colon of property name and value (use `{ sum: 10 }` instead of `{ sum:10 }`)
1. Spaces between operators (use `sum = first + second` instead of `sum=first+second`)

### CSS
1. Use 1 space before leading brace (use `.css-class {` instead of `.css-class{`)
1. 1 space after colon and before style value (use `color: red` instead of `color:red`)

## Naming Convention

1. Avoid single-character names. Make variable names and function names descriptive.

### TypeScript
1. Class names must be in PascalCase
2. Variable names must be in camelCase
3. Prefix private class variables with `_` (e.g., `_camelCase`)

### CSS
1. Class names must be in kebab-case

### Python
1. Variables must be in snake_case
2. Function names must be in snake_case

## Strings

### Typescript
1. Use single quotes for strings
2. Use interpolation instead of concatenation (e.g., use ``Hi, my name is ${name}`` instead of `'Hi, my name is ' + name`)

### HTML 
1. Use double quotes to enclose attribute values

### CSS
1. Use double quotes

### Python
1. Use single quotes unless there's a single quote within the string value, then use double quote

