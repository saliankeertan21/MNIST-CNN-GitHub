# Handwritten Digit Recognition with a CNN

An introductory deep-learning portfolio project that classifies handwritten digits 0–9 with a convolutional neural network (CNN) trained on MNIST.

## Reported results

| Model | MNIST test accuracy |
|---|---:|
| Dense neural network | 97.26% |
| Dense + Dropout | 97.73% |
| Dense + Dropout + Early Stopping | 98.10% |
| CNN | **99.03%** |

The CNN incorrectly classified **97 of 10,000 test images**. The most frequently confused direction was **actual 9 predicted as 4** (count not yet recorded). Results are from one training run and may differ upon retraining.

## Model architecture

- Input: grayscale 28×28 image
- Conv2D(32, 3×3), ReLU; MaxPooling2D(2×2)
- Conv2D(64, 3×3), ReLU; MaxPooling2D(2×2)
- Flatten; Dense(64), ReLU; Dropout(0.2)
- Dense(10), Softmax

The architecture has **121,930 trainable parameters**.


**Note:** `mnist_cnn.keras` is not included in this starter package. You must supply your trained model. The app has not been tested against your individual trained weights.

## Method and evaluation

Input pixel values were scaled to [0, 1]. The CNN was trained using Adam, sparse categorical crossentropy, 64-image batches, up to 15 epochs, and EarlyStopping on validation loss with patience 3. Training stopped after 9 epochs. Model selection should use validation data; keep the test set reserved for final reporting.

The demo crops, resizes, centers, and normalizes sketches before predicting. Hand-drawn browser inputs can differ from MNIST images (distribution shift), so demo accuracy may be lower than the reported MNIST test accuracy.


## Learning topics

Dense layers, convolutional filters, ReLU, pooling, Softmax, Dropout, Early Stopping, feature maps, confusion matrices, preprocessing
