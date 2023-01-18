---
title: "∙ Viewing the contents of files"
subtitle: "Different ways to see what is inside a file"

date: 2022-09-13T00:00:00+01:00

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

### Viewing files

There are two main ways of viewing the contents of files on the command line: "printing" the output to the terminal window, and viewing file contents with a "pager".

### `cat`
Let's look at outputting first with a command called `cat`. Sadly, this has nothing to do with small furry felines. `cat` is short for "conCATenate", which means "join files end to end", but it is commonly used for looking at a single file. Move into the folder called `example_files`, and run this command

```
cat meaning_of_life.txt
```

which means "output the contents of of the file `meaning_of_life.txt` to the terminal". This is useful for seeing what is in short files. Using `cat` for longer files, it is less useful.

Move into the folder called `alexandre-dumas` and try this and see for yourself:

```
cat The-Count-Of-Monte-Cristo.txt
```

{{< admonition type="question" title="Questions" open=true >}}
- What happened to the terminal?
- What would happen if the file was several gigabytes?
- Remember that `ctrl-c` is `cancel` on the command line.
{{< /admonition >}}

### `head` and `tail`
We might want to just see the start or the end of the file, so experiment with these commands:

```
head The-Count-Of-Monte-Cristo.txt
tail The-Count-Of-Monte-Cristo.txt
```

`head` and `tail` are common both on the command line, and in programming languages like `Python` and `R`. We can change how many lines we see using the flag `-n` followed by a number.

### More ways of printing files
Here are some more commands for outputting file contents in a variety of ways. Try them on the example files and work out what they do. You might want to run these commands on shorter files to make it easier to understand the output, `animals.txt`, back in the `sandpit` folder might be useful here.
```
tac
rev
uniq
sort
```
These might seem trivial (maybe even useless!) but these are powerful building blocks for arranging data.

### Introducing wildcards `*`
We will cover this in more detail later, but let's look at using the asterisk, `*`, as a wildcard. Experiment with a command like these
```
head -n 3 numbers*
tail -n 4 w*
head -n 2 *
head -n 3 *ea*
```

### The strangely-named `less`
Now let's look at using a pager. A pager does not put the file contents to the terminal output, but *instead shows it to you in a piece of dedicated software*. It might not look like it, since it is still just plain text in your terminal window! But when using a pager, you are *no longer on the command line*. We will use the command `less`, which will open a pager to view a file. (Why this program is called "less" is a story for another time :)

```
less The-Count-Of-Monte-Cristo.txt
```

{{< admonition type="info" open=true >}}
- You can scroll down and up with `space` and `b`
- `Page up` and `page down` keys will also work.
- To exit the pager, press `q`.
- It can be confusing using a pager, to begin with. It looks a lot like the command line. But if you don't see a prompt, you are not on the command line!
{{< /admonition >}}

Programs like `less` are useful for viewing large files, since it does not need to load the whole file into memory to show it to you. There are many things that `less` can do, but for now I will mention that you can search by pressing `/` and typing what you are looking for, and you can start `less` at the bottom of the file with `less +G [filename]`.
