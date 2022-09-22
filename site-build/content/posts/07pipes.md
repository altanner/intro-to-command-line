---
title: "‣ Pipes"
subtitle: "Using command outputs as command inputs"

date: 2022-01-08T00:00:00+01:00

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

In the last section, we counted the number of lines in our folder of Shakespeare plays. But what if we wanted these in order? We could do this by using another command. This is where we would use a *pipe*. (The pipe symbol is `|` - to the left of the enter key on MacOS, and to the left of the number row on Windows.) A pipe sends the output of one command as the input for another command, linking them together, like in plumbing. A series of pipe and command operations is known as a "pipeline" (these might be saved as a small program, or a "script").

We can use the output of `wc` as the input for `sort`. Try these commands in the folder `some_plays`

```
wc -l * | sort
```

Here the _output_ of the command `wc -l *` is being *piped* into the command `sort`. Building up commands with pipes can lead to some very powerful automation.

{{< admonition type="question" title="Exercise" open=true >}}
- Pipe the output of `ls` into `grep` to count the number of `.txt` files present
- Look at the `man` page of `sort`, and find a way of reversing the order of the above command.
- Pipe the output of `wc` into `sort` into `head` to get the three shortest plays in our folder of plays.
{{< /admonition >}}

### Using pipes and redirects together

Combining redirects and pipes can be very useful. here is a simple example where we pipe one command to another, then send the output of the next command into a file:

```
wc -l * | sort -r > ordered_by_line
```

Understanding this kind of flow is essentially the first step towards programming. While the command line is a whole scripting language in itself, as things get more sophisticated we start to use proper programming languages. This aids in compatibility, portability, and allows you to use purpose-built tools.

{{< admonition type="question" title="Exercise" open=true >}}
- Count the total number of lines with the word "bird" in all the plays.
- Make a new file containing every line in these plays with the word "hills" in.
- Pipe `wc` into `sort` into `head` to get the three shortest plays in our folder of plays.
{{< /admonition >}}
