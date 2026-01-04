# Automated Sperm Cell Detection and Tracking in Fruit Flies

---

## Introduction

This project was developed as part of a final-year project in collaboration with the Hebrew University,
within the framework of a broader biological research initiative focused on fertility studies.

The fruit fly (*Drosophila melanogaster*) is a widely accepted model organism in fertility research due to the 
similarities between its reproductive mechanisms and those of humans.

Numerous studies suggest that breakthroughs in understanding fertility mechanisms in fruit flies may eventually
lead to significant advances in human fertility research.  
Accurate tracking of sperm cell movement presents a major challenge due to the cells’ small size, rapid motion, high density,
and visual noise inherent to microscopy imaging.

In this project, we developed an automated tool for detecting and tracking sperm cells in microscopy videos,
designed to serve as a reliable research infrastructure for precise, consistent, and objective motion analysis.

---

## Project Objectives

The main goals of this project are:

- **Automatic detection** of sperm cells in individual microscopy video frames
- **Consistent tracking** of each sperm cell across frames while preserving a unique Track ID
- **Analysis of motion characteristics** such as speed, direction, and movement patterns
- **Generation of outputs** for research purposes, including quantitative data and visual representations

---

## System Overview

The system operates through a multi-stage pipeline:

1. **Video Preprocessing:** The microscopy video is split into individual frames and enhanced for contrast using OpenCV.  
2. **Detection:** Each frame is processed by a YOLOv8 model trained specifically for sperm cell detection in dense and noisy environments.  
3. **Tracking:** Sperm cells are tracked across consecutive frames using Euclidean distance calculations between bounding box centroids to preserve cell identity.  
4. **Output Generation:** The system produces labeled videos and data files for further analysis.

---

## Sperm Cell Detection

Detection is performed using a **YOLOv8 model** fine-tuned on a custom dataset of microscopy images from the fruit fly reproductive system.  
The training included a combination of automated and manual annotations to improve performance under conditions of high cell density and overlap.

---

## Sperm Cell Tracking

After detection, each sperm cell is tracked across the video sequence.  
Tracking is based on calculating the distance between cell positions in consecutive frames, allowing the system to maintain a unique identifier for each cell.

This method enables **continuous motion analysis** even in complex biological environments, without relying on heavy predictive models.

---

## Motion Analysis and Outputs

The system extracts the following motion metrics:

- **Cell velocity:** Calculated from pixel displacement between consecutive frames
- **Direction and movement patterns** over time
- **Duration of continuous movement** for each cell

Outputs include:

- A labeled video with sperm cell Track IDs
- A CSV file containing quantitative motion data
- Labeled images for visual inspection

---

## Key Results

- **Precision:** 83.75%
- **Recall:** 64.61%

The system demonstrated stable and reliable sperm cell detection and tracking in complex microscopy environments,
producing consistent data suitable for biological research.

---

## Technologies Used

- Python
- OpenCV
- YOLOv8 (Ultralytics)
- NumPy
- Pandas

---

## Poster and Presentation

The project poster and product presentation can be found here:  

- **Poster:** [Poster](docs/Poster.pdf)  
- **Presentation:** [Presentation](docs/presentation.pdf)
