---
layout: lesson
root: .
title: Intro to ecoli evo experiment
minutes: 5
---

## Learning Objectives 
* Have a general idea of the experiment and its objectives
* Understand how and why we choose this dataset

## Lesson 

Microbes are ideal organisms for exploring 'Long-term Evolution Experiments' (LTEEs) - thousands of generations can be generated and stored in a way that would be virtually impossible for more complex eukaryotic systems. In Lenski et.al. 12 populations of *Escherichia coli* were propagated for more than 40,000 generations in a glucose-limited minimal medium. This medium was supplemented with citrate which *E. coli* cannot metabolize in the aerobic conditions of the experiment. Sequencing of the populations at regular time points reveals that spontaneous citrate-using mutants (Cit+) appeared in a population of *E.coli* (designated Ara-3) at around 31,000 generations. It should be noted that spontaneous Cit+ mutants are extraordinarily rare - inability to metabolize citrate is one of the defining characters of the *E. coli* species. Eventually, Cit+ mutants became the dominate population as the experimental growth medium contained a high concentration of citrate relative to glucose. 

Without going to deeply into the science of the paper (which the reader can review at their leisure) this dataset was selected for our exercise on NGS Data Carpentry for several reasons, including:

* Simple, but iconic NGS-problem: Examine a population where we want to characterize changes in sequence *a priori* 
* Dataset publicly available - in this case through the NCBI Sequence Read Archive (http://www.ncbi.nlm.nih.gov/sra)
* Small file sizes - while several of related files may still be hundreds of MBs, overall we will be able to get through more quickly then if we worked with a larger eukaryotic genome

####References

Blount, Z.D., Barrick, J.E., Davidson, C.J., Lenski, R.E.
Genomic analysis of a key innovation in an experimental Escherichia coli population
(2012) Nature, 489 (7417), pp. 513-518.
