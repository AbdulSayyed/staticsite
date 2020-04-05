Title: Installing git on Windows
Date: 2020-04-05 12:40
Modified: 2020-04-05 12:40
Status: published
Category: This site
Tags: python, markdown, blog
Slug: first-post
Authors: Abdul Sayyed
Summary: This is the summary of the first post


> By the end of this chapter you should be able to learn the following:

- The concept behind the **git** program.
- Why was it written initially?
- What does it mean to say a program is a git client?
- How to install **git** software on Windows?
- What is **.gitconfig** file and how to manipulate it?
- Why three different config files, system-config, local-config and global-config
- Where are they saved in your system
- How to set your identity with config file
- How and why line ending important
- What is GitHub and GitHub client
- How to place the repository containing code to a remote machine
- How to use git help to understand git.

### Git commands used

> Note: The structure of git command  <command> [<arg>] 

```
    1. > git --version
    2. > git config <variable>
    3. > git config --global user.name "your name"
    4. > git config --global user.email "your email"
    5. > git config --list
    6. > git config --global -l
    7. > git config --local -l
    8. > git config --global add < key >
    9. > git config --global user.dob "1977/09/03"
    10.> git --global --replace-all user.dob "new values"
    11.> git config --local -e
    12.> git help -g
```

> This guide is no way a comprehensive guide to **git** but a lay man endeavour to understand **git** and help to many others who goggles for term like fork,branch, push ,pull and so on to figure out what the heck is all about.  This guide was written last year. Since then the version of git may have changed!

#### What is Git?

