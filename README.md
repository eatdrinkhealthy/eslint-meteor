# Code Style
Based on AirBnB ESLint, and forked from [OKGrow javascript style guide](https://github.com/okgrow/guides/tree/master/style-guide/code-style/javascript).

**NOTE:** for simpler (more current) steps to install and configure eslint, please refer to this [blog post by Jeffrey Zhen](https://blog.echobind.com/integrating-prettier-eslint-airbnb-style-guide-in-vscode-47f07b5d7d6a). This repo is still helpful in adding meteor and flow eslint configs, as well as providing links to eslint config resources.


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

1) To install the correct version of each package, run:

using npm...
```
(
  export PKG=eslint-config-airbnb;
  npm info "$PKG" peerDependencies --json | command sed 's/[\{\},]//g ; s/: /@/g' | xargs meteor npm install --save-dev "$PKG"
  meteor npm install --save-dev eslint-plugin-meteor
)
```

using yarn...
```
(
  export PKG=eslint-config-airbnb;
  npm info "$PKG" peerDependencies --json | command sed 's/[\{\},]//g ; s/: /@/g' | xargs yarn add --dev "$PKG"
  yarn add --dev eslint-plugin-meteor
)
```

2) Copy the latest `.eslintrc.json` to your project root:
```
curl -O https://raw.githubusercontent.com/eatdrinkhealthy/eslint-meteor/master/.eslintrc.json
```

## Rules & Style Guide References
* [ESLint.org Rules (all)](http://eslint.org/docs/rules/)
* [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript#airbnb-javascript-style-guide-)
* [Airbnb React/JSX Style Guide](https://github.com/airbnb/javascript/tree/master/react#airbnb-reactjsx-style-guide)
* [eslint-plugin-import supported rules list](https://github.com/benmosher/eslint-plugin-import#rules)
* [eslint-plugin-react supported rules list](https://github.com/yannickcr/eslint-plugin-react#list-of-supported-rules)
* [eslint-plugin-jsx-a11y supported rules list](https://github.com/evcohen/eslint-plugin-jsx-a11y#supported-rules)
* [eslint-plugin-meteor supported rules list](https://www.npmjs.com/package/eslint-plugin-meteor)

### ESLint for Flow
If you wish to add eslint checking for flow based rules, an eslint plugin for flow can be added. The eslint-plugin-flowtype package, and instructions for installation can be found [here](https://github.com/gajus/eslint-plugin-flowtype). Note, this package requires using babel-eslint parser. 
   
A default set of flow project rules can be found in this repo's `flow.eslintrc.json` file. Those rules and settings should be merged in to the project's `.eslintrc.json` file.

## Eslint Configuration File Versions
Typically changes in rules are versioned for ease of reference. Versions of eslint rule files can be seen on the [releases](https://github.com/eatdrinkhealthy/eslint-meteor/releases) page.

```
NOTE: to see a brief description of the rule changes for each version,
click on the ellipsis adjacent to the version number
```
### Compatability Issues
* [v1.3.0](https://github.com/eatdrinkhealthy/eslint-meteor/releases) 
    - __NOTE:__ eslint-plugin-import 'seems' to have a defect in v2.8.0, where the import/core-module settings does not work (modules listed there are not recognized)
        + check your yarn.lock or npm lock file, to determine which package version was installed
        + explicitly install v2.7.0, or a later version when a fix is known to have been added
    - new rule configurations were added to suppress errors which arose from the eslint-plugin-import v2.7.0
        + import/extensions
        + import/no-extraneous-depedencies
            * NOTE: this rule was added to address a likely defect with this version. the default values listed in the documentation do not seem to be correct, unless explicitly adding any setting for this rule (once any single value is added to this rule, all defaults them seem to function as described)
* [v1.2.0](https://github.com/eatdrinkhealthy/eslint-meteor/releases) introduces a settings section for meteor core module imports to address eslint errors when using some eslint plugin package versions
    - by default, the common meteor core modules `meteor, accounts-base, mongo` are included in this section
    - add or remove meteor core modules in this section as needed 
