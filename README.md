# Mozilla Foundation JS Style Guide

This repo contains "RC" files, which represent our standard rules, for several different JavaScript linters ([JSHint](http://jshint.com/), [JSCS](http://jscs.info/), and [JSBeautifier](https://github.com/beautify-web/js-beautify)).

In your project you can use npm to install the RC files as a module, which can then be individually used by your project's build system (eg: Gulp or Grunt). Most linting tasks/plugins allow you to specify an external RC file, which you can point to your copies in `node_modules`.

Simply run `npm install mofo-style --save-dev`.

## Task Naming

You should have at least 2 style tasks in your runner.

- `validate` - Run all 3 linters in read only mode and report any errors.
- `clean` - Run all 3 linters but also run JSBeautifier in write mode to automatically fix any formatting errors that it's capable of repairing.

## Rules

Refer to the [RC files](https://github.com/MozillaFoundation/javascript-style-guide/tree/master/linters) for specifics.

### Roadmap

- **Deprecate JSBeautifier** - JSCS has [an open issue](https://github.com/jscs-dev/node-jscs/issues/516) to add autoformatting, which will eliminate the need for JSBeautifier.