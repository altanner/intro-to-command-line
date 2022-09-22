---
title: "‣ Working with remote computers"
subtitle: "Work with far away machines from the comfort of your own computer!"

date: 2022-09-18T00:00:00+01:00

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

### Working remotely

The original super-power of the command line is that it allows us to connect to other machines. While today we have remote-desktops and screen-shares to see and work with other computer's GUIs, the command line has been doing this since the 1960s!

In research, we often work on remote machines ("computing clusters", "HPC", "supercomputers", or even just "servers"), which we need to log in to. Once we are logged in, the terminal will behave as if we are sitting at that machine, which might be on the other side of the world. (As such, it can be confusing to know whether a terminal is just controlling your computer, or one far away, as the terminal will still look very similar!)

### Using `ssh`

`ssh` is a program for opening a command line session on a remote computer. The name is short for "secure shell", because it opens a shell to communicate with a remote machine on the same network, using an encrypted, secure connection. In other words, it uses the international network (also known as the internet!) to talk to another computer, and that conversation is private, locked with encryption keys.

We have specific documentation for how to use `ssh` (and `scp`) on our [HPC training](https://www.acrc.bris.ac.uk/protected/hpc-docs/training/intro-to-hpc-slurm/logging_on.html). Here we will cover the basics of how to understand these commands, and their syntax.

Note that when you are not on University of Bristol campus or premises, you will need to use the university's VPN service to successfully `ssh` into computing facilities. See [these pages](https://uob.sharepoint.com/sites/itservices/SitePages/vpn.aspx) for more details on how to install the VPN on your computer.

### Using the command line, but on a remote machine

To successfully connect to another machine using `ssh`, that machine needs to know who you are: you will need a username and a password (although other authorisation methods exist, which we will not cover here). The syntax is the command `ssh`, followed by your username and the hostname (just like you see in a prompt), for example
```
ssh yt29876@bc4login.acrc.bris.ac.uk
```
or, you might log in using the IP address of the remote machine
```
ssh yt29876@137.222.1.10
```
You will then be asked to enter your password - it will not display anything or display stars (\*) as you type, it will just look empty. If the password is correct, you will then see a new prompt, including the name of the machine you are now logged in to, for example:
```
[yt29876@bc4login3 ~]$
```
{{< admonition type="tip" open=true >}}
If you forget your `ssh` login commands, remember that all your previous commands are stored in `history`. Perfect use of a pipe! To list your previous `ssh` commands, we can pipe the output of `history` into `grep`, searching for `ssh`, with
```history | grep "ssh"```
{{< /admonition >}}

Now your command line session is running *another* command line session, on another computer. (Kind of like in *Inception*. I expect that cultural reference is out of date now.) Just like with a local command line, you can leave using the command `exit`. You will be able to move around and run commands, just like on the machine that is actually in front of you. Of course, other machines will be structured differently, and have security measures meaning you cannot look at other people's folders or run dangerous commands. If you are using shared computing facilities, as with all of the University of Bristol's computing clusters, keep in mind that you are in a bustling hub of colleagues and researchers - you can see who is logged on with the command `w` (yes, just a "w").

For HPC machines *do not run research work on the login nodes!* An HPC machine has a "headnode", a kind of "lobby" where you can arrange your work in your home folder. But, you send your analysis in to the high-performance computers using "submission scripts". Running work "on the headnode" is like walking into a factory, then asking the receptionist to do the industrial work! Not only is this slow, but it can break the whole system, which could result in the loss of work for others! Avoid this at all costs :)

We do not cover submission scripts in this course, but to learn more please see our [HPC resources](https://www.acrc.bris.ac.uk/protected/hpc-docs/introduction/index.html).

### Copying files to and from remote machines using `scp`

`scp` ("secure copy") is just like `cp`, except it can copy files and folders to and from another computer. Just like with `ssh` above, we will need to specify what computer the file or folder is on. To do this, `scp` needs to know the address of the machine it is working with.

First, let's copy a file *from* our local machine *to* another machine. If you have the resources from earlier in this course, try copying one of the plays to another machine. As with `cp`, the syntax is `cp [what to copy] [where to copy this to]`. Move to the appropriate folder, and try a command similar to this (you will need to substitute a real username and hostname!)
```
scp macbeth.txt yt29876@bc4login.acrc.bris.ac.uk:/user/home/yt29876
```
Note that the destination includes a full path. Sometimes, the remote machine will understand `~` as your home folder, and missing it out completely will also work, sending the file to your home folder. The important bit is, don't forget the `:`, or your computer will think you want to copy the file locally, and name the file the name of the remote computer! So, if you see a file hanging around called something bizarre like `yt29876@bc4login.acrc.bris.ac.uk`, this is usually the result of a failed `scp`.

Just like with `cp`, you can copy the contents of folders with the flag `-r`. See the `man` pages for more details.

{{< admonition type="warning" open=true >}}
Careless use of `scp` can result in data loss! If a file with the same name already exists in the remote machine in the destination folder, it will be permanently overwritten, without warning, by `scp`!
{{< /admonition >}}

Copying *from* the remote machine back to your local machine uses similar syntax, except you must provide the full path to the file (or folder) you want to copy. Often, you specify the local destination of the `scp` command with the abbreviation for "here": `.`. Alternatively, you can provide an absolute or relative path, or a different filename as the destination.

So, the above command, but to copy *back* to your own machine would be
```
scp yt29876@bc4login.acrc.bris.ac.uk:/user/home/yt29876/macbeth.txt .
```
{{< admonition type="info" open=true >}}
If you are already `ssh`ed into another computer, you might think you can `scp` a file from there, back to your own computer. However, the internet just doesn't work that way! A valid remote machine is "known" to the internet (has a public IP address that can be looked up), and its communication channels are set to allow incoming and outgoing transfers. In contrast, your own private machine, typically, is not open for other computers to directly connect to it - trying to `scp` back to your own machine won't work, as the internet has no idea what or where your own computer is!

So, if your terminal is tied up with an `ssh` session but you want the data back on your own computer, you will have to open another terminal and "request" the files using `scp`, as above.
{{< /admonition >}}
