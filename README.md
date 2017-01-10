# Code Style
Based on AirBnB ESLint, and forked from [OKGrow javascript style guide](https://github.com/okgrow/guides/tree/master/style-guide/code-style/javascript).

## Linting

**Every new project should contain a `.eslintrc.json` file in its root.**

As technologies and coding styles advance with time, each individual project can be updated with a simple refresh of `.eslintrc.json` if appropriate.  This will stop old projects lighting up like a christmas tree, and still enforce good coding style.

We will stay as close to the [AirBnB style guide](https://github.com/airbnb/javascript) as possible as it has quickly become an industry standard with ~36k stars on GitHub (more than Meteor!).

## Installation & Setup
### Notes
We will use the official [AirBnB eslint config](https://github.com/airbnb/javascript/tree/master/packages/eslint-config-airbnb).

The eslint, airbnb and meteor specific modules should be locally installed in the project (not global).

The default [eslint-config-airbnb export](https://github.com/airbnb/javascript/tree/master/packages/eslint-config-airbnb) contains all of the AirBnB ESLint rules, including ECMAScript 6+ and React. It requires `eslint, eslint-plugin-import, eslint-plugin-react, eslint-plugin-jsx-a11y`.

### Installation
1. To install the correct version of each package, run:
```
(
  export PKG=eslint-config-airbnb;
  npm info "$PKG" peerDependencies --json | command sed 's/[\{\},]//g ; s/: /@/g' | xargs meteor npm install --save-dev "$PKG"
  meteor npm install --save-dev eslint-plugin-meteor
)
```

2. Copy the latest `.eslintrc.json` to your project root:
`curl -O https://raw.githubusercontent.com/eatdrinkhealthy/eslint-meteor/master/.eslintrc.json`

## Rules & Style Guide References
* [ESLint.org Rules (all)](http://eslint.org/docs/rules/)
* [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript#airbnb-javascript-style-guide-)
* [Airbnb React/JSX Style Guide](https://github.com/airbnb/javascript/tree/master/react#airbnb-reactjsx-style-guide)
* [eslint-plugin-import supported rules list](https://github.com/benmosher/eslint-plugin-import#rules)
* [eslint-plugin-react supported rules list](https://github.com/yannickcr/eslint-plugin-react#list-of-supported-rules)
* [eslint-plugin-jsx-a11y supported rules list](https://github.com/evcohen/eslint-plugin-jsx-a11y#supported-rules)
* [eslint-plugin-meteor supported rules list](https://www.npmjs.com/package/eslint-plugin-meteor)

## Eslint Configuration File Versions
Typically changes in rules are versioned for ease of reference. Versions of eslint rule files can be seen on the [releases](https://github.com/eatdrinkhealthy/eslint-meteor/releases) page.

```
NOTE: to see a brief description of the rule changes for each version,
click on the ellipsis adjacent to the version number
```
### Compatability Issues
* [v1.2.0](https://github.com/eatdrinkhealthy/eslint-meteor/releases) introduces a settings section for meteor core module imports
    - by default, the common meteor core modules `meteor, accounts-base, mongo` are included in this section
    - add or remove meteor core modules in this section as needed 
