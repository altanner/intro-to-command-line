---
title: "∙ File system navigation"
subtitle: "Understanding where you are, and how to move around"

date: 2022-09-11T00:00:00+01:00

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

### Where am I?
Let's run our first command!

```
pwd
```

With `pwd` we are asking "print my current working directory / where am I?" You will then get some *output* to the terminal window, something like

```
/home/at9362
```

This is your current location, here shown as a "path" - what folder you are in, starting from the "root" folder that contains the whole file system.

{{< admonition type="info" open=true >}}
There are five abbreviations for locations that you might come across
- `~` "tilde", your home folder
- `.` "dot", your current working folder
- `..` "dot dot", one folder "up" or "back" from here
- `-` "dash", the folder you were *most* *recently* in
- `/` "root", the folder containing the whole file system
{{< /admonition >}}

### What is in this folder?

Now that we know where we are, let's see what is here by running a program called `ls` ("list" or "ell ess"). `ls` shows you the contents of your current folder, much like looking at the file manager window in a GUI (Finder in MacOS or Explorer on Windows):

```
ls
```

For me, I get this output, a list of what is here.

```
logfile  records_january  credentials.txt  creds  data_depot  git
```

Yours will be different. Each of these things are the items (files and folders) in your current working directory. For most terminals, items in white are files, and items in blue are folders. The first thing we are going to do is make a new folder, where we will be doing our work. We will use the command `mkdir` ("make directory"), and this command needs an *argument* (gramatically, an "object"):

### Making our first folder.

Let's create a folder where we can learn how to move around.

```
mkdir intro-to-command-line
```

This command is asking "make a new folder here, called intro-to-command-line". You'll be getting used to the names of commands being abbreviations! Run `ls` again, and see what has changed. Hopefully you will see a new folder, appropriately named.

{{< admonition type="info" open=true >}}
"Folder" and "directory" are different words for the same thing! I prefer "folder" myself.
{{< /admonition >}}

We can then move into the folder we have made with

```
cd intro-to-command-line
```

Here we are asking to "change my working folder to intro-to-command-line". This is the same as double-clicking a folder in your GUI, to move into that folder. Try doing `ls` and `pwd` here, to see how the output changes. We can go back to your home folder by going

```
cd ..
```

This means "change folder to the one above this one". Going `cd ..` will always move you "backwards" in your folders, unless you are in the root folder `/`. If you are ever lost, remember you can just go `cd` to go back to your home folder.

{{< admonition type="info" open=true >}}
There are actually three ways we could move back to our home folder from here.
`cd ..` as above,
`cd -`, and just
`cd`
{{< /admonition >}}

### Exercise
{{< admonition type="question" title="Questions" open=true >}}
`cd` alone will always take you back to your home folder. Try repeating `cd ..`, and do `ls` each time.
- Where do you end up if you do this several times?
- What is there?
- Can you return to the folder you named `intro-to-command-line`, *using its absolute path*?
{{< /admonition >}}

{{< admonition type="info" open=true >}}
If you end up in a folder called `/`, you are in the "root" folder.

This folder contains the whole file system of the machine you are working on.

You might find mysterious folders called things like `opt`, `etc`, `tmp`. Don't worry about these things for now! They are just folders holding the components of your operating system.
{{< /admonition >}}

Move back to your folder `intro-to-command-line`. From this point forward, we will be working with the [course materials](https://github.com/alleetanner/intro-to-command-line/raw/master/command-line-files.zip) (this is the same file as linked on the home page of this course). Download this file, and using your GUI, move this file into the folder we made in the last section. This might be in your home folder, or your desktop - it doesn't matter where, as long as it makes sense to you! Then unzip the file - double click it, or right-click and "open" it. You will then have a new folder called `command_line_files`.

If you are working on Windows, run this command (since you are using GitBash, we can directly clone the files)
```
git clone https://github.com/alleetanner/intro-to-command-line.git
```

Using `cd`, move into the folder called `sandpit`. From here, look around using `ls`, move around using `cd`, and see what is in each folder.
