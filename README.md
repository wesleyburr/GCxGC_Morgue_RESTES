# GCxGC Morgue and RESTES VOCs  [![DOI](https://zenodo.org/badge/611850743.svg)](https://zenodo.org/badge/latestdoi/611850743)


Code for analysis of GCxGC data from Morgue+RESTES decomposition study. Darshil Patel, PhD candidate at UQTR, under Dr. Shari Forbes, ran a number of experiments gathering headspace observations from decomposition of human remains, for the question of "VOC Profile of the post-mortem period". 

This code is a set of routines which work with the exported "hit list" from the LECO software environment, as StatCompare was not compatible with the Pegasus equipment used for these observations. In this code, we organize, collate, normalize and synchronize the observations from the large number of GCxGC observations, to provide useful inputs for analysis via clustering algorithms, e.g., PCA. 

There are 11 main files, all R Markdown documents, which perform varying steps in the pipeline.

* 0: load the Excel sheets from LECO; process and run an alignment procedure, first across the reference controls, and then across the observations
* 1: clean up the results from 1, organize in preparation for coincidence detection
* 2: load the .rda objects, and normalize with respect to Bromobenze, the reference standard
* 3: select, filter, clean and merge compounds using logic as described in the thesis
* 4: filter out extraneous results
* 5: merge, reorganize
* 6: check the alignment of bromobenzene, as suggested by one thesis reviewer
* 6: compare the aligned RTs
* 7: identify common compounds
* 8: normalize the alignment again
* 9: clean-up, with normalization, alignment and RT filtering done first
* 10: filter, again, following 9
* 11: merge, again, following 10

All scripts were executed on a server running an AMD Threadripper 2950X (16 cores, 32 threads) with 256GB of RAM, and Ubuntu Linux 20.04. **Note**: if you wish to reproduce these results, expect the alignment process to take 4-6 days assuming you have the same compute power available to you that was used in the original iteration. This is not suitable for executing on a standard laptop or desktop system!
