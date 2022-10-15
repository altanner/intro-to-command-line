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

With `Genome` as your search database, enter "SARS-CoV-2", and run the search. You should get one result (if you get more, choose the top result). Note the information get here, and follow the link to the reference genome by clicking "Severe acute respiratory syndrome coronavirus 2", near the top of the page. On this screen, get both the nucleotide and amino acid genome, by clicking the links next to "Download sequences in FASTA format". Move these two files to a suitable folder to work in, and unzip them. Note their file extensions - `faa` is "FASTA, amino acids", `fna` is "FASTA, nucleotides", although these are just plain text files, like most files we work with on the command line. FASTQ files are the same as FASTA, except with read quality scores, and are typically untrimmed.

We'll start with the nucleotide genome - open it with `less` to get a feel of what the data looks like.

{{< admonition type="question" title="Exercise 1" open=true >}}
Use command line tools taught earlier in this course to answer these questions about the **nucleotide** genome:
- How long is this genome, in kilobases? 
- What is the total nucleotide count each for A, T, C and G in the genome? Is it G-C enriched, or A-T enriched?
- How many times do we see the start codon (Methionine) in the genome?
- How many times does the motif ATGTAG occur in the genome?
- Assume that all protein-coding genes in this genome start with the motifs ATGCTT and ATGACC. How many genes does this covid-19 genome appear to contain?
- The covid nucleocapsid glycoprotein starts with the motif ATGTCTGAT and end with CAGGCCTAA
  - What line does the capsid gene start? And end?
  - Isolate the capsid gene and make a new file, containing just that gene. Manually trim any non-capsid sequence with a text editor. Make sure it is in FASTA, and give the sequence a name.
  - How many nucleotides long is the nucleocapsid glycoprotein gene?
{{< /admonition >}}

Now let's have a look at the proteome. Again, open it with `less` and have a look at how it is structured and annotated, noting the differences compared to the nucleotide version of this genome.

{{< admonition type="question" title="Exercise 2" open=true >}}
Answer these questions about the proteome:
- How many protien-coding genes does SARS-CoV-2 contain?
- What is the most common amino acid?
{{< /admonition >}}

{{< admonition type="success" title="Learn more" open=true >}}
When learning to use computer clusters and high-performance computers, we often run jobs using "submission scripts". These are just the same as a shell script - they are not magic, merely running commands one after another, just like you could on the command line itself.

You can learn these skills in our course *Introduction to HPC*, do an internet search for our current courses.
{{< /admonition >}}

