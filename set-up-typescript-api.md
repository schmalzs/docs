# Setting Up TypeScript API

## Initialize Yarn

```
$ yarn init
```

## Initialize TypeScript

```
$ yarn add --dev typescript
$ yarn tsc --init --rootDir src --outDir dist
```

## Set Up Scripts to Run App

```
$ yarn add --dev nodemon ts-node
```

package.json

```
"scripts": {
  "build": "tsc",
  "dev": "nodemon --watch src/**/*.ts --exec ts-node src/index.ts",
  "start": "node dist/index.js"
}
```

## Set Up ESLint + Prettier

```
$ yarn add --dev eslint prettier eslint-config-prettier eslint-plugin-prettier @typescript-eslint/eslint-plugin @typescript-eslint/parser
```

.eslintrc.js

```
module.exports = {
  parser: '@typescript-eslint/parser',
  parserOptions: {
    ecmaVersion: 2018,
    sourceType: 'module',
  },
  extends: [
    'plugin:@typescript-eslint/recommended',
    'plugin:prettier/recommended',
  ],
  plugins: ['@typescript-eslint', 'prettier'],
  rules: {
    'prettier/prettier': ['error'],
  },
};
```

.eslintignore

```
/build
/node_modules
```

.prettierrc.js

```
module.exports = {
  singleQuote: true,
  trailingComma: 'es5'
};
```

package.json

```
"scripts": {
  "lint": "eslint ."
}
```

## Set Up Express

```
$ yarn add express
$ yarn add --dev @types/express
```
