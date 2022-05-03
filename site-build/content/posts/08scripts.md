---
title: "Shell scripts"
subtitle: "Commands as files, files as commands"

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

### Scripts

So far, we have been running things directly on the command line, "interactively". However, you might want to keep your commands in a file, and be able to run, share, modify, or use files as templates. This is the gateway to coding - and is great practice for developing your reproducible work, for communicating your methods with others, and for archiving your work.

A "script" is a file of instructions that can be directly read and run by a program. For example, a file of Python code is a script, since it does not need to be compiled into binary - this is done by the Python interpreter, working as it goes along. In our case, we are going to make a script, but the language will be shell (all of the commands we have been using so far are shell commands).

Let's create a very simple script - open `nano`, creating a file called "my-first-script.sh" (or anything you like!) and include two lines
```shell
ls -l *part*
echo "That is all of the files with \"part\" in that I could find here."
```
{{< admonition type="info" open=true >}}
- If you didn't look up `echo` earlier, use `man` to work out what it does.
- Think of `echo` as `print`, used commonly in programming languages.
{{< /admonition >}}

Save the file and exit `nano`. Now, we are going to run this file, in the folder `some_plays`. To do this, we are going to ask the program `sh` ("shell") to run it, with
```shell
sh my-first-script.sh
```

Let's use all of the skills we have learned today to build a script to complete a task. The goal here is to

{{< admonition type="question" title="Exercise" open=true >}}
- Use `nano` to start a new, empty file.
- Write your commands, each on a new line.
- Save and exit, and run the script.
{{< /admonition >}}

Learn more box here - intro to hpc etc.