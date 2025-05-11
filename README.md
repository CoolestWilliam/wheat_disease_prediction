# DS-UA 301 Project: CNN-powered Wheat Disease Detection
[Presentaion Slides](https://github.com/CoolestWilliam/wheat_disease_prediction/blob/main/ATDS%20Project%20Slides.pdf)
# Project Backgroud
We are exploring the use of CNN-based image recognition to detect diseases in wheat crops and recommend effective treatments. Our analysis aims to answer how accurately deep learning can diagnose wheat diseases and then provide the correct treatment solutions to minimize crop losses. According to the study "Multi-peril pathogen risks to global wheat production: A probabilistic loss and investment assessment" (Chai_Senay_Horvath_Pardey_2022), wheat farmers around the globe lose 4-10 billion USD annually due to disease-related yield reductions, making treatment measures of topmost priority. As the world population continues to grow, ensuring global food security becomes more essential than ever. Our project will go beyond image classification – we will also use our models to recommend wheat disease treatment as well.

# Dataset
Dataset contains all wheat images can be found on [Kaggle](https://www.kaggle.com/datasets/kushagra3204/wheat-plant-diseases/data).

# Project Goal Overview
<img width="870" alt="截屏2025-05-10 下午8 01 53" src="https://github.com/user-attachments/assets/b3376abf-c50e-477a-aaca-7776b4b92453" />

# Steps
We trained three CNNs and compare their performance on wheat disease prediction. 

The chose ResNet18, MobileNetV2, and a customized CNN model.

The code used to train ResNet18 is in [resnet18.ipynb](https://github.com/CoolestWilliam/wheat_disease_prediction/blob/main/resnet18.ipynb).

The code used to train MobileNetV2 is in [MobileNetV2.ipynb](https://github.com/CoolestWilliam/wheat_disease_prediction/blob/main/MobileNetV2.ipynb).

The code used to design the customized CNN and train it is in [customCNN.ipynb](https://github.com/CoolestWilliam/wheat_disease_prediction/blob/main/customCNN.ipynb).

We also created a method for [treatment recommendation](https://github.com/CoolestWilliam/wheat_disease_prediction/blob/main/treatmentRecommendation.ipynb) that can be utilized with the given disease type, powered by the [treatment dataframe](https://github.com/CoolestWilliam/wheat_disease_prediction/blob/main/wheat_treatments.csv) created after agricultural research.

# Results
ResNet18:

<img width="471" alt="PNG image" src="https://github.com/user-attachments/assets/1713d167-2c99-4d04-9eec-e5e9fdb44c71" />

MobileNetV2:

<img width="531" alt="截屏2025-04-17 下午9 16 39" src="https://github.com/user-attachments/assets/5533fe6c-1440-4a16-8a4c-3ce97f7eef53" />

Customized CNN:

<img width="529" alt="PNG image" src="https://github.com/user-attachments/assets/7e7d1e61-105a-4f0a-a205-3e0a3df9b83f" />

Our CNN-powered wheat disease classification yielded initial promising results – we trained 3 models: ResNet18, a custom CNN, and MobileNetV2, and the former two yielded strong overall accuracy, precision, recall, and F-1 Score. However, all models had poor accuracy (>0.10) on healthy class images. Our next goal was to use various techniques to improve this accuracy, and observe how each CNN changes after applying the techniques.

Ex. The result of ResNet18.

<img width="406" alt="截屏2025-05-10 下午9 33 12" src="https://github.com/user-attachments/assets/34864f7c-7406-45a4-b473-e3a155bce596" />

After using data augmentation and balancing, it gives negative results, all CNNs experience a decrease in accuracy. This result indicates the issue regarding the healthy class needs more advanced techniques to solve.

Ex. MobileNetV2 before and after applying data augmentation techniques.
<img width="900" alt="截屏2025-05-10 下午9 38 44" src="https://github.com/user-attachments/assets/623df79b-2b22-4750-8f0d-40cd917397e0" />

# Conclusion

CNN-based models are strong at classifying the differences between disease classes. However, when tasked with predicting the healthy wheat classes (absence of disease), they struggle and have very low accuracy. Even when various techniques are used to try to fix these issues, such as data augmentation and class rebalancing, the model does not see any significant improvement in healthy class prediction accuracy. Worse, this change causes all other disease classes to have significantly reduced prediction accuracy. Potential solutions to address this issue include expanding the dataset to provide the CNN with more examples of healthy wheat, enhancing the model with a more powerful image classification architecture, and incorporating an attention mechanism to help the network focus more effectively on distinguishing disease-specific patterns.

# Reference
Inspired by the article of using CNN for wheat disease detection:

https://www.sciencedirect.com/science/article/pii/S2352914821001313

and the wheat disease loss data from the Crop Protection Network:

https://cropprotectionnetwork.org/publications/wheat-disease-loss-estimates-from-the-united-states-and-ontario-canada-2020

