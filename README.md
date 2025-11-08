# **☪️Comparing Adam and RMSProp Optimizer in MFCC CNN Architecture (Case: Quranic Murottal Rhythm)**

This project utilizes MFCC and CNN to classify Quran murottal rhythm, achieving an accuracy of 99.82%. It analyzes 8 qaris' recitations of Al-Fatiha and Juz 30, optimizing parameters for robust rhythm recognition with strong potential for Islamic speech analysis.

### 📃You can see the full paper at:
  - Thesis (Indonesian): https://repository.uinjkt.ac.id/dspace/handle/123456789/84765
  - Journal (English): *under publishing process to IEEE Journal (already presented at 13th International Conference on Cyber and IT Service Management (CITSM) 2025)*
    
## ❓About this research (abstract)
This research aims to apply Mel Frequency Cepstral Coefficient (MFCC) feature extraction, especially in speech recognition, as well as a Convolutional Neural Network (CNN) classification model using Quran murottal rhythm, and find out its effect on the results. In this case, the ability to distinguish the type of rhythm in the current Quran murottal is still relatively low, so a Quran murottal rhythm classification is needed. The methods used are data collection and simulation methods. This study experimented with various scenarios of coefficients and frame length in MFCC feature extraction as well as optimizer and dropout rate in CNN model using a dataset of 8 qori on the rhythm of recitation of Surah Al-Fatiha and Juz 30, totaling 4,794 data points, showing the new opportunity from previous studies. The results showed that the combination of 40 MFCC coefficients, 20 ms frame length, RMSProp optimizer, and 0.3 dropout rate on the CNN model achieved 99.82% accuracy and 100.00% accuracy validation in recognizing the rhythm of the Quran murottal. This research has the potential to provide solutions in effective modeling and similar literature on murottal rhythm in the future.

## ⚙️Adam and RMSProp Optimizer Differences
Both Adam and RMSProp are adaptive optimization algorithms used to update model weights during training. Adam maintains moving averages of both the gradients and the squared gradients, using this information to adjust the learning rate for each weight update, which leads to improved convergence [8][15]. RMSProp focuses on addressing vanishing learning rates by storing a moving average of the squared gradients and using this value to modify the learning rate, enabling faster and more efficient learning [8]. Despite their different approaches, both algorithms are designed to enhance model convergence and reduce overall training time [8].

<img width="469" height="600" alt="Gambar2" src="https://github.com/user-attachments/assets/2099ddcf-7092-437e-89f8-b21022b47aac" />


## 🛠️Methods
  1. Problem Formulation: Literature Review
  2. Conceptual Model: using MFCC and CNN architecture
  3. Collection and Analysis of Input Data: 8 qaris of Surah Al-Fatiha and all Surahs in Juz 30
  4. Modeling: preprocessing, Fourier transform, mel filtering, MFCC, CNN
  5. Simulation: using Google Colaboratory
  6. Verification and Validation
  7. Experimentation
  8. Output Analysis

**MODEL SCENARIO**

| Scenario | MFCC Extraction Feature | ~          | CNN Model | ~           |
|----------|-------------------------|----------|-----------|-----------|
|          | MFCC Coefficient        | Frame Length | Optimizer | Dropout Rate |
| 1        | 13                      | 20       | Adam      | 0.3       |
| 2        | 13                      | 40       | Adam      | 0.3       |
| 3        | 40                      | 20       | Adam      | 0.3       |
| 4        | 40                      | 40       | Adam      | 0.3       |
| 5        | 13                      | 20       | Adam      | 0.5       |
| 6        | 13                      | 40       | Adam      | 0.5       |
| 7        | 40                      | 20       | Adam      | 0.5       |
| 8        | 40                      | 40       | Adam      | 0.5       |
| 9        | 13                      | 20       | RMSProp   | 0.3       |
| 10       | 13                      | 40       | RMSProp   | 0.3       |
| 11       | 40                      | 20       | RMSProp   | 0.3       |
| 12       | 40                      | 40       | RMSProp   | 0.3       |
| 13       | 13                      | 20       | RMSProp   | 0.5       |
| 14       | 13                      | 40       | RMSProp   | 0.5       |
| 15       | 40                      | 20       | RMSProp   | 0.5       |
| 16       | 40                      | 40       | RMSProp   | 0.5       |


