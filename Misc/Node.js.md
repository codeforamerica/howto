# Node.js
Node.js (often simply called `node`) is a general purpose, server-side programming environment built on top of Google's V8 JavaScript engine. It employed non-blocking I/O, which allows it to be highly responsive and scalable.

Node.js isn't for everyone. There are some specific reasons why Node may be a good option for your project, and some reasons you may want to avoid it:

- Node code can be both server-side and client-side. There are fewer things to learn for new developers, less context switching, and the ability to reuse code across the two sides.
- Uses non-blocking I/O, and Chrome's V8 engine, to provide fast, highly scalable servers.
- NPM, Node's package manager, is the largest ecosystem of open source software in the world, and contains modules for most web-based tasks, and is easily expandable.
- It is backed by the [Node.js Foundation](https://nodejs.org/en/foundation/) (a Linux Foundation Collaborative Project), which is joined and backed by companies like Microsoft, IBM, and Intel.

You may not want to use Node if your application is computation or mathematics heavy, or if you're interfacing with older technology (like requiring a PHP or Perl module). You should also take into account the skills of the team you are assembling when deciding.

## Install

While the installer found at [nodejs.org/download](http://nodejs.org/download/) is the canonical reference, it becomes difficult to use when you are switching between multiple projects that use different versions of Node. That installer also installs the Node and NPM binaries to require admin privileges, which is [a common anti-pattern](https://www.reddit.com/r/node/comments/3nlzql/why_is_it_a_bad_idea_to_sudo_install_a_global_npm/).

The easiest way to install Node, outside of the canonical link found above, is to install it via NVM (Mac/Linux: [nvm](https://github.com/creationix/nvm), Windows: [windows-nvm](https://github.com/coreybutler/nvm-windows). Follow the instructions outlined in the respective installer, and once finished, return here.

Once you have NVM installed, you can install a new version of node by typing `$ nvm install <version-number>`, where `<version-number>` is the version you want to install, e.g. `0.12`, `4`, `5.7.0` etc. To switch between versions, use `$ nvm use <version-number>`. To set one as default, use `$ nvm alias default <version-number>`, this will load that version of node on terminal start. 

You should now have `node` and `npm` installed in your `$PATH`.


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
`npm` is used to install modules and to publish your own. It is reasonably well documented at the [npm website](https://docs.npmjs.com/cli/npm).

In brief, you can find modules to use at [npmjs.org](https://www.npmjs.com/) with the search feature. Then, you can install them:

```console
$ npm install foo
```

Modules are installed in the `node_modules/` directory in your project. You will generally want to add `node_modules` to your `.gitignore` file, as it can become quite large.

To save your dependencies to your project, you will need a `package.json` file, which you can create by running `$ npm init`. This will ask some basic questions about your project, and create a `package.json` file in your current working directory. Once you have that file, you can install/save node modules by running `$ npm install foo --save`.

When you first clone a project using node, you need to run `$ npm install` which will install all of the project's module dependencies specified in the `package.json` file in the project root.

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

For example, if you want to run [`nodemon`](https://github.com/remy/nodemon) as a development script, you can add it to your package.json like this:

```js
{
  "scripts": {
    "start": "node index.js",
    "develop": "nodemon index.js",
  }
}
```

Then, in your console, you can run:

```console
$ npm run develop
```


## `package.json` & configuration
`package.json` has lots of fun stuff for your project. All of the fields are optional. A great resource for exploring what fields are available is [browsenpm.org/package.json](http://browsenpm.org/package.json)
