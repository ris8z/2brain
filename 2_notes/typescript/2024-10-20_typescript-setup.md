---
date: 2024-10-20 
tags: 
    - typescript
hubs: 
    -   "[[2024-10-20_typescript-basics]]"
---

# typescript setup

## Requirments
- node `node -v` 
- npm `npm -v`  

## Create a Project dir
```bash
mkdir my_first_project_typescript
cd my_first_project_typescript
```

## Create a **packege.json** file
This file will keep track of all your project dependencies and scripts
```bash
npm init -y
```

## Install typescript
This install typescript as a dependencies of our project (not globaly)
```bash
npm install typescript --save-dev
```

## Create **tsconfig.json** file
This file tells the typescript complier (**tsc**) how to complile your project.
```bash
npx tsc --init
```
This will create a default tsconfig.json file with various options. 

- __"target"__: The version of JavaScript you want to compile to (ES5, ES6, etc.).
- __"module"__: The module system to use (commonjs, esnext, etc.).
- __"strict"__: Enable strict type-checking.
- __"outDir"__: Specifies the directory where compiled JavaScript files will go.
- __"rootDir"__: Specifies the directory of your TypeScript source files.

This is a simple exmpale:
```json
//tsconfig.json
{
  "compilerOptions": {
    "target": "ES6",
    "module": "commonjs",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true,
    "outDir": "./dist",
    "rootDir": "./src"
  },
  "include": ["src/**/*"],
  "exclude": ["node_modules"]
}
```

## Test
create a src dir
```bash
mkdir src
```
add a simple ts file
```javascript
// scr/index.ts
const greeting: string = "Hello world!";
console.log(greeting);
```
complie the ts file:
```bash
npx tsc
```

after copiling the file run the js created
```bash
node dist/index.js
```

## Build script
we can edit the **packege.json** to get a similar behaviour of a makefile
```bash
{
    "scripts": {
        "build": "tsc",
        "start": "node dist/index.js"
    }
}
```
Now, instead of running npx tsc and node dist/index.js separately, you can run:
```bash
#Compile TypeScript
npm run build
#Run the Project
npm start
``` 
