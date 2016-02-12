# Mozilla Foundation JS Style Guide

This repo contains an [ESLint](http://eslint.org/) "RC" file, which defines our standard JavaScript formatting rules.

Additionally, ESLint will discover common syntax errors in your code.

## Installing ESLint

Assuming you already have Node and npm installed, run `npm install -g eslint` in your terminal. This will create a global install of the ESLint CLI.

## Setup

Even if you have ESLint as a global install, it's good practice to require it as a development dependency for your project. This ensures that it will be available for all developers regardless of their local configuration. It will also ensure that Travis is able to validate your code, which is a good idea since it ensures malformed code won't be deployed or merged.

Simply run `npm install eslint --save-dev` in your project root.

After you include ESLint in your project you can use npm to install this RC file as a module, which you can direct ESLint to use.

Run `npm install mofo-style --save-dev`

Once you have ESLint and this RC file, you can lint your project's code.

*For example:*

`eslint --config ./node_modules/mofo-style/.eslintrc.yaml example.js`

It's recommended that you add a linting task to your project's task runner (preferably npm) as well as instruct Travis to execute it.

### Automated formatting

ESLint has a very helpful flag, `--fix`, which will automatically fix many styling issues for you (anything with a wrench icon on [this page](http://eslint.org/docs/rules/)).

If you incorporate `--fix` into your task runner, then it's recommended that you make a new task for it instead of adding it to your standard linting task. This will allow you to safely connect your standard read-only test to Travis without running the risk of it modifying your committed code.

## Extending The RC

The RC provided in this repo is intended to cover any ES6 based project. It's up to you to extend it to cover your project's specific environment(s). You can either specify environments via the `--env` flag or add a `eslintConfig` field to your `package.json` with your extended configuration. Read more on this topic [here](http://eslint.org/docs/user-guide/configuring).

## Rules

Refer to the [RC file](https://github.com/MozillaFoundation/mofo-style/blob/master/.eslintrc.yaml) and the corresponding [rule definitions](http://eslint.org/docs/rules) for specifics.

## EditorConfig

To more easily follow the rules you can add the [EditorConfig](http://editorconfig.org/) plugin to your editor (if it needs one), which will read an `.editorconfig` file. Unfortunately, EditorConfig doesn't allow you to dynamically set a path for the config, so you'll need to copy .editorconfig into your project's root directory if it doesn't already have one.
