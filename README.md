# stylelint-selector-bem-pattern

A [stylelint](https://github.com/stylelint/stylelint) plugin that incorporates [postcss-bem-linter](https://github.com/postcss/postcss-bem-linter).

To learn more about postcss-bem-linter, please read [that module's documentation](https://github.com/postcss/postcss-bem-linter).

## Installation

```
npm install stylelint-selector-bem-pattern
```

## Usage

Add it to your stylelint config `plugins` object, then add it to your rules,
specifying the severity and your postcss-bem-linter settings as the primary option.
Like so:

```js
// .stylelintrc
{
  "plugins": {
    "selector-bem-pattern": "stylelint-selector-bem-pattern"
  },
  "rules": {
    // ...
    "selector-bem-pattern": [2, {
      "componentName": "[A-Z]+",
      "componentSelectors": {
        "initial": "^\\.{componentName}(?:-[a-z]+)?$",
        "combined": "^\\.combined-{componentName}-[a-z]+$"
      },
      "utilitySelectors": "^\.util-[a-z]+$"
    }],
    // ...
  }
}
```

For more examples of postcss-bem-linter configuration possibilities,
please read [that module's documentation](https://github.com/postcss/postcss-bem-linter).
Keep in mind that if your stylelint config is JSON you will have to use strings to
specify your selector patterns (as above).
