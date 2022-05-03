---
title: "Redirection"
subtitle: "Using command outputs to create new files"

date: 2022-01-07T00:00:00+01:00

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

### Using outputs as inputs
bob
This page will cover some more advanced ways of using the command line, in particular how to link different commands together. Firstly we will cover a concept called "redirection". Move into the folder `example_files`. We can see, for example, the first three lines of `plants.txt` with the command

```
head -3 plants.txt
```

But what if, instead of printing the output to the terminal, we wanted to put it into a file? This is called "redirecting", and is done with the symbol `>`

```
head -3 plants.txt > first_three_plants.txt
```

The terminal will not give you any output, but what is inside the file `first_three_plants.txt`? Let's expand on this by using wildcards. Try this command, and examine the contents of the output file:

```
head -3 * > my_new_file
```

**Be careful! Redirects will overwrite the target file!! If `my_new_file` already existed, it would be permanently overwritten by the above command!** If we want to **append** to a file, we use a double arrow, for example we can go:

```
tail -10 romeo-and-juliet.txt >> another_file
tail -10 king-lear.txt >> another_file
```

Finally, we will look at how to make one command take the output from another command. This is called a "pipe", `|`. That is the "bar symbol", on Mac keyboards it is next to `enter`, on Windows it is usually by the left shift key, and on Linux it is usually to the left of the 1 key. Move to the folder `some_plays`, and let's use a new command, `wc`

```
wc -l macbeth.txt
```

`wc` is "word count", but here we are asking for the number of lines with the flag `-l`. We can use a wildcard to see how many lines are in all of the plays, with

```
wc -l *
```

But what if we wanted these in order? We can use the output of `wc` as the input for `sort`. Try these commands

```
wc -l * | sort
wc -l * | sort -r
```

Combining redirects and pipes can make powerful scripts, here is a simple example where we pipe one command to another, then send the output of the next command into a file:

```
wc -l * | sort -r > ordered_by_line
```

Understanding this kind of flow is essentially the first step towards programming. While the command line is a whole scripting language in itself, as things get more sophisticated we start to use proper programming languages. This aids in compatibility, portability, allows you to use purpose-built tools.

Further useful commands to explore for yourself (there are thousands, so here are just a handful!). Some of these will run by themselves, some of them will need files to work on. (Some of these might not be available on your particular system.)

```
history
man
file
cut
sed
tr
du
df
who
w
whoami
tree
exit
```

If you have got this far, then you have covered the most useful commands for the command line interface! Although there are many commands, the ones mentioned in this workshop make up 90% of what most people need to do on the command line. Congratulations!

All pages: [Introduction](https://altanner.github.io/intro_to_CLI) • [Navigation]({{ site.baseurl }}{% link 01_navigation.md %}) • [Copying, moving and deleting]({{ site.baseurl }}{% link 02_manipulation.md %}) • [Viewing file contents]({{ site.baseurl }}{% link 03_viewing_files.md %}) • [Editing files]({{ site.baseurl }}{% link 04_editing_files.md %}) • [Searching]({{ site.baseurl }}{% link 05_searching.md %}) • [Further skills]({{ site.baseurl }}{% link 06_further.md %})
