
# 👁 Eye Disease Detector

This project is an AI-powered tool designed to detect common eye diseases such as red eye (redness), cataract, and crossed eyes using deep learning. It leverages pre-trained models for redness detection and a custom Convolutional Neural Network (CNN) for cataract detection, providing an automated way to assist in early diagnosis.




### 🚀 Features

**Redness Detection 🟥:**
Uses a pre-trained model to identify eye redness, a symptom of conditions like conjunctivitis.

**Cataract Detection 👀:** 
 A custom-trained CNN model detects the presence of cataracts from eye images.

**Crossed Eye Detection 👁️‍🗨️:**
Analyzes eye alignment to detect strabismus (crossed eyes).
    

### 📂 Dataset

**Redness Detection:** Used a pre-trained model (e.g., ResNet, MobileNet) trained on a dataset of red-eye vs. normal-eye images.

**Cataract Detection:** Trained a custom CNN using an open-source dataset of cataract images.

**Crossed Eye Detection:** Used a dataset containing images of normal and misaligned eyes.


### 🏗 Model Architecture

**🔴 Redness Detection:**
*  **Eye Detection:**
    * Uses Haar Cascade Classifier (haarcascade_eye_tree_eyeglasses.xml) to locate eyes in the image.

* **Convert to HSV Color Space:**
    * The image is converted from BGR to HSV, since HSV better isolates colors.

* **Redness Masking:**
    * Two red color ranges in HSV are defined:

        * Lower range: [0, 120, 70] to [10, 255, 255]

        * Upper range: [170, 120, 70] to [180, 255, 255]

    * A binary mask is created where only red areas are highlighted.

* **Redness Quantification:**
    * The percentage of red pixels in the detected eye region is calculated.

    * A threshold of 5% is used to classify redness vs. normal.


**👁 Cataract Detection:**
* **Convolutional Layers:**     
  * 4 **Convolutional layers** with increasing filters.
  * **Kernel sizes:** (3,3).
  * **Activation Function:** ReLU
  * **Batch Normalization** after each convolutional layer.

* **Pooling Layers:**
  * **MaxPooling** layers (2,2) after each convolutional block.

* **Fully Connected Layers:**
  * Flatten layer to convert feature maps to a dense vector.
  * Dense Layer with 256 neurons and ReLU activation.
  * Dropout Layer (0.5 dropout rate) to prevent overfitting.
  * Output Layer with 3 neurons (softmax activation).

* **Optimizer & Loss Function:**
  * **Optimizer:** Adam (learning_rate=0.0001) for stability.
  * **Loss Function:** Categorical Crossentropy.

### How to use:
  Redness Detection: <a href="https://colab.research.google.com/drive/1l83gVpr1dy-9k7Bo8GN0TR0fmILduGoS">Redness Detection (Colab)</a>
  
  Cataract Detection: <a href="https://www.kaggle.com/code/shivanshyadav1514/notebookf50a04b1d9/edit/run/225623938">Cataract Detection (Kaggle)</a>

### 📌 Future Improvements:
  * 🏥 Expand the dataset with more real-world images.
  * 📱 Build a mobile/web app for easy access.
  * 🔍 Enhance accuracy by fine-tuning models with more data.
  * 🧠 Implement more eye disease detections, e.g., glaucoma, diabetic retinopathy.