## Results
  1. 🔎Verification and Validation
     In this phase, a verification process is conducted to ensure that the simulation executed within the program aligns with the results obtained from Google Colaboratory. The purpose of this verification is to confirm that the simulation using the model has been carried out correctly. The training of the CNN model is performed using the training data over 20 epochs, commencing with the execution of the source code to train the CNN model.

     <img width="242" height="174" alt="Gambar11" src="https://github.com/user-attachments/assets/08ad8599-3697-49d4-85f9-37432cf319cd" />

     _Image of execution console at Google Colaboratory_

  2. 🧪Experimentation
     The experiments are conducted by training the model according to the scenarios of coefficient distribution and frame length in the MFCC feature extraction, along with the configuration of the optimizer and dropout rate for each CNN model. This is followed by testing using the testing data. The results of the CNN model are evaluated based on the accuracy values obtained from both the training and testing processes.
     
  3. 📝Evaluation

     <img width="378" height="322" alt="Screenshot 2025-11-08 123210" src="https://github.com/user-attachments/assets/d0ba79c1-3f46-4f02-a5dd-71ecf23057c3" />

     _Image of Scenario 11 Confusion Matrix (highest result)_
     
     The highest accuracy of 99.82% and validation accuracy of 100.00% was achieved in scenario 11 using 40 MFCC coefficients, a 20ms frame length, the RMSProp optimizer, and a 0.3 dropout rate, while the lowest performance (74.78% accuracy, 86.13% validation) occurred in scenario 14 with 13 coefficients, a 40ms frame, RMSProp, and 0.5 dropout. Similarly, the Adam optimizer performed best in scenario 3 (99.77% accuracy, 99.79% validation) using the optimal 40/20ms/0.3 combination, and worst in scenario 6 (74.97% accuracy, 88.11% validation) with the inferior 13/40ms/0.5 parameters, demonstrating that the combination of 40 coefficients, a 20ms frame length, and 0.3 dropout consistently yields the highest accuracy with both optimizers.

     <img width="375" height="320" alt="Screenshot 2025-11-08 123229" src="https://github.com/user-attachments/assets/2377e328-304b-4202-af5a-bde143e7a79b" />

     _Image of Scenario 14 Confusion Matrix (lowest result)_
     
     From Table below, the model in scenario 11 achieved a perfect accuracy of 100%, indicating exceptional performance with no classification errors, while scenario 14 recorded the lowest accuracy of 96.53%, revealing significant prediction errors for certain labels. The results prove that variations in MFCC coefficients, frame lengths, optimizer selection, and dropout rates significantly influence accuracy, as the same RMSProp optimizer yielded both the best and some of the worst results depending on its combination with other feature extraction and model parameters. Overall, despite these variations, each model demonstrated good performance by achieving relatively high accuracy and low loss.

**ACCURACY AND LOSS RESULTS OF MODEL SCENARIO EXPERIMENTS**

