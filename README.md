# iM-Seeker

iM-Seeker is commandline software designed to predict i-Motif folding status and folding strength.

# Principle

![Uploading iM-seeker F1.png…]()


# Requirement
The software is developed on Python 3.9. And four Python packages are needed:
  
  os
  
  argparse (developed on v1.1)
  
  regex (developed on v2.5.109)
  
  numpy (developed on v1.22.4)

# Usage
The python script 'Putative-iM-Searcher.py' can be downloaded directly. The stored directory can be added to the ‘PATH’ environmental variable or the scripts with full path can be run alternatively. The help page can be checked by following command:
``` 
python3 Putative-iM-Searcher.py -h
``` 
Parameters can be configured according to the user's own needs.Here is an example:
``` 
python3 Putative-iM-Searcher.py --nuc_type DNA --sequence input.fa --overlapped 2 --greedy 2 --stem_short 3 --stem_long 5 --loop1_short 1 --loop1_long 12 --loop2_short 1 --loop2_long 12 --loop3_short 1 --loop3_long 12 --representative_conformation 3 --output_conformation 1 --output_folder output_path
``` 

# Input and output
The input sequences should be in fasta formation, for instance:

\>test1

CCCTCCCCCTCCCCTCCCTCCCCCCCCTCCCCTCCCTCCCTCCCCCCCCTCCCTTTTTTTTTTTTTTTTTTTTTTTTTTTTTTTTTTCCCCCCCCCTCCTCCCCTCCCCCTCCCCTCCCTCCCTCC

\>test2

CCCCCTCCCCCTCCCCCTCCCCCTCCCCC

\>test3

CCCTAACCCTAACCCTAACCCTAACCCTAACCCTAACCC

\>test4

CCCCGACCCCAACCCCTCCCCCAACCCCTCCCC

The output files are stored in the pre-set output folder.

If --representative_conformation is set as 1, 'Putative_iM_Searcher_result_average_conformation.txt' includes conformation A of pre-set iM structures. 

If --representative_conformation is set as 2, 'Putative_iM_Searcher_result_side_shorter_conformation.txt' includes conformation B of pre-set iM structures. 

If --representative_conformation is set as 3, 'Putative_iM_Searcher_result_average_conformation.txt' and 'Putative_iM_Searcher_result_side_shorter_conformation.txt' include conformation A and B of pre-set iM structures, respectively. 

If --output_conformation is set as 1, 'Putative_iM_Searcher_result_all_conformation.txt' includes all putative iMs.
