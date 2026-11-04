# Day vs. Night Object Detection Using YOLOv8

**Deep Learning | Computer Vision | Object Detection | Transfer Learning**

An experimental study investigating how daytime and nighttime training data affect object detection performance in autonomous driving scenarios.

## Project Overview

Object detection is a critical component of autonomous driving systems. However, challenging lighting conditions, including low illumination, shadows, and headlight glare, can affect detection performance.

This project investigates how different training-data compositions influence the performance of YOLOv8n on the BDD100K driving dataset.

**Research Question:** How does training on daytime, nighttime, or a combination of both lighting conditions affect object detection accuracy?

## Technologies Used

- Python
- PyTorch
- Ultralytics YOLOv8n
- BDD100K Dataset
- Google Colab
- OpenCV
- Matplotlib
- Transfer Learning

## Dataset

The project uses the BDD100K autonomous driving dataset, focusing on five object categories:

- Person
- Bicycle
- Car
- Bus
- Truck

The evaluation uses 1,500 validation images, comprising 750 daytime and 750 nighttime images.

Dataset: https://bdd-data.berkeley.edu/

## Methodology

We initialized YOLOv8n using COCO-pretrained weights and fine-tuned separate models using different lighting conditions.

The experiments include:

- **E0 — Pretrained Baseline:** Original COCO-pretrained model without BDD100K fine-tuning.
- **E1 — Balanced Training:** 3,500 daytime and 3,500 nighttime images.
- **E2 — Night-Only Training:** Training exclusively on nighttime images.
- **E3 — Day-Only Training:** Training exclusively on daytime images.

The models are evaluated separately on daytime and nighttime validation images using mAP50 and mAP50–95.

## Experimental Results

The following validation results were obtained from the original experiment runs:

| Model | Daytime mAP50 | Nighttime mAP50 |
|---|---:|---:|
| E1 — Balanced | 45.23% | 47.91% |
| E2 — Night-only | 32.15% | 39.48% |
| E3 — Day-only | 44.74% | 37.43% |

**Key observations:**

- Balanced training achieved the highest nighttime mAP50 among the evaluated fine-tuned models.
- Night-only training showed better nighttime than daytime performance.
- Day-only training showed better daytime than nighttime performance.
- The balanced model showed the smallest absolute day–night mAP50 gap.


## Evaluation Metrics

- **mAP50:** Mean Average Precision at IoU = 0.50.
- **mAP50–95:** Mean Average Precision averaged across IoU thresholds from 0.50 to 0.95.
- **Precision:** Proportion of predicted detections that are correct.
- **Recall:** Proportion of ground-truth objects successfully detected.

## Key Learnings

This project provided practical experience in:

- Fine-tuning pretrained object detection models.
- Preparing and converting object detection annotations.
- Designing experiments to investigate distribution shifts.
- Evaluating detection performance across lighting conditions.
- Interpreting model performance and experimental limitations.

## Future Improvements

- Evaluate performance on a separate held-out test set.
- Analyze class-wise performance under different lighting conditions.
- Experiment with low-light data augmentation and image enhancement.
- Compare larger YOLOv8 variants.


## Author

**Rishab Choudhary**  
Master's Student in Computer Science  
University of Gothenburg, Sweden

