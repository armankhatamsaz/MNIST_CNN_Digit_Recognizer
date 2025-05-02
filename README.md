# MNIST CNN Digit Recognizer

A Convolutional Neural Network (CNN) built with TensorFlow/Keras to classify handwritten digits from the popular MNIST dataset. This project demonstrates the basic workflow of building, training, and evaluating a CNN for image classification tasks, including integration with TensorBoard for monitoring.

## Features

*   Loads and preprocesses the MNIST dataset (`mnist.npz` handled internally by Keras).
*   Defines a standard CNN architecture using Keras Sequential API:
    *   Two Convolutional Layers (with ReLU activation)
    *   Two Max Pooling Layers
    *   A Flatten Layer
    *   Two Dense (Fully Connected) Layers (ReLU and Softmax activations)
*   Trains the model using the Adam optimizer and `sparse_categorical_crossentropy` loss.
*   Evaluates the model's accuracy on the test set.
*   Integrates TensorBoard for visualizing training metrics (loss, accuracy) in real-time.
*   Includes code to visualize a sample test image and its predicted label.

## Dataset

This project uses the MNIST handwritten digit dataset. The dataset consists of 60,000 training images and 10,000 testing images of size 28x28 pixels. The `tf.keras.datasets.mnist.load_data()` function is used to automatically download and load the data. The images are normalized to the [0, 1] range and reshaped to include a channel dimension (28, 28, 1) suitable for CNN input.

## Model Architecture

The CNN architecture is defined as follows:

1.  `Conv2D`: 32 filters, kernel size (3, 3), activation 'relu', input shape (28, 28, 1)
2.  `MaxPooling2D`: Pool size (2, 2)
3.  `Conv2D`: 64 filters, kernel size (3, 3), activation 'relu'
4.  `MaxPooling2D`: Pool size (2, 2)
5.  `Flatten`
6.  `Dense`: 128 units, activation 'relu'
7.  `Dense`: 10 units (for digits 0-9), activation 'softmax'

## Requirements

*   Python 3.x
*   TensorFlow >= 2.x
*   NumPy
*   Matplotlib

You can install the necessary libraries using pip:
```bash
pip install tensorflow numpy matplotlib


(TensorBoard is typically included with the TensorFlow installation).

## Usage

Clone the repository:

git clone https://github.com/armankhatamsaz/MNIST_CNN_Digit_Recognizer.git
cd MNIST_CNN_Digit_Recognizer

Run the Jupyter Notebook:
The primary file is MNIST_CNN_Digit_Recognizer.ipynb. You can run it using Jupyter Notebook or Jupyter Lab:

jupyter notebook MNIST_CNN_Digit_Recognizer.ipynb

Alternatively, you can upload and run the notebook directly in Google Colaboratory, which provides a free GPU environment suitable for training. The notebook includes Colab-specific commands (%tensorflow_version, %load_ext tensorboard, google.colab).

Training: Execute the cells in the notebook sequentially. The MNIST dataset will be downloaded automatically if not found locally. The model will train for 5 epochs by default.

Evaluation: After training, the model's accuracy on the test set will be printed.

Prediction Example: The code includes a cell to display test image #47 and print the model's prediction for it.

TensorBoard Integration

Training logs (loss and accuracy for training and validation sets) are saved to the logs/scalars/ directory, organized by timestamp.

To launch TensorBoard:

Open a terminal in the project's root directory (MNIST_CNN_Digit_Recognizer).

Run the following command:

tensorboard --logdir logs
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
Bash
IGNORE_WHEN_COPYING_END

Open your web browser and navigate to the URL provided by TensorBoard (usually http://localhost:6006).

You can monitor the training progress and analyze the metrics visually in TensorBoard.

Results

The CNN model typically achieves high accuracy (often >98%) on the MNIST test set after 5 epochs of training. Exact results may vary slightly depending on the specific run and hardware.
