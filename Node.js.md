# Node.js
Node.js (often simply called `node`) is a general purpose programming environment built on top of Google's V8 JavaScript engine.

## Install
Download the installer for your system from [http://nodejs.org/download/](http://nodejs.org/download/)

You now have `node` and `npm` installed in your `$PATH`.

## Using `node`
`node` is the program interpreter. You can run a javascript program:

```
$ node program.js
```

You can also start node in interactive ([REPL](http://nodejs.org/api/repl.html)) mode:
```
$ node
```

## Using `npm`
`npm` is used to install modules and to publish your own. It is reasonably well documented at the [npm website](https://www.npmjs.org/doc/cli/npm.html).

In brief, you can find modules to use at [npm.im](https://npm.im) with the search feature. Then, you can install them:

```
$ npm install foo
```

Modules are installed in the `node_modules/` directory in your project.

When you first clone a project using node, you need to run `npm install` which will install all of the project's module dependencies specified in the `package.json` file in the project root.


## Running node programs
Typically this is done via
```
$ npm run
```

## Testing node programs
Typically this is done via
```
$ npm test
```

## `package.json` & configuration
`package.json` has lots of fun stuff for your project. All of the fields are optional. A great resourcce for exploring what fields are available is [package.json.nodejitsu.com/](http://package.json.nodejitsu.com/)
