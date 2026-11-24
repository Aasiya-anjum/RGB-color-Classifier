# RGB-color-Classifier
# RGB Color Object Classifier

## Project Overview

This beginner machine learning project classifies an image into one of three categories based on the dominant color of the object shown:

- Red
- Green
- Blue

The model was trained in Google Colab using labeled images organized into color folders.

## Dataset

The dataset contains **90 downloaded images** organized into three classes: `red`, `green`, and `blue`. Each image was placed in the folder matching the dominant color of its object.

## Method

1. Loaded the labeled images with OpenCV.
2. Resized each image to **64 × 64 pixels**.
3. Flattened the pixel values into a feature vector and normalized them by dividing by 255.
4. Split the data into **80% training** and **20% testing** sets, using stratification to preserve class balance.
5. Trained a **Linear Support Vector Machine (SVM)** classifier.
6. Evaluated the model using accuracy and a confusion matrix.
7. Saved the trained model with Joblib.

## Results

- Total images: **90**
- Training images: **72**
- Testing images: **18**
- Model: **Linear SVM**
- Test accuracy: **94.44%** (17 correct predictions out of 18)

### Confusion Matrix

Rows show the actual class. Columns show the model’s predicted class.

| Actual / Predicted | Red | Green | Blue |
|---|---:|---:|---:|
| Red | 5 | 1 | 0 |
| Green | 0 | 6 | 0 |
| Blue | 0 | 0 | 6 |

### Observations

- The model correctly classified all test images in the Green and Blue classes.
- One Red test image was predicted as Green.
- The test set contains 18 images, so the accuracy is an initial result and may change with more varied images.

## Project Files

- `RGB_Color_Classifier.ipynb` — Colab notebook containing the workflow and results.
- `rgb_object_classifier.pkl` — saved trained classifier.
- `README.md` — project overview and results.

## Limitations

This is a small image dataset. The model may make mistakes on images with different backgrounds, lighting, object sizes, or colors. A larger and more varied dataset would help evaluate it more reliably.

## Tools Used

- Python
- Google Colab
- OpenCV
- NumPy
- Scikit-learn
- Joblib
