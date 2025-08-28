# Detection of Chronic Heart Failure using Machine Learning and Deep Learning

This project presents a robust method for detecting Chronic Heart Failure (CHF) from heart sound recordings. It leverages a hybrid approach combining classic Machine Learning (ML) techniques with end-to-end Deep Learning (DL) models to achieve high accuracy in classifying heart sounds as normal or abnormal.

Chronic heart failure affects over 26 million people globally, with its incidence increasing by 2% annually. Early detection can significantly improve patient outcomes and reduce healthcare costs. This system provides an automated tool to analyze phonocardiogram (PCG) signals, assisting physicians in diagnosing CHF, especially when expert cardiologists are unavailable.

## 🎯 Project Objective

The primary goal is to develop a highly accurate system for CHF detection using heart sounds. By addressing the limitations of existing systems, which often suffer from lower accuracy, this project combines the strengths of ML models trained on expert-selected features and DL models trained on raw audio data. The system aims to facilitate easier identification of new CHF patients and support the development of home-based monitoring tools to prevent hospitalizations.

## ⚙️ Methodology

The project employs a hybrid model that processes heart sound data through two main pathways:

1\. **Classic Machine Learning (ML) Path**:

   - **Feature Extraction**: Systolic and diastolic features are extracted from PCG signals (`.dat` files), as traditional ML algorithms cannot train directly on raw signal data.

   - **Model Training**: A Random Forest classifier is trained on these extracted and selected features.

2\. **Deep Learning (DL) Path**:

   - **Raw Feature Processing**: The end-to-end DL model learns directly from a spectro-temporal representation of raw heart sound recordings (`.wav` files).

   - **Model Architecture**: Utilizes a Convolutional Neural Network (CNN) to process audio features.

3\. **Hybrid Recording Model**:

   - **Feature Aggregation**: Features from both trained ML and DL models are extracted and averaged.

   - **Final Classification**: A third Random Forest classifier is trained on these aggregated features, yielding higher accuracy than either model alone. The Average Aggregate Recording model consistently outperforms other algorithms.

## 📂 Dataset

