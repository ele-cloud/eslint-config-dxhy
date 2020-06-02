# [eslint-config-dxhy](http://dxhy.90paw.com:4005/eslint-config-dxhy)

[![Build Status](https://img.shields.io/travis/ele-cloud/eslint-config-dxhy.svg)](https://travis-ci.com/ele-cloud/eslint-config-dxhy) [![npm package](https://img.shields.io/npm/v/@ele-cloud/eslint-config-dxhy.svg)](https://www.npmjs.org/package/@ele-cloud/eslint-config-dxhy)

English / [简体中文](./README.zh-CN.md)

---

The Ele Cloud ESLint config is not only a progressive ESLint config for your React/Vue/TypeScript projects but also the best reference for configuring your personalized ESLint rules.

## Quick start

Please choose the following configuration based on the technology stack used by your project:

- [Built-in](#built-in)
- [React](#react)
- [Vue](#vue)
- [TypeScript](#typescript)
- [TypeScript React](#typescript-react)

## Philosophy

- Let [Prettier][] handle style-related rules
- Inherit [ESLint's philosophy](https://eslint.org/docs/about/#philosophy) and help everyone build their own rules
- High degree of automation: advanced rules management, test as a document, as a [website][]
- Keep up with the times, follow up the latest rules as soon as possible

## Usage

### Built-in

```bash
npm install --save-dev eslint babel-eslint eslint-config-dxhy
```

Create an `.eslintrc.js` in the root directory of your project, then copy the following content into it:

```js
module.exports = {
    extends: [
        'dxhy',
    ],
    env: {
        // Your environments (which contains several predefined global variables)
        //
        // browser: true,
        // node: true,
        // mocha: true,
        // jest: true,
        // jquery: true
    },
    globals: {
        // Your global variables (setting to false means it's not allowed to be reassigned)
        //
        // myGlobal: false
    },
    rules: {
        // Customize your rules
    }
};
```

### React

```bash
npm install --save-dev eslint babel-eslint eslint-plugin-react eslint-config-dxhy
```

Create an `.eslintrc.js` in the root directory of your project, then copy the following content into it:

```js
module.exports = {
    extends: [
        'dxhy',
        'dxhy/react',
    ],
    env: {
        // Your environments (which contains several predefined global variables)
        //
        // browser: true,
        // node: true,
        // mocha: true,
        // jest: true,
        // jquery: true
    },
    globals: {
        // Your global variables (setting to false means it's not allowed to be reassigned)
        //
        // myGlobal: false
    },
    rules: {
        // Customize your rules
    }
};
```

### Vue

```bash
npm install --save-dev eslint babel-eslint vue-eslint-parser eslint-plugin-vue eslint-config-dxhy
```

Create an `.eslintrc.js` in the root directory of your project, then copy the following content into it:

```js
module.exports = {
    extends: [
        'dxhy',
        'dxhy/vue',
    ],
    env: {
        // Your environments (which contains several predefined global variables)
        //
        // browser: true,
        // node: true,
        // mocha: true,
        // jest: true,
        // jquery: true
    },
    globals: {
        // Your global variables (setting to false means it's not allowed to be reassigned)
        //
        // myGlobal: false
    },
    rules: {
        // Customize your rules
    }
};
```

### TypeScript

```bash
npm install --save-dev eslint typescript @typescript-eslint/parser @typescript-eslint/eslint-plugin eslint-config-dxhy
```

Create an `.eslintrc.js` in the root directory of your project, then copy the following content into it:

```js
module.exports = {
    extends: [
        'dxhy',
        'dxhy/typescript',
    ],
    env: {
        // Your environments (which contains several predefined global variables)
        //
        // browser: true,
        // node: true,
        // mocha: true,
        // jest: true,
        // jquery: true
    },
    globals: {
        // Your global variables (setting to false means it's not allowed to be reassigned)
        //
        // myGlobal: false
    },
    rules: {
        // Customize your rules
    }
};
```

### TypeScript React

```bash
npm install --save-dev eslint typescript @typescript-eslint/parser @typescript-eslint/eslint-plugin eslint-plugin-react eslint-config-dxhy
```

Create an `.eslintrc.js` in the root directory of your project, then copy the following content into it:

```js
module.exports = {
    extends: [
        'dxhy',
        'dxhy/react',
        'dxhy/typescript',
    ],
    env: {
        // Your environments (which contains several predefined global variables)
        //
        // browser: true,
        // node: true,
        // mocha: true,
        // jest: true,
        // jquery: true
    },
    globals: {
        // Your global variables (setting to false means it's not allowed to be reassigned)
        //
        // myGlobal: false
    },
    rules: {
        // Customize your rules
    }
};
```

## Troubleshooting

### With VSCode

ESLint will not lint `.vue`, `.ts` or `.tsx` files in VSCode by default, you need to set your `.vscode/settings.json` like this:

```json
{
    "eslint.validate": [
        "javascript",
        "javascriptreact",
        "vue",
        "typescript",
        "typescriptreact"
    ]
}
```

### autoFixOnSave is not working

If you want to auto fix-on-save for `.vue`, `.ts` or `.tsx` files, you need to set your `.vscode/settings.json` like this:

```json
{
    "eslint.autoFixOnSave": true,
    "eslint.validate": [
        "javascript",
        "javascriptreact",
        {
            "language": "vue",
            "autoFix": true
        },
        {
            "language": "typescript",
            "autoFix": true
        },
        {
            "language": "typescriptreact",
            "autoFix": true
        }
    ]
}
```

### With Prettier

`eslint-config-dxhy` does not include all style-related rules in v3, so there is no need to install `eslint-config-prettier`. Just install `prettier` and related VSCode plugins.

Here is a `.prettierrc.js` configuration used by AlloyTeam for reference only:

```js
// .prettierrc.js
module.exports = {
    // max 100 characters per line
    printWidth: 100,
    // use 4 spaces for indentation
    tabWidth: 4,
    // use spaces instead of indentations
    useTabs: false,
    // semicolon at the end of the line
    semi: true,
    // use single quotes
    singleQuote: true,
    // object's key is quoted only when necessary
    quoteProps: 'as-needed',
    // use double quotes instead of single quotes in jsx
    jsxSingleQuote: false,
    // no comma at the end
    trailingComma: 'none',
    // spaces are required at the beginning and end of the braces
    bracketSpacing: true,
    // end tag of jsx need to wrap
    jsxBracketSameLine: false,
    // brackets are required for arrow function parameter, even when there is only one parameter
    arrowParens: 'always',
    // format the entire contents of the file
    rangeStart: 0,
    rangeEnd: Infinity,
    // no need to write the beginning @prettier of the file
    requirePragma: false,
    // No need to automatically insert @prettier at the beginning of the file
    insertPragma: false,
    // use default break criteria
    proseWrap: 'preserve',
    // decide whether to break the html according to the display style
    htmlWhitespaceSensitivity: 'css',
    // lf for newline
    endOfLine: 'lf'
};
```

## Scripts

```bash
# install dependencies
npm i
# build eslintrc like index.js, react.js, etc.
npm run build
# run tests
npm test
# autofix ESLint errors
npm run eslint:fix
# autofix prettier errors
npm run prettier:fix
# check if all rules are currently covered
npm run test:rulesCoverage
# publish new version
npm version <major|minor|patch>
git push --follow-tags
npm publish
```

## Q & A

### Why another ESLint config

Our team initially used Airbnb rules, but because it was too strict, some rules still needed to be personalized, which led to more and more changes in the future and finally decided to maintain a new set. After more than two years of polishing, `eslint-config-dxhy` is now very mature and progressive and has been welcomed by many teams inside and outside the company.

### Why not standard

The standard specification believes that everyone should not waste time in personalized specifications, but the entire community should unify a specification. This statement makes some sense, but it runs against the ESLint's design philosophy. Don't you remember how ESLint defeated JSHint and became the most popular JS code inspection tool? It is because of the plugin and configuration that ESLint advocates, which meets the individual needs of different technology stacks of different teams.

Therefore, `eslint-config-dxhy` also inherits the philosophy of ESLint. It will not force you to use our config. Instead, we help you to _make your config_ by referencing our examples, tests, websites and so on.

### Why not `airbnb`

1. `eslint-config-dxhy` has officially maintained `vue`, `typescript` and `react+typescript` rules. In contrast, airbnb's `vue` and `typescript` are maintained by third parties.
2. Progressive to ensure that we can keep up with the times, as mentioned earlier
3. Convenient personalization, including explanations and website examples

### Looks good, but I still choose `airbnb`

It's okay, `eslint-config-dxhy` believes that different teams and projects can have different configurations from the design concept. Although you choose to use `airbnb`, you can still come to our [website][] when you have personalized configuration needs.

## Reference

- [Alloyteam Code Guide](http://alloyteam.github.io/CodeGuide)
- [ESlint Code Guide](http://eslint.org/docs/user-guide/configuring)
- [ESlint Shareable Config](http://eslint.org/docs/developer-guide/shareable-configs)

[Prettier]: https://prettier.io/
[website]: http://dxhy.90paw.com:4005/eslint-config-dxhy/
[ESLint's philosophy]: https://eslint.org/docs/about/#philosophy
