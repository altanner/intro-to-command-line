---
title: "‣ Bioinformatics"
subtitle: "Managing sequence data on the command line"

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

This section is aimed at those wanting to use the command line, and perhaps computing clusters, to work with sequence information (that is, genetic, genomic, proteomic and other bioinformatic data). While we recommend using a dedicated programming language for more complex work: this is easier to share, replicate, test and collaborate on, the command line remains a useful environment to acquire and manage data, especially as the first part of an analysis pipeline.

### Sequence archives and repositories
All publicly-funded research creating sequence information is obliged to share their data, and this is typically done by placing it with one of the major sequence repositories, for example [GenBank](https://www.ncbi.nlm.nih.gov/genbank/) at the National Centre for Biotechnology Information (NCBI), or [Ensembl](https://www.ensembl.org/index.html) at the European Bioinformatics Institute (EBI). Given the scale of these repository, and the varied working practices of many labs across the world, you will sometimes come across poorly-annotated, mislabeled or otherwise inaccurate data. However, just keep this in mind - the vast majority of deposited data is accurate and well-catalogued!

### Exercise
Let's work with some real data to answer some real research questions. Firstly, we are going to acquire a small genome to work with. Go to [NCBI genbank](https://www.ncbi.nlm.nih.gov/genbank/), and in the search dropdown menu, select `Genome`. While you are here, notice the other databases that NCBI hosts. Many of these are quite niche, but common ones to use are `Genome`, `Gene`, `Protein` and `SRA`, the latter for raw, unassembled sequence reads.

With `Genome` as your search database, type "covid", and run the search. You should get one result (if you get more, choose the top result). Note the information get here, with XXXXXXX

{{< admonition type="question" title="Exercise" open=true >}}
- How long is this genome, in kilobases? 
- What is the total nucleotide count each for A, T, C and G in this genome?
- How many times do we see the start codon (Methionine) in the genome?
- How many times does the motif ATGTAG occur in the genome?
- Assume that all protein-coding genes in this genome start with the motifs ATGCTT and ATGACC. How many genes does this covid-19 genome appear to contain?
- The covid nucleocapsid glycoprotein starts with the motif ATGTCTGAT and end with CAGGCCTAA
  - What lines do the capsid gene start and end?
  - Isolate the capsid gene and make a new file, containing just that gene.
  - How many nucleotides long is the gene?
- Keep in mind all the limitations that the above has!
{{< /admonition >}}

If you can complete this task - congratulations, you now know all of the important ways of navigating the file system, of searching files, and the basics of shell scripting.

{{< admonition type="success" title="Learn more" open=true >}}
When learning to use computer clusters and high-performance computers, we often run jobs using "submission scripts". These are just the same as a shell script - they are not magic, merely running commands one after another, just like you could on the command line itself.

You can learn these skills in our course *Introduction to HPC*, do an internet search for our current courses.
{{< /admonition >}}

