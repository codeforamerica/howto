When working with a command line interface, you can use a text file with environmental variables to store logins and passwords, and to edit how you can refer to applications like ```git```.

##Why Use Them for Logins/Password
Sometimes you need to share code with other people and don't want to share your passwords or logins too. For example, you might have put a database login and password into a script.

You can use Environmental Variables to store these logins on your local operating system, and then call them from whatever script you are using. That way you can share that script with other people without worrying, because the login is saved in another file.

###Where do I write them down?
Environmental Variables are typically put in a hidden text file somewhere you rarely put your files manually.

Where this file is typically placed typically depends on your operating system (OS) and its version.

###How can I make sure they are loaded at the Command Line?
Whether and when this file is loaded typically depends both on your and on the command line interface, console, or terminal you are using.

###How do I refer to the Environmental Variables in my scripts?
This varies, but here are some examples in [shell](http://www.kingcomputerservices.com/unix_101/understanding_unix_shells_and_environment_variables.htm) and [vagrant](http://stackoverflow.com/questions/19648088/pass-environment-variables-to-vagrant-shell-provisioner)

###Operating Systems and Versions

####OS X / Linux:

[Good General Guide to how to set Environmental Variables and how they are are loaded in Unix systems ](http://dghubble.com/blog/posts/.bashprofile-.profile-and-.bashrc-conventions/)

#####Yosemite (10.10)

[Global--including for Applications with a GUI-Works??](http://stackoverflow.com/questions/25385934/setting-environment-variables-via-launchd-conf-no-longer-works-in-os-x-yosemite)

#####Mavericks (10.9.5)

[Global--including for Applications with a GUI](http://stackoverflow.com/questions/135688/setting-environment-variables-in-os-x

###Windows 7

[Global--Set in System Preferences](http://www.itechtalk.com/thread3595.html)

[PowerShell](https://technet.microsoft.com/en-us/library/ff730964.aspx)

[Git Bash](http://markashleybell.com/portable-git-windows-setting-home-environment-variable.html)

##Applications (Aliases/PATH/etc)
TO FILL IN LATER--Stuff about PATH
