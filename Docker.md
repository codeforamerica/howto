Docker has instructions for installation on their site ([mac], [windows], [linux]).

## Mac or Windows setup

If you are running Docker for the first time on OS X or Windows,
you'll need to [install docker-machine] and [VirtualBox].
On Mac, our recommended approach is through [homebrew].

```bash
brew install docker
brew install docker-machine
brew cask install virtualbox
```

[homebrew]: http://brew.sh/

Once you have Docker installed, create a virtual machine:

```bash
$ docker-machine create --driver virtualbox default

# Add relevant environment variables to your shell
# (if you don't use bash, replace with `.zshrc`, `.profile`, etc.
$ echo 'eval $(docker-machine env)' >> ~/.bashrc && source ~/.bashrc

# Open up port 3000 between the host and the virtualbox machine
$ VBoxManage modifyvm "default" --natpf1 "guestnginx,tcp,,3000,,3000"
```

## Confirm dependencies are installed correctly:

```bash
$ docker run --rm hello-world
# should print something like:

Hello from Docker!
This message shows that your installation appears to be working correctly.
...
```

[Docker]: https://www.docker.com/
[mac]: https://docs.docker.com/mac/
[windows]: https://docs.docker.com/windows/
[linux]: https://docs.docker.com/linux/
[install docker-machine]: https://docs.docker.com/machine/install-machine
[VirtualBox]: https://www.virtualbox.org/wiki/Downloads
