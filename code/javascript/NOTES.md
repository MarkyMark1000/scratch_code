# OVERVIEW OF SYSTEM SETUP

Jest Website:
[Jest](https://jestjs.io/docs/getting-started)

## Setup

I used yarn for this:

```
npm install --save-dev jest        yarn add --dev jest
```

Next, create the main.js file and the main.test.js file to contain your code and your
unit test.

Adjust the package.json file so that it contains the following:

```
"scripts": {
    "test": "jest",
    "cov": "jest --coverage"
},
```

## Prettier

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
