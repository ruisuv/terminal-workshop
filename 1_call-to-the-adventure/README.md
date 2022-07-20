# Call to the Adventure
The Ubuntu image just installed has only the basic so we will need to install some tools.
## Automated way:
There is a `.dotfile` on this same folder with the same commands we are running.
You can copy the file to the container itself

Access Ubuntu container

`docker exec -it d01d18af48ad bash`

Create a directory for placing dotfiles

`mkdir .dotfiles` 

From your local computer `cp`  the file

`docker cp 1_call-to-the-adventure/.ubuntu-setup d01d18af48ad:/.dotfiles`

From Ubuntu Container run it
```
ls -lha .dotfiles
sh .dotfiles/.ubuntu-setup
```

## Manual Way
Note: Ubuntu image we pulled is running as `su` (superuser). 
Normally we would like to add `sudo` (superuser do) for `apt-get` 

### apt-get
> [apt-get](https://linux.die.net/man/8/apt-get) is a command line interface for retrieval of packages
and information about them from authenticated sources and
for installation, upgrade and removal of packages together
with their dependencies. 

- Pull to your local machine the latest dependencies

  `apt update`
- Install the following tools we will be using for this workshop
  ```
        apt-get update
        apt-get install vim
        apt-get install nano
        apt-get install curl
        apt-get install unzip
        apt-get install zip
        apt-get install git
    ```
- Get [SDKMAN](https://sdkman.io/) for working with Java

  `curl -s "https://get.sdkman.io" | bash && source "$HOME/.sdkman/bin/sdkman-init.sh" && sdk version`
- Install Java 8 (because we are playing with an old system)

  `sdk install java 8.0.292-open`
- (Optional) Get [Oh My Zsh](https://ohmyz.sh/) because it is pretty
  
    ```
    apt-get install zsh
    sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    ```
- 