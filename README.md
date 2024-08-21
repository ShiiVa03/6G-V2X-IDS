# Misbehavior Detection System for V2X Networks

## Overview

This project is part of a dissertation titled **"Intrusion Detection Systems in 6G Vehicle-to-Everything environments"**, which was graded 19/20. The dissertation addresses the emerging challenges in Vehicle-to-Everything (V2X) communications, especially the security vulnerabilities that accompany advancements in 6G networks. The objective of this dissertation was to develop a mechanism to detect these vulnerabilities using AI and ML tools.

### Background

Recent advancements in V2X communications have significantly improved transportation systems by increasing connectivity and driving autonomy levels. However, these benefits also introduce new security challenges and vulnerabilities. Traditional security solutions may not suffice in combating these types of threats, making the use of AI/ML essential for intrusion detection in V2X environments.

This dissertation proposes a two-stage architecture for anomaly detection:
1. **First Stage**: Utilizes a deep learning model, such as an LSTM Autoencoder or CNN-LSTM, to reconstruct Basic Safety Message (BSM) sequences and calculate reconstruction errors, which are used as anomaly scores.
2. **Second Stage**: A supervised deep learning model is trained on the labeled data generated by the first stage to refine the classification of genuine and anomalous BSM sequences.

The approach was validated using three different unsupervised DNN models for the first stage and two supervised DNN models for the second stage. The results demonstrated the framework's effectiveness in identifying anomalies, including unknown ones, based on reconstruction errors. The best-performing model outperformed existing frameworks in terms of key evaluation metrics and was lightweight enough for resource-constrained environments.

### Publications

This dissertation also resulted in two research papers:

1. **Securing V2X Communication: A Hybrid Deep Learning Approach for Misbehavior Detection**
   - **Abstract**: This paper proposes a hybrid deep learning approach for misbehavior detection in 6G V2X communication. The approach utilizes a two-stage architecture to identify misbehaving vehicles, achieving high accuracy and outperforming existing frameworks in key evaluation metrics while being suitable for resource-constrained environments.
   - **Keywords**: Misbehavior Detection, V2X Communications, Machine Learning, Artificial Intelligence, Deep Learning

2. **AI/ML for Secure V2X in 6G Networks**
   - **Abstract**: This paper discusses the challenges of V2X communications in 6G networks, including security vulnerabilities. It explores the necessity of AI/ML-based Intrusion Detection Systems (IDS) and discusses the state-of-the-art solutions and their limitations.
   - **Keywords**: 6G, V2X Communications, Artificial Intelligence, Machine Learning, Intelligent Transportation System, Intrusion Detection Systems

## Developed System

#### Unsupervised Anomaly Detection

**Objective:** Develop and compare deep unsupervised models to detect anomalies in V2X (Vehicle-to-Everything) data, which is time-series in nature.

**Models Used:**
1. **LSTM Autoencoder (M1):** Combines autoencoders with LSTM layers to leverage the temporal dependencies in time-series data. M1 has 2 encoder layers and 2 decoder layers with 1024 and 512 LSTM units, respectively.
   
2. **CNN-LSTM (M2):** Utilizes convolutional layers to extract spatial features followed by LSTM layers to capture temporal dependencies. M2 consists of 2 CNN layers (1024 and 512 units) and 4 stacked LSTM layers (512 units each).

3. **CNN-BiLSTM (M3):** Similar to M2 but replaces LSTM with Bidirectional LSTM (BiLSTM) layers to better capture context from both past and future sequences. M3 includes 2 CNN layers (1024 and 512 units) and 4 stacked BiLSTM layers.

#### Supervised Learning for Misbehavior Detection

**Objective:** Deploy on edge servers to classify V2X sequences as either genuine or indicative of misbehavior.

**Models Used:**
1. **CNN (S1):** Converts V2X sequences into images and processes them using CNNs to detect misbehavior. S1 has two 2D CNN layers (256 and 128 units) followed by dense layers (100 and 10 units), with a final dense output layer for binary classification.

2. **Stacked LSTM (S2):** Directly processes sequences using stacked LSTM layers. S2 comprises 4 layers of 256 LSTM units each, with a final dense layer for binary classification.

**Key Differences:**
- **S1** requires transforming input sequences into images (20x6x1) before processing, while **S2** handles sequences directly without such transformation.

**Training:** Both models are trained with labeled datasets generated from the unsupervised anomaly detection phase. 

These models aim to enhance anomaly detection and misbehavior classification in V2X systems by leveraging both temporal and spatial features of the data.

## Conclusion

This project provides a comprehensive MDS for V2X networks, combining the strengths of unsupervised and supervised learning to detect and classify misbehavior effectively. By leveraging deep learning techniques, the system adapts to the dynamic nature of V2X environments, ensuring robust performance in real-world scenarios.

