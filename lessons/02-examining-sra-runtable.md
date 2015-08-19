---
layout: lesson
root: .
title: examining SRA run table
minutes: 20
---

## Learning Objectives 

* Get a general understanding of the NCBI SRA
* Understand how to download a summary run table of the SRA
* Be able to open a run table using a spreadsheet editor 
* Be able to examine a run table (text file) at the command line

## Lesson 

The NCBI Sequence Read Archive is a large (>3 quadrillion basepairs as of 2014) repository for next-generation sequence data. Like many NCBI database it is complex and mastering its use is greater than the scope of this lesson. Very often, as in the Lenski paper, there will be a direct link (perhaps in the supplemental information) to where on the SRA the dataset can be found. The link from the Lenski paper is: http://www.ncbi.nlm.nih.gov/sra?term=SRA026813 


## Exercises

> Sections A and B of these exercises take place on your own laptop - no need to open the shell or connect to your remote computer yet!

#### A. Locate the Run Accessor for the Lenski Dataset on the SRA

1. Access the Lenski dataset from the provided link: http://www.ncbi.nlm.nih.gov/sra?term=SRA026813 
    > You will be presented with a page for the overall SRA accession SRA026813 - this is a collection of all the experimental data
2. Click on the first entry ([ZDB30](http://www.ncbi.nlm.nih.gov/sra/SRX040669%5Baccn%5D)); this will take you to an a page for an SRX (Sequence Read eXperiment). Take a few minutes to examine some of the descriptions on the page
3. Click on the [Run Selector Link](http://www.ncbi.nlm.nih.gov/Traces/study/?acc=SRP004752); this is a description of all of the NGS datasets related to the experiment. 
4. Go to the top of the page and **In the 'Total row'** you will see there are 37 runs, 10.15Gb data, and 16.45 Gbases of data. Click the 'RunInfo Table' button. 
    > We are not downloading any actual sequence data here! This is only a text file that fully describes the entire dataset

You should now have a file called **SraRunTable.txt**

#### B. Review the SraRunTable in a spreadsheet program


1. Using your choice of spreadsheet program open the **SraRunTable.txt** file. If prompted this is a tab-delimited file. 

Taking a quick glance at the file, you should be able to answer the following questions:

1. What strain of *E. coli* was used in this experiment?
2. What was the sequencing platform used for this experiment?
3. What samples in the experiment contain [paired end](http://www.illumina.com/technology/next-generation-sequencing/paired-end-sequencing_assay.html) sequencing data?

After answering the question, you should avoid saving this file; we don't want to make any changes. If you were to save this file, make sure you save it as a plain **.txt** file. 

### C. Looking at a text file at the command line

We are going to be doing our formal shell lesson next. However, we can already play with a few simple commands that have you thinking about how the shell can be useful tool in examining your dataset

> At this point, please verify that you are working from the the ami-6516b30e image where we have prestaged all the data for the rest of the lessons


During the shell lesson we will go much more step-by-step, building our way through every command before we use it. For this first command go ahead any copy and paste if you are just getting use to the shell. The other commands are short enough to type and follow. 

1. Follow you instructor's direction to navigate to the sample SraRunTable.txt file that has be placed on your remote computer

    ```bash
$ cd ~/dc_sample_data/sra_metadata
```
2. Display the contents of the SraRunTable.txt on your screen
    ```bash
$ cat SraRunTable.txt
```
3. That's probably not too pretty, so lets view it in a little more organized a format

    ```bash
$ column -t SraRunTable.txt
```
4. In this case we are using the 'column' program to make the print out more pretty. 


In the next lesson on the shell, we will be able to find out how to do a lot more with the shell, including what else the commands we have done can do. 

## Data Description 

For the purposes of this workshop, we will be working with 6 of the fastq reads used in this experiment. 

|SRA Run Number|Clone|Generation|Clade|
|--------------|-----|----------|-----|
|SRR098028|REL1166A|2,000|?|
|SRR098281|ZDB409|5,000|?|
|SRR098283|ZDB446|15,000|UC|
|SRR097977|CZB152|33,000|Cit+|
|SRR098026|CZB154|33,000|Cit+|
|SRR098027|CZB199|33,000|C1|

## Where to learn more

#### About the Sequence Read Archive

* You can learn more about the SRA by reading the [SRA Documentation](http://www.ncbi.nlm.nih.gov/Traces/sra/)
* The best way to transfer a large SRA dataset is by using the [SRA Toolkit](http://www.ncbi.nlm.nih.gov/Traces/sra/?view=toolkit_doc)
