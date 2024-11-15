# Hand Gesture Recognition Project

## Project Overview

This project focuses on developing a hand gesture recognition model capable of identifying and classifying different hand gestures from image or video data. The goal is to enable intuitive human-computer interaction and gesture-based control systems. The model is trained on a dataset containing hand gesture images, and it aims to classify these gestures into predefined categories.

## Dataset

The dataset used for this project is sourced from the [Leap Gesture Dataset](https://www.kaggle.com/gti-upm/leapgestrecog), which consists of hand gesture images captured under various conditions. Each image corresponds to a specific gesture, and the dataset is organized into subfolders for each gesture class.

### Dataset Structure

- **Number of Classes:** 10 (one for each gesture)
- **Images per Class:** Varies, but each folder contains multiple images representing the corresponding gesture.
- **Image Size:** Varies across images.
- **Format:** Images are stored in `.png` format.

## Project Structure
   ```sh

   Hand_Gesture_Recognition/
   │
   ├── datasets/
   │   └── leapGestRecog/   # Place the Leap Gestures dataset here (organized in subfolders by gesture classes)
   │
   ├── models/
   │   └── best_model.keras    # Saved model after training (will be generated after training)
   │
   ├── notebooks/
   │   └── Hand_Gesture_Recognition_Model.ipynb  # Your Jupyter notebook file for experimentation and prototyping
   │
   ├── src/
   │   ├── __init__.py      # Marks the folder as a package
   │   ├── data_preprocessing.py  # Contains functions to preprocess images and load data
   │   ├── model.py         # Defines the CNN model architecture
   │   ├── train.py         # Code to train the model
   │   ├── evaluate.py      # Script to evaluate the model performance
   │   ├── utils.py         # Utility functions such as visualization, callbacks
   │
   │
   ├── results/
   │   └── performance_plots.png  # Store plots of accuracy/loss curves for analysis
   │
   ├── .gitignore           # Git ignore file to ignore unnecessary files such as datasets, models
   ├── README.md            # Project description, setup instructions, and usage details
   ├── requirements.txt     # List of dependencies (TensorFlow, Keras, etc.)
   └── run.sh               # Bash script to automate the training and evaluation process

   ```


## Model Overview

The hand gesture recognition model uses deep learning techniques for classification. The core architecture of the model is a Convolutional Neural Network (CNN), which is particularly effective for image data.

### Key Steps in the Model Development:

1. **Data Preprocessing:**
   - Images are loaded from their respective directories.
   - Data is preprocessed (resized, normalized) for input into the CNN model.
   - Augmentation techniques such as flipping, rotation, and scaling are applied to increase the diversity of the training data.

2. **CNN Architecture:**
   - The CNN consists of multiple convolutional layers followed by max-pooling layers.
   - These layers extract key features from the images that are relevant for classification.
   - Fully connected (dense) layers are used after the convolutional layers to output predictions for the 10 gesture classes.

3. **Model Compilation:**
   - The model is compiled with the categorical cross-entropy loss function and the Adam optimizer.
   - Accuracy is used as the evaluation metric.

4. **Training and Evaluation:**
   - The model is trained on the dataset using a training-validation split.
   - Accuracy and loss are monitored during training to track the model's performance.
   - The trained model is evaluated on a test set to measure its accuracy and generalization ability.

## Instructions for Running the Project

### Prerequisites

Before running the project, make sure you have the following installed:

- Python 3.x
- TensorFlow
- Keras
- NumPy
- Pandas
- Matplotlib
- OpenCV

### Steps to Run

1. **Clone the Repository:**
   Clone this project repository using the following command:

   ```sh
   git clone https://github.com/abigiyaayele/PRODIGY_ML_04.git
   ```

2. **Download the Dataset:**
    Download the dataset from Kaggle and place it in the data/ folder.

3. **Run the Model:**
    You can run the model by executing the train.py file:
    ```sh
    python train.py
    ```

    Alternatively, open the Hand_Gesture_Recognition_Model.ipynb notebook and run the cells step by step to train the model interactively.

4. **Evaluate the Model:**
    The model's accuracy and loss will be displayed during training. You can also visualize the training process by plotting accuracy and loss curves.


## Future Work
Possible enhancements to improve the model and the project include:

- Implementing more advanced augmentation techniques to further improve model generalization.
-Experimenting with different model architectures (e.g., ResNet, Inception) to achieve higher accuracy.
-Implementing real-time hand gesture recognition using a webcam.

## Conclusion
This project demonstrates the effective use of CNNs for hand gesture recognition. The model can classify different hand gestures with high accuracy and serves as a foundation for more complex human-computer interaction systems.