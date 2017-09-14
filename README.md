## Installation
To install, you will need to make a few small changes to RNA structure. Follow
instructions in changes_to_RNAstructure.txt and modify program_constants.txt 
to reflect the location of RNAstructure. Using the standard RNAstructure 
executables is okay, but the probability of entropy constraints will not be correct. 

## Instructions for running
1. To run the MIBP script, make this folder your current matlab directory and
execute the master_script_hibp.m script.

2. To change which RNA molecule is being considered edit the program_constants.txt file.

3. After completion, visualization.html will appear. Open this with firefox to view a 
visulization. Click on a node of the tree to get a detailed view. Files for the 
visualization are located in the jsons folder. To retain a visualization simply rename 
visualization.html and make sure that it is in the same folder as a folder called 
'jsons' containing the appropriate files.

4. The results folder contains a large dump of data related to the run. If you are not 
interested in this, you may wish to delete it before running again. The format for the file names is:
<RNA_NAME>_<node_name>_<kind>
where kind is
a. energy: the total free energy of structures in the node. This value is used to calculate the probability of a cluster.
b. entropy: a constraint file used by RNAstructure to specificy the entropy constraints
c. probs: the probability plot output from RNAstructure containing log10 probability for each base pair with positive probability.
d. mibps: the base pairs whose presence/absence defines that node
Finally there is a <RNA_NAME>.mat file. If loaded in matlab it will give access to some summary statistics including:
a. RNA_LENGTH: length of the sequence
b. n: number of regions
c. probs: probility of regions without entropy constraints
d. probs_le: probility of regions with entropy constraints
e. all_structs: number of possible structure
f. structs: structures in each region without entropy constraints
g. structs_le: structures in each region with entropy constraints
h. sum_of_bp_entropy: sum of base pair entropy for the ensemble
i. entropies_le: sum of base pair entropy for each region with entropy constraints
j. centroids: centroids of each region
k. native_cluster: regions that contains the native structure
l. tree_strings: binary string name of node (1=go right, 0=go left)
