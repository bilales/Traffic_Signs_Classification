# Traffic Sign Classification using Deep Learning

A project by Azdad Bilal, Ourkia Abdelhakim, and Sarhane Abdelmouhaimen.

## 📖 Overview

This project implements a deep learning model for the classification of traffic signs. A Convolutional Neural Network (CNN) is built from scratch using TensorFlow and Keras to classify images into five distinct categories of traffic signs: **stop**, **crosswalk**, **speed limit**, **traffic light**, and **no-entry**.

The project encompasses the entire machine learning pipeline, from data collection via web scraping to model training, evaluation, and data augmentation.

---
## ✨ Features

* **Web Scraping for Data Collection**: A Python script (`web_scraping.py`) is included to gather image data from Google Images using Selenium and BeautifulSoup.
* **Data Cleaning**: A utility script (`delete_small_images.py`) is provided to preprocess the dataset by removing images smaller than a 50x50 pixel threshold.
* **Custom CNN Architecture**: The core of the project is a custom-built CNN designed for image classification, featuring multiple convolutional and max-pooling layers.
* **Data Augmentation**: To prevent overfitting and improve model generalization, the training process utilizes `ImageDataGenerator` for real-time data augmentation, creating variations of the training images (rotation, shifts, zoom, etc.).
* **Model Evaluation**: The model's performance is tracked during training by monitoring accuracy and loss on both the training and validation sets, with visualizations provided by `matplotlib`.

---
## ⚙️ How It Works

The project is structured into several key stages:

1.  **Data Collection**: The `web_scraping.py` script automates the process of searching and downloading images for the specified traffic sign classes.
2.  **Data Preparation**:
    * The downloaded dataset is cleaned using `delete_small_images.py` to ensure a minimum image quality and size.
    * The main notebook, `projet_deep_learning.ipynb`, loads the data from a GitHub repository, resizes all images to 64x64 pixels, and splits them into training, validation, and test sets.
3.  **Model Architecture**: A sequential CNN model is defined in TensorFlow/Keras. It consists of:
    * Four `Conv2D` layers with increasing filters (32, 64, 96, 128) and ReLU activation.
    * `MaxPooling2D` layers after each convolution to reduce dimensionality.
    * A `Flatten` layer to transition from 2D feature maps to a 1D vector.
    * A `Dense` layer with 512 neurons and ReLU activation.
    * A final `Dense` output layer with 5 neurons and a `softmax` activation function for multi-class classification.
4.  **Training and Evaluation**:
    * The model is compiled with the 'adam' optimizer and 'sparse_categorical_crossentropy' loss function.
    * The `ImageDataGenerator` is used on the training data to introduce augmented images during the training loop, which runs for 20 epochs.
    * Training and validation accuracy/loss are plotted to visualize the model's learning progress.

---
## 🚀 Getting Started

### Prerequisites

To run this project, you will need Python 3 and the following libraries:

* TensorFlow
* scikit-learn
* NumPy
* Matplotlib
* Pillow (PIL)
* SciPy
* Selenium
* BeautifulSoup4

You can install them using pip:
```bash
pip install tensorflow scikit-learn numpy matplotlib pillow scipy selenium beautifulsoup4
```

## Usage

1.  **Clone the Data Repository**: The first step in the `projet_deep_learning.ipynb` and `chargement_donnees.ipynb` notebooks is to clone the data.

2.  **Run the Jupyter Notebook**: Open and run the `projet_deep_learning.ipynb` notebook. This will handle data loading, model creation, training, and evaluation.

3.  **(Optional) Collect Your Own Data**: You can run the `web_scraping.py` script to create your own dataset. Note that you will need to have chromedriver installed and configured for Selenium to work.

## 🤝 Contributing

Contributions are welcome! If you'd like to contribute to this project, please follow these steps:

1.  Fork the repository.

2.  Create a new branch (`git checkout -b feature/your-feature`).

3.  Make your changes.

4.  Commit your changes (`git commit -m 'Add some feature`).

5.  Push to the branch (`git push origin feature/your-feature`).

6.  Open a Pull Request.

## 📜 License
This project is licensed under the MIT License.
