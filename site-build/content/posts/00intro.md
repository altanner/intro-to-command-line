---
title: "∙ Welcome to the command line!"
subtitle: "The keys to great power are easier to use than you think :)"

date: 2022-09-10T00:00:00+01:00

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

{{< admonition type="note" title="Glossary" open=false >}}
It it entirely normal to be confused about these words:
* **terminal** - a program which emulates (mimics, in software) a (now redundant) piece of hardware, which provides the command line.
* **console** - effectively, the same thing as a terminal. Note that we also say "console" when referring to an interactive session of a programming language, for example Python.
* **shell** is a program that sends our commands to the operating system (OS), and sends responses from the OS back to the user. Technically, we are using a shell language on the command line, but you don't need to worry about that!
* As far as we are concerned, **these all mean the same thing: the command line!** Being confused by this is entirely natural.
{{< /admonition >}}

### Starting a terminal
If you are using MacOS or Linux, you will have *Terminal* already installed - open this program and you will be presented with a command line. To open a suitable terminal session on Windows, install and run *GitBash*, or use *Windows Subsystem for Linux (WSL)* to install a Linux distribution (we recommend Ubuntu or Debian) - then open that program. The Windows-native *PowerShell* is not a "UNIX-like" terminal, and is not compatible with this course.

### The prompt
When you open a terminal, you will be provided with a line for entering commands, starting with a *prompt*. The prompt tells you where, in your computer you are. When on the command line, you always have a location, just like you do in graphical file managers like MacOS's "Finder", or Windows' "Explorer". Here is what a typical prompt looks like:

```
[alleetanner@work_laptop:/Users/at9362] $
```

Your prompt will look different, but here is what it means

```
[ your name @ the computer's name : the current folder ] $
```

First is your own user name. On university computers, it might be a code like in your email address, such as `bx22657`. After the `@` comes the computer's name (also known as the "hostname"). This could be something like `Megans_iMac` or `ubuntu`, for example. Note that this is the name of the computer *that you are logged in to*! Usually, on opening a terminal, that is the actual computer in front of you. But, for example when using HPC, it will instead be another computer - a "remote" machine, that you have logged in to. However, in this course, we will only be working on your own machine, the "local" computer. Finally, we have the folder you are working in, after the `:`. Yours might say `~` ("tilde") - find out what that means in the next section.

The `$` (or you might have a `%`) symbol means the terminal is waiting for a command. *Sometimes you will see commands on the internet which include the `$` symbol at the start of the command - you don't need to include this as part of the command, say if you cut and paste!* 

### The command line
The space after the prompt is where you enter your instructions of what you want the computer to do: your **commands**.

{{< admonition type="info" open=true >}}
- The command line is case-sensitive. The letter `H` is entirely different from `h`, for example! So if you are having issues, always check your capitalisation is correct.
- You can select, cut etc with the mouse cursor, but you *cannot* move the position of your typing cursor with the mouse! You can only do that with the arrow keys. This is because a remote machine can only understand plain text, not communications from your mouse.
- You can use `tab` to auto-complete: *try this wherever you can!*, it will save you lots of time and typos.
- You can scroll back through your previous commands with the `up arrow` (and `down arrow`) - another big time-saver.
- If it looks like the terminal is stuck, or you want to cancel a command, it is `ctrl-c`.
- To exit a terminal session, type `exit`.
{{< /admonition >}}

### The grammar of a command
Thinking about the grammar - the structure - of a command helps us understand what we are doing. Luckily, command grammar is much simpler than English grammar, with just three things to remember.
##### Verbs
Every line you write starts with a *command* - the name of a program. Even the most basic operations (such as listing files) are small programs you are asking the computer to run, or to *do*. So, in grammatical terms, the command is a *verb*.
##### Adverbs
We can ask the computer to run a command, *in a particular way* - these are *adverbs*. In computing speak, these are known as *flags*, and usually start with a `-` symbol. 
##### Objects
Often we need to tell the program *what we are doing the action to* - the *object*. These are also known as an *argument* (yes, more strange words, I agree!).

Just like in spoken language, where a sentence must have a verb to be complete, a command must have at the very least the name of a program to run. Adverbs are optional. And many verbs require an object to act upon. So the correct grammatical order for a command is
```
verb adverb object
```
or
```
[program to run] [how to run it] [what to run it on]
```

Let's get started with our first commands in the next section!

