# EEG-Signal-Processing-and-Classification
📘 EEG Signal Classification Using Machine Learning and Deep Learning Approaches

This repository contains the implementation of the methodology presented in the work “Exploring the effectiveness of machine learning and deep learning techniques for EEG signal classification in neurological disorders”, which was developed as part of my master’s thesis. The project focuses on building a complete EEG signal processing pipeline to investigate how classical machine learning and modern deep learning architectures perform in the classification of neurological conditions from EEG recordings.

The study is motivated by the increasing need for reliable and automated EEG analysis systems capable of assisting in the detection and characterization of neurological disorders. EEG signals are inherently non-stationary, noisy, and highly subject-dependent, which makes their analysis challenging and justifies the use of advanced preprocessing and learning strategies.

The pipeline begins with the acquisition of raw EEG signals from EDF files, which are processed using the MNE library. Each recording is standardized through resampling, bandpass filtering, and spatial referencing using the international 10–20 montage system. To improve signal quality and reduce artifacts such as muscle activity and ocular interference, Independent Component Analysis (ICA) is applied. The cleaned signals are then segmented into fixed-length epochs in order to transform continuous EEG recordings into structured samples suitable for machine learning.

Once the data is prepared, multiple feature extraction strategies are applied to capture both temporal and spectral characteristics of the EEG signals. These include statistical descriptors such as mean, variance, skewness, and kurtosis, along with entropy-based measures, wavelet decomposition using the Daubechies-4 (DB4) wavelet, and frequency-domain representations derived from power spectral density across standard EEG bands. This multi-domain feature representation is designed to preserve the physiological information embedded in the EEG signals while making them suitable for classification algorithms.

The extracted features are then used to train and evaluate several classical machine learning models, including K-Nearest Neighbors, Logistic Regression, Support Vector Machines, Random Forests, and Linear Discriminant Analysis. To ensure robust evaluation and prevent data leakage across subjects, GroupKFold cross-validation is employed, where all samples from the same subject are kept within the same fold.

In parallel, deep learning models are designed to directly learn representations from EEG sequences. These architectures combine convolutional layers for spatial-temporal feature extraction with recurrent layers such as LSTM and GRU to capture long-term dependencies within the signal. A ChronoNet-inspired hybrid architecture is also explored to enhance temporal modeling capacity. All neural networks are trained and validated under the same cross-validation strategy to ensure fair comparison with traditional methods.

The performance of all models is assessed using a comprehensive set of evaluation metrics, including accuracy, precision, recall, F1-score, specificity, Matthews correlation coefficient, and Cohen’s kappa. This allows for a detailed analysis of model behavior beyond simple accuracy, particularly in imbalanced or multi-class scenarios.

Overall, this work provides a comparative study of machine learning and deep learning approaches for EEG-based neurological disorder classification, highlighting the strengths and limitations of each paradigm in handling complex brain signal data.

📄 Citation

If you use this repository, please cite the associated work:

Khalfallah, S. (2026). Exploring the effectiveness of machine learning and deep learning techniques for EEG signal classification in neurological disorders. Master’s Thesis, ISSAT Sousse.

⚙️ Repository Description

This repository includes the full implementation of the EEG preprocessing pipeline, feature extraction methods, machine learning experiments, and deep learning architectures used in the thesis. It is built using Python, MNE, Scikit-learn, PyWavelets, and TensorFlow/Keras, and is intended to provide a reproducible framework for EEG signal classification research.
