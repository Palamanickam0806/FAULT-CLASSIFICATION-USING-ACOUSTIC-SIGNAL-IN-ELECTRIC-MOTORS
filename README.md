# FAULT-CLASSIFICATION-USING-ACOUSTIC-SIGNAL-IN-ELECTRIC-MOTORS
# Overview
This project presents a deep learning-based diagnostic system that leverages acoustic signals for non-invasive, real-time fault detection in electric motors. Using Mel-frequency cepstral coefficients (MFCC) extracted from vibration recordings, we trained multiple neural network architectures (CNN, RNN, and CNN+RNN) to classify motor bearing faults with high accuracy and low compuation, even in noisy industrial environments.
# Dataset
* CWRU dataset - The Case Western Reserve University Bearing Data Center
# Scope
  * Early Detection of Motor Faults: Identify defects such as single-point failures in drive and fan end bearings.
  
  * Acoustic-Based Diagnostics: Use audio signals instead of traditional vibration sensors for a more cost-effective, flexible solution.
  
  * Robust Modeling: Handle noisy environments with minimal preprocessing using deep learning.
  
  * Efficiency & Real-Time Focus: Tailored for edge deployment using quantization and model approximation.
# Novelty approach
  * Hybrid Deep Learning Models: Comparison of CNN, RNN, and a custom CNN + GRU + Conv1D hybrid model to determine optimal trade-offs between accuracy and speed.
  
  * Real-Time Ready: Achieved the lowest inference time (65.67 ms) with the hybrid model—suitable for live industrial settings.
  
  * Quantization & Approximation Strategies:
  
      INT8 & FP16 quantization for low-power devices.
      
      Use of depthwise separable convolutions and lightweight activation functions to reduce latency and model size.
  
  * MFCC Conversion Pipeline: A dedicated notebook for converting .mat sensor data to MFCC-based .npy format for easy model ingestion.

# Models and Results

| Model  | Accuracy | Trainable params  | Inference Time |
| ------------- | ------------- | ------------- | ------------- |
| CNN  | 89%  | 2.2M  | 82.3 ms  |
| RNN  | 81%  | 807k  | 77.12 ms  |
| CNN + RNN  | 93.75%  | 176K  | 65.67 ms  |

*** The hybrid model (CNN + GRU + Conv1D) provided the best balance of accuracy, speed, and model size, making it ideal for embedded or edge AI applications.

# Repository Structure
   main.ipynb: Includes training and evaluation code for CNN, RNN, and hybrid models.
   data processing.ipynb: Converts raw .mat files into MFCC .npy format.

# 🚀 Future Plans

   * Data Augmentation: Introduce real-time audio augmentation to further enhance generalization.
   
   * Deployable App: Wrap model inference in a web or mobile dashboard.
   
   * On-Device Optimization: Implement TFLite or ONNX for actual deployment on microcontrollers or Raspberry Pi.
   
   * Real-World Testing: Expand dataset with real industrial motor sounds to validate robustness.

