# Eye-Gaze Estimation with Artificial Neural Networks

A deep learning system for accurate eye-gaze estimation using convolutional neural networks, designed for natural human-robot interaction applications using standard RGB cameras.

## Overview

This project implements an eye-gaze estimation system that predicts where a person is looking without requiring specialized hardware or infrared filters. By combining CNNs with head pose estimation, the system achieves robust gaze tracking across diverse conditions and demographics.

## Key Features

- **Hardware-Free Approach**: Works with standard RGB cameras, eliminating the need for IR sensors or specialized equipment
- **Multi-Modal Input**: Combines eye region analysis with head pose estimation for improved accuracy
- **Diverse Training Data**: Trained on 57,000+ synthetic images featuring 15 unique characters with variations in age, ethnicity, eye color, and facial structure
- **Real-World Applicability**: Designed for human-robot interaction scenarios with cross-dataset validation

## Technology Stack

### Core Components

- **Convolutional Neural Networks (CNNs)**: Primary architecture for processing eye region images and extracting gaze features
- **RetinaFace**: Face detection and localization for preprocessing pipeline
- **SixDRepNet**: Head pose estimation to provide complementary spatial information
- **Unreal Engine + Metahuman**: Synthetic data generation platform for creating diverse, high-quality training datasets

### Dataset

The training dataset consists of over 57,000 images generated using Unreal Engine's Metahuman technology, featuring:
- 15 distinct characters with varied demographics
- Multiple eye and head positions
- Dynamic lighting conditions
- Comprehensive gaze angle coverage

**Naming Convention**: `{character_name}_{id}_OP_{vertical_angle}_{horizontal_angle}.png`

## Model Architecture

The system employs a multi-stage pipeline:

1. **Face Detection**: RetinaFace localizes faces in input frames
2. **Head Pose Estimation**: SixDRepNet calculates 6D head orientation
3. **Gaze Prediction**: CNN processes eye regions alongside head pose data to estimate gaze coordinates

The architecture combines convolutional layers for feature extraction with fully connected layers for regression, optimized through extensive experimentation.

## Performance

The models have been validated across multiple datasets:
- Metahuman synthetic dataset
- Columbia Gaze dataset
- Combined cross-dataset evaluation

Cross-validation demonstrates strong generalization capabilities and robustness across varying lighting conditions and subject demographics.
