# Pothole Detection Under Waterlogging for Safe Driving

**Authors:**  
- Madhumitha R, School of Computer Science and Engineering (SCOPE), VIT Chennai  
  Email: [madhumitha.2020a@vitstudent.ac.in](mailto:madhumitha.2020a@vitstudent.ac.in)  
- Manish Aniruddha P, School of Computer Science and Engineering (SCOPE), VIT Chennai  
  Email: [manishaniruddha.p2020@vitstudent.ac.in](mailto:manishaniruddha.p2020@vitstudent.ac.in)

---

## Overview

This repository contains the implementation of a pothole detection system designed to enhance safe driving during rainy weather by identifying potholes obscured under waterlogging. Leveraging deep learning techniques, this project trains an object detection model using YOLOv8, a state-of-the-art architecture, with simulated underwater images. These simulations address the challenges posed by turbid water, which limits visibility and complicates detection.

---

## Key Features

- **Deep Learning-Based Detection:** Utilizes YOLOv8 for real-time and efficient pothole detection.
- **Image Simulation:** Employs a physical image formation model to simulate underwater images for robust model training.
- **Performance Improvement:** Demonstrates a significant 19.8% improvement in F1 score when tested with underwater images.
- **Real-Time Suitability:** Prioritizes speed and precision for deployment in driver assistance and autonomous vehicle systems.

---

## Methodology

1. **Data Augmentation:**
   - The original dataset, sourced from [Mendley Pothole Dataset](https://data.mendeley.com/datasets/...), includes annotated images of dry and water-filled potholes.
   - Simulated underwater images were generated using a physical image formation model, replicating light attenuation in turbid water.

2. **Depth Estimation:**
   - Monocular depth maps were created using the MiDaS model to account for light attenuation based on depth.

3. **Model Training:**
   - YOLOv8 was trained using the simulated underwater images.
   - Data was split into 80% training and 20% testing sets for evaluation.

4. **Evaluation Metrics:**
   - Metrics such as mAP50, precision, recall, and F1 score were used to measure performance.

---

## Results

| **Training Data**    | **Testing Data**    | **mAP50** | **Precision** | **Recall** | **F1 Score** |
|-----------------------|---------------------|-----------|---------------|------------|--------------|
| Original Images       | Generated Images   | 0.354     | 0.577         | 0.317      | 0.410        |
| Generated Images      | Generated Images   | 0.582     | 0.635         | 0.583      | 0.608        |

Training with simulated images resulted in better detection performance under waterlogged conditions.

---

## How to Run

### Prerequisites
- Python 3.8 or later
- Required libraries: `Ultralytics`, `torch`, `numpy`, `opencv-python`, `matplotlib`

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/pothole-detection-under-waterlogging.git
   cd pothole-detection-under-waterlogging
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Train the model:
   ```bash
   python train.py --dataset simulated_images --model yolov8
   ```

4. Evaluate the model:
   ```bash
   python evaluate.py --test-data generated_images
   ```

5. Deploy for real-time detection:
   ```bash
   python detect.py --video input_video.mp4
   ```

---

## Future Work

- Extend to address other underwater imaging challenges like low contrast and environmental variability.
- Optimize the system for better real-time performance in diverse conditions.

---

## Citation

If you use this repository in your work, please cite:

```
Madhumitha R, Manish Aniruddha P. "Pothole Detection Under Waterlogging for Safe Driving in Rainy Weather."
```

---

## Acknowledgments

This project builds on research in computer vision and autonomous driving, integrating techniques from the latest YOLOv8 and MiDaS depth estimation models.

For inquiries or collaboration, contact the authors via the emails provided above.

---
