# Visual Wake Word Detection

![Build Status](https://img.shields.io/badge/build-passing-brightgreen)
![License: MIT](https://img.shields.io/badge/license-MIT-blue)

---

## Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Directory Structure](#directory-structure)
- [Contribution Guidelines](#contribution-guidelines)
- [License](#license)
- [Credits](#credits)
- [Contact](#contact)

---

## Project Overview

**Visual Wake Word Detection** is an inclusive, real-time gesture recognition system that enables individuals—especially those with vocal impairments—to control smart home devices using finger gestures. The project leverages lightweight deep learning models (MobileNetV2) optimized for deployment on edge devices via TensorFlow Lite, making smart environments accessible and intuitive for everyone.

---

## Features

- **Gesture-Based Control:** Recognizes hand/finger gestures (0–5) for device interaction.
- **Edge Deployment:** Uses TinyML and TensorFlow Lite for real-time inference on low-power devices.
- **High Accuracy:** Achieves over 94% accuracy on test data.
- **Non-Verbal Accessibility:** Designed for users with speech or mobility limitations.
- **Portable & Scalable:** Easily extendable to healthcare, industrial, and smart home applications.

---

## Installation

1. **Clone the Repository**

```
git clone https://github.com/yourusername/visual-wake-word-detection.git
cd visual-wake-word-detection

```

2. **Install Dependencies**

```
pip install -r requirements.txt
```

_Key dependencies: TensorFlow, Keras, h5py, numpy, matplotlib, Pillow_

3. **Prepare Dataset**

- Place gesture image datasets in the `data/` directory as specified in the notebook.

4. **Run the Notebook**

- Launch `visual_wake_word_detection.ipynb` in Jupyter Notebook or compatible environment.

---

## Usage

### Training the Model

```
In visual_wake_word_detection.ipynb
Load and preprocess data
X_train, Y_train, X_test, Y_test, classes = load_dataset()

Train the model
history = model.fit(X_train, Y_train, epochs=50)

```

### Model Conversion for Edge Deployment

```
import tensorflow as tf
converter = tf.lite.TFLiteConverter.from_keras_model(model)
tflite_model = converter.convert()
with open("model.tflite", "wb") as f:
f.write(tflite_model)
```

### Running Inference

interpreter = tf.lite.Interpreter(model_path="model.tflite")
interpreter.allocate_tensors()

Prepare input image as shown in the notebook
Run inference and get predictions

---

## Directory Structure

```
visual-wake-word-detection/
│
├── data/ # Gesture image datasets (HDF5 files)
├── visual_wake_word_detection.ipynb # Main project notebook
├── model.tflite # Exported TFLite model
├── model_quantized.tflite # Quantized TFLite model
├── requirements.txt # Python dependencies
├── README.md # Project documentation
└── ... # Supporting scripts and assets
```

_See the notebook for detailed code and methodology._

---

## Contribution Guidelines

We welcome contributions! To contribute:

- Fork this repository.
- Create a new branch (`git checkout -b feature/your-feature`).
- Commit your changes and push to your fork.
- Submit a pull request with a clear description.

Please follow PEP8 style and add docstrings where appropriate.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Credits

- **Daksh Baweja** (2022UCA1810)
- **Archit Jain** (2022UCA1865)
- **Aditya Bhandari** (2022UCA1819)

Special thanks to the open-source community and referenced research on gesture recognition and TinyML.

---

## Contact

For questions, suggestions, or collaboration, please contact:

- Daksh Baweja: dakshbaweja.ug22@nsut.ac.in
- Archit Jain: architjain.ug22@nsut.ac.in
- Aditya Bhandari: adityabhandari.ug22@nsut.ac.in

---

> _“Making technology accessible, one gesture at a time.”_
