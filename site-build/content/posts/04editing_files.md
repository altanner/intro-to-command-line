---
title: "Editing files"
subtitle: "How to create and modify files"

date: 2022-01-05T00:00:00+01:00

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

```shell
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

```shell
nano my_new_file
```

Note that in Linux systems and MacOS, the file extensions (for example `.txt` or `.mp3` or `.pdf`) are entirely optional. You can even have multiple extensions, like `file.txt.new.extension`, which to Linux system is all just the name. In Windows, file extensions are important! They are also useful for humans too, so where it is appropriate, best to stick to convention. Calling an `.mp3` file a `.docx` file is valid, but highly confusing :)

If you try to leave `nano` (`ctrl-x`) when there are unsaved changes, it will ask to `save modified buffer?`. So, save or not with `y` or `n`, and let's look at examining files back on the command line.

{{< admonition type="info" open=true >}}
"Buffer", in computing speak, is information that exists on your screen, or in your RAM, but does not exist in storage memory.
{{< /admonition >}}
