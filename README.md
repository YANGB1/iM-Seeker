# iM-Seeker

iM-Seeker is commandline software designed to predict DNA i-Motif folding status and folding strength.

# Principle

![iM-seeker F1](https://github.com/YANGB1/iM-Seeker/assets/92316121/375b7be5-8320-4bc7-a9f4-5c7572936c39)


# Requirement
The software is developed on Python 3.9. And six Python packages are needed:
  
  os
  
  argparse (developed on v1.1)
  
  regex (developed on v2.5.109)
  
  numpy (developed on v1.22.4)

  imbalanced-learn (developed on v0.11.0)

  xgboost (developed on v1.7.6)

  

# Usage
The python script 'iM-Seeker.py' and two models 'pickle_model_final_classification.pkl' and 'pickle_model_final_regression.pkl' can be downloaded directly. 'iM-Seeker.py', 'pickle_model_final_classification.pkl' and 'pickle_model_final_regression.pkl' need to be put in the same folder. The downloaded directory can be added to the ‘PATH’ environmental variable or the scripts with full path can be run alternatively. 

But, please pay attention!!!!!! Model 'pickle_model_final_classification.pkl'(about 188Mb) has been uploaded by git lfs (Large file storage) because of the github limitation. Please use git lfs to download the file. You can't pull down the completed file via https link directly. Alternatively, all the files can be found at , which can be downloaded directly.
The help page can be checked by following command:
``` 
python3 iM-Seeker.py -h
``` 
Parameters can be configured according to the user's own needs.Here is an example:
``` 
python3 iM-Seeker.py --sequence input.fa --overlapped 2 --greedy 2 --stem_short 3 --stem_long 5 --loop1_short 1 --loop1_long 12 --loop2_short 1 --loop2_long 12 --loop3_short 1 --loop3_long 12 --representative_conformation 2 --output_folder output_path
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

If --representative_conformation is set as 1, 'iM-seeker_result_average_conformation.txt' includes conformation A of pre-set iM structures. 

If --representative_conformation is set as 2, 'iM-seeker_result_side_shorter_conformation.txt' includes conformation B of pre-set iM structures. 

The prediction result is kept in 'iM-seeker_final_prediction.txt'.

"0" of folding status means unfolded while "1" means folded. Folding strength is a continuous number. 



