# MNIST Handwritten Digit Classifier
A Python project that decodes, visualizes, and classifies handwritten digits from the raw MNIST dataset.<br>
Includes custom loaders for IDX binary files and a feedforward neural network implementation from scratch.

Author: Timothy Johnson <br>
Date: April 2024

## Overview

&nbsp;&nbsp;&nbsp;&nbsp; This project demonstrates how to work with the MNIST handwritten digit dataset directly from raw binary files. It includes scripts for decoding and visualizing digits, preprocessing data into NumPy arrays, and training a simple neural network classifier.

&nbsp;&nbsp;&nbsp;&nbsp; The goal is to provide an educational introduction to dataset preprocessing, neural network training, and end-to-end digit classification.

🧩 Features

    🧾 Custom IDX parsers – Decode MNIST image (IDX3) and label (IDX1) binary formats.

    🖼️ Visualization – Convert digit images into grayscale PNGs using Pillow.

    🔢 One-hot encoding – Prepare label vectors for supervised training.

    🧮 Neural network implementation – From-scratch feedforward network with SGD.

    📚 Dataset loading – Load all training/test data into structured NumPy arrays.

🔄 User Workflow

    Download MNIST dataset files (train-images-idx3-ubyte, train-labels-idx1-ubyte)

    Run the Python script

      python train.py

    Evaluate or classify digits with:

      python run_model.py

    Visualize outputs and PNG reconstructions of digit samples.

📁 Code Structure

  src/ contains the main project pipeline: loaders, preprocessing, training, and inference.<br><br>
  prototypes/ includes standalone scripts for decoding MNIST data (images/labels) used as exploratory steps while building the main pipeline.<br>

.<br>
mnist-handwritten-digit-classifier/<br>
├── src/<br>
│   ├── load_mnist.py &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; Loads full MNIST dataset (images + labels) into NumPy arrays with one-hot encoding<br>
│   ├── load_mnist_labels.py &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; Extracts and saves label data from IDX1 files<br>
│   ├── loader.py &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; General data pipeline utilities (image decoding, one-hot labels, PNG saving)<br>
│   ├── mnist_loader.py &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; Combines image and label loaders into paired datasets<br>
│   ├── network.py &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; Feedforward neural network (bias/weight init, SGD, backprop placeholders)<br>
│   ├── train.py &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; Main training script, runs SGD on MNIST and saves trained model<br>
│   ├── run_model.py &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; Loads trained model and classifies sample digits, saving them as PNGs<br>
│   ├── mnist.ipynb &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; Interactive notebook for visualization and dataset exploration<br>
│   ├── train-images-idx3-ubyte &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; Raw MNIST training images (60k samples)<br>
│   ├── train-labels-idx1-ubyte &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; Raw MNIST training labels<br>
│   ├── t10k-images-idx3-ubyte &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; Raw MNIST test images (10k samples)<br>
│   └── t10k-labels-idx1-ubyte &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; Raw MNIST test labels<br>
├── prototypes/<br>
│   ├── load_images.py &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; Standalone script to decode MNIST image files and export them as PNGs<br>
│   ├── load_labels.py &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; Standalone script to decode MNIST label files and save as ASCII text<br>
│   └── network.py &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; Alternate implementation of the neural network class<br>

⚙️ How It Works

🧱 Binary Decoding

    Parses IDX headers for image count, width, and height.

    Reads pixel values, reshapes into 28×28 arrays, and saves to PNG.

🔢 Label Extraction

    Reads individual byte values from the IDX1 label file

    Converts integers to one-hot vectors.

    Pairs images with labels into datasets.

🧮 Neural Network

    Implemented in network.py.

    Includes weight/bias initialization, feedforward pass, and training with SGD.

    Supports loading/saving models for evaluation (run_model.py).

📦 Full Dataset Loading

    load_all_training_images() reads all images into a NumPy array of shape [60000, 784, 1]

    Data type: np.ubyte (8-bit grayscale)

🖼️ Screenshots / Visuals

![mnist](https://github.com/user-attachments/assets/f75cb907-97d8-4a77-a4ea-82d79b2d5f26)

🧰 Technologies Used

    🐍 Python --- Core programming language
    
    🧮 NumPy --- Numerical operations and array storage
    
    🖼️ Pillow (PIL) --- Image decoding and saving

    📓 Jupyter --- Interactive visualization and dataset exploration
    
    🗃️ File I/O ---	Low-level binary file reading of IDX format

🚀 Getting Started

    git clone https://github.com/MrTimmyJ/MNIST-Handwritten-Digit-Classifier.git
    cd MNIST-Handwritten-Digit-Classifier

    # Download MNIST dataset files
    # https://yann.lecun.com/exdb/mnist/

    pip install pillow numpy

      python train.py

      python run_model.py

    ⚠️ Requires Python 3, Pillow, and NumPy

🪪 License

This open-source project is available under the [MIT License](https://opensource.org/license/mit).
