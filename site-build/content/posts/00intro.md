---
title: "‣ Welcome to the command line!"
subtitle: "The keys to great power are easier to use than you think :)"

date: 2022-01-01T00:00:00+01:00

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

### Starting a terminal
If you are using MacOS or Linux, you will have "Terminal" already installed - open this program and you will be presented with a terminal session. To open a suitable terminal session on Windows, install and run *GitBash*, or use *Windows Subsystem for Linux (WSL)* to install a Linux distribution (we recommend Ubuntu or Debian) - then open that program. The Windows-native *PowerShell* is not a "UNIX-like" terminal, and is not compatible with this course.

### The prompt
When you open a terminal, you will be provided with a line for entering commands, starting with a *prompt*. The prompt tells you where, in your computer you are. When on the command line, you always have a location, just like you do in graphical file managers like MacOS's "Finder", or Windows' "Explorer". Here is what a typical prompt looks like:

```
[alleetanner@work_laptop:/Users/at9362] $
```

Your prompt will look different, but here is what it means

```
[ your name @ the computer you are logged in to : the current folder ] $
```

First is your own user name. On university computers, it might be a code like in your email address, such as `bx22657`. After the `@` comes the computer's name (also known as the "hostname"). This could be something like `Megans_iMac` or `ubuntu`, for example. Note that this is the name of the computer *that you are logged in to*! Usually, on opening a terminal, that is the actual computer in front of you. But, for example when using HPC, it will instead be another computer - a "remote" machine, that you have logged in to. However, in this course, we will only be working on your own machine, the "local" computer. Finally, we have the folder you are working in, after the `:`. Yours might say `~` ("tilde") - find out what that means in the next section.

The `$` sign means the terminal is waiting for a command. *Sometimes you will see commands on the internet which include the `$` symbol at the start of the command! You don't need to include this as part of the command, say if you cut and paste!* 

### The command line
The space after the prompt is where you enter your instructions of what you want the computer to do: your **commands**.

{{< admonition type="warning" open=true >}}
- The command line is case-sensitive. The letter `H` is entirely different from `h`, for example! So if you are having issues, always check your capitalisation is correct.
- You can select, cut etc with the mouse cursor, but you *cannot* move the position of your typing cursor with the mouse! You can only do that with the arrow keys.
{{< /admonition >}}
{{< admonition type="info" open=true >}}
- You can use `tab` to auto-complete: try this wherever you can, it will save you lots of time and typos.
- You can scroll back through your previous commands with the `up arrow` (and `down arrow`) - another big time-saver.
- If it looks like the terminal is stuck, or you want to cancel a command, it is `ctrl-c`.
- `ctrl-a` is "move my cursor to the start of the line"
- `ctrl-e` is "move my cursor to end of line"
- To exit a terminal session, type `exit`.
{{< /admonition >}}

### Anatomy of a command
Every line you write starts with a *command*: the name of a program. Even the most basic operations of moving around and listing files are small programs you are asking to run. Sometimes we only need the command, but as we will see, sometimes we need to tell the program what we are doing the action to - linguistically, the *object*. At other times, we might need to ask the program to do the action *in a particular way* - think of these as *adverbs*. In any case, the syntax for a command is in this order:

```
verb adverb object
```

In the next section we will run our first commands!
