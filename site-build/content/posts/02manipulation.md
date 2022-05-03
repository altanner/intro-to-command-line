---
title: "Working with files"
subtitle: "How to delete, rename and copy files (and folders)"

date: 2022-01-03T00:00:00+01:00

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

{{< admonition type="success" title="Learn more" open=true >}}
We give some warnings on this page, but don't be intimidated! Mistakes are only human, and you won't be able to damage your computer through any of these commands.

To improve your skills in backing up, version control, and minimising risk in computing, look for our courses on *Best Practices in Software Engineering*.
{{< /admonition >}}

From this point forward, we will be working with the [course materials](https://github.com/altanner/intro-to-command-line/raw/master/command-line-files.zip) (this is the same file as linked on the home page of this course). Download this file, and using your GUI, move this file into the folder we made in the last section. This might be in your home folder, or your desktop - it doesn't matter where, as long as it makes sense to you! Then unzip the file - double click it, or right-click and "open" it. You will then have a new folder called `command_line_files`.

In our terminal, use the command line to move into the course materials folder, `command_line_files`. When you run `ls` in this folder, you should see the list of contents looking like
```
example_files sandbox       some_plays
```
Personally, I don't find that clear to look at, so let's use our first *flag*, running `ls -l`.

{{< admonition type="question" title="Questions" open=true >}}
- What do you think the `-l` is short for?
- What extra information are you given?
{{< /admonition >}}

{{< admonition type="info" open=true >}}
- Flags are also known as "arguments" and "options" - you will have to get used to this!
- Flags start with a `-`, a dash.
- Spoken, the command `ls -l` might be said "L S dash L"... but sometimes people say "minus", or "hyphen" instead of "dash". These all mean the same thing: the key to the left of the `=+` key.
{{< /admonition >}}

### Copying
Let's move into the folder called `sandbox` and play with some files. Firstly, let's copy a file:

```shell
cp data1 data3
```

Here we are saying "copy the file called data1 to a new file called data3". We now have two identical copies of the same file, only different by name.

{{< admonition type="warning" open=true >}}
- The command line will overwrite files with **no warning!** If, for example, `data3` already exists, the command `cp data1 data3` would overwrite `data3` with the contents of `data1` - permanently deleting the contents of `data3`!
- With great power comes great responsibility! :)
{{< /admonition >}}

### Deleting
Now let's try to delete, or "remove", the file we just made:

```shell
rm data3
```

Here we said "remove the file called data3".
{{< admonition type="warning" open=true >}}
- `rm`, "remove" is the same as delete. But **without a recycle bin, undo, back button, or any other safety-nets.**
- `rm`, `cp` and `mv` commands all have the potential to cause permanent data loss!
{{< /admonition >}}

Now let's try copying, moving and removing folders. There are some folders in the sandbox to play with. Have a go at using `cp` and `rm` on there, and notice what it will and will not let you do. For folders that are not empty, we will need to use another *flag*:

```shell
cp -r folder_with_files_inside folder_copy
```

Here we asked the computer to "copy, recursively, this folder to that folder". Empty folders can be copied, moved and removed, but you will need to use `-r` if there are items insides. `-r` is a common flag which we will use again later.

{{< admonition type="info" open=true >}}
Not all flags mean the same, when applied to other commands! `-r` does the same thing for `cp` and `mv` and `rm`, but don't assume it does the same thing for all commands!
{{< /admonition >}}

Try moving into the folder with files inside.

{{< admonition type="question" open=true >}}
Can you `cp` a file to the folder *containing* the one you are in?
{{< /admonition >}}

### Moving
Finally, let's look at moving files.
```shell
mv data1 data4
```

Which means, "move the file called to data1 to a file called data4". Move is essentially "rename" (although it is doing exactly the same as moving items in your graphical interface).

{{< admonition type="warning" open=true >}}
- As such, if `data4` already existed, it would be *deleted* by the command `mv data1 data4`! Be very careful with `mv`!
- OK, that is my last warning for now :)
{{< /admonition >}}

### Exercise
Have a play in the sandpit, using `cd`, `ls`, and the file manipulation commands `cp`, `rm` and `mv`.
{{< admonition type="question" title="Questions" open=true >}}
- Can you `mv` one file to more than one destination?
- What happens if you give `cp` no destination?
- Can you `cp`, but without being inside the folder it is located in?
- Can you move a folder?
- How does moving a *file* onto a *folder* behave?
- Can you `mv` the folder you are actually in?
{{< /admonition >}}

