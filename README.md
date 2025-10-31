# **Comparing Adam and RMSProp Optimizer in MFCC CNN Architecture (Case: Quranic Murottal Rhythm)**

This project utilizes MFCC and CNN to classify Quran murottal rhythm, achieving an accuracy of 99.82%. It analyzes 8 qaris' recitations of Al-Fatiha and Juz 30, optimizing parameters for robust rhythm recognition with strong potential for Islamic speech analysis.

### You can see the full paper at:
  - Thesis (Indonesian):
  - Journal (English):
    
## About this research (abstract)
This research aims to apply Mel Frequency Cepstral Coefficient (MFCC) feature extraction, especially in speech recognition, as well as a Convolutional Neural Network (CNN) classification model using Quran murottal rhythm, and find out its effect on the results. In this case, the ability to distinguish the type of rhythm in the current Quran murottal is still relatively low, so a Quran murottal rhythm classification is needed. The methods used are data collection and simulation methods. This study experimented with various scenarios of coefficients and frame length in MFCC feature extraction as well as optimizer and dropout rate in CNN model using a dataset of 8 qori on the rhythm of recitation of Surah Al-Fatiha and Juz 30, totaling 4,794 data points, showing the new opportunity from previous studies. The results showed that the combination of 40 MFCC coefficients, 20 ms frame length, RMSProp optimizer, and 0.3 dropout rate on the CNN model achieved 99.82% accuracy and 100.00% accuracy validation in recognizing the rhythm of the Quran murottal. This research has the potential to provide solutions in effective modeling and similar literature on murottal rhythm in the future.

## Adam and RMSProp Optimizer Differences
Both Adam and RMSProp are adaptive optimization algorithms used to update model weights during training. Adam maintains moving averages of both the gradients and the squared gradients, using this information to adjust the learning rate for each weight update, which leads to improved convergence [8][15]. RMSProp focuses on addressing vanishing learning rates by storing a moving average of the squared gradients and using this value to modify the learning rate, enabling faster and more efficient learning [8]. Despite their different approaches, both algorithms are designed to enhance model convergence and reduce overall training time [8].

## Methods
  1. Problem Formulation: Literature Review
  2. Conceptual Model: using MFCC and CNN architecture
  3. Collection and Analysis of Input Data: 8 qaris of Surah Al-Fatiha and all Surahs in Juz 30
  4. Modeling: preprocessing, Fourier transform, mel filtering, MFCC, CNN
  5. Simulation: using Google Colaboratory
  6. Verification and Validation
  7. Experimentation
  8. Evaluation: using F1-score and confusion matrix

## Results
  1. Verification and Validation
     In this phase, a verification process is conducted to ensure that the simulation executed within the program aligns with the results obtained from Google Colaboratory. The purpose of this verification is to confirm that the simulation using the model has been carried out correctly. The training of the CNN model is performed using the training data over 20 epochs, commencing with the execution of the source code to train the CNN model.

  2. Experimentation
     The experiments are conducted by training the model according to the scenarios of coefficient distribution and frame length in the MFCC feature extraction, along with the configuration of the optimizer and dropout rate for each CNN model. This is followed by testing using the testing data. The results of the CNN model are evaluated based on the accuracy values obtained from both the training and testing processes.
     
  3. Evaluation
     The highest accuracy of 99.82% and validation accuracy of 100.00% was achieved in scenario 11 using 40 MFCC coefficients, a 20ms frame length, the RMSProp optimizer, and a 0.3 dropout rate, while the lowest performance (74.78% accuracy, 86.13% validation) occurred in scenario 14 with 13 coefficients, a 40ms frame, RMSProp, and 0.5 dropout. Similarly, the Adam optimizer performed best in scenario 3 (99.77% accuracy, 99.79% validation) using the optimal 40/20ms/0.3 combination, and worst in scenario 6 (74.97% accuracy, 88.11% validation) with the inferior 13/40ms/0.5 parameters, demonstrating that the combination of 40 coefficients, a 20ms frame length, and 0.3 dropout consistently yields the highest accuracy with both optimizers.
    [attach]
    From Table 5, the model in scenario 11 achieved a perfect accuracy of 100%, indicating exceptional performance with no classification errors, while scenario 14 recorded the lowest accuracy of 96.53%, revealing significant prediction errors for certain labels. The results prove that variations in MFCC coefficients, frame lengths, optimizer selection, and dropout rates significantly influence accuracy, as the same RMSProp optimizer yielded both the best and some of the worst results depending on its combination with other feature extraction and model parameters. Overall, despite these variations, each model demonstrated good performance by achieving relatively high accuracy and low loss.
    [attach]

## Discussion and Conclusion
A Convolutional Neural Network (CNN) utilizing Mel Frequency Cepstral Coefficient (MFCC) feature extraction has been successfully applied to classify Quranic murottal rhythms. The optimal configuration, combining 40 MFCC coefficients with a 20ms frame length, an RMSProp optimizer, and a 0.3 dropout rate in the CNN, achieved exceptional accuracy metrics of 99.82%, 100.00% validation accuracy, and 100.00% accuracy. The study demonstrated that variations in MFCC parameters, optimizer selection, and dropout rates significantly influence the model's performance, with the RMSProp optimizer yielding results ranging from 74.78% to 99.82% depending on the specific combination used.

To further enhance this research, increasing the dataset size and scope is recommended to improve robustness. Future work should systematically address key gaps, including the use of more recent, domain-specific references to better map the state of the art in rhythm recognition, and the formulation of operationalized, rhythm-specific metrics rather than reciter-based labels. Methodological improvements are crucial, such as implementing a per-speaker data split to prevent identity leakage from timbre, and providing full replication details, including sampling rate, hop length, number of mel filters, learning rate, and code. The experimental design should be strengthened with cross-validation, statistical testing, and ablation studies tailored to the rhythm objective, while results should include detailed error analysis, confusion matrices, and comparisons against robust baselines like SVM-MFCC to properly contextualize the high reported accuracies and rule out overfitting. Exploring the model's generalizability on unrelated audio domains could also be valuable.
