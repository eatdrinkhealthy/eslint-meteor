# Code Style
Based on AirBnB ESLint, and forked from OKGrow code style guide.

## Linting

**Every new project should contain a `.eslintrc.json` file in its root.**

As technologies and coding styles advance with time, each individual project can be updated with a simple refresh of `.eslintrc.json` if appropriate.  This will stop old projects lighting up like a christmas tree, and still enforce good coding style.

We will stay as close to the [AirBnB style guide](https://github.com/airbnb/javascript) as possible as it has quickly become an industry standard with ~36k stars on GitHub (more than Meteor!).

## Installation & Setup

We will use the official [AirBnB eslint config](https://github.com/airbnb/javascript/tree/master/packages/eslint-config-airbnb).

Install the eslint, airbnb and meteor specific modules to the project itself (not global).

The default eslint-config-airbnb export contains all of the AirBnB ESLint rules, including ECMAScript 6+ and React. It requires `eslint, eslint-plugin-import, eslint-plugin-react, eslint-plugin-jsx-a11y`.

To ensure all correct versions are installed, run:
```
(
  export PKG=eslint-config-airbnb;
  npm info "$PKG" peerDependencies --json | command sed 's/[\{\},]//g ; s/: /@/g' | xargs meteor npm install --save-dev "$PKG"
  meteor npm install --save-dev eslint-plugin-meteor
)
```

Copy the latest `.eslintrc.json` to your project root:

`curl -O https://raw.githubusercontent.com/eatdrinkhealthy/eslint-meteor/master/.eslintrc.json`

## Rule File Versions
Typically changes in rules are versioned for ease of reference. Versions of eslint rule files can be seen on the [releases](https://github.com/eatdrinkhealthy/eslint-meteor/releases) page.

```
NOTE: to see a brief description of the rule changes for each version,
click on the ellipsis adjacent to the version number
```
