# Node.js
Node.js (often simply called `node`) is a general purpose programming environment built on top of Google's V8 JavaScript engine.

🚧 This guide is provided for historical purposes—new CfA projects should not use Node.js 🚧

## Install
Download and run the installer for your system from [http://nodejs.org/download/](http://nodejs.org/download/)

You now have `node` and `npm` installed in your `$PATH`.


## Using `node`
`node` is the program interpreter. You can run a javascript program:

```console
$ node program.js
```

You can also start node in interactive ([REPL](http://nodejs.org/api/repl.html)) mode:
```console
$ node
```


## Using `npm`
`npm` is used to install modules and to publish your own. It is reasonably well documented at the [npm website](https://www.npmjs.org/doc/cli/npm.html).

In brief, you can find modules to use at [npm.im](https://npm.im) with the search feature. Then, you can install them:

```console
$ npm install foo
```

Modules are installed in the `node_modules/` directory in your project.

When you first clone a project using node, you need to run `npm install` which will install all of the project's module dependencies specified in the `package.json` file in the project root.


## Running node programs
Typically this is done via
```console
$ npm start
```

When you first clone a repository, make sure to run `$ npm install` in the directory to download all of the dependencies.

When creating a node program, you can set the start script by added it to your `package.json` like this:
```js
{
  "scripts": {
    "start": "node index.js"
    }
}
```


## Testing node programs
Typically this is done via
```console
$ npm test
```

When you first clone a repository, make sure to run `$ npm install` in the directory to download all of the dependencies.

When creating a node program, you can set the test script by added it to your `package.json` like this:
```js
{
  "scripts": {
    "test": "node test.js"
    }
}
```


## Scripting tasks (builds, testing, etc)
In addition to `start` and `test` scripts mentioned above, npm includes a way to run other tasks related to your program by
adding them to the `scripts` property in `package.json`. This is a powerful and standard way to add functionality to node
programs. Read [this excellent blog post](http://substack.net/task_automation_with_npm_run) to learn more about this.


## `package.json` & configuration
`package.json` has lots of fun stuff for your project. All of the fields are optional. A great resource for exploring what fields are available is [package.json.nodejitsu.com/](http://package.json.nodejitsu.com/)