The project uses a heart sound dataset from the [PhysioNet website](https://physionet.org/content/challenge-2016/1.0.0/). The dataset includes recordings from 405 subjects, with 117 normal and 288 abnormal heart sounds, comprising three file types per entry:

- `.wav`: Raw heart sound audio recording.

- `.dat`: PCG signal data.

- `.hea`: Header file with metadata, including class labels (Normal or Abnormal).

**Note**: Download the dataset from PhysioNet and place it in a folder named `Dataset` within the project directory for the application to load it correctly.

## 🛠️ System Modules

The application is structured into the following functional modules:

1\. **Upload Physionet Dataset**: Loads the dataset into the application.

2\. **Dataset Preprocessing**: Extracts audio, systolic, and diastolic features from the dataset and normalizes values.

3\. **Run ML Segmented Model with FE & FS**: Trains the Random Forest model on systolic and diastolic features and evaluates accuracy.

4\. **Run DL Model on Raw Features**: Trains the DL model on raw audio features and calculates performance.

5\. **Run Recording ML Model**: Combines features from ML and DL models, retrains a final classifier for improved accuracy.

6\. **Predict CHF from Test Sound**: Allows users to upload a heart sound file (e.g., `.wav`) to predict whether it is Normal or Abnormal.

## 📈 Results

The models achieved the following accuracies during testing:

- **Classic ML Model (Random Forest)**: 90.12% accuracy.

- **End-to-End DL Model**: 93.90% accuracy.

- **Recording Feature Aggregate Model**: 96.34% accuracy.

The hybrid model demonstrated superior performance, confirming the effectiveness of combining ML and DL approaches.

## 💻 System Requirements

### Hardware Requirements

- **Processor**: Intel i3 or above

- **Speed**: 1.1 GHz

- **RAM**: 4 GB (minimum)

- **Hard Disk**: 500 GB (minimum)

### Software Requirements

- **Operating System**: Windows 10 or above

- **Programming Language**: Python 3.7.0

- **Key Libraries** (specified in `requirements.txt`):

  - Keras==2.3.1

  - Tensorflow==1.14.0

  - scikit-learn==0.22.2.post1

  - pandas

  - numpy

  - matplotlib

  - wfdb

## 🛠️ Installation

1\. **Install Python**:

   - Download and install Python 3.7.0 from the [official Python website](https://www.python.org/downloads/release/python-370/).

   - Ensure Python is added to your system's PATH during installation.

2\. **Clone the Repository**:

   ```bash

   git clone https://github.com/Athiya-Farhanaz/Chronic-Heart-Failure.git

   cd Chronic-Heart-Failure
1.  **Set Up a Virtual Environment** (Recommended):

    bash

    `

    python -m venv venv

    .\venv\Scripts\activate # On Windows

    # source venv/bin/activate # On macOS/Linux

    `

2.  **Install Dependencies**:
    -   Use the provided requirements.txt file to install all necessary libraries:

        bash

        `

        pip install -r requirements.txt

        `

3.  **Download the Dataset**:
    -   Download the heart sound dataset from [PhysioNet](https://physionet.org/content/challenge-2016/1.0.0/).
    -   Extract and place it in a folder named Dataset inside the project directory.

**Note**: Due to the use of older versions of TensorFlow (1.14.0) and Keras (2.3.1), ensure compatibility with Python 3.7.0. If you encounter issues, consider using a dedicated virtual environment to avoid conflicts with newer library versions.

🚀 How to Run
-------------

1.  **Launch the Application**:
    -   Double-click the run.bat file in the project directory to start the graphical user interface (GUI).
2.  **Using the GUI**:
    -   **Upload Physionet Dataset**: Click to load the Dataset folder containing the PhysioNet data.
    -   **Dataset Preprocessing**: Extract and normalize features from the dataset.
    -   **Run ML Segmented Model with FE & FS**: Train and evaluate the Random Forest model.
    -   **Run DL Model on Raw Features**: Train and evaluate the DL model.
    -   **Run Recording ML Model**: Combine features and train the final classifier.
    -   **Predict CHF from Test Sound**: Upload a .wav file (e.g., 1.wav or 2.wav) to predict Normal or Abnormal.

🖼️ Screenshots
---------------

### Main Application Window

<img src="./media/image18.png" alt="Main UI">

### Dataset Preprocessing and Analysis

<img src="./media/image21.png" alt="Dataset Graph">

### Model Performance Comparison

<img src="./media/image25.png" alt="Performance Graph">

### Prediction on a Test Sound (Abnormal)

<img src="./media/image27.png" alt="Prediction Abnormal">

📚 References
-------------

1.  Gjoreski et al., "Chronic heart failure detection from heart sounds using a stack of machine-learning classifiers," 2017 International Conference on Intelligent Environments (IE), 2017.
2.  Clifford et al., "Classification of normal/abnormal heart sound recordings: the PhysioNet/Computing in Cardiology Challenge 2016," 2016 Computing in Cardiology Conference (CinC), 2016.
3.  Jiang et al., "Speed up deep neural network based pedestrian detection by sharing features across multi-scale models," Neurocomputing, 2016.
4.  Krizhevsky et al., "ImageNet classification with deep convolutional neural networks," International Conference on Neural Information Processing Systems, 2012.
5.  Szegedy et al., "Inception-v4, inception-ResNet and the impact of residual connections on learning," Thirty-First AAAI Conference on Artificial Intelligence, 2017.

For a complete list of references, refer to the project documentation files.

📝 License
----------

This project is licensed under the MIT License - see the LICENSE file for details.

👥 Contributors
---------------

-   **Athiya Farhanaz** (Main Developer)

🙌 Contributing
---------------

Contributions are welcome! Please fork the repository and submit a pull request with your changes. For major changes, open an issue first to discuss what you would like to change.

If you find this project useful, please give it a ⭐ on GitHub! For issues or questions, feel free to open an issue on the repository.
