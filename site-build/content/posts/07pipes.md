---
title: "∙ Pipes"
subtitle: "Using command outputs as command inputs"

date: 2022-09-17T00:00:00+01:00

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

### Pipes

The pipe operator, looks like this `|` (to the left of the enter key on MacOS, and to the left of the number row on Windows). A pipe allows us to take the output of one command, and use it as the input for another command. For example, we can count the number of lines of each file in our folder of Shakespeare plays, using `wc`. But what if we wanted these in order, numerically? This is where we could use a *pipe*. A series of pipe and command operations is known as a "pipeline" (these might be saved as a small program, or a "script").

We can use the output of `wc` as the input for `sort`. Try these commands in the folder `some_plays`

```
wc -l * | sort
```

Here the *output* of the command `wc -l *` is being *piped* into the command `sort`. Building up commands with pipes can lead to some very powerful automation.

{{< admonition type="question" title="Exercise" open=true >}}
Use pipes to answer these questions:
- How many `.txt` files are in the `some_plays` folder? (hint: use `ls` and `grep`)
- Which play has exactly 5730 lines? (hint: use `grep` and `wc`)
- How many lines, in all the plays, have *both* the words "true" and "love" in?
- What is the total line count of every file in the folder? (A single number)
- What is the 629th line of *Pericles*? (use `head` and `tail`)
- What is the 97th line of *Othello*, backwards?
- What is the 107th from last line of *Antony and Cleopatra*?
- What are the five longest plays, in order of line count? (Don't include the total from `sort`)
{{< /admonition >}}

### Using pipes and redirects together

Combining redirects and pipes can be very powerful, as we can easily save the output of a series of commands into a new file. Here is a simple example where we pipe one command to another, then send the output of the next command into a file:

```
wc -l * | sort -r > ordered_by_line
```

Understanding this kind of flow is a first step towards programming. While the command line is a whole scripting language in itself, as things get more sophisticated we start to use proper programming languages rather than the command line, but the command line remains very useful and powerful. Let's do some exercises using pipes and redirects.

{{< admonition type="question" title="Exercise" open=true >}}
Move into the folder called `alexandre-dumas`, this contains a text file of the book *The Count of Monte Cristo*. Try these:
- Make a new file containing every line in the book with the word "hills" in.
- Make a new file containing all lines with the word "benefactor", sorted alphabetically (ignoring the case). 
- Make a new file containing the one line of text containing the word "baroness" and "magistrate".
- Add to this file a single number: the total number of words in all the lines containing the word "opportunity".
- Make a new file *in the folder that contains the folder `alexandre-dumas`*, with the total character count of *The Count of Monte Cristo* (just a single number).
- Check the contents of that file (the character count file), without moving from the folder `alexandre-dumas`.
{{< /admonition >}}
