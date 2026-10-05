# 🤖 Deep Learning Learnings

This repository contains my hands-on **Deep Learning practice notebooks**. The notebooks introduce artificial neural networks, convolutional neural networks, and recurrent neural networks using TensorFlow and Keras.

## 📚 Notebooks

| # | Notebook | Type | Main Topics |
|---|---|---|---|
| 1 | 🧠 [ANN.ipynb](ANN.ipynb) | Binary classification | Dense neural network, feature scaling, SGD and momentum |
| 2 | 🖼️ [CNN.ipynb](CNN.ipynb) | Image classification | MNIST digits, dense network, convolutional neural network |
| 3 | 💬 [RNN.ipynb](RNN.ipynb) | Text classification | Tokenization, padding, embeddings, SimpleRNN, sentiment labels |

The notebooks are independent. A suggested learning order is **ANN → CNN → RNN**, moving from tabular inputs to images and then text sequences.

---

# 🧠 1. Artificial Neural Network (ANN)

## 📌 Overview

This notebook builds a small binary classifier to predict whether a plant needs watering. The example dataset is created directly in the notebook, so no external data file is needed.

## 📊 Example Data

The model uses three input features:

| Feature | Description |
|---|---|
| `soil_moist` | Soil moisture value |
| `temp_c` | Temperature in Celsius |
| `sun_hours` | Sunlight hours |
| `needs_water` | Binary target label |

The notebook scales the inputs with min-max normalization and uses a train-test split. It trains a dense network with a ReLU hidden layer and sigmoid output, then compares SGD with an SGD optimizer configured with momentum.

## 🤖 Model Setup

- Hidden layer: 8 units with ReLU activation
- Output layer: 1 unit with sigmoid activation
- Loss: binary cross-entropy
- Training: 100 epochs, batch size 4

Notebook: [ANN.ipynb](ANN.ipynb)

---

# 🖼️ 2. Convolutional Neural Network (CNN)

## 📌 Overview

This notebook classifies handwritten digits from the MNIST dataset. It prepares grayscale 28×28 images, normalizes pixel values, and compares a simple dense classifier, a deeper ANN, and a CNN.

## 📊 Dataset Files Required

The notebook expects two CSV files in the repository root:

```text
mnist_train.csv
mnist_test.csv
```

Each CSV must include a `label` column and 784 pixel columns. **These files are not currently included in the repository**, so add them before running this notebook. The notebook uses `label` as the target and reshapes the pixel columns into 28×28 images.

## 🤖 Models Compared

1. A single dense softmax classifier (named “perceptron” in the notebook)
2. A fully connected ANN with two hidden layers
3. A CNN with convolution, max-pooling, dropout, and dense layers

The notebook trains each model for five epochs, evaluates accuracy on the test data, and plots training and validation curves.

Notebook: [CNN.ipynb](CNN.ipynb)

---

# 💬 3. Recurrent Neural Network (RNN)

## 📌 Overview

This notebook demonstrates basic sentiment classification with a SimpleRNN. It uses a small set of positive and negative example sentences written directly in the notebook, so no external text dataset is needed.

## 🔄 Text Processing and Model

- Tokenize the sentences and convert them to integer sequences.
- Pad sequences to a common length.
- Map tokens to vectors with an embedding layer.
- Pass the sequence through a SimpleRNN and a sigmoid output layer.
- Train with binary cross-entropy for 25 epochs, using a batch size of 8.

The example contains 30 short sentences with binary sentiment labels. It is an introductory demonstration; it does not create a separate test set for evaluation.

Notebook: [RNN.ipynb](RNN.ipynb)

---

# 🛠️ Technologies Used

### Programming Language

- Python

### Libraries

- TensorFlow / Keras
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

### Deep Learning Concepts

- Dense neural networks
- Activation functions and loss functions
- Feature normalization
- Convolution and pooling
- Image classification
- Text tokenization and sequence padding
- Embeddings and recurrent layers
- Training and validation curves

---

# 📂 Repository Structure

```text
DL-learnings/
├── README.md
├── ANN.ipynb
├── CNN.ipynb
├── RNN.ipynb
├── mnist_train.csv  # required by CNN.ipynb; not included yet
└── mnist_test.csv   # required by CNN.ipynb; not included yet
```

> Add the MNIST CSV files only if their source permits redistribution. Keep them in the repository root, or update the paths in `CNN.ipynb` to match where you store them.

---

# 🚀 How to Run

## 1. Open the repository folder

Open a terminal in the repository root, where the notebooks are located.

## 2. Create and activate a virtual environment

Use a Python version supported by TensorFlow on your operating system. Check the [official TensorFlow installation guide](https://www.tensorflow.org/install/pip) for current Python and platform requirements.

```bash
python -m venv .venv
```

On Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

On macOS/Linux:

```bash
source .venv/bin/activate
```

## 3. Install dependencies

```bash
python -m pip install --upgrade pip
python -m pip install tensorflow numpy pandas matplotlib seaborn scikit-learn notebook
```

## 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open a notebook and run its cells from top to bottom. `ANN.ipynb` and `RNN.ipynb` use example data defined inside the notebooks. Before running `CNN.ipynb`, place `mnist_train.csv` and `mnist_test.csv` in the repository root.

---

# 🎯 Learning Objectives

Through these notebooks, I practiced:

- Building and training neural networks with Keras
- Scaling numeric features for a small classification example
- Comparing optimizers and momentum
- Preparing image data for dense and convolutional models
- Tokenizing and padding text sequences
- Using embedding and recurrent layers for sequence classification
- Inspecting model training and validation behavior

---

## 👨‍💻 Author

**Rajnikant**

Deep Learning Learner

---

⭐ These notebooks are part of my ongoing deep learning practice journey.
