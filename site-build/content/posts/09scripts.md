---
title: "‣ Shell scripts"
subtitle: "Files as a series of commands"

date: 2022-09-19T00:00:00+01:00

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
```
ls -l *part*
echo "That is all of the files with \"part\" in that I could find here."
```
{{< admonition type="info" open=true >}}
- If you didn't look up `echo` earlier, use `man` to work out what it does.
- Think of `echo` as `print`, used commonly in programming languages.
{{< /admonition >}}

Save the file and exit `nano`. Now, we are going to run this file, in the folder `some_plays`. To do this, we are going to ask the program `bash` ("Bourne Again shell", a widely-used shell program) to run it, with
```
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

If you can complete this task - congratulations, you now know all of the important ways of navigating the file system, of searching files, and the basics of shell scripting.

{{< admonition type="success" title="Learn more" open=true >}}
When learning to use computer clusters and high-performance computers, we often run jobs using "submission scripts". These are just the same as a shell script - they are not magic, merely running commands one after another, just like you could on the command line itself.

You can learn these skills in our course *Introduction to HPC*, do an internet search for our current courses.
{{< /admonition >}}

