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

The original super-power of the command line is that it allows us to work on other machines. While we now have remote-desktops and screen-shares to see and work with other computers's GUIs, the command line has been doing this since the 1960s! In research, we often work on remote machines ("computing clusters", "supercomputers", "HPC", or even just "servers"), which we need to log in to

### `ssh`

`ssh` is a program for opening a command line session on a remote computer. It is short for "secure shell", named this because it opens shell communications using an encrypted, secure connection. In other words, it uses the internet to talk to another computer, and that conversation is private. (This happens for almost all communications on your computer and phone, for example.)

### edit me

Let's create a very simple script - open `nano`, creating a file called "my-first-script.sh" (or anything you like!) and include two lines
```shell
ls -l *part*
echo "That is all of the files with \"part\" in that I could find here."
```
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
