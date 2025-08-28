# Detection of Chronic Heart Failure using Machine Learning and Deep Learning

This project presents a robust method for detecting Chronic Heart Failure (CHF) from heart sound recordings. [cite_start]It leverages a hybrid approach by combining classic Machine Learning (ML) techniques with end-to-end Deep Learning (DL) models to achieve high accuracy in classifying heart sounds as normal or abnormal[cite: 34, 111].

[cite_start]Chronic heart failure affects over 26 million people globally, and its early detection can significantly improve patient outcomes and reduce healthcare costs[cite: 43, 71, 74]. [cite_start]This system provides an automated tool to analyze phonocardiogram (PCG) signals, assisting physicians in diagnosing CHF, especially when expert cardiologists are not readily available[cite: 2].

## 📋 Table of Contents
- [Project Objective](#-project-objective)
- [Methodology](#-methodology)
- [Dataset](#-dataset)
- [System Modules](#-system-modules)
- [Results](#-results)
- [System Requirements](#-system-requirements)
- [How to Run](#-how-to-run)
- [Screenshots](#-screenshots)

## 🎯 Project Objective
[cite_start]The primary goal is to develop a highly accurate system for CHF detection using heart sounds[cite: 33, 110]. [cite_start]The project addresses the limitations of existing systems, which often suffer from lower accuracy[cite: 47, 223]. [cite_start]By combining the strengths of ML models trained on expert-selected features and DL models trained on raw audio data, this system aims to provide a reliable diagnostic aid[cite: 34, 35]. [cite_start]This can lead to easier identification of new CHF patients and the development of home-based monitoring tools to prevent hospitalizations[cite: 41, 118].

## ⚙️ Methodology
The core of this project is a hybrid model that processes heart sound data in parallel through two main pathways:

1.  **Classic Machine Learning (ML) Path**:
    * [cite_start]**Feature Extraction**: Systolic and diastolic features are extracted from the PCG signals found in `.dat` files[cite: 4, 5, 9, 10]. [cite_start]This is necessary because traditional ML algorithms cannot train on raw signal data directly[cite: 5].
    * [cite_start]**Model Training**: A Random Forest classifier is trained on these extracted and selected features[cite: 10, 628].

2.  **Deep Learning (DL) Path**:
    * [cite_start]**Raw Feature Processing**: The end-to-end DL model learns directly from a spectro-temporal representation of the raw heart sound recordings (`.wav` files)[cite: 5, 11, 35].
    * [cite_start]**Model Architecture**: The system uses a Convolutional Neural Network (CNN) to process the audio features[cite: 555, 557, 558].

3.  **Hybrid Recording Model**:
    * [cite_start]**Feature Aggregation**: Features are extracted and averaged from both the trained ML and DL models[cite: 2, 6].
    * [cite_start]**Final Classification**: A third classifier (Random Forest) is retrained on these aggregated features to produce the final prediction, which yields higher accuracy than either model alone[cite: 6, 12, 843]. [cite_start]The Average Aggregate Recording model consistently gives better accuracy compared to the other algorithms[cite: 3, 840].

## 📂 Dataset
[cite_start]The project utilizes a heart sound dataset from the **PHYSIONET website**[cite: 4, 841]. [cite_start]This dataset contains recordings from multiple subjects and includes three main file types for each entry[cite: 15, 845]:
* `.wav`: The raw heart sound audio recording.
* `.dat`: Contains the PCG signal data.
* `.hea`: A header file containing metadata, including the class label (Normal or Abnormal).

[cite_start]The pre-processing step identified a total of 405 PCG signals in the dataset, comprising 117 normal and 288 abnormal heart sounds[cite: 21, 851].

## 🛠️ System Modules
[cite_start]The application is structured into the following functional modules[cite: 7, 235]:

1.  [cite_start]**Upload Physionet Dataset**: Allows the user to load the dataset into the application[cite: 8, 236].
2.  [cite_start]**Dataset Preprocessing**: Extracts audio, systolic, and diastolic features from the dataset and normalizes the values[cite: 9, 237].
3.  [cite_start]**Run ML Segmented Model with FE & FS**: Trains the classic Random Forest model on systolic and diastolic features and evaluates its accuracy[cite: 10, 238].
4.  [cite_start]**Run DL Model on Raw Features**: Trains the DL model on raw audio features and calculates its performance[cite: 11, 239].
5.  [cite_start]**Run Recording ML Model**: Combines features from the ML and DL models and retrains a final classifier for improved accuracy[cite: 12, 240].
6.  [cite_start]**Predict CHF from Test Sound**: Allows the user to upload a new heart sound file to get a real-time prediction (Normal or Abnormal)[cite: 13, 241].

## 📈 Results
The models achieved the following accuracies during testing:
* [cite_start]**Classic ML Model (Random Forest)**: 90.12% accuracy[cite: 23, 853].
* [cite_start]**End-to-End DL Model**: 93.90% accuracy[cite: 24, 854].
* [cite_start]**Recording Feature Aggregate Model**: **96.34% accuracy**[cite: 25, 855].

[cite_start]The final aggregate model demonstrated the highest performance, confirming the effectiveness of the hybrid approach[cite: 26, 856].

## 💻 System Requirements

### [cite_start]Hardware Requirements[cite: 58, 414]:
* [cite_start]**Processor**: Intel i3 or above [cite: 59, 415]
* [cite_start]**Speed**: 1.1 GHz [cite: 60, 416]
* [cite_start]**RAM**: 4 GB (min) [cite: 61, 417]
* [cite_start]**Hard Disk**: 500 GB [cite: 62, 418]

### [cite_start]Software Requirements[cite: 66, 422]:
* [cite_start]**Operating System**: Windows 10 or above [cite: 67, 423]
* [cite_start]**Programming Language**: Python 3.7.0 [cite: 68, 264]
* **Key Libraries**:
    * [cite_start]Keras==2.3.1 [cite: 266]
    * [cite_start]Tensorflow==1.14.0 [cite: 267]
    * [cite_start]scikit-learn==0.22.2.post1 [cite: 271]
    * [cite_start]Pandas [cite: 273]
    * [cite_start]Numpy [cite: 272]
    * [cite_start]Matplotlib [cite: 543]
    * [cite_start]wfdb [cite: 549]

## 🚀 How to Run
To run the project, simply execute the `run.bat` file. [cite_start]This will launch the graphical user interface[cite: 17, 847].
```bash
double-click "run.bat"
```

## 🖼️ Screenshots

**Main Application Window**
![Main UI](https://i.imgur.com/uG9xOaR.png)

**Dataset Preprocessing and Analysis**
![Dataset Graph](https://i.imgur.com/1O6wL3e.png)

**Model Performance Comparison**
![Performance Graph](https://i.imgur.com/TIZtJ9y.png)

**Prediction on a Test Sound**
![Prediction Abnormal](https://i.imgur.com/N710rY8.png)
