# 🫀 Detection of Chronic Heart Failure using Machine Learning and Deep Learning

This project presents a robust method for detecting **Chronic Heart Failure (CHF)** from heart sound recordings. It leverages a **hybrid approach** combining classic Machine Learning (ML) techniques with end-to-end Deep Learning (DL) models to achieve high accuracy in classifying heart sounds as normal or abnormal.

Chronic heart failure affects over **26 million people globally**, with its incidence increasing by 2% annually. Early detection can significantly improve patient outcomes and reduce healthcare costs. This system provides an **automated tool** to analyze phonocardiogram (PCG) signals, assisting physicians in diagnosing CHF—especially when expert cardiologists are unavailable.

---

## 🎯 Project Objective

The primary goal is to develop a **highly accurate system for CHF detection** using heart sounds.  
By addressing the limitations of existing systems (often lower accuracy), this project combines the strengths of **ML models trained on expert-selected features** and **DL models trained on raw audio data**.

The system aims to:
- Facilitate easier identification of new CHF patients.
- Support development of **home-based monitoring tools** to prevent hospitalizations.

---

## ⚙️ Methodology

The project employs a **hybrid model** that processes heart sound data through two main pathways:

### 1. Classic Machine Learning (ML) Path
- **Feature Extraction**: Systolic and diastolic features are extracted from PCG signals (`.dat` files).  
- **Model Training**: A **Random Forest classifier** is trained on these extracted and selected features.

### 2. Deep Learning (DL) Path
- **Raw Feature Processing**: The DL model learns directly from **spectro-temporal representations** of raw heart sound recordings (`.wav` files).  
- **Model Architecture**: A **Convolutional Neural Network (CNN)** processes the audio features.

### 3. Hybrid Recording Model
- **Feature Aggregation**: Features from both trained ML and DL models are extracted and averaged.  
- **Final Classification**: A third **Random Forest classifier** is trained on these aggregated features, yielding higher accuracy.  
- ✅ The **Average Aggregate Recording model** consistently outperforms other algorithms.

---

## 📂 Dataset

The project uses the **PhysioNet 2016 heart sound dataset** ([link](https://physionet.org/content/challenge-2016/1.0.0/)).

- Subjects: **405**
  - 117 Normal
  - 288 Abnormal  
- Each subject includes:
  - `.wav`: Raw heart sound audio recording  
  - `.dat`: PCG signal data  
  - `.hea`: Header file with metadata (including class labels: Normal/Abnormal)

> ⚠️ **Note**: Download the dataset from PhysioNet and place it in a folder named `Dataset` inside the project directory.

---

## 🛠️ System Modules

1. **Upload Physionet Dataset** – Loads the dataset into the application.  
2. **Dataset Preprocessing** – Extracts audio, systolic, and diastolic features, and normalizes values.  
3. **Run ML Segmented Model with FE & FS** – Trains Random Forest on extracted features and evaluates accuracy.  
4. **Run DL Model on Raw Features** – Trains CNN on spectrogram-based features and calculates performance.  
5. **Run Recording ML Model** – Combines ML and DL features, retrains classifier for improved accuracy.  
6. **Predict CHF from Test Sound** – Upload a `.wav` file (e.g., `1.wav` or `2.wav`) to predict Normal or Abnormal.

---

## 📈 Results

| Model                                | Accuracy   |
|--------------------------------------|------------|
| **Classic ML (Random Forest)**       | 90.12%     |
| **End-to-End DL Model (CNN)**        | 93.90%     |
| **Hybrid Recording Model**           | **96.34%** |

✅ The **hybrid model** demonstrated **superior performance**, confirming the effectiveness of combining ML and DL.

---

## 💻 System Requirements

### Hardware
- **Processor**: Intel i3 or above  
- **Speed**: 1.1 GHz  
- **RAM**: 4 GB (minimum)  
- **Disk**: 500 GB (minimum)  

### Software
- **OS**: Windows 10 or above  
- **Programming Language**: Python 3.7.0  
- **Key Libraries** (from `requirements.txt`):  
  - `Keras==2.3.1`  
  - `Tensorflow==1.14.0`  
  - `scikit-learn==0.22.2.post1`  
  - `pandas`, `numpy`, `matplotlib`, `wfdb`  

---

## 🛠️ Installation

### 1. Install Python
- Download and install Python 3.7.0 from [python.org](https://www.python.org/downloads/release/python-370/).  
- Ensure Python is added to **PATH** during installation.

### 2. Clone the Repository
```bash
git clone https://github.com/Athiya-Farhanaz/Chronic-Heart-Failure.git
cd Chronic-Heart-Failure
```

### 3. Create and Activate Virtual Environment
```bash
# Create virtual environment
python -m venv venv

# Activate on Windows
.\venv\Scripts\activate

# Activate on macOS/Linux
source venv/bin/activate
```

### 4. Install Dependencies
```bash
pip install -r requirements.txt
```

### 5. Download the Dataset
- Download the heart sound dataset from [PhysioNet](https://physionet.org/content/challenge-2016/1.0.0/).  
- Extract and place it inside a folder named **`Dataset`** in the project directory.

> ⚠️ Due to the use of older TensorFlow (1.14.0) and Keras (2.3.1), ensure compatibility with **Python 3.7.0**.  
> It’s recommended to use a dedicated virtual environment to avoid conflicts with newer versions.

---

## 🚀 How to Run

1. **Launch the Application**:  
   Double-click the `run.bat` file in the project directory to start the **GUI**.

2. **Using the GUI**:  
   - **Upload Physionet Dataset**  
   - **Dataset Preprocessing**  
   - **Run ML Segmented Model with FE & FS**  
   - **Run DL Model on Raw Features**  
   - **Run Recording ML Model**  
   - **Predict CHF from Test Sound**

---

## 📝 License
This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

---

## 👥 Contributors
- **Athiya Farhanaz** (Main Developer)

---

## 🙌 Contributing
Contributions are welcome!  

- Fork the repo, create a branch, and submit a PR with your changes.  
- For major changes, open an issue to discuss them first.  

If you find this project useful, please ⭐ it on GitHub!  
For issues or questions, feel free to open an **Issue**.

---
