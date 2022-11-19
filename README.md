# DEEP LEARNING - ALPHABET SOUP

## Background

The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With your knowledge of machine learning and neural networks, you’ll use the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

From Alphabet Soup’s business team, you have received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as:

* **EIN** and **NAME**—Identification columns
* **APPLICATION_TYPE**—Alphabet Soup application type
* **AFFILIATION**—Affiliated sector of industry
* **CLASSIFICATION**—Government organization classification
* **USE_CASE**—Use case for funding
* **ORGANIZATION**—Organization type
* **STATUS**—Active status
* **INCOME_AMT**—Income classification
* **SPECIAL_CONSIDERATIONS**—Special consideration for application
* **ASK_AMT**—Funding amount requested
* **IS_SUCCESSFUL**—Was the money used effectively

## Steps Taken to accomplish assignment
1. Preprocess the Data
2. Compile, Train, and Evaluate the Model
3. Optimize the Model
4. Write a Report on the Neural Network Model (below)


## Report on the Neural Network Model
### Overview of the analysis: 
The purpose of this analysis is to assist the nonprofit foundation Alphabet Soup with selecting the best applicant for funding as determined by their success in their ventures. The ask was to use binary classifier to predict whether applicants will be successful if funding was provided.

### Results:
* **Data Preprocessing**
    * What variable(s) are the target(s) for your model?
      * IS_SUCCESSFUL was the target variable for the model.
    * What variable(s) are the features for your model?
      * The features of the model were the remaining columns after EIN, NAME and IS_SUCCESSFUL were removed - 9 features.
    * What variable(s) should be removed from the input data because they are neither targets nor features?
      * Those variables were mentioned above: EIN and NAME columns.
  
* **Compiling, Training, and Evaluating the Model**
    * How many neurons, layers, and activation functions did you select for your neural network model, and why?
      * To start off two (2) hidden layers were selected with neurons for each being 80, 30 respectively. The activation selected was "relu" since it tends to perform better i.e., produces higher accuracy than other activations for this case.

              Model: "sequential"
              _________________________________________________________________
              Layer (type)                Output Shape              Param #   
              =================================================================
              dense (Dense)               (None, 80)                3520      
                                                                              
              dense_1 (Dense)             (None, 30)                2430      
                                                                              
              dense_2 (Dense)             (None, 1)                 31        
                                                                              
              =================================================================
              Total params: 5,981
              Trainable params: 5,981
              Non-trainable params: 0
              _________________________________________________________________

    * Were you able to achieve the target model performance?
      * The goal model performance was set at 75% however, only an accuracy of 73% (rounded) was achieved.
          
          *#Evaluate the model using the test data*
          model_loss, model_accuracy = nn.evaluate(X_test_scaled,y_test,verbose=2)
          print(f"Loss: {model_loss}, Accuracy: {model_accuracy}")
          
          268/268 - 0s - loss: 0.5563 - accuracy: 0.7254 - 499ms/epoch - 2ms/step
          Loss: 0.5562915802001953, Accuracy: 0.7253644466400146


    * What steps did you take in your attempts to increase model performance?
        1. Increase the list of classification
        2. Modified existing hidden layer number of neurons to 100 and 40 for the first and second layers respectively
        3. Added another hidden layer with number of neurons equal to 20
        4. Increased the number of epochs from 100 to 200
      * Summary of efforts: The model underperformed by 0.1%

### Summary:
Although an improved level of accuracy was not achieved, I believe that additional features should have possibly increase accuracy of the model. Also, it is possible that the effectiveness of this model could benefit from additional data since that is when Neural Network thrives.