| Scenario | % Accuracy | % Val Acc | % Loss   | % Val Loss |
|----------|------------|-----------|----------|------------|
| 1        | 97,76      | 98,54     | 7,00     | 5,43       |
| 2        | 98,17      | 98,02     | 6,27     | 4,64       |
| 3        | 99,77      | 99,79     | 0,90     | 1,27       |
| 4        | 99,09      | 99,79     | 3,36     | 1,09       |
| 5        | 90,04      | 94,89     | 32,77    | 17,84      |
| 6        | 74,97      | 88,11     | 68,58    | 41,23      |
| 7        | 95,85      | 98,96     | 12,05    | 2,76       |
| 8        | 98,62      | 99,90     | 5,32     | 0,82       |
| 9        | 97,24      | 98,96     | 9,62     | 5,15       |
| 10       | 97,91      | 97,71     | 10,23    | 9,80       |
| 11       | 99,82      | 100,0     | 1,20     | 0,02       |
| 12       | 99,74      | 99,90     | 1,89     | 0,10       |
| 13       | 94,03      | 96,66     | 22,17    | 15,43      |
| 14       | 74,78      | 86,13     | 76,77    | 42,57      |
| 15       | 99,19      | 99,90     | 4,39     | 0,32       |
| 16       | 99,32      | 99,69     | 4,32     | 1,54       |

**RESULTS OF MODEL SCENARIO EXPERIMENT METRIC CALCULATIONS**

| Scenario   | % Accuracy | % Precision | % Recall   | % F1-Score |
|------------|------------|-------------|------------|------------|
| 1          | 99,64      | 98,51       | 98,44      | 98,47      |
| 2          | 99,50      | 98,06       | 97,97      | 98,01      |
| 3          | 99,95      | 99,80       | 99,80      | 99,80      |
| 4          | 99,95      | 99,79       | 99,80      | 99,79      |
| 5          | 98,72      | 97,78       | 94,70      | 94,86      |
| 6          | 97,03      | 95,27       | 87,81      | 88,10      |
| 7          | 99,74      | 98,93       | 98,94      | 98,93      |
| 8          | 99,97      | 99,89       | 99,90      | 99,89      |
| 9          | 99,74      | 98,93       | 98,87      | 98,89      |
| 10         | 99,43      | 97,74       | 97,74      | 97,71      |
| 11         | 100,0      | 100,0       | 100,0      | 100,0      |
| 12         | 99,97      | 99,90       | 99,89      | 99,90      |
| 13         | 99,17      | 96,68       | 96,60      | 96,56      |
| 14         | 96,53      | 88,77       | 85,87      | 86,18      |
| 15         | 99,97      | 99,90       | 99,89      | 99,89      |
| 16         | 99,92      | 99,69       | 99,70      | 99,69      |

## 🔖Discussion and Conclusion
A Convolutional Neural Network (CNN) utilizing Mel Frequency Cepstral Coefficient (MFCC) feature extraction has been successfully applied to classify Quranic murottal rhythms. The optimal configuration, combining 40 MFCC coefficients with a 20ms frame length, an RMSProp optimizer, and a 0.3 dropout rate in the CNN, achieved exceptional accuracy metrics of 99.82%, 100.00% validation accuracy, and 100.00% accuracy. The study demonstrated that variations in MFCC parameters, optimizer selection, and dropout rates significantly influence the model's performance, with the RMSProp optimizer yielding results ranging from 74.78% to 99.82% depending on the specific combination used.

To further enhance this research, increasing the dataset size and scope is recommended to improve robustness. Future work should systematically address key gaps, including the use of more recent, domain-specific references to better map the state of the art in rhythm recognition, and the formulation of operationalized, rhythm-specific metrics rather than reciter-based labels. Methodological improvements are crucial, such as implementing a per-speaker data split to prevent identity leakage from timbre, and providing full replication details, including sampling rate, hop length, number of mel filters, learning rate, and code. The experimental design should be strengthened with cross-validation, statistical testing, and ablation studies tailored to the rhythm objective, while results should include detailed error analysis, confusion matrices, and comparisons against robust baselines like SVM-MFCC to properly contextualize the high reported accuracies and rule out overfitting. Exploring the model's generalizability on unrelated audio domains could also be valuable.

### 🔗Codings, References, and Other Attachments
See the full paper at https://repository.uinjkt.ac.id/dspace/handle/123456789/84765 (Indonesian)
