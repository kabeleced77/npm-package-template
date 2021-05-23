# Create TypeScript-based NPM package base on this project
This project provides a kind of a template for a NPM package using 
- `TypeScript` for programming language
- `ES-lint` for linting
- `Prettier` for formatting code
- `Editorconfig` for formatting code while writing
- `Travis` for continuos integration
- `Mocha` / `Chai` for testing
- [Optionally] `js-dom` mock-up DOM in tests
- [Optionally] `sinon-chrome` mock-up `chrome` in tests

This template is based on several tutorials like followings
- https://blog.logrocket.com/publishing-node-modules-typescript-es-modules/
  - NPM package using TypeScript
  - Publish ES and CommonJS
- https://itnext.io/step-by-step-building-and-publishing-an-npm-typescript-package-44fe7164964c
  - NPM package using TypeScript
  - Linting using `ts-lint` (`es-lint` is recommended though, at least used here)
  - Formating using `prettier`
  - Testing using `jest`
  - Publishing using `npm` magic scripts
- https://codeburst.io/https-chidume-nnamdi-com-npm-module-in-typescript-12b3b22f0724
  - New NPM package using TypeScript
  - Testing using Mocha and Chai
  - CI using Travis

# How to use this template

1.  Clone template repository 
    ```
    git clone 
    ```
1.  Remove this `README.md` and rename prepared one
    ```
    mv README-for-package.md README.md
    ```
1.  Adjust content of new `README.md`
    1.  Replace placeholder by name of package
    1.  Fill in needed information
1.  Adjust content of `package.json`
    1.  Replace placeholder by name of package
    1.  Remove packages not needed (can also be done later by `npm uninstall package_name`)
    1.  Change license if needed
1.  Make a new `git` repository based on template (current `git` files are removed)
    ```
    rm -rf .git 
    git init .
    git add .
    git commit -m "First commit"
    ```


# Create new NPM package based on template

## Preconditions
1.  Make sure you have `npm` account for publishing
1.  Make sure you have `travis` account for continuos integration

## Preparations 

1.  When `package.json` has been finalised regarding needed packages install latest versions of each configured package to start with
    ```
    npx npm-check-updates && npm-check-updates -u && npm install
    ```
    If needed, force it
    ```
    npx npm-check-updates && npm-check-updates -u && npm install --force
    ```    
1. Create source code of package in folder `src`
1. Create tests of package in folder `test`
1. Import and export modules -> create `index.ts`, e.g.
    ```javascript
	import { IFromJson } from "./IFromJson.js";
	import { IKey } from "./IKey.js";
	import { ISetting } from "./ISetting.js";
	import { KeyString } from "./KeyString.js";

	export { IFromJson, IKey, ISetting, KeyString };
    ```
      Keep file extension in order to support ES modules.
1.  Build source code
1.  Test source code
1.  Package NPM package
1.  [Optionally] Pre-publish package
1.  Publish package