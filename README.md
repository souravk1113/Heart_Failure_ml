
# Heart Failure: Diagnosis and Severity Estimation through Machine Learning.
This repo explores methods for Heart Fialure detection using machine learning. It models approaches on three different kinds of data - ECG, Longitudinal and
tabular numeric data. It specailly focuses on applying deep sequence modelling techniqes. It also develops a deep architecture combing LSTMs and CNNs
for heart failure severity detection.

## Instructions to run notebooks:
   - Lstm_inception.ipynb-
    Open the notebook on colab or local jupyter environment and simply run all blocks in sequence.
    All datasets will automatically be dowloaded in local session
   - svm_hf.ipynb-
    Open the notebook on colab or local environment. Make sure to put all the data files in svm_modelling_data
    in your working directory and change the paths to these files in the releveant blocks in the notebook accordingly. Run all blocks
   - seq_model_hf.ipynb-
    Open the notebook in colab or local environment. Put all files present in ehr_data in your working directory
    and change the paths to these files in the relevant blocks accordingly. Then run all blocks
   - ehr_data_preprocessing.ipynb-
    This notebook is for preprocessing and feature contrution. It takes the files in the ehr_data and creates a 
    outputall.csv file which is provided in svm_modelling_data folder.
    To run this notebook open in colab or local environment and put all files in the ehr_data in your working 
    directory and change the paths accordingly in relevant block in the notebook
    
## Notebook Description:
- **Lstm_inception** :This notebook deals with predicting the severity of Heart failure according to NYHA classification.
This notebook downloads ECG data from five different sources and creates a combined data set. It then creates a deep LSTM based Inception
network and trains it on rr intervals from ecg signals.
- **svm_hf**: This notebooks applies SVM, KNNs and random forest techniques on some standard heart failure data sets as well as on the dataset constrcuted using
 longitudinal data. It only gives detection no severity estimation of the disease
- **seq_model_hf**: This notebook creates a LSTM based sequence model for HF detection on longitudinal data. It does preprocessing of files in ehr_data and creates 
  features for training. To quantify realtive importannce of different categories of features it does seperate modelling for each feature type( diagnostics, vitals, medication)
  and compares performance. It then does modelling on all features combined
- **ehr_data_preprocessing**- This notebooks is for preprocessing ehr data files for svm training. It constructs features and creates an csv outputfile on while svm
  and other classical machine learning techniques are applied for HF detection.
## Data files description:
   1. ehr_data: This containes five files:
        - diagnosis_record.pdf-  It contains the patient records with only diagnosis features (ICD-9 codes) 
        - vitals_record.pdf- It contains the patients records with only vitals (systolic, diastolic pressure) features
        - medication_record.pdf- This containes the patients records with only medication features
        - combined_features.pdf- It combines all the above three files to include all three categories of features for a patient
        - patient_cohort.pdf- It containes the list of all unique patients with diagnosis date and assigned label
   2. svm_modelling_data: This containes three files:
        - heart.csv- This is the cleveland dataset on which traditional approaches were tried.
        - heart_failure_clinical_records_dataset.csv- This is the second dataset (BMC informatics dataset)
        on which traditional approaches were tried.
        - output_all.csv- This files was created after preprocessing files in ehr_data and constructing features from them.
        The same traditional approaches(svm, knn, random forests) were applied on this.
  ## Code Contributor
  Sourav kumar (souravk1113@gmail.com, sourav.kumar@philips.com)
   

    
