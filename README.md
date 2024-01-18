# iM-Seeker

iM-Seeker is commandline software designed to predict DNA i-Motif folding status and folding strength.

# Principle

![iM-seeker F1](https://github.com/YANGB1/iM-Seeker/assets/92316121/2702225d-23c9-452d-923c-d280cfe2fc35)



# Installation
The dependency packages can be installed by:
``` 
pip3 install -r requirements.txt
``` 
iM-Seeker (available at https://pypi.org/project/iM-Seeker/) can be installed by:
``` 
pip3 install iM-Seeker
```
Alternatively, the python script 'iM-Seeker.py' can be downloaded directly from Github. The stored directory can be added to the ‘PATH’ environmental variable or the scripts with full path can be run alternatively using command like: 
``` 
python3 iM-Seeker.py -h. 
``` 
The python script 'iM-Seeker.py' and two models 'pickle_model_classification.pkl' and 'pickle_model_regression.pkl' can be downloaded directly. 'iM-Seeker.py', 'pickle_model_classification.pkl' and 'pickle_model_regression.pkl' need to be put in the same folder. The downloaded directory can be added to the ‘PATH’ environmental variable or the scripts with full path can be run alternatively. 
**But, please pay attention !!!!!! Model 'pickle_model_classification.pkl'(about 210Mb) need to be uploaded by git lfs (Large file storage) because of the github limitation. Please find all the files at https://figshare.com/s/e4e72e2e8ceaa0a4fbd6, which can be downloaded directly.**
  

# Usage

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


# Test
We provide the 'test.fa' in zipped folder 'test'. 'test.fa' contain Chr4 and Chr5 of Arabidopsis thaliana. Besides, there are nine example output files. 

After intalled the package with 'pip', the same output files as 'Overlapped_Greedy_conformationA.txt', 'Overlapped_Greedy_conformationB.txt', and 'All_conformation.txt' can be generated with the following command, 
``` 
iM-Seeker.py --sequence test.fa
``` 


