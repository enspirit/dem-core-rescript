# Doc-e-mate, your document's best friend

This repository holds the core library of the ReScript version of Doc-e-mate,
a tool that allows you to generate and print documents written in Markdown,
styled in CSS, with business data injected from JSON or YAML files.

```
> Text     + Data  + Style  ->  Beautiful Business Documents
> HTML     + Json  + CSS    ->  Beautiful Business Documents
> Markdown + YAML  + SASS   ->  Beautiful Maintainable Business Document
```

*This is a split of the https://github.com/enspirit/dem-rescript project,
in order to remove unwanted dependencies between the modules of the tool.*

This is a ReScript library. Its main interface is hold in 
https://github.com/enspirit/dem-core-rescript/blob/main/src/app.resi .

Use the `compile` function to generate an html string from markdown, css and
json string inputs.

All parameters are optional. Default values can be found in
https://github.com/enspirit/dem-core-rescript/blob/main/src/app.res .

Find examples of use in the tests file 
https://github.com/enspirit/dem-core-rescript/blob/main/__tests__/app_spec.res .

Use the `dem-fsi-rescript` library (https://github.com/enspirit/dem-fsi-rescript)
to generate your document and convert it into a pdf document.

### Mustache partials

Doc-e-mate supports mustache partials. Please take a look at Mustache partials
documentation first: https://mustache.github.io/mustache.5.html.

`TL;DR`: you may include text from some separated markdown dependencies and 
identified using the following syntax in your main text: `{{> white_hat}}`.
In this case, the library will load the `white_hat` partial from the given
partials dictionnary.

Also do not hesitate to use several levels of inclusion: `white_hat` may refer
to another markdown partial called `powers/shield_of_light`. Use the
`partials_dependencies` function to scan the given markdown string in order to
create the dictionnary to use in the `compile` function.

### Build your data with javascript

Doc-e-mate supports data file written in CommonJS. Use the `dem-fsi-rescript`
library (https://github.com/enspirit/dem-fsi-rescript) for that purpose.

## Hacking

Doc-e-mate is written in ReScript, with great help from the
following libraries:
* mustache.js, see https://mustache.github.io/
* markdown-it, see https://github.com/markdown-it/markdown-it and https://spec.commonmark.org/

### Getting started with the source code

Clone the repository, then run the following command to initialize your dev
environment:

```
npm install
```
### Building the tool

You can build the program with

```
npm run re:build
```

or in watch mode with

```
npm run re:start
```

### Running tests

You can run the tests in watch mode using:

```
npm run testw
```

 ## Publishing

 All the releases were published using `np` so far. Cf.
 https://github.com/sindresorhus/np
