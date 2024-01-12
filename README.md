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
   - Defined a helper function to map numeric labels to characters ('0' to '9', 'A' to 'Z', 'a' to 'z').
   - Loaded and preprocessed the images, resizing them to a common size (64x64) and converting them to grayscale.

2. **Binary Classifiers:**
   - Selected the classes 'A' and '4' for binary classification.
   - Shuffled and split the data into training, validation, and testing sets (both randomly and using stratified sampling).
   - Trained a logistic regression model for binary classification and evaluated its performance on training and testing data. Confusion matrices, accuracy, recall, precision, ROC curves, and AUC were presented.

3. **Multiclass Classifier:**
   - Expanded the task to a multiclass classification involving classes '4', 'A', 'H', and 'u'.
   - Similar to binary classification, shuffled and split the data into training, validation, and testing sets (both randomly and using stratified sampling).
   - Trained a logistic regression model for multiclass classification and evaluated its performance on training and testing data. Confusion matrices, accuracy, average recall, average precision, F1 scores, and class distribution visualization were presented.

4. **Results and Discussion:**
   - Provided detailed result explanations for both binary and multiclass classification.
   - Discussions included observations about class imbalances, performance on easier and more difficult classes, impact of stratified sampling, and challenges faced by the model on testing data.

5. **Visualizations:**
   - Included visualizations such as bar charts and pie charts to show class distributions.
   - Confusion matrices, ROC curves, and class-wise performance visualizations were presented.

6. **Challenges and Future Considerations:**
   - Result explanations highlighted challenges faced by the model, especially on minority classes ('4' and 'u').
