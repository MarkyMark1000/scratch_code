# OVERVIEW OF SYSTEM SETUP

We use vitest for testing ecma scripts:

Vitest Website:
[Vitest](https://vitest.dev/guide/)

The Node Website tells you how to setup javascript for commonjs or ecma:
[Node - commonjs and ecsma] (https://nodejs.org/docs/latest/api/esm.html#introduction)

## Setup

I used yarn for this:

```
npm install -D vitest        yarn add -D vitest
```

To get coverage working, I also had to install this:
```
npm install @vitest/coverage-v8     OR yarn add @vitest/coverage-v8
```

Next, create the main.js file and the main.test.js file to contain your code and your
unit test.

Adjust the package.json file so that it contains the following:

```
"type": "module",
"scripts": {
    "test": "vitest",
    "cov": "vitest run --coverage"
},
```

## ecma

To set the files as common js you can do any of the following:
- use .mjs files
- use --input-type "module" as an argument
- use "type": "module", which is what I have done in this project

## Prettier

Prettier Website:
[Prettier](https://prettier.io/docs/install)

```
npm install --save-dev --save-exact prettier        yarn add --dev --exact prettier
```

Then create some config files:

```
node --eval "fs.writeFileSync('.prettierrc','{}\n')"
node --eval "fs.writeFileSync('.prettierignore','# Ignore artifacts:\nbuild\ncoverage\n')"
```

I added node_modules to the ignore file so that we don't format the node_modules directory.

Then to format the files:

```
npx prettier . --write          yarn prettier . --write
```

I added commands to package.json and the makefile to simplify this.

## ESLint

ESLint Website

```
npm init @eslint/config@latest          yarn create @eslint/config
```

I had some problems getting this to work using the website instructions, but
found adjusting the eslint.config.mjs file so that it says this helped fix
problems:

```
{languageOptions: { globals: globals.node }},       // was originally something else
```

I then managed to get it to run using the following command:

```
npx eslint *.js            yarn eslint *.js
```
