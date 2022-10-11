---
title: "‣ Searching"
subtitle: "Find what you are looking for, both in folders, and inside files"

date: 2022-09-15T00:00:00+01:00

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

### Searching for files

We can use the program `find` as our search command, but it has some strange syntax... if you are a little confused, you are not alone! The syntax is

```
find [where to look] [what type of file] ["the match you are looking for, in quotes"]
```

Let's go back to your folder `command-line-files`, and try each of these commands.

```
find . -iname "data1"
find . -iname "data*"
find . -iname "*txt"
find . -iname "*a*"
find . -iname "parakeet"
```

Here we are using `.` (the current location) as the starting point, and `find` will look in all the containing folders below that location. To search a whole file system, we could go `find / -iname "my_file"`, but just like doing this in a GUI, it is very slow. `find` will also, unhelpfully, tell you all the folders you do not have access to.

The flag `-iname` is saying "the file or folder has this name, case insensitive" (you can do `-name` too, if you are sure of the case). In the name, we can have wildcards to say "anything". (More on wildcards later.) Notice the last query, for `"parakeet"`, does not find anything, but the command line doesn't tell you that. It just finishes and gives you your prompt back. This is standard for the command line - unless you get an error, your command did run correctly - sometime with no output at all!

{{< admonition type="info" open=true >}}
If you are on MacOS or Linux, you may have a command installed called `fzf` - "fuzzy find". This is a more modern search command than `find`, which will find matches and similiar matches (without having to use wildcards), and give you a list of the closest matches. Give it a try with just `fzf` (and `enter` without a search query), then start typing your query and it will search as you type, a little like a browser can. You can scroll the results with your arrow keys, and press `enter` to print results to the terminal.
{{< /admonition >}}

### Searching in files

A strength of the command line is being able to easily search inside files. Here we will use a command called `grep`. Strange name I agree, but apparenly back in the depths of time it stood for "global regular expression print". Don't worry about what that means! Although, in programming "global" means "everywhere" - nothing to do with the world!

{{< admonition type="info" open=true >}}
Think of `grep` as `ctrl-f` ("find"), that you might use in a document or a browser, to find particular words.
{{< /admonition >}}

Move into the folder `some_plays` and try this command:

```
grep "fish" king-lear.txt
```

Here we are saying "Run grep, searching for the word *fish*, in the file called king-lear.txt". `grep` will show you the lines with exact matches. Be careful that grep is case sensitive, and it will do exactly what you asked - "fish" will match words with those letters in, not just the word "fish".

{{< admonition type="question" title="Questions" open=true >}}
Try changing what `grep` is searching for.
- What is the most common noun you can find in King Lear?
- Can you find a word which appears only once?
- Can you search for more than one word? (for example the phrase "and such")
{{< /admonition >}}

### Exercise
`grep` can take many useful flags. Try each of these commands with flags, and work out what they do:

```
grep "faith" king-lear.txt
grep "Faith" king-lear.txt
grep -i "faith" king-lear.txt
grep -n faith king-lear.txt
grep -c faith king-lear.txt
grep -c Faith king-lear.txt
grep -ci faith king-lear.txt
grep faith king-lear.txt julius-caesar.txt
```

{{< admonition type="info" open=true >}}
Note that we can combine multiple flags, as in that `-ci` command above.
{{< /admonition >}}

Also, that final command doesn't have flags, but is asking to search two files for the same match. Note that if you want to search for something with a space in it, you will need quotes around your query, for example

```
grep "this scattered kingdom" king-lear.txt
```

{{< admonition type="warning" open=true >}}
If the quotes were absent, `grep this scattered kingdom king-lear.txt`, the command line would think you want to find the word "this", in the files called "scattered", "kingdom", and "king-lear.txt".
{{< /admonition >}}

### Recursive searching
In computer speak, "recursive" means "repeat this action for everything in the folder". So, let's search multiple files. We can do this in a couple of way. First, let's move out of the folder `some_plays`, back one level with `cd ..`. From here, let's recursively search for something inside `some_plays` with a couple of commands

```
grep -r sparrow some_plays
grep -rc sparrow some_plays
```

Often, when referring to the file we want to search (or apply any command to), we can use *wildcards* to specify files with similarities in name. Move back into the folder called `some_plays`, and use this command

```
grep sparrow *
```

Here, `*` means "every file and folder in this location". We could also specify just part of the filename, for example `a*` would mean all files starting with the letter `a`.

### Exercise
```
Use `grep` to answer these questions:
- Which plays have the word "squirrel" in?
- How many plays have the word "apple" in?
- How many plays have the word "beach" in?
- Which plays, with the word "and" in their title, have the word "asleep" in them?
- How many lines does Lady Macbeth have in *Macbeth*?
- Which act has the most scenes in *Henry VI Part 2*?
- What is the combined line count for both Juliet and Romeo in their play? (Bonus: Can you run this `grep` as a single command?)
```

We won't go into it here, but `grep` can search in very sophisticated ways not possible with `ctrl-f`, for example finding ambiguous spellings, returning matches a certain number of lines from the actual match, or being able to look ahead or behind to conditionally match. If you are wondering what the command line version of "find and replace" is, look up a command called `sed` ("string editor") - this command is beyond the scope of this course, but is a commonly-used command for automating modification to files.

To use wildcards in the search query itself, we have to use regular expressions ("regex"). For example searching for variations of spelling, or when a word is near another match, or not showing the match but the word after the match, or the line after the match.

{{< admonition type="warning" open=true >}}
One more note on `grep`: when counting, it only counts the number of _lines_ that the match appears on. If the same match occurs twice on the same line, it will only count as 1 match. `grep` can count all matches, rather than lines - try looking this up.
{{< /admonition >}}

Have a bit more of practice with wildcards, by going back a folder (you should be in `command-line-files`) - what do you get if you run these commands?

```
ls *
tail -3 some_plays/*
head -10 some_plays/king*
```

{{< admonition type="info" open=true >}}
Remember that anything ending with a `/` character is a folder, not a file.
{{< /admonition >}}

We could also use the *absolute path*, ie the path that will work from any location in the filesystem.

