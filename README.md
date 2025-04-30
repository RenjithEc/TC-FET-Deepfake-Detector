# TC-FET-Deepfake-Detection
# Detecting Deep-Fake from Temporal Consistency of Facial Expression Transitions

This repository contains code, data, and documentation for the project **Detecting Deep-Fake from Temporal Consistency of Facial Expression Transitions**. The main goal of this work is to leverage spatial and temporal features—optical flow and edge maps—combined with CNN and BiLSTM + Attention to improve deepfake detection robustness.

---

## 📁 Repository Layout

```
TC-FET-DEEPFAKE-DETECTOR
│   .gitignore
│   file_list.txt
│   folder-structure.txt
│   README.md
│
├── 0exp_setups/                  Experiment setups for the “Angry” expression subset
│   ├── angry_dataset_real_fake.csv
│   ├── angry_dataset_real_fake_filtered.csv
│   ├── angry_expression_model_best.pth
│   ├── angry_feature_cnn.ipynb
│   ├── angry_experiment2/
│   │   ├── angry_dataset_real_fake_filtered.csv
│   │   ├── angry_expression_model_best.h5
│   │   ├── cnn.ipynb
│   │   └── output/               Training logs and plots (confusion, ROC, PR)
│   ├── angry_experiment3/        Additional CNN experiments
│   ├── angry_lightuniform_front_cnn/
│   │   └── fix_output/           Overfit fixes and final model output
│   ├── fake_cnn/                 CNN on fake-only preprocessing
│   ├── lstm_exp1/                Initial LSTM experiments split into parts
│   ├── lstm_exp2/                BiLSTM baseline (no attention)
│   ├── lstm_exp3/                BiLSTM (v3)
│   ├── lstm_exp5/                Latest BiLSTM + attention (v5)
│   ├── lst_exp4/                 Improved BiLSTM with regularization
│   ├── manipulated_data_prep/    Notebooks for creating manipulated frames/flows
│   └── source_data_prep/         Notebooks for raw frame/flow extraction
│
├── 1preprocessing/               Preprocessing and .npz dataset creation notebooks
│   ├── fake_preprocessing.ipynb
│   ├── npz*.ipynb                Scripts for each emotion and combined data
│   ├── preprocessing.ipynb
│   └── shape_predictor_68_face_landmarks.dat
│
├── angry/                        Final angry-expression model & notebook
│   └── bilstemexp5.ipynb
├── contempt/                     Final contempt-expression model & notebook
├── disgust/                      Final disgust-expression model & notebook
├── fear/                         Final fear-expression model & notebook
├── happy/                        Final happy-expression model & notebook
├── neutral/                      Final neutral-expression model & notebook
├── sad/                          Final sad-expression model & notebook
└── surprise/                     Final surprise-expression model & notebook
```

> **NOTE:** Each top-level emotion directory (`angry/`, `contempt/`, etc.) contains the final best model (`.h5`) and the corresponding `bilstemexp5.ipynb` training notebook.

---

## 🛠️ Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/RenjithEc/TC-FET-Deepfake-Detector.git
   cd TC-FET-Deepfake-Detector
   ```

2. Create and activate a virtual environment:
   ```bash
   python3 -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   ```


---

## 🚀 Usage

1. **Preprocessing**  
   Run the **preprocessing.ipynb** notebook to extract face crops, optical flow, and edge maps from raw videos.  

2. **Data Integration**  
   Use **npz_combined.ipynb** to batch-process images into a compressed `.npz` dataset with 9‑channel inputs (RGB + Flow + Edge).  

3. **Model Training & Evaluation**  
   - **bilstemexp5.ipynb** contains code for training and evaluating BiLSTM variants.  
   - Modify hyperparameters directly in the notebooks as needed.  


---

## 🤝 Contributing

Contributions are welcome! Please open an issue or submit a pull request to suggest improvements, report bugs, or add new experiments.

---










