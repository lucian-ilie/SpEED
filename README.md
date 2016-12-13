# SpEED
##Version 1.0: April. 1, 2011
##Copyright (C) 2011 Lucian Ilie, Silvana Ilie, Anahita Mansouri Bigvand

SpEED is a program designed to compute effectively highly sensitive multiple spaced seeds. 

***********************************************
##OVERVIEW
***********************************************

SpEED is a program for computing highly sensitive multiple spaced seeds, which are the current state-of-the-art tool for similarity search. Multiple spaced seeds are used by a variety of software programs, for similarity search, read mapping, oligonucleotide design, etc. Computing the optimal (most sensitive) seeds is a hard problem and therefore the need for heuristic approaches. SpEED constructs multiple spaced seeds in the most widely used Bernoulli model. It provides the first seeds very quickly (within a few seconds -- this is called the SpEED-first seed) and then iteratively improves that (SpEED-best). It provides the time and sensitivity for all seeds computed.

SpEED-fast will always compute a seed because it runs in polynomial time and space. However, computing sensitivity requires exponential space. Hence, depending on the input parameters, you need enough RAM to obtain the sensitivity and SpEED-best seeds. Otherwise, the program will report "MEMORY ERROR" and exit.

Another thing to bear in mind is that computation of single spaced seeds IS feasible be exhaustive search. SpEED is designed for two or more seeds. 

***********************************************
##INSTALLING SpEED
***********************************************
 
 gunzip SpEED.tar.gz
 
 tar -xf SpEED.tar
 
 cd SpEEDcode/
 
 make


***********************************************
##RUNNING SpEED
***********************************************

 ./SpEED < weight > < numberOfSeeds > < similarity > < lengthOfHomologyRegion > 

The user has to input a number of parameters:

< weight > is the number of matches in each seed; this is essential for the sensitivity and specificity; specificity increase with      < weight > while sensitivity < decreases >

< numberOfSeeds > is the number of seeds in each multiple spaced seed; more seeds will have higher sensitivity but will be slower and use more space

< similarity > is the expected similarity level between the homologous regions; this represents how similar the region searched for is to the query sequence; it will be very high, e.g., 0.95, for read mapping but it can be as low as 0.70 for similarity search of remote homologues

< lengthOfHomologyRegion > is the length of the homologous regions; traditionally, 64 was used here for similarity search (from the PatternHunter papers); if mapping reads of length, say, 75bp, then this is the number to be used

##CITE

If you find SpEED program useful, please cite the our papers:

L. Ilie, S. Ilie, and A. Mansouri-Bigvand, [SpEED: fast computation of sensitive spaced seeds, Bioinformatics](http://bioinformatics.oxfordjournals.org/content/27/17/2433.short) 27(17) (2011) 2433 -- 2434

L. Ilie and S. Ilie, [Multiple spaced seeds for homology search, Bioinformatics](http://bioinformatics.oxfordjournals.org/content/23/22/2969.short) 23(22) (2007) 2969 -- 2977
