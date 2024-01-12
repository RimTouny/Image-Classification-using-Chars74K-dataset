# **Image Classification using the Chars74K dataset**
Employing advanced techniques, the project seamlessly integrates binary and multiclass classifiers for character classification using [Chars74K dataset](http://www.ee.surrey.ac.uk/CVSSP/demos/chars74k/) . It offers a comprehensive analysis and adeptly addresses challenges in the realm of computer vision.This project was  part of my uOttawa Master's in Computer Vision course (2023).

- Required libraries: scikit-learn, pandas, matplotlib.
- Execute cells in a Jupyter Notebook environment.
- The uploaded code has been executed and tested successfully within the [Google Colab](https://colab.google/) environment.


## Image Classification problem
Character Classification using Binary and Multiclass classifiers in computer vision: 4’,’A’ // 4’,’A’,’u’ and ’H’ .

### Exploring Data:
The dataset utilized in this project is Chars74K, containing images of English alphabet characters. Accessible from [Chars74K dataset](http://www.ee.surrey.ac.uk/CVSSP/demos/chars74k/),the dataset is stored in the [EnglishImg.tgz]() archive. Upon extraction, it reveals a 'Bmp' folder within 'EnglishImg/English/Img/GoodImg,' organized into 62 subdirectories for each character in the Latin alphabet and digits.
Specifically focusing on characters '4,' 'A,' 'u,' and digit 'H,' located in subdirectories Sample005, Sample011, Sample057, and Sample018, respectively.

## **Key Tasks Undertaken**
1. **Data Loading and Preprocessing:**
   - Successfully uploaded the 'EnglishImg.tgz' file from Google Drive and extracted it to the 'EnglishImg' directory.
   - Map numeric labels to characters ('0' to '9', 'A' to 'Z', 'a' to 'z').
     + Extract the numeric part.
     + Remove leading zeros.
     + Convert the number string to an integer.
       - For numbers 1 to 10, Map them to strings '0' to '9'.
       - For numbers 11 to 36, Map them to uppercase letters 'A' to 'Z'. (+54)
       - For numbers 37 to 62, Map them to lowercase letters 'a' to 'z'. (+60)
   - Loaded and preprocessed the images, resizing them to a common size (64x64) and converting them to grayscale.

2. **Binary Classifiers:**
   - Selected the classes 'A' and '4' for binary classification.
       <p align="center">
           <img src="https://github.com/RimTouny/Image-Classification-using-Chars74K-dataset/assets/48333870/d00a8957-938e-4d35-a235-48bb386fe129"/>
       </p>
       
   - Shuffled and split the data into 60% training, 20% validation, and 20% testing sets (both randomly and using stratified sampling).
   - Trained a logistic regression model for binary classification and evaluated its performance on training and testing data. Confusion matrices, accuracy, recall, precision, and  ROC curves were presented.
     + Randomly Spilting
       <p align="center">
           <img src="https://github.com/RimTouny/Image-Classification-using-Chars74K-dataset/assets/48333870/a86d6936-e5c7-428a-a13a-7e49589c0306"/>
      </p>

     + Tratified Sampling
       <p align="center">
           <img src="https://github.com/RimTouny/Image-Classification-using-Chars74K-dataset/assets/48333870/0b5b8de5-90fe-4c42-9e53-b3782d7b7b9b"/>
      </p>
      
   - Result Explanation
     + When shuffling the data without using stratified sampling, there's a risk of creating training and testing sets with significantly imbalanced class distributions. This randomness can lead to variable model performance, where the model may perform exceptionally well on the training data but poorly on the testing data, especially if it overfits to the majority class.
     + On the other hand, when using stratified sampling without shuffling, the class balance is maintained in both the training and testing sets. This approach ensures that each class is represented proportionally in both sets, leading to more consistent and reliable model performance metrics. The model trained with stratified sampling is likely to generalize better to unseen data, resulting in more stable and consistent results.

3. **Multiclass Classifier:**
   - Expanded the task to a multiclass classification involving classes 4', 'A', 'H', and 'u'.
       <p align="center">
           <img src="https://github.com/RimTouny/Image-Classification-using-Chars74K-dataset/assets/48333870/abfd0c86-dc0b-43dc-9994-0ebd787ff9ba"/>
      </p>
   - Similar to binary classification, shuffled and split the data into 60% training, 20% validation, and 20% testing sets (both randomly and using stratified sampling).
   - Trained a logistic regression model for multiclass classification and evaluated its performance on training and testing data.  Confusion matrices, accuracy, recall, precision, and  ROC curves were presented.
     + Randomly Spilting
       <p align="center">
           <img src="https://github.com/RimTouny/Image-Classification-using-Chars74K-dataset/assets/48333870/815882b5-6b84-49b6-a03e-9ca765fdb46a)"/>
      </p>

     + Tratified Sampling
       <p align="center">
           <img src="https://github.com/RimTouny/Image-Classification-using-Chars74K-dataset/assets/48333870/cbeb2c90-d1b9-4a1c-917d-8a8ed5af09ce"/>
      </p>

   - Result Explanation
     + In the multiclass classification task using a Logistic Regression classifier with the 'one-vs-rest' (OvR) strategy and four target classes ('4', 'A', 'H', and 'u'), the performance of the classifier is influenced by class imbalance.

     + Class Imbalance: The dataset exhibits significant class imbalance, with 'A' having the largest number of samples (558), 'H' having 193 samples, '4' having 47 samples, and 'u' having 41 samples.

     + Easier vs. More Difficult Classes:Easier Classes: The classifier performs very well on the majority classes 'A' and 'H' in both training scenarios. These classes have larger sample sizes, and the model effectively learns to classify them.

     + More Difficult Classes: The minority classes '4' and 'u' are more challenging for the classifier. In both training scenarios, the model struggles to correctly classify these classes, resulting in lower accuracy, average recall, average precision, and F1 scores for these classes.

     + Confusion: The classifier tends to confuse the minority classes ('4' and 'u') with the majority classes ('A' and 'H'). This confusion is evident from the lower average recall and precision scores for these minority classes.

     + Impact of Stratified Sampling: Stratified sampling helps maintain class balance in the training set without significantly impacting overall performance. It results in slightly lower accuracy on the training data but maintains good average recall, average precision, and F1 scores.

     + Challenges on Testing Data: On the testing data, regardless of stratified sampling, the classifier faces difficulties in generalization, especially for the minority classes. This indicates that the model struggles to perform well on unseen data, particularly for underrepresented classes.
