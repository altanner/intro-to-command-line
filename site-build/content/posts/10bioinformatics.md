---
title: "‣ Bioinformatics"
subtitle: "Working with sequence information"

date: 2022-09-20T00:00:00+01:00

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

### Sequence information on the command line

This section is aimed at those wanting to use the command line, and perhaps computing clusters, to work with sequence information (that is, genetic, genomic, proteomic and other bioinformatic data). We recommend using a dedicated programming language for more complex work: this is easier to share, replicate, test and collaborate on. But the command line remains a useful environment to acquire and manage data, especially as the first part of an analysis pipeline.

Here we are going to use the command line to download some sequence information from a major genomic information repository, called NCBI. We will be asking the repo for a particular gene sequence from a range of organisms, and then cleaning the data ready for downstream work.

{{< admonition type="info" open=true >}}
- If you didn't look up `echo` earlier, use `man` to work out what it does.
- Think of `echo` as `print`, used commonly in programming languages.
{{< /admonition >}}

### Exercise
Let's use all of the skills we have learned today to build a script to complete a task. Be in the folder `some_plays`. Use `nano` to start a new, empty file. Create a script that will:

{{< admonition type="question" title="Exercise" open=true >}}
- Print the final line of _Macbeth_
- Count how many time the word "merry" occurs in all plays starting with the letter "m"
- Count how many times Hamlet speaks in _Hamlet_
- Print the line of who edited each play
- Use `head` and `tail` to print _just_ the 500th line of _All's Well That Ends Well_
- Make a new file containing _just_ the 1000th line of _A Midsummer Night's Dream_ **backwards**!
- Make a new file, in the folder _containing_ `some_plays`, of the total count of the lines containing the word "love" in all of the plays (combined - ie a single number).
{{< admonition type="tip" open=true >}}
Test each of your commands individually on the command line, before building them into your script.
{{< /admonition >}}
{{< /admonition >}}

If you can complete this task - congratulations, you now know all of the important ways of navigating the file system, of searching files, and the basics of shell scripting.

{{< admonition type="success" title="Learn more" open=true >}}
When learning to use computer clusters and high-performance computers, we often run jobs using "submission scripts". These are just the same as a shell script - they are not magic, merely running commands one after another, just like you could on the command line itself.

You can learn these skills in our course *Introduction to HPC*, do an internet search for our current courses.
{{< /admonition >}}

