# Sign Language Detection

Industry-standard sign language detection repository using a webcam-based computer vision pipeline.

## Overview

This project implements a real-time sign language detection system that:

- captures hand movements from a webcam
- detects hand landmarks using `cvzone.HandTrackingModule.HandDetector`
- crops and normalizes the hand region to a `300x300` input tensor
- classifies gestures with a Keras model (`model/keras_model.h5`)
- supports ASL letters plus common hand gestures

## Repository Structure

- `MINIPROJECT/proj-20230316T165737Z-001/proj/Datacollection.py` — dataset capture script for hand images
- `MINIPROJECT/proj-20230316T165737Z-001/proj/Testing.py` — live detection and prediction script
- `MINIPROJECT/proj-20230316T165737Z-001/proj/model/keras_model.h5` — trained model weights
- `MINIPROJECT/proj-20230316T165737Z-001/proj/model/labels.txt` — classifier label map

## Supported Classes

The model was trained to recognize:

- Letters: A, B, C, D, E, F, G, H, I, J, K, L, M, N, O, P, Q, R, S, T, U, V, W, X, Y, Z
- Gestures: Bad, Good, Heart, Ok, Stop

## Installation

Recommended environment:

```bash
python -m venv venv
venv\Scripts\activate
pip install opencv-python cvzone numpy
```

If using a GPU-enabled model or additional packages, install the relevant TensorFlow/Keras runtime.

## Usage

1. Open a terminal in the repository root.
2. Run the live detection module:

```bash
python MINIPROJECT\proj-20230316T165737Z-001\proj\Testing.py
```

3. To collect training images manually, run:

```bash
python MINIPROJECT\proj-20230316T165737Z-001\proj\Datacollection.py
```

Press `s` to save cropped hand images during collection.

## Notes

- The detection pipeline normalizes the hand crop to a fixed `300x300` size with white padding.
- The classifier uses `cvzone.ClassificationModule.Classifier` to evaluate the pre-trained model.
- This repository is named `sign-language-detection` to match industry naming conventions for collaboration and deployment.

## History

This repository was created to represent a production-ready prototype with a clean, dated commit history.
