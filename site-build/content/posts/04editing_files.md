---
title: "∙ Editing files"
subtitle: "How to create and modify files"

date: 2022-09-14T00:00:00+01:00

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

### Text editors

We can create and modify files on the command line using text editors. These are like very minimal word-processors, with no formatting options, but with many powerful ways of editing that are not available in word-processors. There are lots of different command line editors, which range from user-friendly (but less powerful), to more difficult (but powerful and fast, once learned).

{{< admonition type="info" open=true >}}
Here are some common editors you might come across, or choose to learn:
- `nano` an easy to use and widely-available editor
- `micro` a more modern version of nano
- `emacs` a hugely-powerful editor, jokingly referred to as an operating system in itself. Medium learning-curve.
- `jove` a minimal version of emacs (this is my favourite ;)
- `vim` is legendary as the "coder's editor", being very powerful, very fast, but having a steep learning curve and heavy reliance on keyboard shortcuts. Very widely available - almost all systems have `vim` installed.
{{< /admonition >}}


### Editing a file with `nano`
We will learn the basics with `nano`. Run this command:

```
nano animals.txt
```

The screen will look a little different: just like with `less`, *you are now not on the command line*, but running the program called `nano`. Try making some changes to the file with your keyboard (remember the mouse cannot move your cursor).

{{< admonition type="info" open=true >}}
There are many commands that `nano` can do, but here are a few you will need to know
- `ctrl-o` is save ("output a file")
- `ctrl-w` is search ("where?")
- `ctrl-x` is used to exit `nano`.

Note that there is a basic cheatsheet along the bottom of the screen for some common commands inside `nano`.
{{< /admonition >}}

### Creating a new file
Have a play. Exit back to the command line. Now we are going to make a new file. You can call it whatever you like - as long as that file name doesn't already exist here, it will make an empty file.

```
nano my_new_file
```

Note that in Linux systems and MacOS, the file extensions (for example `.txt` or `.mp3` or `.pdf`) are entirely optional. You can even have multiple extensions, like `file.txt.new.extension`, which to Linux system is all just the name. In Windows, file extensions are important! They are also useful for humans too, so where it is appropriate, best to stick to convention. Calling an `.mp3` file a `.docx` file is valid, but highly confusing :)

If you try to leave `nano` (`ctrl-x`) when there are unsaved changes, it will ask to `save modified buffer?`. So, save or not with `y` or `n`, and let's look at examining files back on the command line. (A "buffer" is information that exists on your screen, or in your RAM, but does not exist in storage memory. In other words, stuff you have not saved yet.)

{{< admonition type="info" open=true >}}
Don't be afraid of error messages :)

When you get things wrong, the command line will tell you, but messages can seem hard to understand. Most commonly, the message will tell you what went wrong, or how to use a command. For example, if I try to copy a file which does not exist:
```
cp file99999 file3
```
the computer responds with
```
cp: file99999: No such file or directory
```
Think of this as a speech bubble, with `cp:` being who is speaking, here saying that a file doesn't exist, at least not in this folder. Here is another example
```
lf
```
and the shell itself (`zsh` in this case) tells you it doesn't know what `lf` means:
```
zsh: command not found: lf
```
Some commands will give you very brief instructions on how it is used as an error message. For example, if we ask `mv` to run, but not actually move anything,
```
mv
```
we get a couple of `usage` instructions:
```
usage: mv [-f | -i | -n] [-v] source target
      mv [-f | -i | -n] [-v] source ... directory
```
The items in the square brackets are flags that `mv` can take, and `source target` tells you the order of arguments. The `...` means that you can copy multiple items to a single target location (typically, when you `mv` multiple items into the same folder).
{{< /admonition >}}
