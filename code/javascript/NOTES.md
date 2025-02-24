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

