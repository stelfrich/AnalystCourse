# Setting up a Java development environment for Fiji and friends.

The goal of this 'homework' is to have you set up the main tools required to develop for Fiji and other related softwares using the Java programming language. With them, you are all set for the course, ready to program on day 1. Of course, given the audience of the course it is likely that some if not all these tools are already installed on your laptop. Nonetheless, please check that you have all of them, so that we all share a common development environment. 

So this homework is mainly made of installation instructions for various piece of programming softwares. It is best to follow the order of this text, as it abides tool dependencies. We also try to cover several platforms (Windows, Mac OSX, Linux). If something goes wrong, it is likely that the text is wrong. In that case contact Jean-Yves (jeanyves.tinevez@gmail.com) so that he fixes it.

Careful, doing all the installation below can be quite long, particularly if things go wrong.

----------


## Java SE Development Kit.

Most computers have the software installed needed to run Java programs. This is the Java SE Runtime Environment (JRE). We want to develop Java programs, so we need the Java Development Kit (JDK) which is not installed by default. 

As of 2017, Fiji and friends require at least Java 8. Packages can be found on [Oracle webpage](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html). Pick the latest version for your platform. Very important: we need a 64-bit computer with the 64-bit compatible libraries, so only take the `XXXX-x64` version of the JDK.

On **Mac-OS-X**, the installation package is a `dmg` file that contains a `JDK 8 Update XXX.pkg`  file. After installation, the JDK files can be found in a folder named `/Library/Java/JavaVirtualMachines/jdk1.8.0_XXX.jdk`. If you browse with a terminal in the folder `Contents/Home/bin` of the aforementioned folder, you will see that there is a list of executable files, one of them being `java`. Running `./java -version` from this folder should yield something in the line of:

    java version "1.8.0_111"
	Java(TM) SE Runtime Environment (build 1.8.0_111-b14)
	Java HotSpot(TM) 64-Bit Server VM (build 25.111-b14, mixed mode)


----------


## Git - the version control system.

We now need a tool to fetch and manage the code as files, and track the edits we make to them. To do so in an orderly manner, we use a version control system ([VCS](https://en.wikipedia.org/wiki/Version_control)). 

A version control system allows us to fetch a codebase we want to work on. When you edit a file, or create a new one (corresponding to a Java class, a Java interface, an icon file, _etc._), the *changes* you made are recorded and logged by the VCS. It is a great tool if you need to undo a change you made, or to branch the code to experiment with it, or to properly communicate to other what you did. It is so useful that we (the Fiji community) do not develop out of a VCS.

There are many of them, and in the Fiji ecosystem we use [Git](https://git-scm.com/) quasi exclusively. How to get it strongly depends on your platform.

### Git for Windows.

Several distributions of Git exist for Windows. Here we will rely on the *Git for Windows* distribution that can find [here](https://git-for-windows.github.io/). Interestingly, this package is nowadays maintained by the mother of Fiji, Johannes Schindelin.

This distribution ships several goodies such as a good terminal application (Git BASH) and GUIs for Git commands (`git gui`, `gitk`), particularly welcomed for Windows, as this platform is not natively well endowed for developers. 

### Git for Mac-OS-X.

Apple offers a version of Git through XCode, but we favor here a more recent version equipped with GUIs. Go on the [Git download](https://git-scm.com/downloads) webpage and pick the Mac-OS-X version. You will get a `dmg` file containing the installer and a useful README file.

### Testing Git installation and basic configuration.

Open a terminal and check that Git is properly installed with the paths set by typing: `git --version` in the shell. You should get something in line of 

	git version 2.6.4

It is a good idea to perform its basic configuration now. We want to tell it who we are and what is our email for instance. This is done with the `git config --global XXX` command:

	git config --global user.email "you@yourdomain.com"
	git config --global user.name "Your Name"
	git config --global color.ui true

Then check that everything was properly recorded:

	git config --list

----------


## Maven - the build automation tool.

Maven is the tool Fiji uses to build the code into an executable Java program. It does much more than simply compiling java files: it takes care of the dependencies of your software in an automated manner, but we have to comply to a certain organisation of the code. 

Maven is a software written in Java, so the installation procedure changes a little from what we are used to on our respective platforms. First go to the [download page of Maven](https://maven.apache.org/download.cgi) and pick one of the binary distribution (_e.g._ `apache-maven-x.y.z-bin.zip`). 

Unzip it and copy the whole ``apache-maven-x.y.z` folder somewhere convenient. For instance, I recommend creating a `Development` folder in your `home` that we will use as workspace for software development. We can put the Maven folder there.

We will use Maven from the command line, so we must add its executable to the shell path. Also, since Maven uses Java, we must properly declare where is the Java Development Kit we installed above. This requires some manipulation of the shell environment of your OS. In case of doubts, follow the instructions from the [Maven installation page](https://maven.apache.org/install.html). Here are some tips for common platforms.

### Maven on Mac-OS-X.

We will use the Mac-OS-X terminal, and the shell defaults to bash normally. Adding to the shell path can be done in the `.bash_profile` file in your home. To edit it, do something like this in a terminal:

	cd # move to your home folder
	vim .bash_profile # open an editor for bash_profile

Of course, the editor we use here is Vim, you might not like it. Any text editor will make it.


----------


## Installing Fiji for development.


----------


## Eclipse - integrated development environment.


----------


## GitHub - Git repository hosting.
