# MNIST-Handwritten-Digit-Classifier
A Python tool that decodes, visualizes, and processes raw MNIST dataset files to identify handwritten numbers.

Author: Timothy Johnson <br>
Date: April 2024

## Overview

&nbsp;&nbsp;&nbsp;&nbsp;MNIST Image Decoder is a Python script that loads and visualizes the MNIST handwritten digits dataset directly from the original binary files.
It provides a simple interface for decoding, reshaping, and displaying grayscale images using NumPy and Pillow, offering a foundational introduction to preprocessing deep learning datasets from raw formats.
It provides a simple interface to decode, reshape, and display the grayscale images using NumPy and Pillow, offering a foundational introduction to how deep learning datasets are preprocessed from raw formats.

🧩 Features

    🧾 Parses IDX3/IDX1 binary formats from the MNIST dataset

    🖼️ Converts image data into grayscale PNGs using PIL

    🔢 One-hot encodes label data for training models

    📚 Loads the full dataset into structured NumPy arrays

    💡 Designed for educational purposes in ML, DL, and data engineering

🔄 User Workflow

    Download MNIST dataset files (train-images-idx3-ubyte, train-labels-idx1-ubyte)

    Run the Python script (python mnist_decoder.py)

    Reconstructed grayscale images are saved as PNG files

    Explore how the binary data maps to image matrices and label vectors

⚙️ How It Works

🧱 Binary Decoding

    Parses the header of the IDX3 file to extract image count, width, and height

    Reads each image as a flattened array of grayscale pixel values

    Reshapes to (28x28) and visualizes with PIL.Image

🔢 Label Extraction

    Reads individual byte values from the IDX1 label file

    Converts labels to one-hot encoded vectors

    Pairs image and label data for training sets

📦 Full Dataset Loading

    load_all_training_images() reads all images into a NumPy array of shape [60000, 784, 1]

    Data type: np.ubyte (8-bit grayscale)

🖼️ Screenshots / Visuals

![mnist](https://github.com/user-attachments/assets/f75cb907-97d8-4a77-a4ea-82d79b2d5f26)

🧰 Technologies Used

    🐍 Python --- Programming language
    
    🖼️ Pillow --- Image processing and PNG saving
    
    🧮 NumPy --- Efficient numerical array manipulation
    
    🗃️ File I/O ---	Low-level binary file reading of IDX format

🚀 Getting Started

    git clone https://github.com/yourusername/mnist-decoder.git
    cd mnist-decoder

    # Download MNIST dataset files
    # https://yann.lecun.com/exdb/mnist/

    python mnist_decoder.py

    pip install pillow numpy

      ⚠️ Requires Python 3, Pillow, and NumPy

🌱 Upcoming Features

    💾 Save generated maps to file

    🗂️ Switch between address schemes (Olympia, Tokyo, etc.)

    🏙️ Add buildings, zoning, and population simulation

    📏 Customizable city size and road density

    🧠 Smarter intersection logic for address naming

🪪 License

This open-source project is available under the [MIT License](https://opensource.org/license/mit).