It is a free and open source computer software developed by [*Linus Torvalds*](https://en.wikipedia.org/wiki/Linus_Torvalds) for the purpose built  version control system [**VCS**](https://en.wikipedia.org/wiki/Version_control).

It is a software  developed for people who want keep track of their work from beginning to end ( having different versions of their work ) and for those who want to work together as a team on any topic of common interest sitting remotely anywhere in the world with the facility of having a program which allows them to collaborate with each other painlessly. 

In other words  a project or any piece of work before it comes to its final stage for publication goes through many phases  (and these phases may be understood by their versions) before it is ready to come out. To keep all those records in a systematic way requires a frame work and **git** provides that frame work to you on your system whether you like to work alone or with others. It is completely acceptable and possible to work alone and use **git** but for this purpose you may have other options which may be much easier to learn and use.

**Git** is not only a **VCS** but a [**DVCS**](https://en.wikipedia.org/wiki/Distributed_version_control) distributed / decentralized version control system. The main difference b/w a centralized VCS and Distributed VCS is that a DCVS is not dependent upon the centralized remote server  but it can work itself alone because the user machine has a DVCS installed on its computer so it can keep working even if the remote server is down. Before we learn how to install git on local computer bear in mind if you search/google for " What does git stands for ? " the answer is, it stands for so many things of not your interest. In software technologies many programs names are not supposed to be acronym of anything. Thus git does not stand for anything which you may be looking for.  

### How to Install Git on Windows 

[//]:# ( Which different version of git are available . The back ground )

Visit the site [git-scm.com](https://www.git-scm.com) and click on download link select windows option if you are on windows,select the right version for your platform , look for what is available there. An exe file similar to *Git-2.6.2-64-bit.exe* will be downloaded on your desktop. Double click to install it on your computer click `Next >`

![installing-windows](/images/git/installing-windows-01.png)

Next Dialogue box will give you different options to install. Since you are installing it on Windows click the options shown on the image.It is handy to have an Explorer integration option so that you can use with the right click of your mouse selecting any folder , click `Next` . 

![installing-windows](/images/git/installing-windows-02.png)

in this dialogue box choose the one which says Git from windows command prompt

![installing-windows](/images/git/installing-windows-03.png)

the next dialogue box asks you how git should treat line endings check the one which says Windows-style

![installing-windows](/images/git/installing-windows-04.png)

Remaining dialogue box accept the default options as they have to do with GitBash which is used on Mac computer.

![installing-windows](/images/git/installing-windows-05.png)

Once git is installed you need to check if it is installed correctly or not.

[//]: # ( Add section about the git added shell bourne shell or command prompt)

### Check The Installation

```shell
    K:>git --version
    git version 2.6.2.windows.1
```

The **git** version command is best way to find out if it is installed or not. Typing only `>git` will result in displaying the usage of **git**. If you can not see the above and see the  the message similar to this instead

```shell
K:> git
git is not recognized as an internal or external command,operable program or batch file.
```

It means **git** is not installed on your local computer , you need to try again and if needs goggle it to find the solution.

### Start Using git

You have already used one command of **git** that is `git --version` now type `>git` only and see you get the list of commands that you can use.The system tells you how to use **git** command for what purpose as shown in figure below.

![installing-windows](/images/git/command-prompt-03.png

Before starting to use git it needs to be configured so **git** knows who you are and what is your contact details and what is your options so that it can provide its services to you.

### How to Configure git

**git** configuration details are kept in a config file called **.gitconfig**. In windows environment it is present in user's profile folder which is usually set under this folder  `C:\Users\Yourlogin name\ ` . This is also a  home directory where you can find *.gitconfig* file . An easy way to change the values of this file to open in any editor and do some changes. Another way to edit this file is to use the command prompt. By default some values are set by the **git**  installation. To see what values are set by default use`>git config --list`. Note to open a global config file from a command prompt in a default editor use `>git config --global -e`. This command will open your default editor or the editor you have set to be used in the config file. 

![Configuring-git](/images/git/config-git-01.png)

<!-- The above details were set by **git** installation. They may not make some sense at this stage but later on gradually you will understand what  these terms are about. Now set your personal details with git. -->

### Setting your id

#### Configuring ***.gitconfig*** file from command prompt. 

Set your user name and user email by setting the value in *user.name* and *user.email* variables as follows

```
>git config --global user.name "your name"
>git config --global user.email "your email"

Once your identity is set run the `config --list` command again to see the setting in config file . You should be able to see your user name and email set . In case if you have made any mistake open `.gitconfig`file in any editor and correct your mistake. To see if the values are set properly get the listing again. If you ever need to find out an individual variable value **git** allows you this as well by using this format `>git config < variable >`  to find out which email is set with git use `git config user.email` and it will output the result. To see the help associated with confgi commnad use `>git config` as done below.

        
        K:\>git config
    usage: git config [<options>]
    Config file location
        --global              use global config file
        --system              use system config file
        --local               use repository config file
        -f, --file <file>     use given config file
        --blob <blob-id>      read config from given blob object
    Action
        --get                 get value: name [value-regex]
        --get-all             get all values: key [value-regex]
        --get-regexp          get values for regexp: name-regex [value-regex]
        --get-urlmatch        get value specific for the URL: section[.var] URL
        --replace-all         replace all matching variables: name value [value_regex]
        --add                 add a new variable: name value
        --unset               remove a variable: name [value-regex]
        --unset-all           remove all matches: name [value-regex]
        --rename-section      rename section: old-name new-name
        --remove-section      remove a section: name
        -l, --list            list all
        -e, --edit            open an editor
        --get-color           find the color configured: slot [default]
        --get-colorbool       find the color setting: slot [stdout-is-tty]
    Type
        --bool                value is "true" or "false"
        --int                 value is decimal number
        --bool-or-int         value is --bool or --int
        --path                value is a path (file or directory name)
    Other
        -z, --null            terminate values with NUL byte
        --name-only           show variable names only
        --includes            respect include directives on lookup

The `--global` option was used when setting user.name and user.password . These values are used when you make commits and must be set. The `--global` option will make sure that no matter where you are the values set by this option will be used automatically. If you are working on a different project where a different user name or an email is used you can set the values without the `--gloabl ` option and those values will be used for that purpose only.

### Why more than one ***.gitconfig*** file

When **git** is installed it installs these files on different places to use for different purposes. **git** follows this concept that local settings  are more specific  than global setting and global settings are more specific than system settings. Thus when reading the values they are read first from least specific place that is from the system then from the global setting and from the local repository setting. To read from  global config file a  `--gloabl` option is used and so on as shown in following code.

### Reading from **.gitconfig** files

Finding what is set by configuration file first use `>git config -l` , this command will read from all configuration files and result a list of all values set. Note if you are not in local repository it will only read values from system and global config files The following listing is taken from within local repository thus it includes values from `--system , --global ` config files and from local repository config files.

```javascript
    K:\projects\c-dir-record>git config -l
    core.symlinks=false                            |
    core.autocrlf=true                             |
    core.fscache=true                              |
    color.diff=auto                                |
    color.status=auto                              |
    color.branch=auto                              |<-- system config settings
    color.interactive= true                        |
    help.format=html                               |
    http.sslcainfo=C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt |
    diff.astextplain.textconv=astextplain          |
    rebase.autosquash=true                         |
    ______________________________________________ |
    user.name=Abdul Sayyed                         |
    user.email=s.a.ghafoor@outlook.com             |
    filter.lfs.clean=git-lfs clean %f              | <-- global config settings
    filter.lfs.smudge=git-lfs smudge %f            |
    filter.lfs.required=true                       |
    ______________________________________________ |
    core.repositoryformatversion=0                 |
    core.filemode=false                            |
    core.bare=false                                |
    core.logallrefupdates=true                     |
    core.symlinks=false                            | <--local repository settings
    core.ignorecase=true                           |
    core.hidedotfiles=dotGitOnly                   |
```

The above configuration values can be individually read by using specific option as shown below.

```git        
    K:\>git config --global -l
    user.name=Abdul Sayyed
    user.email=s.a.ghafoor@outlook.com
    filter.lfs.clean=git-lfs clean %f
    filter.lfs.smudge=git-lfs smudge %f
    filter.lfs.required=true
```

To see what values are set in local repository you have to be in a **git** repository otherwise it can not read any file as shown below.

```git
    K:\>git config --local -l
    fatal: unable to read config file '.git/config': No such file or directory
```


The `--local ` option is used for any local git repository file which is created when git is initialized locally as shown below.

    K:\projects\c-dir-record>git config --local -l
    core.repositoryformatversion=0
    core.filemode=false
    core.bare=false
    core.logallrefupdates=true
    core.symlinks=false
    core.ignorecase=true
    core.hidedotfiles=dotGitOnly

### Writing to **.gitconfig** file

When it comes to writing the new values to the config file by default it is written in reverse order i.e., it is written to the most specific repository which is local repository config file. If you need to write to global config file or system config file then the use of `--global` or `--system` flag is necessary. Below we will be writing to the global config file.

#### Setting an editor globally with **.gitconfig**

By default **git** uses **vim** editor  to change the default editor add the details of your favourite editor in **.gitconfig** file. Following code will set sublime  globally as a default editor.

        K:\>git config --global core.editor "'C:/Program Files/Sublime Text 3/sublime_text.exe' -w"
        K:\>git config --global core.editor     <-------- query the setting
        'C:/Program Files/Sublime Text 3/sublime_text.exe' -w

#### Setting a different editor locally with **.gitconfig**

If for some reason you need to use a different editor for any particular project you are working on then set its detail in a local **config** file which is kept under the local repository **.git/.config**. Following example will set a notepad++ editor to be used locally. 
    
    K:\projects\c-dir-record>git config --local --add core.editor "'C:\Program Files (x86)\Notepad++\notepad++.exe'"
    

Once it is set a user can invoke this editor using `>git config -e` this will invoke a locally set editor instead of globally set editor

To add any user specfic variable use `>git config --global --add < key > <value>` pair as shown below.

        K:\>git config --global --add user.dob "1978/03/02"

To change the above value use `--replace-all`

        K:\projects\c-dir-record>git config --global --replace-all user.dob "1999/01/11"
Similarly to delete the entry use `--unset-all` option.

        K:\projects\c-dir-record>git config --global --unset-all user.dob "1999/01/11"

#### Changing Color Setting for local repository

Though these days there are number of desktop programs which help you perform day to day jobs with git and provides a better graphical user interface with color coded result yet the option to change some  settings are allowed from **git**. You can either add the values manually in **.git/.config** files or add the values into this file by using option provided by config file from command prompt.Following code will add some values to local config fle:

- Open local repository config file using `>git config --local -e`

#### Where are they saved ?

One of the file named `gitconfig` is saved under `C:/User/UserName/` where it can be modified directly.

[//]: # ( above - t )

### What is the line ending

There is one important thing to note when working with windowed environment and this is the way windows handle line endings of any text file. In order to understand the problem one must understand that every time   "Enter" Key is hit  the system adds an invisible line-ending character to mark that this an "Enter Key" a line ending key and it is not a part of the text being written. This "Enter " key is also known as carriage return "CR" Unix and its variants systems including OS X use `LF` character while Windows uses `CRLF` to mark end of line. This end of line invisible character is also stored when every time  a file is stored along with the contents of the file and read back when reading the file.

If the concerned code was not shared there was nothing to worry about but the whole existence of **git** is to share code regardless of what system being used. **git** has chosen to use the `LF` character over `CRLF` probably because of its author's background. So when you `commit` your files basically you are writing something to the object database which is itself a file stored in the **.git** local repository. Thus every commit involves changing `CRLF` to `LF` if you are working in windows environment. Similarly if you are reading it back i.e., when you `checkout` or `clone` a git repository in windows environment the conversion from `Lf` to `CRLF` takes place again. 

To make sure the above process happens smoothly **git** adds a line in your system config file `core.autocrlf = true` Which ensures that the writing to and reading from database file operation carried out as intended. This value can be checked by running `>git config -l` as done in previous section. If you are working in Unix environment and working locally without sharing your code the value of this variable most probably be set to false `core.autocrlf = false` . If this value is set to input as `core.autocrlf=input` means that conversion from `CRLF` to `LF` takes place only when writing to  object database but not the other way round. If you noticed when installing the **git** you were provided the choice about the line ending if you didn't understand what was all about make sure you understand it now. Follwoing option were given to you  and according to you choice values were added to the config file.

![installing-windows](/images/git/installing-windows-04.png)

If you had noticed previously,  the out put of `>git config -l` command,  you must have  seen  that the system setting has already this entry of `cor.autocrlf=true`  set to true which should be the case in Windows environment and obviously this setting should be in **git** system configuration file not in global or local config file.

Though the above discussion of line ending and having autocrlf set to true sounds safe but is regarded the old way. From the **git** version 1.7.2 and above **git** expects you to define the details of your files  and how these files should be treated whether a conversion is required or not and if it required what is the line ending character and not only this **git** also gives you option to define explicitly which files are to be treated as a test file and whether **git** should perform any checking operation or not.

This is done by providing `text ` attribute to the files which you intend to tell **git** to treat as a text file by mentioning it in a file named `.gitattribut`that you keep it with your repository. Here is an example of `.gitattribute` file. 

[//]: # ( provide better detail)

        # Default behaviour
        * text      auto
        
        # Following files are text files 
        *.css       text
        *.md        text
                                                                                
        # Following files are not text files    
        *.png       binary
        *

What exactly you are telling **git** is that all files defined as text files should be normalized  without **git** checking it. A conversion of `CRLF` to `LF` must take place.


To understand why it was done is to understand that not all the the time a text file is written to object database. There are number of files which differs from text files so it seems an intelligent choice to put this responsibility to the person who is to commit the files.

# Start Using git remotely

The purpose of installing **git** was to make sure that the project  files or files in the project folder ,you are working on, remains intact with version system and if later on you decide to share them on remote repository so other can collaborate smoothly.In next chapter we will learn how to set a repository for the project of our interest.Be clearly sure that so far only a local repository software **git** has been installed and configured for a one person to use, nothing else has been done.

## What is GitHub

GitHub is a remote website, that you can use to store your repositories so that they can be shared and others can contribute to your work. So can you by finding out any project of your interest and collaborate.

## How to interact with GitHub account

The whole idea of using git is not only to use a source version control system but also to share your work with other people what is known as collaboration.The very first step you need to do is to go to [github](https://github.com) and create your account. Once your *github* account is ready on remote sever. The second step is to make a link between *git* on your computer and *github* on your remote server what is known as **Authenticating with GitHub from Git**. And to do so you may download a program called [GitHub Desktop Client](https://desktop.github.com/) . As the name suggest it sits on your computer and interacts with the remote server providing you a UI ( user interface ) which lets you do all the related works you might want to do . The same process of interacting to the remote server can be done using a command prompt or any other utility program too.

### Installing GitHub Desktop Client

Download this program  [GitHub Desktop Client](https://desktop.github.com/) from the GitHub site and run it . When run, it will ask you to provide the user name or the email address of your GitHub account as shown below, fill it up with the right information. When *git* account from your computer gets linked with *github* account on remote server. You can perform all the task which you many do from the command prompt.  This client application  will further ask you to select any repository from your computer to be uploaded to your github account. You can skip this step if you want as this is done in next chapter.  

[//]:# (@Change this picture ![Configuring-git](/images/git/installing-gitclient-01.png))


### **git help**

Before finishing the chapter we will look into **git**'s available help options.**git** provides extensive help through its manual pages as well as short format on command prompt. The rule of thumb is that if you type any  valid **git** command without its expected flag **git** will output the command specific short help with some suggestion as we saw earlier typing only `>git`.

All **git** commands are also known as **git** tools since they provide some services and perform some actions. Remember if you type a command which does not take any argument to run followed by the **git** then this command will run. Thus a rule of thumb is to use this syntax `>git < command > --help`. This syntax will always open manual page related to this tool/command in an external browser.

To use the  git commands correctly , understanding of a  syntax is must a common usage is `>git <command> [<args>]` .

```text
            command
                |   argument
                |   |
                V   V
        >git  init  .       <------- Initializes the current direcotry
                                          as a repository
```

Let's look at the help command itself first provided by **git** using the above rule. To find out what help options are available for **help** tool use `>git help --help` and a manual page will be open to see the help in detail.
in short format just use the above rule and type `>git`. The output will give commonly used commands and at the end it suggests to use `>git help -a` and `git-help-g` it also suggests to see `git help < command >` or `>git help < concept > ` to read about any specific subcommand or concept.

- First use `>git help -a` and look at the result shown. It gives you the list of git commands that are used but without any explanation of how to use them.
- Secondly use `>git help -g` and look at the result shown. It gives you list of common **git** guides available on your platform . Following is the output of this command.

```text

            K:\projects\c-dir-record>git help -g
            The common Git guides are:
            attributes   Defining attributes per path
            everyday     Everyday Git With 20 Commands Or So
            glossary     A Git glossary
            ignore       Specifies intentionally untracked files to ignore
            modules      Defining submodule properties
            revisions    Specifying revisions and ranges for Git
            tutorial     A tutorial introduction to Git (for version 1.5.1 or newer)
            workflows    An overview of recommended workflows with Git
```


Let's look at the guides suggested by the above result using `>git help < guide name >` as `>git help tutorial` or `>git help glossary` and so on. By typing these commands **git** opens installed default browser to show this guide. These guides provide tremendous amount of  knowledge for someone who is interested in learning more. Coming back to our help commands topic to use any specific tool of git using the same rule just type the command followed by the **git**. For example to see how to use `init` command type `>git help init` and it should open its associated manual page with the detail about this command and its usage. Similarly type `>git help config` or `>git config --help` This should open a manual page of help in your default browser about using config command.Have a look if it make any sense to you. Do not worry, every thing takes time specially if you have never worked on Unix system.

<!-- this chapter ,try the following command to open help in the html format as you may have noticed in our config setting it says `help.format = html` Type either of these and you will get the same result. -->



As we have tried the very first command option listed you can go ahead and try the second one `>git --help` and you get the same listing as you did get it without  `--help`.So make a note that either `>git` , `>git --help` or `>git help` will give output the same result. This rules applies to most of the git commands.To see a clear listing of all available help type`>git --help -a | more` and you get all the available command through pipe `|` symbols so you can read them easily with the help of a space bar to scroll down. To see help in your browser use `>git help man ` or `>git man --help` . To see what guides are available use `>git help -g `

## Installing `git` on Linux

`Git` is developed in linux and very easy to install but different from windows installation as they both system differs greatly. To install `git` on linux just use `apt-get` package or any other package installer according to your distro.

```shell
$ apt-get update or sudo apt-get update or sudo apt-get install git-core
// you need the following line to install git, you can do whatever way you like
$ apt-get install git-core 
```

git will be installed hopefully in `/usr/bin/` directory, if needs to know where it is installed use `which /usr/bin`. Use `git version` command to see the installed git version.

### Configuring git in linux

Unlike windows linux does not require many varaibles to be set up, if you try to take the listing of git, you might end up with having no listing at all. As it is not needed by default. The only entries that are present and expected to be changed by you is the user name and email address which pops up time and time again when working so it is best to have those values stored in `.gitconfig` file.

```shell
$ git config --list
$ 
$ git config --global --list
$
$ git config --local --list
```

Nothing is set so nothin is shown, go to your user home directory.`cd ~/` and look for the entry `.gitignore` and open it in the editor or use `cat .gitigonre` to see the contents. Change the values whatever you want.

```git
sayyed@AI:~|⇒  cat .gitconfig
# This is Git's per-user configuration file.
[user]
# Please adapt and uncomment the following lines:
#       name = Abdul Sayyed
#       email = sayyed@localhost.localdomain
```

This is the default values and filled from the system setting when git was installed you can change to whatever you wish.

>Note: you will still not find any listing for the --global or --system flag.



### Summary

What we have learned so far:

1. How to install **git**
2. How to check the installation if it is working or not
3. How to configure git to set your identity
4. Which .gitconfig file? { local, global or system}
5. Writing to gitconfig file
6. Setting different editors to use  git locally and globally
7. What is the line ending and why it is necessary to understand it
8. what is GitHub, installing Github client
9. How to use git help locally

<!-- #Quiz#
Here you are given simple scenario choose the best answer and see your progress


### To Do

1.	What is GitHub
2.	How to clone git from outside resources
2.	How to remove external .git using `rm -rf <package name>/.git
3.	How to add files or folders to be ignored by git.
4.	 -->

