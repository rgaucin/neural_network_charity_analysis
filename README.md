# Neural Network Charity Analysis

## Overview

The purpose of this analysis is to create a neural network model that will predict the effectiveness of donations to various charities, to ensure that the investments are worth making.

## Results

### Data Preprocessing

The target of the model is the "Is Successful" variable in the data.

The features of the model are, for each charity:
- Application Type
- Affiliation
- Classification
- Use Case
- Organization
- Status
- Income Amount
- Special Considerations
- Ask Amount

The following variables are neither targets nor features and are removed from the data:
- EIN
- Name

### Compiling, Training, and Evaluating the Model

- **Neurons:** The numbers of neurons selected for the model are between 80-90, roughly twice as the number of inputs in each of the optimization attempts.
- **Layers:** One optimization attempt uses 5 layers (an input, an output, and 3 hidden layers) to try to capture more of the interactions between variables. The other optimization attempts use 3 layers (input, output, 1 hidden layer).
- **Activation:** Each layer (except outputs) uses a ReLU activation function for their effectiveness. Output layers use sigmoid activation functions to produce a binary output.

The best model performance produces an accuracy of 72% on test data, below the target accuracy of 75%. The steps taken to improve performance were:
- Adjusting the binning of the Affiliation and Classification variables, as well as an experimental and unsuccessful re-binning of Application Type into 'T3' (the vast majority of application type) and 'Other'.
- Adding additional hidden layers. This produced an accuracy performance of 74% on training data, but 71% on test data, suggesting overfitting.
- Removing Use Case and Special Considerations from input data. This produced an accuracy performance of 72%.

## Summary

Overall, the neural network models identify the success of charities with about 72% accuracy. Because the goal of the analysis is to classify nonlinear data into two groups, an SVM model may be an effective alternative.