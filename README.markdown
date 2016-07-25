# How to Edit the Wiki

If your reading this you are probably either a CFA employee, fellow, or brigade member. To edit the Wiki you will need two basic skills.

1.  Basic knowledge of the git command line and/or working with github.
2.  Basic fluency in Github flavored markdown

If you already have these skills please read the section on branching, pull requests, and merging and get going.  If markdown or git are new to you this please keep reading.

## Working with github

Our wiki's repo is stored on [github here](https://github.com/codeforamerica/howto), if you don't already have a github account go ahead and set one up.  If you work at CFA contact [Mikela](mailto:mikela@codeforamerica.org) and they will add you to our organization.  If not please [fork](https://help.github.com/articles/fork-a-repo/#fork-an-example-repository) the repository.

Once you have a github account and a access to the howto repo(or a fork of it), its time to download and install the git cli tool.  If you are using OSX please download from [here](https://git-scm.com/download/mac).

After that downloads and you follow the instructions to install open the github repository page for your fork and find the [link](https://help.github.com/articles/fork-a-repo/#step-2-create-a-local-clone-of-your-fork) to the git repo and copy it.

Now open your terminal.  If the terminal is new to you read this simple explainer [tutorial](http://blog.teamtreehouse.com/introduction-to-the-mac-os-x-command-line).  In your terminal cd into your documents folder like so and clone the howto repository

```bash
cd ~/Documents
git clone https://github.com/codeforamerica/howto.git
cd howto
```

Except if you're using a fork then paste the url you just copied.

## Editing Markdown

Great you've just checked out the Wiki and we can start editing.  Editing markdown is fairly simple and only requires learning a handful of basic rules.

[This](http://www.markdowntutorial.com/) is great interactive tutorial to help learn markdown quickly and is great for beginners.  Once you've learned it this is a great [cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

Once you have the basics under your belt you can use any plain-text or markdown specific editor of your choice.  I prefer using [Atom](https://atom.io/)'s markdown preview mode which works wonderfully.

## Committing and Publish Changes

Once you've finished making your changes its time to go back to the terminal to use git to add, commit, and push your changes.

First thing you will want to do is to take a look at your changes.

```bash
git status
git diff
```

After confirming those are all of the changes you want you need to start a branch and then add the files that you've changes like so

```bash
git checkout -b feature/name_of_change
git add path/to/file
git add path/to/other/file
...
```

Once all your changes are added you need to commit and push your changes.

```bash
git commit -m 'Message explaining what you\'ve changed'
git push origin feature/name_of_change
```

And thats basically it you've made you first wiki submission.  Once your sure the changes you've made are good(or feel good about them)  go to Github and do a pull request to merge in the master branch of the original repository.  [Here](https://help.github.com/articles/using-pull-requests/) are instructions from Github on how to do a simple PR.  Shortly after someone on our team will either merge in your changes or request changes be made before we can merge them in.
