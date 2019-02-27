READMe file to navigate to data and codes used in the paper:
=================
Title: ANALYZING HUMAN REACTION TIME FOR TALKER CHANGE DETECTION
Authors: Neeraj Sharma, Shobhana Ganesh, Sriram Ganapathy, Lori L. Holt
Conference: ICASSP 2019, May 12-19, Brighton, UK.
=================

Repository Guide:
=================
1. CSV file with subject ID, RT, FEATURES DISTANCE
    a. files are stored at: ./icassp2019_data/rt_feats/subject_wise_rt_featsDist_dur_X.csv
    b. where X = {1->25%,2->50%,3->75%,4->100%} segment duration before change instant.
    
2. Random forest training and prediction uses: icassp2019_rt_feats_RF_prediction.py (or icassp2019_rt_feats_RF_prediction.ipynb)
    a. Reads the files in 1. Does train and val computation for subjectwise log-RT prediction and save CSVs:
          i. randforest_mu_train_subwise_X.csv (X same as in 1.b above)
         ii. randforest_std_train_subwise_X.csv
        iii. same for validation
         iv. randforest_featImportance_subwise_X.csv
    c. Does train and val computation by pooling all subject data and saves CSVs:
          i. randforest_mu_train_subpool_X.csv (X same as in 1.b above)
         ii. randforest_std_train_subpool_X.csv
        iii. same for validation
         iv. randforest_featImportance_subpool_X.csv
          v. randforest_pred_train_subpool.csv (train set RT: (predict, actual)
         vi. randforest_pred_val_subpool.csv (val set RT: (predict, actual)

3. Plotting of figures uses plot_randomForest_predictions.m
    a. using csv files from 1 and 2 to make the plots in the paper.
     
4. The machine performance scores are stored in ./results/ directory as:
    a. offlinePLDA_mean_hit_miss_fa.csv, offlinePLDA_talkerwise_fa.csv
    b. human_mean_hit_miss_fa.csv, human_talkerwise_fa.csv, human_subjectwise_hit_miss_fa.csv
    c. For implementation details of machine approaches see the repository for the JASA paper: tcd_jasa2019
    
5. Experiment audio file stimulus set is present in: ./icassp2019_data/stimuli/M_5_spkrs_8_pairs_v0/ 
===========
