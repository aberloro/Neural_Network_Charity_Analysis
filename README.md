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

  ### Data Preprocessing 
   - What variable(s) are considered the target(s) for your model? 
      - The "IS_SUCCESSFUL" variable is the target.  We are aiming to predict if an applicant's project will be successful if we fund it. 
   - What variable(s) are considered to be the features for your model? 
      - NAME
      - APPLICATION_TYPE (binned)
      - AFFILIATION
      - CLASSIFICATION (binned)
      - USE_CASE
      - ORGANIZATION
      - INCOME_AMT 
   - What variable(s) are neither targets nor features, and should be removed from the input data? 
      - The EIN is an identifier, and can be removed because it is redundant to the name column.  
      - The SPECIAL_CONSIDERATIONS AND STATUS columns can also be removed because they are 'noisy'. 

  ### Compiling, Training, and Evaluating the Model
   - How many neurons, layers, and activation functions did you select for your neural network model, and why? 
      - 3 hidden layers
      - 120, 60, and 20 neurons for layers 1-3 respectively.
      - Additional layers and neurons were meant to improve the model's ability to process nonlinear data and weigh features. 
      - ReLU was used for layers 1 + 2 while sigmoid was used for layer 3 and the ooutput layer. ReLU is great for nonlinear data and sigmoid helps with classification. 
   - Were you able to achieve the target model performance? 
      - Yes! The optimized model has an accuracy score of 80% and loss of 0.45. 
   - What steps did you take to try and increase model performance? I went through iterations to see what changes worked the best:
      - [Non-Optimized](https://github.com/aberloro/Neural_Network_Charity_Analysis/blob/main/AlphabetSoupCharity.ipynb): accuracy score of .7299
      - [Attempt 1](https://github.com/aberloro/Neural_Network_Charity_Analysis/blob/main/Optimization_Iterations/AlphabetSoupCharity_Optimization_01.ipynb): removal of noisy features SPECIAL_CONSIDERATIONS and STATUS. Almost no improvement.
      - [Attempt 2](https://github.com/aberloro/Neural_Network_Charity_Analysis/blob/main/Optimization_Iterations/AlphabetSoupCharity_Optimization_02.ipynb): adjust bins for APPLICATION_TYPE and CLASSIFICATION. Slight deterioration of accuracy.
      - [Attempt 3](https://github.com/aberloro/Neural_Network_Charity_Analysis/blob/main/Optimization_Iterations/AlphabetSoupCharity_Optimization_03.ipynb): retain and encode NAME data. This was the most impactful change and took accuracy from 73% to 80%
      - [Final Model](https://github.com/aberloro/Neural_Network_Charity_Analysis/blob/main/AlphabetSoupCharity_Optimization.ipynb): add neurons, layers, and additional epochs. No change over attempt 3. 
  
## Summary
Retaining and encoding the NAME data had the biggest impact on the accuracy of this model.  Counting the number of times eacch name appeared is equivalent to counting how many times they applied: companies who applied 3 or more times were more likely to succeed if funded.  A Random Forest Model would be another option for this data because it is an ensemblel learner that tolerates nonliner data and may be easier to code and faster to run than this neural network. 
