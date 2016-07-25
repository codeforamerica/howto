# Super basic bash guide 

This guide meant to help absolute beginners use the command line on Mac and
Linux computers. For windows, you'll need to install the [git command line tool](http://git-scm.com/download/win) 
or [cygwin](http://www.cygwin.com/) in order to use these commands. For Mac, you can open the command line with the __Terminal__ application, inside __Applications > Utilities__. 

This guide is supposed to be brief enough to be
learned in a few minutes. For more in-depth guidance on using the command line, try 
[this tutorial](http://cli.learncodethehardway.org/book/) or [this tutorial](http://www.linuxcommand.org/lc3_lts0010.php).
Please feel free to leave comments suggesting changes, 
additions, or clarifications.

_Note:_ In the examples below, the `#` symbol indicates a comment. Anything following a `#` will be ignored by the
command line. I'm just using them to explain what each command does, so focus
on the part _before_ the `#`.

## 10 commands: [`pwd`](#pwd), [`cd`](#cd), [`ls`](#ls), [`mv`](#mv), [`cat`](#cat), [`cp`](#cp), [`mkdir`](#mkdir), [`rm`](#rm), [`ssh`](#ssh), [`scp`](#scp)

### `pwd`

`pwd` -- _Print Working Directory:_ tells
you the folder that you are currently working in. In other words, it asks
"Where am I right now?". The "working directory" is also called the "current directory".

![pwd command animation](images/pwd.gif)

### `cd`

`cd` -- _Change Directory:_ This command allows you to move to different
folders on the computer. This and `ls` are probably the most used bash
commands. You will often enter `cd somedirectory`, then `ls`, then `cd someotherdirectory`, 
then `ls`, ... and so on. In the animation below, when you see a folder name
suddenly completed, that's because I pressed the `tab` key to use autocomplete.

```bash
cd ~ # change to my user home directory
cd .. # go up one folder
cd myfolder # change to `myfolder` (`myfolder` must be in the current directory)
cd / # go to the root folder for this computer
cd /Users/bgolder/Desktop # move to the desktop
cd Desktop # move to the Desktop (`Desktop` must be in the current directory)
cd ~/Desktop/myfolder # go to my folder, which is in `Desktop`
cd ../myfolder # go up one folder and then go into `myfolder`
cd ../../.. # go up three folders
cd - # go to the previous folder
```

![cd command animation](images/cd.gif)

### `ls`

`ls` -- _List Stuff:_ Allows you to list the contents of a folder. Adding
options allows you to list more details and see hidden files.

```bash
ls # list the contents of the current directory
ls .. # list the contents of the directory above this one
ls ~ # list the contents of my user directory
ls myfolder # list the contents of `myfolder`
ls -l # list contents in a vertical format with details
ls -a # list contents, including hidden files
ls -l -a # list contents in detail format, including hidden files
ls -l -a ~ # list the contents of my home user directory, in detail, with hidden files
```

![ls command animation](images/ls.gif)

### `cat`

`cat` -- _Like a CAT coughing up a hairball, spit out the contents of a file:_
This will print out the contents of any file onto the command line, so you can
read it without opening it. If a file is binary instead of plain-text, the
result will look like [gobbledygook](http://en.wiktionary.org/wiki/gobbledygook). Secretly, `cat` is actually short for _concatenate_, and this command has many applications covered by more in-depth tutorials.

```bash
cat myfile.txt # print out the contents of `myfile.txt`
cat Desktop/notes.txt # print out the contents of `notes.txt`, in the Desktop folder
```

![cat command animation](images/cat.gif)

### `mv`

`mv` -- _Move:_ This command moves files and folders. It can also be used to
rename things.

```bash
mv myfile.txt ~/Desktop/ # move `myfile.txt` onto the desktop
mv myfile.txt ../ # move `myfile.txt` to the folder above
mv myfile.txt file.txt # rename `myfile.txt` to `file.txt`
mv myfile.txt ../myfolder/file.txt # move `myfile.txt` up and then to `myfolder` AND rename it to `file.txt`
mv myfolder ../ # move `myfolder` up one directory
mv myfolder folder # rename `myfolder` to `folder`
```

### `cp`

`cp` -- _Copy:_ This command copies files and folders, obviously. For folders,
you need to use the `-r` option, which copies all the contents of a folder as
well as the folder.

```bash
cp myfile.txt file.txt # make a copy of `myfile.txt` and call the copy `file.txt`
cp myfile.txt myfolder/ # copy `myfile.txt` to `myfolder`, don't rename it.
cp myfile.txt myfolder/file.txt # copy `myfile.txt` to `myfolder`, and call the copy `file.txt`
cp -r myfolder ~/Desktop/ # copy `myfolder` and its contents to `Desktop`
cp -r myfolder folder # make a copy of `myfolder` called `folder`
```

### `mkdir`

`mkdir` -- _Make Directory:_ creates a new folder with the given name.

```bash
mkdir myfolder # creates a new folder in the current directory called `myfolder`
mkdir ~/Desktop/myfolder # makes `myfolder` on the desktop.
```

### `rm`

`rm` -- _Remove:_ deletes files or folders. For folders, you need to use the
`-rf` option which deletes all the contents of the folder before deleting the
folder.

```bash
rm myfile.txt # delete `myfile.txt`
rm -rf myfolder # delete `myfolder` along with everything it contains
rm myfolder/myfile.txt # delete `myfile.txt` which is inside `myfolder`
rm *.csv # delete all files that end with `.csv` in the current directory.
rm -rf ~/Downloads/* # delete everything in the `Downloads` folder
```

### `ssh`

`ssh` -- _Secure Shell:_ allows you to connect to another computer. It's like
`cd`, but gets you to completely different computer instead of just a
different folder. Often you'll need to enter your password after entering this
command. You should enter the password for the user account you are logging
into the server with. In the examples below, I would use the password for
`bgolder` on athena. By default, this will put you on the `~` user home directory for that
user account on the server, an important detail to know for `scp`. When you enter your password, you wont see any visible changes.

```bash
ssh bgolder@athena.dialup.mit.edu # log into the athena servers as the user `bgolder`
ssh bengolder@bengolder.webfactional.com # log into the webfaction servers as user `bengolder`
```

### `scp`

`scp` -- _Secure Copy:_ just like `cp` but it can be used to copy stuff to
or from other computers. It's like `cp` but for sending things through `ssh`.
Just like `cp`, you need to use the `-r` option for folders. This will often
be followed by a request for your password.

```bash
scp myfile.txt bgolder@athena.dialup.mit.edu # put `myfile.txt` into `bgolder`'s home folder on athena
scp myfile.txt bgolder@athena.dialup.mit.edu:www/ # put `myfile.txt` into the `www` folder inside `bgolder`'s home folder on athena
scp -r myfolder bgolder@athena.dialup.mit.edu:www/ # put `myfolder` in `~/www` on athena
scp bgolder@athena.dialup.mit.edu:myfile.txt ./ # copy `myfile.txt` from `~/` on athena into this current directory from `~/` on athena into this current directory
scp -r bgolder@athena.dialup.mit.edu:www ./ # copy `~/www` folder on athena to this current directory
scp -r bgolder@athena.dialup.mit.edu:www ~/Desktop/ # copy `~/www` folder on athena to the Desktop
```

### Other Useful Tips

* Press the `↑` and `↓` arrow keys to scroll through previous commands. This is
  useful when using the same command repeatedly.
* When you are entering a file or directory path, you can use the tab key to
  autocomplete the names of folders and files. If it doesn't autocomplete,
  that probably means there is more than one file or folder that begins with the
  same letters that you've typed.
* When you enter your password for `ssh` or `scp`, you won't see anything
  change in the terminal window. That's okay, just type your password and
  press enter.
* on a Mac, you can enter `open .` to open the current directory in Finder.
  You can use `open` with anything actually, and it will open the input file
  or folder with the default program. For example, `open niceviz.psd` would
  open `niceviz.psd` in Photoshop.
* making a file in `~/` called `.bash_profile` (the `.` is important and will make
  it a hidden file), will allow you to add any custom shortcut, also called
  "alias". I often use `alias ll='ls -l -a'` which means if I type `ll`, it will
  be a shortcut for `ls -l -a`. In fact, feel free to look at [my most used bash shortcuts](https://gist.github.com/bengolder/9160875).

### Glossary

__directory__ -- the same thing as a folder. It's just a place on the computer
that can store files.

__option__ -- an additional piece of text that you give to a command in order
to change how the command works. These typically follow the command name, and
begin with dashes, for example `ls -l -a`. 

