---
layout: lesson
root: .
title: 
minutes: 20
author: Adina Howe
---

# Automating a script in R

### Exercise

First, let's start off with some review dealing with creating text files.  I need you to create 3 data files using a text editor (e.g., nano).  Each data file should contain a comma-separated row of numbers (at least two numbers).  For example: 

    1,2,3,4

could go into a file that I call data.txt.  And I could make another of my three requested files to contain, for example:

    5,6,7,1

Please make at least 3 files containing at least 2 numbers.  You can make more if you'd like.  

### Our goal

Our goal is to write an program written in R which will take an arbitrary number of these data files and return the sum of the first two numbers.  Though this is a pretty simple example, keep in mind that you could write a script to plot graphs, do statistics, etc.  Here, we're just writing a script that will be a calculator.

### The commandArgs command

We are going to introduce the idea of command line arguments.  In R, you would typically type the name of the file you would like to open or analyze WITHIN R.  Instead, we are going to use the commandArgs command to let you specify the name of the file you would like to manipulate OUTSIDE of R on the command line.

### Exercise

Let's first write a script to add two numbers in R.  Let's write this solution out to a file, your choice in name.

If you want to try it yourself, don't look below.  But in case you need some hints.  You can see the solution here:

    data <- read.csv("data.txt", header=FALSE)
    sum <- data[1] + data[2]
    print(sum)
    write.table(sum, file="data.txt.sum", quote=FALSE, row.names=FALSE, col.names=FALSE)

To execute an Rscript on the command line, you could type:

    Rscript <name of script> 

### Adding the commandArgs

Now, if you wanted to add commandArgs to this script, your script might look like:

    args <- commandArgs(TRUE)
    data <- read.csv(args[1], header=FALSE)
    sum <- data[1] + data[2]
    write.table(sum, file=args[2], quote=FALSE, row.names=FALSE, col.names=FALSE)

To execute this:

    Rscript <name of script> <arg1> <arg2>

In summary, the following command can be added to your R script that will store the arguments in a R vector or list.

    args <- commandArgs(TRUE)

where <arg1> is args[1], <arg2> is args[2], etc.

### Together we will write a script using a for-loop in the shell to execute this R program.

Here's how to execute it on one file, where data.txt is my input file and data.sum is the file I will write the sum to:

    Rscript <name of script> data.txt data.sum

A for loop might look like:

    for x in *txt; do Rscript myRscript.R $x $x.sum; done
    
TADA!
