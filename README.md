# Neural_Network_Charity_Analysis
Use neural network to create a binary classifier that is capable of predicting applicant success if funded by client


## Overview of Project
  ### Purpose
   Client has requested a neural network binary classifier to predict if applicant projects will be successful if funded.  This will allow the client to invest in succesful projects and increase impact.  
  
  ### Deliverables
   - D1: Preprocess data for a neural network
   - D2: Compile, train, and evaluate the model
   - D3: Optimize the model to >75%
   - D4: Written report
   
  ### Resources
   - Data Sources: charity_data.csv
   - Technology:  Jupyter Notebook, Python 3.7

## Results

  ### Data Preprocessing results
   - What variable(s) are considered the target(s) for your model? The "IS_SUCCESSFUL" variable is the target.  We are aiming to predict if an applicant's project will be successful if we fund it. 
   - What variable(s) are considered to be the features for your model? Features include NAME, APPLICATION_TYPE (binned), AFFILIATION, CLASSIFICATION (binned), USE_CASE, ORGANIZATION, and INCOME_AMT. 
   - What variable(s) are neither targets nor features, and should be removed from the input data? The EIN is an identifier, and can be removed because it is redundant to the name column.  The SPECIAL_CONSIDERATIONS AND STATUS columns can also be removed because they are 'noisy'. 

  ### Compiling, Training, and Evaluating the Model
   - How many neurons, layers, and activation functions did you select for your neural network model, and why? 
   - Were you able to achieve the target model performance?
   - What steps did you take to try and increase model performance?
  
## Summary
  ### Conclusions
  ### Limitations
  ### Additional Analysis - different model
