# 🧠 EEG Classification Using Normalized Compression Distance (NCD)

This repository contains the full implementation and documentation for our final capstone project:
**"EEG Classification for ADHD Diagnosis Using Text Compression."**

Instead of using traditional machine learning models, we explore a feature-free, interpretable approach by comparing EEG signal structures using the **Normalized Compression Distance (NCD)** and the **BZ2 (ZB2) compression algorithm**.

---

## 📌 Poster Presentation

📄 Click the image below to view the full project poster:  
[![Project Poster](https://raw.githubusercontent.com/mhmdkh1905/EEG-classifaction-using-text-compression/main/assets/PosterPreview.jpg)](https://raw.githubusercontent.com/mhmdkh1905/EEG-classifaction-using-text-compression/main/PhaseB/Poster.pdf)

> 📎 The poster summarizes the full pipeline: preprocessing, segmentation, transformation, compression, classification, and evaluation.  
> It presents key findings, including best-performing methods and accuracy insights.

---

## 🧠 Project Summary

- **Goal**: Classify EEG signals from children with and without ADHD using compression-based similarity instead of machine learning.
- **Data**: EEG recordings from 121 participants (61 ADHD, 60 Control) over 19 channels.
- **Method**:
  - Bandpass filter EEG (1–40 Hz)
  - Extract dominant frequency regions using sliding windows (2s–10s)
  - Convert regions to symbolic sequences
  - Compute pairwise NCD between all participants using 1000-character chunks
  - Aggregate similarity scores using **min**, **avg**, and **median**
  - Classify participants based on NCD thresholds

---

## ⚙️ How It Works

### 🧪 Preprocessing
- Filter EEG recordings from `/adhdcsv/` and `/controlcsv/`
- Save cleaned signals to `/filteredadhdcsv/` and `/filteredcontrolcsv/`

### 🧠 Feature Extraction
- Segment signals into symbolic representations
- Store results in `/brainwave_sequence_2s/`, `/5s/`, etc.

### 🔁 NCD Similarity Calculation
- Compute NCD values using `zlib` (ZB2)
- Results saved under `/parts_ncd_Xs/`

### 📊 Classification
- Compute min, avg, and median NCDs for each participant
- Use median to classify group similarity
- Final scores saved to `/classification_based_on_median/`

---

---

## 📌 Insights

- Shorter windows (2s) yielded more frequent high scores.
- The **average** method gave the best per-participant accuracy in several cases.
- NCD offered an interpretable and reproducible way to distinguish ADHD from control participants.
- No machine learning or AI needed — pure signal structure and statistical reasoning.

---

## 👥 Authors

- **Mohammad Khateeb**  
- **Jad Taha**  
Supervised by: *Dr. Samah Idres Ghazawy, Dr. Anat Dahan*

---

## 📬 Contact

Feel free to contact us for collaborations or questions:

- ✉️ mhmd52kh@gmail.com
- 🔗 [LinkedIn](https://www.linkedin.com/in/mohammad-khateeb-891332303/)
- 💻 [GitHub](https://github.com/mhmdkh1905)

---

## 📄 License

This project is academic and open for research purposes only. Please cite appropriately if reused.



