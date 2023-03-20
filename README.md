## Introduction

This repository presents the code used to create a non-linearity analysis on the basis of keystroke data from the logger Inputlog, and accompanies the paper *Measuring non-linearity of long-term writing processes* (written by Floor Buschenhenke, Rianne Conijn, Luuk Van Waes, submitted to Reading & Writing special issue on methodology). For context, the abstract of our paper follows below. 



## Abstract

Non-linearity in writing provides important insight into the dynamics of writing and writing disfluencies. Currently, a range of linearity measures are available. These metrics are calculated based upon the leading edge, and are mostly used for short texts and single writing sessions. However, for longer, multi-session writing processes, the concept of the leading edge, as the singular outer boundary of the text-in-progress, is not enough to distinguish between linear production and non-linear text alterations.
Therefore, in the current study, we propose a novel automatized non-linearity analysis. Within this approach, all backwards and forwards cursor and mouse operations from the point of utterance are extracted from keystroke data, and characterized both based on duration and distance. 
We illustrate this approach by analyzing the writing process of a complete novel based on more than 400 writing sessions totaling 276 hours of writing. The results show that this approach allows us to successfully cluster these writing sessions using the non-linearity characteristics.

## Overview of the steps we have taken

We are using Inputlog-General Analysis files as our source material. You could apply the steps to the output of other keystroke loggers as well. The General Analysis is a table in which each keystroke action has its own row. It is quite similar to the raw output from other academic keystroke loggers.

Steps:
1. load all General Analysis files (one for each writing session) into R and merge them into one table, preserving the original session-numbering. (not including in this notebook)
2. aggregate/annotate the keystroke events in this table into larger segments of typing, deleting, jumping/navigating and focus (activities outside of the work document).
3. Calculate characteristics for each jump event and each typing event
4. Create a summary table with descriptive statistics for each session
5. Running a correlation matrix, removing highly correlation variables, then performing a cluster analysis to explore similarities between sessions. This step is not included in this notebook.


