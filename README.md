# Orthology and selection scripts

## Scripts used for orthology prediction together with OrthoMCL and selection analysis.

### obtain-blast-score-construct-clusters-short.py

As OrthoMCL can be too conservative in orthology prediction, this script is meant as a second round analysis of OrthoMCL clusters that do not only contain single copy orthologs.

Based on an all vs. all blastx of the sequences in the cluster, the most likely orthologs are filtered out by blast scores. 

Output will be to STDOUT, so just pipe it with '>' into an appropriate place. Intended to use with a for-loop where you can name the output appropriately.

The output will be useable by codeml from the paml package for orthology prediction. 


#### The script requires some leg work to be useful.

Take a tabular blast results file (outfmt 6), reduced to the the three colums query, hit and score (use "cut", from GNU coreutils, presumably included in most Linux distros), to obtain the score of each relevant pairwise comparison.

Outgroup ID is hardcoded in the script and assumed to be present in the cluster, change or remove as necessary. Or you could change it to be a second input parameter sys.argv[2] and dynamically use multiple outgroups.



### calculate-lrt-corr-all-short.py

The second script is used to calculate the likelihood ratio test for the codeml output. It uses the chi square test. Pipe into a singe file to get a table with all p values. You may want to correct for multiple testing afterwards.


## Please note:

Feel free to use if you find it helpful, and ask questions. But I cannot guarantee any support whatsoever. There may not ever be any updates. Use at your own risk.

# Contact:
Daniel Elsner,
Evolutionary Biology & Ecology,
University of Freiburg,
GERMANY

E-Mail: daniel.elsner [at] biologie . uni-freiburg . de

(remove spaces and insert @ as appropriate)
