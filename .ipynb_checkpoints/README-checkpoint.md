# neural-network-challenge-1
Module 18 Challenge

STUDENT LOAN RISK WITH DEEP LEARNING
STEP 1 PREPARE THE DATA TO BE USED ON A NEURAL NETWORK 
------------------------------------------------------------------------------------------------------
After importing our libraries we will now, import our csv file to work and transform the data 
to work with the neural network. Looking at the data everything is a float64, and int64, so 
everything is a value the neural network could use. chekcing the credit_ranking with value counts
gives us our test data to use against the training data. 

STEP 2: USING THE PREPREPROCESSED DATA, CREATE THE FEATURES X, AND Y DATASETS. THE TARGET DATASET
SHOULD BE DEFINED BY THE PREPROCESSED DATAFRAME COLUMN USING "CREDIT_RANKING". THE REMAINING
COLUMNS SHOULD BE DEFINE THE FEATURES DATASET. 
------------------------------------------------------------------------------------------------------
The first step is to create X and Y datasets, Y is loans_df.credit_ranking and X the whole dataset 
dropping the y column of loans_df.credit_ranking. 

STEP 3: SPLIT THE FEATURES AND TARGET SETS INTO TRAINING AND TESTING DATASETS
------------------------------------------------------------------------------------------------------
For this step we use train_test_split with a random state of 1.

STEP 4: USE SCIKIT-LEARN'S STANDARDSCALER TO SCALE THE FEATURES DATA.
------------------------------------------------------------------------------------------------------
We start with creating an instance of the StandardScaler() and calling it scaler. We fit X_train and
transform X_test and X_train. 

COMPILE AND EVALUATE A MODEL USING A NEURAL NETWORK
STEP 1: CREATE A DEEP NEURAL NETWORK BY ASSINGING THE NUMBER OF INPUT FEATURES, THE NUMBER OF LAYERS, 
AND THE NUMBER OF NEURONS ON EACH LAYER USING TENSORFLOW'S KERAS.
------------------------------------------------------------------------------------------------------
We count the number of features going into the neural network. We establish the number of nodes for 
each layer. Then we create an instance of the model for tf.keras.models.Sequential(), after we call for 
the model we create each layer. using "relu" for the deep layers, and "sigmoid" for the output layer. 
Then we call a summary of the model and the number of parameters created. 

STEP 2: COMPILE AND FIT THE MODEL USING THE BINARY_CROSSENTROPY LOSS FUNCTION, THE ADAM OPTIMIZER, AND
THE ACCURACY EVALUATION METRIC.
------------------------------------------------------------------------------------------------------
After creating the neural network we then compile the neural network using "adam" as the optimizer, 
after we fit the model and run 50 epochs.

STEP 3: EVALUATE THE MODEL USING THE TEST DATA TO DETERMINE THE MODEL'S LOSS AND ACCURACY
------------------------------------------------------------------------------------------------------
we use nn_model.evaluate to see the model_loss and model_accuracy and print these values out. Loss
was about 52% and accuracy was about 74%. 

STEP 4: SAVE AND EXPORT YOUR MODEL TO A KERAS FILE, AND NAME THE FILE STUDENT_LOANS.KERAS
------------------------------------------------------------------------------------------------------
We create the file path and save to file_path then tell nn_model.save to the file path.

PREDICT LOAN REPAYMENT SUCCESS BY USING YOUR NEURAL NETWORK MODEL
STEP 1: RELOAD YOUR SAVED MODEL
------------------------------------------------------------------------------------------------------
With the path you choose in file_path the file will be created with our neural network. We use the 
file path to tf.keras.models.load_model to nn_imported. 

STEP 2: MAKE PREDICTIONS ON THE TESTING DATA AND SAVE THE PREDICTIONS TO A DATAFRAME.
------------------------------------------------------------------------------------------------------
We take the imported model and save the nn_model.predictions to predictions and use the X_scaled data.
We then save this to a DataFrame and then round predictions results to the nearest whole number. Then 
we print the results seeing our values. After we print the classification_report to see our accuracy of 
the model. 



































