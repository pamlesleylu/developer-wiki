---
layout: page
title: Directory Structure & Filenames
permalink: /best-practices/directory-structure
---

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
|   +-- module-1/
|       +-- sub-module-1/
|       +-- module-1.component.html
|       +-- module-1.component.less
|       +-- module-1.component.spec.ts
|       +-- module-1.component.ts
|       +-- module-1.module.ts
|   +-- module-2/
|       +-- module-2.component.html
|       +-- module-2.component.less
|       +-- module-2.component.spec.ts
|       +-- module-2.component.ts
|       +-- module-2.module.ts
+-- shared/
|   +-- components/
|   +-- data/
|   +-- models/
|   +-- services/
+-- assets/
+-- environments/
+-- styles/
+-- app.component.html
+-- app.component.less
+-- app.component.ts
+-- app.module.ts
```

> 	- modules/: Angular modules are heavily used to group togehter common blocks of codes. This also allows the usage of lazy loading to break up the download of client-side codes. 
> 	- shared/: where shared codes like common directives and components, models and services are placed
> 	- assets/: where static files like images and fonts are stored