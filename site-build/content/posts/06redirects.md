---
title: "‣ Redirection"
subtitle: "Using command outputs to create new files"

date: 2022-09-16T00:00:00+01:00

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

### Sending outputs to files

Move into the folder `example_files`. We can see, for example, the first three lines of `plants.txt` with the command

```
head -3 plants.txt
```

But what if, instead of printing the output to the terminal, we wanted to put it into a file? This is called "redirecting", and is done with the character `>`

```
head -3 plants.txt > first_three_plants.txt
```

The terminal will not give you any output, but what is inside the file `first_three_plants.txt`? Let's expand on this by using wildcards. Try this command, and examine the contents of the output file:

```
head -3 * > my_new_file
```

{{< admonition type="warning" open=true >}}
Be careful! Redirects will **overwrite** the target file!! If `my_new_file` already existed, it would be permanently overwritten by the above command!
{{< /admonition >}}

Using `>` will create a new file, or overwrite a file if it already exists. We might want to append instead, and we do that with a double arrow, `>>`, for example

```
tail -10 romeo-and-juliet.txt >> another_file
tail -10 king-lear.txt >> another_file
```

### Exercise
Try these redirection and appending tasks, in the folder `some_plays`.
{{< admonition type="question" title="Exercise" open=true >}}
- Make a new file called "last_50_lines.txt" of the last 50 lines of *Romeo and Juliet*.
- Make another new file, containing the last 86 lines, of *all* the plays.
- Make a file containing all the lines, from all the plays, containing the word "Queen".
- Create a file containing the total *number* of lines spoken by Theseus, Oberon and Lysander in *A Midsummer Night's Dream*. 
- Add the final 100 lines of *The Tempest* to this file.
{{< /admonition >}}

### Getting help on the command line

Much of your knowledge about commands will of course come from the internet, but you can also look up help and manuals on the command line itself.

### `man` pages
`man` is short for "manual". When you run this command, for example

```
man ls
```

You will get description and instructions on what the command does, how to use it, and what flags it can take. Some `man` pages are better than others, but it is good to get familiar with them, and get a feel for how documentation is structured. When you search for a command on the internet, often the best results are just the `man` pages, presented in a webpage, which might be easier to understand and search through.

{{< admonition type="info" open=true >}}
- Note that `man` pages are presented in a _pager_: you are not on the command line while viewing `man` pages.
- Just like with `less`, you can leave a `man` page with `q`.
{{< /admonition >}}

{{< admonition type="question" title="Exercise" open=true >}}
- Use `man` to look up the command `wc`
- Use `wc`, plus a flag, to count the number of lines in Macbeth, in the folder "some_plays"
- Use `wc` to count the characters in A Midsummer Night's Dream.
- Use `wc` to count the number of lines in all of the plays in this folder.
- Use `man` to look up the following commands. And give the commands themselves a try
```
history
man
file
cut
sed
echo
tr
du
df
who
w
whoami
```
{{< /admonition >}}

