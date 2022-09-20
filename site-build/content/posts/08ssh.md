---
title: "‣ Logging in to remote computers using `ssh`"
subtitle: "Work with far away machines from the comfort of your own computer!"

date: 2022-01-09T00:00:00+01:00

fontawesome: true
linkToMarkdown: true

toc:
  enable: true
  keepStatic: false
  auto: false
code:
  copy: true
math:
  enable: true
share:
  enable: true
comment:
  enable: true
---

### Working "remotely"

The original super-power of the command line is that it allows us to work on other machines. While we now have remote-desktops and screen-shares to see and work with other computers's GUIs, the command line has been doing this since the 1960s! In research, we often work on remote machines ("computing clusters", "supercomputers", "HPC", or even just "servers"), which we need to log in to. Once we are logged in, the terminal will behave as if we are sitting at that machine, which might be on the other side of the world. (As such, it can be confusing to know whether a terminal is just controlling your computer, or a different computers, as the terminal will still look almost identical!)

### `ssh` and `scp`

`ssh` is a program for opening a command line session on a remote computer. The name is short for "secure shell", because it opens a shell to communicate with the remote machine, using an encrypted, secure connection. In other words, it uses the internet to talk to another computer, and that conversation is private, locked with encryption keys. (This happens for almost all communications on your computer and phone, for example.)

`scp` ("secure copy") is just like `cp`, except it can copy files and folders to and from another computer.

We have specific documentation for how to use `ssh` and `scp` on our [HPC training](https://www.acrc.bris.ac.uk/protected/hpc-docs/training/intro-to-hpc-slurm/logging_on.html). Here we will cover the basics of how to understand these commands, and their syntax.

Note that University of Bristol machines will only allow you access when your connection is using the university's VPN service. See [these pages](https://uob.sharepoint.com/sites/itservices/SitePages/vpn.aspx) for more details on how to install the VPN on your computer.

### Using the command line on a remote machine

Using `ssh` from the command line will require a valid log in or user account on the machine you want to log in to. The syntax is to run `ssh` followed by your username and the hostname (just like in a prompt), for example
```shell
ssh yt29876@bc4login.acrc.bris.ac.uk
```
or, you might log in using the IP address of the remote machine
```shell
ssh yt29876@137.222.1.10
```
You will then be asked to enter your password - it will not display anything or display stars (\*) as you type, it will just look empty. If the password is correct, you will then see a new prompt, including the name of the machine you are now logged in to:
```
[yt29876@bc4login3 ~]$
```
Now your command line session is running *another* command line session, on another computer. (Like in *Inception*. I expect that reference is out of date now.) You will be able to move around and run commands, just like on the machine that is actually in front of you. Obviously, other machines will be structured differently, and have security measures meaning you cannot look at other people's folders or run dangerous commands. If you are using shared computing facilities, as with all of the University of Bristol's computing clusters, keep in mind that you are in a bustling hub of colleagues and researchers, so remember to be polite!

You can see who is logged on with the command `w` (yes, just a "w"). For HPC machines *make sure you do not run research work on the login nodes!* An HPC machine has a kind of "lobby" where you can arrange your work, and you send your analysis in to the proper factory-floor of powerful computers. Running "on the headnode" is like arriving at an industrial facility, then asking the receptionist to do the work meant for the facility! Not only is this slow, but it can break the whole system, which could result in the loss of work of hundreds of researchers!

We do not cover job scheduling in this course, but to learn more please see our [HPC resources](https://www.acrc.bris.ac.uk/protected/hpc-docs/introduction/index.html)
{{< admonition type="info" open=true >}}
- If you didn't look up `echo` earlier, use `man` to work out what it does.
- Think of `echo` as `print`, used commonly in programming languages.
{{< /admonition >}}

Save the file and exit `nano`. Now, we are going to run this file, in the folder `some_plays`. To do this, we are going to ask the program `bash` ("Bourne Again shell", a widely-used shell program) to run it, with
```shell
bash my-first-script.sh
```

### Exercise
Let's use all of the skills we have learned today to build a script to complete a task. Be in the folder `some_plays`. Use `nano` to start a new, empty file. Create a script that will:

{{< admonition type="question" title="Exercise" open=true >}}
- Print the final line of _Macbeth_
- Count how many time the word "merry" occurs in all plays starting with the letter "m"
- Count how many times Hamlet speaks in _Hamlet_
- Print the line of who edited each play
- Use `head` and `tail` to print _just_ the 500th line of _All's Well That Ends Well_
- Make a new file containing _just_ the 1000th line of _A Midsummer Night's Dream_ **backwards**!
- Make a new file, in the folder _containing_ `some_plays`, of the total count of the lines containing the word "love" in all of the plays (combined - ie a single number).
{{< admonition type="tip" open=true >}}
Test each of your commands individually on the command line, before building them into your script.
{{< /admonition >}}
{{< /admonition >}}
