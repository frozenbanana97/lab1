
## Contents

  * [Contents](#contents)
  * [Overview](#overview)
- [Setting Up](#setting-up)
  * [Opening Command Line](#opening-command-line)
    + [Windows](#windows)
    + [Mac](#mac)
  * [Installing Python](#installing-python)
    + [Option 1 - Installing Python 3 the basic way](#option-1---installing-python-3-the-basic-way)
      - [Windows](#windows-1)
        * [Using bash in WSL 2](#using-bash-in-wsl-2)
        * [Using DOS](#using-dos)
      - [Mac](#mac-1)
    + [Option 2 - Installing Python 3 using a versioning management system](#option-2---installing-python-3-using-a-versioning-management-system)
      - [Ubuntu](#ubuntu)
      - [Mac](#mac-2)
- [Intro to the tools of the trade](#intro-to-the-tools-of-the-trade)
  * [Navigating Command Line](#navigating-command-line)
  * [Setting up Git](#setting-up-git)
    + [Making sure Git is installed](#making-sure-git-is-installed)
      - [Ubuntu](#ubuntu-1)
      - [Mac](#mac-3)
      - [DOS](#dos)
    + [Using Git in this course](#using-git-in-this-course)
  * [Creating Virtual Environments](#creating-virtual-environments)
    + [Installing Python packages](#installing-python-packages)
    + [Intro to Jupyterlab](#intro-to-jupyterlab)
  * [Mastering markdown](#mastering-markdown)
    + [Sharing your work to Github](#sharing-your-work-to-github)
    + [Exiting your virtual environment](#exiting-your-virtual-environment)
- [Deliverables](#deliverables)

## Overview

The goal of this lab is to get Git and Jupyterlab up and running so you can start programming collaboratively and interactively in Python as of the next lab session. There are several ways of getting there depending on your particular setup. To do this, we have to start with the command line, where we will install and configure Python, among other things...

# Setting Up

## Opening Command Line

What is command line? it's the black box that you imagine hackers using to do all sorts of powerful things on a computer. Indeed, this is where you can run just about anything using a simple set of commands typed from a keyboard. Don't be confused by the terms terminal, console, command line, cmd, command prompt, or shell. These are all slightly different things, but what you should retain is that your terminal/console uses a command-line interface (rather than a graphic one like other apps), and the commands you enter into this interface are interpreted by a shell. The shell is the program that recognizes your commands as operations that manipulate the computer. See this short [video](https://www.youtube.com/watch?v=Yt57-gg9jVg&ab_channel=Udacity) for further elaboration.

Throughout the course, command line, console and terminal are used interchangeably.

### Windows

To find the command line in Windows 10:
-  start *Command Prompt* / start *Run* (**Windows Key+R**) > type **`cmd`** > **Enter**

Commands entered in Windows command line are basically interpreted by the DOS shell, unlike Mac and Linux which typically use bash. DOS is limited and outdated, whereas bash is much more popular among programmers. Windows 10 introduced the option to enable a bash shell in command line. In doing so, Windows creates its own Linux subsystem (known as WSL), as if you had a separate Linux computer inside your PC.
- Inside command prompt, type **`bash`** and hit **Enter**
  - if you enter a new command line environment, usually characterized by green and blue coloured text, then your Linux subsystem is already enabled and you're good to go.
  - if not, then you will likely need to enable it.
    - To enable the Linux subsystem or WSL 2 on Windows 10, please refer to these instructions: https://docs.microsoft.com/en-us/windows/wsl/install

If you are unable to install WSL 2 for whatever reason, that's ok (but not ideal). Please notify the instructor of this and keep reading...

### Mac

- Open  terminal (*Spotlight*/**Cmd+space** > type Terminal and click) and voilà!

If you bought your Mac since 2019 (version 10.15 Catalina), then your terminal console's default shell is *zsh*. If you've had the same Mac since before then, then your console's shell is probably still *bash*. *zsh* and *bash* have common origins, so they are very similar. The only difference you need to remember is when making changes to the shell's configuration, which is rare.
- To find out what shell your Mac terminal uses, type `which $SHELL` and hit **Enter**. This outputs the shell's directory in your system.

Simply remembering which shell your Mac uses is helpful when following instructions for using your command line. This course won't have you doing too much of that, though.

- Read more [here](https://scriptingosx.com/2019/06/moving-to-zsh/#:~:text=The%20main%20difference%20between%20bash,ignores%20the%20bash%20configuration%20files%20%28%20.&text=There%20is%20an%20entire%20eco,far%20easier%20than%20in%20bash%20.) on bash versus zsh.

## Installing Python

Most computers already have Python installed. Usually this is Python 2, often you might also have Python 3 installed. Option 1 of the instructions below will set you up to use a basic, system-wide installation of Python 3. This is a good option if you're not comfortable at all with command line or if you don't plan on using Python beyond this course. If, however, you plan on using Python beyond this course on your current computer, then it is recommended to install Python using the instructions in option 2.

### Option 1 - Installing Python 3 the basic way

#### Windows

You can run Python from the default command line (DOS) or in WSL 2 (bash). The former is your PC, and the latter is your linux subsystem. Note that installing Python in one of these means the installation is only available in that environment. Instructions are available for installing on either DOS or bash, but it is much more preferable to have WSL 2 enabled and to be using bash, both in this course and beyond...

##### Using bash in WSL 2

Once you have the Windows Subsystem for Linux enabled, you can install python. 

> Note that in bash, you sometimes need to perform `sudo` commands, which are basically actions that require administrator access. These sometimes require a password. If you set a password, remember it! If you are prompted for a password and don't know it, use your login pw or see the instructor.

- In command line, enter `python --version`. If it brings up a version of python 3, you should be good to go.
	- If it returns a version of Python 2, then try `python3 --version` or `py3 --version`. If either of these return a version of Python 3, then you're good to go. Remember, though, that whenever the generic `python` command is asked of you, you will need to use the `python3` (or other) command that worked for you here.
- if you don't have Python 3 installed:
	- Type `sudo apt update` and hit **Enter** (n.b. apt is a package installer/manager for Ubuntu)
	- When apt's repositories are finished updating, enter `sudo apt install python3.10.1` and wait for the installation process to complete.
 - When finished, try the `python --version` or `python3 --version` commands. Whichever one outputs a version of python 3 is the one you should be using from now on. You're good to go!

##### Using DOS

If you were unable to install WSL 2 on your PC for whatever reason and prefer to go ahead without it, keep reading:
- To check if Python is already on your PC: in command line, enter `python --version`. If it brings up a version of python 3, you should be good to go.
	- If it returns a version of Python 2, then try `python3 --version` or `py3`. If either of these return a version of Python 3, then you're good to go. Remember, though, that whenever the generic `python` command is asked of you, you will need to use the `python3` (or other) command that worked for you here.
		- If neither of these return Python 3, then visit https://www.python.org/downloads/ and download and install the latest version of Python 3 for Windows (version 3.10.1 at the time of writing this). Follow the installation instructions carefully.
		- After installing Python 3, try running `python --version` or `python3 --version`. If it returns the title of the Python version you installed, then you're good to go.

#### Mac

- Verify if Python is installed by entering `python --version` in the command line.
	- If this returns a version of python 3, you're good to go.
- if this returns a version 2 of python (e.g. 2.7), then try entering `python3 --version`
  - now, if this brings up a version of python 3, you're good to go, but just remember that you will need to use `python3` as your executable whenever you run python code from command line on your Mac!
 - If you do not have Python 3 installed, then visit https://www.python.org/downloads/ and download and install the latest version of Python 3 for Mac (version 3.10.1 at the time of writing this). Follow the installation instructions carefully.
- After installing Python 3, try entering `python --version` or `python3 --version`. If it returns the title of the Python version you installed, then you're good to go.

### Option 2 - Installing Python 3 using a versioning management system

:exclamation: Note that you cannot install Python this way in DOS. If you are using Windows and are unable to activate WSL 2, then refer to option 1.

If you are running Ubuntu (WSL 2) on Windows or are using a Mac, and you feel somewhat comfortable in command line and would like to take a shot at setting yourself up properly for doing projects with python beyond this course, then consider installing `pyenv`. Pyenv manages python versions seemlessly. For example, when Python 4 is released, you may be inclined to install it (or let's say a project you're working on requires you to use it). If you do this on the computer you are currently using, code that you wrote in this course may no longer run as it did when you wrote it using Python 3. The goal here is therefore to keep multiple versions of python available on your system, and to allow yourself to be able to easily activate different versions depending on what project you're working on. Setting yourself up this way now will save tons of headache for years to come.

In this course, the instructor(s) will be using pyenv with version 3.10.1 activated. This was the latest version of Python at the time of writing this course. If you are using a different version of Python 3, that shouldn't be a problem for what we are trying to do in this course, so you can continue to use it.

However, if you would like to install pyenv, read on, it should only take around 5 minutes:

#### Ubuntu

From the bash shell on Ubuntu (Ubuntu is the Linux OS used by WSL 2), you can enter the following commands, which are based on [these instructions](https://realpython.com/intro-to-pyenv/):
- `sudo apt-get install -y make build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev \
libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev python-openssl` ([source](https://realpython.com/intro-to-pyenv/#build-dependencies))
- `curl https://pyenv.run | bash` ([source](https://realpython.com/intro-to-pyenv/#using-the-pyenv-installer))
- After the previous command finishes installing pyenv, it may instruct you to enter some commands, which you should run to add pyenv to your PATH (therefore making the `pyenv` command work on command line). These instructions differ based on your situation. If in doubt, use the three commands listed in [here](https://github.com/pyenv/pyenv/blob/master/README.md#basic-github-checkout), which are pasted below for your convenience:
  - `sed -Ei -e '/^([^#]|$)/ {a \
export PYENV_ROOT="$HOME/.pyenv"
a \
export PATH="$PYENV_ROOT/bin:$PATH"
a \
' -e ':a' -e '$!{n;ba};}' ~/.profile`
  - `echo 'eval "$(pyenv init --path)"' >>~/.profile`
  - `echo 'eval "$(pyenv init -)"' >> ~/.bashrc`
- Then, restart your command line (`exit` to return to Windows DOS, and then enter `bash` again) and the `pyenv --version` command should work.
- Then install this course's desired version of Python 3 from pyenv: `pyenv install -v 3.10.1` (the installation can take several minutes)
- Finally, simply enter `pyenv global 3.10.1` to enable this newly installed version (see [here](https://realpython.com/intro-to-pyenv/#using-your-new-python) for further reading on switching between versions)

#### Mac

Mac users like to use Homebrew as a package manager for Terminal. To check if you have Homebrew already installed, enter **`brew --version`** in command line, if the command is not recognized, you will need to install Homebrew.

- Go to https://brew.sh/ and copy the command listed
- paste this command into your terminal and hit **Enter**

When finished installing, you might be notified to add Homebrew to your PATH, which you should do. Adding an application to your path makes the service executable from the command line using a command which the computer recognizes as linked to that application.
- To do this, simply perform the commands that Homebrew provides you with at the end of installation

Now, `brew` commands should be recognized. You can test this by entering `brew --version`, which should provide you with the Homebrew version if your installation worked as expected. You can now install anything you want from the command line on your Mac!

Now that you have your package manager installed, we need to install pyenv.
- See [these](https://www.freecodecamp.org/news/python-version-on-mac-update/) or [these](https://realpython.com/intro-to-pyenv/) instructions for installing pyenv on Mac.

# Intro to the tools of the trade

## Navigating Command Line

Now that you've got a version 3 of Python installed, let's create a project folder for today's lab.
- Let's start by identifying our location in our file system: `pwd` (`cd` in DOS)
  - This shows you the directory in which you are currently sending commands
- To view what folders exist in the current directory, enter `ls` (`dir` in DOS)
  - This shows you a list of folders and files that exist in the current directory
- To go inside one of these folders, enter `cd [foldername]` (in my case, I am entering my Desktop by enter `cd Desktop`)
- To go back up one level to the previous directory, you can use the command `cd ..`

Use these `cd` commands to navigate to a folder where you want to store your labs for this course. Once you are where you want to be, let's make a new folder:
- Enter `mkdir geog464`
  - You now have a new folder called *geog464*, which you can see by entering `ls`
- Enter the folder: `cd geog464`. This is where you will be working on your labs for this course!
- Let's start by creating a folder for today's lab: `mkdir lab1`.

Keeping files organized is extremely important when writing code, and this starts with having a consistent folder structure so you don't lose track of where things are.

For more help with navigating the command line, see [this](https://www.guru99.com/linux-commands-cheat-sheet.html) or [this](http://www.mathcs.emory.edu/~valerie/courses/fall10/155/resources/unix_cheatsheet.html) reference.

## Setting up Git

[Git](https://git-scm.com/) is the most widely used version control system. Have you ever saved a Word document and wished you could revert to a previously saved version? Have you ever worked on a document saved to a cloud service while someone else was also working on that same document, only to save it and corrupt the document? Git solves all these issues (i.e. version history and collaboration). However, it can be a daunting technology to learn in one lesson. Familiarizing yourself with the basics, though, can help you with any future work that might require you to use Git. In general, knowing Git will allow you to both benefit from and contribute to open source code.

The most popular Git service is Github. Github allows you to host Git repositories (of code, literature, music: literally any kind of files) on the internet. Users who want to access a repository typically use Git commands (on the command line) to access it. In doing so, users can download, modify and upload their edits to that repository. This [video](https://www.youtube.com/watch?v=2ReR1YJrNOM&ab_channel=ProgrammingwithMosh) also provides a short explanation of Git.

### Making sure Git is installed

#### Ubuntu

- If you are using WSL 2 for Windows, git should already be installed and accessible from your bash shell. Enter `git --version` in command line to check.
- If not, follow [these instructions](https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-git#installing-git)

#### Mac

- Git should already be installed on your Mac. Enter `git --version` in terminal to check.
- If not, follow [these instructions](https://git-scm.com/download/mac)

#### DOS

- Git is likely not installed on your PC. Enter `git --version` in cmd to check.
- To install Git on Windows so that you can use it in DOS command line, see [here](https://git-scm.com/download/win).

### Using Git in this course

We will not be using Git in too many elaborate ways in this course. However, you will need to know how to *clone*, make *commits* to, and *push* repositories (this section will show you how this works).

- First, you will need to make a Github account, so go to github.com and hit *Sign up*!

Since August 2021, Github requires that you use a personal access token for connecting through its API from command line. This makes things a bit more complicated than before, when you only had to use you Github account password... So you will need to create an access token and paste it somewhere you can access it easily for whenever you're interacting with Github.

- Once you've made your account at github.com, Create an access token by following [these instructions](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token#creating-a-token)

Before starting to use git on command line, let's configure your git username and email. Doing so will help Github link your git activity to your Github profile.

- In command line, set your username by following [these instructions](https://docs.github.com/en/get-started/getting-started-with-git/setting-your-username-in-git#setting-your-git-username-for-every-repository-on-your-computer).
- In command line, set your email by following [these instructions](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-user-account/managing-email-preferences/setting-your-commit-email-address#setting-your-email-address-for-every-repository-on-your-computer). Note that if you want your git activity to be associated properly to your Github account online, make sure to **use the same email address** as the one you used to create your Github account.

- Open the link to Github Classroom that was sent to you: This will ask you to link your Github account to the Github Classroom service and to your name on the class roster. You will then need to **Accept this Assignment** (which in this case is today's lab). Github will generate a link to the repository it created for you containing today's content (you may need to refresh the browser page to see it).

- In your new repository, you will find an HTTPS link (*Code* tab > top-right **Code** dropdown > copy link). This link is what you will be using to clone your repository to your computer from the command line.
- In command line and inside your *geog464/* folder, enter `git clone [paste link]` (in Windows, you can either right click or use **Ctrl+Shift+V** if enabled under the *Edit Options* of **Properties**)
- Since the cloning requires you to fetch content from Github, you will need to provide your credentials: input your Github username followed by the personal access token you created.
- You will now find a new folder inside *geog464/* (`ls` to see that it's there)! By default, its title is the name of your Github repository (you could have named it differently by adding an extra argument to your git command: e.g. `git clone [paste link] lab1`).
- Navigate to the cloned repository (`cd [folder name]`). In here you will find the content from today's lab (i.e. just a `README.md` file, which contains an exact copy of the instructions you're currently reading!)
- Navigate out of the repository: `cd ..`.

## Creating Virtual Environments

:exclamation: The following tutorial only applies to Mac and Ubuntu (WSL 2) users. If you are using DOS, please refer to the [instructions for Windows](https://docs.python.org/3/tutorial/venv.html#creating-virtual-environments) alongside the instructions below

We have so far settled on using a version of Python 3 and you have an executable (e.g. `python`, `python3`) that points to an installation of Python 3. When you install python packages such as Jupyter, Pandas or Numpy, these packages and their dependancies will be installed globally for that version of Python. However, you may require different package versions for different projects, and updating certain packages might make certain projects that relied on a specific version of that package which you installed in the past no longer work properly. **Like Python versions, managing Python package versions can also be tricky!** To deal with this, we use virtual environments. Virtual environments create an entire new copy of Python inside your directory and are entirely self-contained. They also make sharing and running other people's code much easier.

Python versions since 3.3 come with a module called [venv](https://docs.python.org/3/tutorial/venv.html) installed by default.

- From within your *lab1* folder, create a virtual environment inside a subfolder called *venv3.10.1* by entering: `python -m venv venv3.10.1` (if you are using a different version of Python 3, then indicate that version number in your folder name instead).

>You can name your virtual environments whatever you want (they're just folders with python source code in them). However, I find it useful to name them based on the package that made it (*venv*) and the Python version that is installed inside it (3.10.1, in this case).

- Now enter `ls` and you should see the new folder containing a new localized Python installation alongside the git repo you cloned (these two folders can be considered *sibling* directories). Any Python packages installed with your virtual environment acivated will be installed inside this new folder.
- To activate your virtual environment: `. venv3.10.1/bin/activate`

Congratulations! You are now running a local version of Python 3. Note that when a virtual environment is active, all python commands in the active command line interface will refer to the Python installation of that virtual environment. This means that packages installed on your computer's system-wide Python installation are not accessible.

### Installing Python packages

Today, we will only install [JupyterLab](https://jupyter.org/) using [pip](https://pypi.org/project/pip/). Jupyterlab is a great interactive notebook for Python that we will be using throughout the course. Pip is a mainstream package installer for Python that you will also use throughout the course to install packages.

- Make sure you're in your lab folder and your virtual environment is activated (`. venv3.10.1/bin/activate`) if it is not already.
- Enter `pip list`. This will show you the packages you currently have installed in your virtual environment (not many, basically the ones you need by default to get started!)
- Enter `pip install jupyterlab`
- When installed, enter `pip list` again: you will see that your jupyterlab installation required the installation of quite a few other packages. These are **dependancies**: packages that the jupyterlab package depends on to function properly.

:pencil: Because we want our code to eventually be reproducible and easy to set up on another machine, it's important that other programmers know what packages we're using. It's good practice to store the package names and versions in a file that others can view. To do this, enter `pip freeze > requirements.txt` ([freeze command documentation](https://pip.pypa.io/en/stable/cli/pip_freeze/)).

- You can view and edit the contents of any file from directly within the command line by using Vim: an ancient command line file editor (like Notepad, but much more unintuitive). Enter `vi requirements.txt` to view your new text file. Exit Vim by entering `:q`.

### Intro to Jupyterlab

- To start using jupyterlab, enter `jupyter-lab --no-browser` (the *--no-browser* is optional: this just suppresses a warning)
- This will output a url where an instance of jupyterlab is being hosted locally. Copy the url and paste it into your web browser.
- In the loaded page, click the **Python 3** icon under *Notebook* to start a new notebook.

:pencil: In your new computational notebook, type out a print statement that will output the message `hello class!` and run it by hitting **Ctrl+Enter**...

- Now, we want to give your notebook a better name: right-click the tab and **Rename Notebook...** from *Untitled.ipynb* to *lab1.ipynb*.
- Now, we're going to want to push this notebook to your Github repository so that your instructor can review it your amazing print statement. let's put the notebook into the repository you just cloned (if it isn't already). Right-click the notebook tab and hit **Show in File Browser**. This should bring up a file browser panel on the left showing the files and directories available to Jupyter Lab: drag your ipynb file into the repository folder you cloned (you could have also done this from command line with the `mv` command by entering `mv lab1.ipynb [folder name]`, but it's safest to not have jupyterlab running when done that way).
- In your command line again, you can stop jupyterlab by hitting **Ctrl+C**/**Cmd+C**.

>For further help with the Jupyter lab interface, see the [official documentation](https://jupyterlab.readthedocs.io/en/stable/user/interface.html). We will be exploring Jupyter Lab in greater depth as the course progresses.

## Mastering markdown

In your respository folder, you will find a *README.md* file which contains the instructions you are currently reading.

:pencil: Edit the current file by adding a section between the two lines below which immitates the styling used in the [Wikipedia page for Python](https://en.wikipedia.org/wiki/Python_(programming_language)) from the **Statements and control flow** header to the point about *try* statements inclusively (7 lines total). Be sure to include any hyperlinks that are part of the piece of text you are recreating.

You can edit a markdown file (like any other file) using any standard text editor (e.g. Notepad, or even Vim). There are many text/code editors out there: you can do your own research to find one you like (Atom is popular on Mac, whereas on PC I would recommend Notepad++). You can refer to the following resources to help you here:

- Live markdown preview (useful if your text editor doesn't provide one): https://markdownlivepreview.com/
- Markdown syntax cheat sheet: https://www.markdownguide.org/cheat-sheet/
- For generating tables in markdown: https://www.tablesgenerator.com/markdown_tables
- For generating ToCs: https://ecotrust-canada.github.io/markdown-toc/
- emoji cheat sheet: https://gist.github.com/rxaviers/7360908

---
---

### Sharing your work to Github

- Make sure that the *requirements.txt* file is in your git repo. If it isn't, from your lab1 parent folder, enter `mv requirements.txt [folder name]` to move it to your repo folder.
- Navigate to your cloned repo folder: `cd [foldername]`.

Git keeps track of changes made inside a repository. Some changes have been made to your repository since you cloned it, in our case by adding some new files (*lab1.ipynb*, *requirements.txt*) and modifying a file (*README.md*).

- Enter `git status` to see what the current situation is in regard to your version history. This will tell you that there are new files in your repository that are untracked. What this means is that git notices they're there, but since they are untracked, changes you make to them (e.g. modifications to code inside these files) aren't noticed by git. If you want git to track changes to files and make them part of the repository, you need to add them to the *staging area*.
- Let's add your new files to the repo: `git add lab1.ipynb requirements.txt`. Now enter `git status` again: this will tell you that the new files were added, and are ready to be *committed*. Read more on what git commits are [here](https://github.com/git-guides/git-commit). You should also enter `git add README.md` to add this file's modifications to the staging area.
- To commit a snapshot of your work to the repo history, enter `git commit -m 'add jupyter notebook, pip requirements and modify readme`. This could be considered a lot to add to one commit: separating these into different commits could be useful if we wanted to revert to a particular change later, but for this lab, we don't need to be that detailed. Note that the message in your commit command following the `-m` argument should always be a brief description of the changes you are committing. See [this reference](http://udacity.github.io/git-styleguide/) on recommended standard wording for git commits.
- Finally, push your changes (your new commit) to your remote repository at Github.com: `git push`. You will be asked to enter your Github credentials once more.

### Exiting your virtual environment

- To exit and return to your global Python environment, simply enter `deactivate`.
- After this, enter `pip list` again.

Notice how few packages there are? This is because you are now using your global (system-wide) version of Python and pip. You wouldn't be able use Jupyterlab in this environment without also installing another instance of it here (but there is no reason to do so).

Note that you can delete the entire virtual Python environment you created by simply deleting its folder (`rm -r venv3.10.1`, but don't do that here!)

# Deliverables

Full points are awarded to successfully pushing (3) changes to the repository you made based on these lab instructions: your requirements list, jupyter notebook file, and the markdown modifications you made to the README file. 

