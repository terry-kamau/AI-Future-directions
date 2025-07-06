# Recyclable Image Classification Project

This project demonstrates the process of building a lightweight image classification model for identifying recyclable materials using the TrashNet dataset and deploying it as a TFLite model for potential use on edge devices.

## 🚀 Getting Started
To view or run the notebook:
1. Open in [Google Colab](https://colab.research.google.com/drive/1ingKra7gcwqXswPhqbuKWE53N8nl3bPw)
2. Run each cell to explore insights and visualizations

## Project Steps:

1.  **Set up Environment**: Necessary libraries including TensorFlow, OpenCV, NumPy, and Matplotlib were installed.

2.  **Download Dataset (TrashNet)**: The TrashNet dataset was downloaded and extracted.

3.  **Prepare Data**: The dataset was prepared for training and validation using `ImageDataGenerator` with rescaling and validation splitting. Data augmentation was also applied to the training set to improve model generalization.

4.  **Hyperparameter Tuning**: A MobileNetV2 model was used as the base model with a custom classification head. The model was compiled with the Adam optimizer and trained with early stopping and model checkpointing.

5.  **Build lightweight model (MobileNetV2)**: A lightweight MobileNetV2 model was built with fine-tuning on the later layers of the base model.

6.  **Train Model**: The lightweight model was trained using the augmented training data and validated on the non-augmented validation data.

7.  **Convert to TF\*Lite**: The trained Keras model was converted to a TFLite model with default optimization (quantization) for deployment on edge devices.

8.  **Test TFLite model**: The converted TFLite model was loaded and tested on the validation dataset to evaluate its accuracy.

9.  **Visualizing the Predictions**: A sample of predictions from the TFLite model on the validation set was visualized to inspect the model's performance.

10. **Analyze misclassifications**: Misclassified images were identified and visualized to understand the types of errors the model is making.

11. **Visualize Correct Predictions**: Correctly classified images were visualized to see examples of successful predictions.

## Results:

*   The final validation accuracy of the TFLite model was **70.38%**.
*   Analysis of misclassifications revealed that the model sometimes confuses similar materials (e.g., cardboard and paper) and struggles with complex backgrounds or multiple objects.

## Files:

*   `recyclable_model.tflite`: The converted TFLite model.
*   `class_labels.json`: A JSON file containing the class labels corresponding to the model's output.

## How to use the TFLite model:

You can load and use the `recyclable_model.tflite` file on an edge device or in another application using the TensorFlow Lite interpreter. You will also need the `class_labels.json` file to map the model's output to the actual class names.

## 📝 Author
Prepared by Nelly for the PLP Academy – AI for Software Engineering Cohort (Feb 2025) Group 94(AI & Chill)

## 📬 Feedback & Collaboration
Feel free to connect for collaboration or feedback on how these insights might be applied to real-world AI workflows.