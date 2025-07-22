# Ottoman Text Line Segmentation Dataset

This repository provides a publicly available dataset designed to support research on **text line segmentation in Ottoman manuscripts**. The dataset includes both manually and automatically labeled samples, generated using a high-performing segmentation model based on **YOLO Oriented Bounding Boxes (OBB)** and **Segmentation** techniques.




## 📦 Dataset Overview

- **Total Pages**: 150
  - 40 pages labeled manually
  - 110 pages labeled automatically
- **Annotation Format**: YOLO (polygon-based)
- **Content**: Ottoman script document images and corresponding text line annotations
- **Annotations**: Each text line is annotated as a polygon with normalized coordinates
- **Performance**: Precision **96.5%**, Recall **98.1%**

## 🔧 Data Format

Each image has a corresponding `.txt` file with the same name. Each line in the label file represents one polygonal text line annotation in the format:

    class-id x1 y1 x2 y2 ... xn yn

- `class-id`: Typically `0` for a single-class dataset
- `xi`, `yi`: Normalized x and y coordinates of polygon vertices

### Example

    0 0.234 0.456 0.238 0.467 0.250 0.472 ...



## 🧪 Dataset Creation Details

- **Model**: YOLO OBB + Segmentation
- **IoU Threshold**: 50%
- **Overlap Threshold**: 90%
- **Post-processing**:
  - Duplicate regions removed
  - Optional filtering by size or count
  - Closely aligned lines can be merged to correct segmentation errors

## 📊 Evaluation Summary

- **Subset**: 20 randomly selected images
- **Ground Truth Lines**: 1,086
- **Correctly Segmented**: 1,066
- **Missed Lines**: 20 (mostly in visually complex layouts)
- **False Positives**: 39 (typically borders or marginal elements)

| Metric     | Score     |
|------------|-----------|
| Precision  | 96.5%     |
| Recall     | 98.1%     |

## 📷 Sample Images

<p align="center">
  <img src="https://github.com/user-attachments/assets/5a837780-9b44-400e-8340-343a12e56901" width="45%" alt="Straight Lines"/>
  <img src="https://github.com/user-attachments/assets/10484ce3-8599-4330-9725-9861d8c17c81" width="45%" alt="Angled Lines"/>
</p>
<p align="center"><em>Figure: Samples from the resulting dataset</em></p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/ca7bbdd5-23a3-4018-bd19-4d31de958881" width="45%" alt="Border"/>
  <img src="https://github.com/user-attachments/assets/a65b3c56-bbac-4240-b2cd-8cac8f4c834b" width="20%" alt="Page number"/>
</p>
<p align="center"><em>Figure: Sample crops from the resulting dataset with false positive detections</em></p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/2f63ad4a-bebd-4a74-958c-931a76662349" width="45%" alt="Multi-column formatting"/>
</p>
<p align="center"><em>Figure: A sample crop from the resulting dataset with multi-column formatting</em></p>


## 📂 Repository Structure

    ottoman-text-line-segmentation-dataset/  
    ├── manual_annotations/  # Manually labeled dataset
    │ ├── images/   
    │ └── labels/ 
    ├── automatic_annotations/  # Automatically labeled dataset
    │ ├── images/  
    │ └── labels/
    ├── README.md 
    └── LICENSE # License file


## 📄 Citation

If you use this dataset in your research, please cite the following master's thesis:

    @mastersthesis{kutal2025ottoman,
     author = {Kutal, Seçilay},
     title = {Automated Text Line Segmentation for Ottoman Manuscript Transcription},
     school = {Sabancı University},
     year = {2025},
     month = {July},
     type = {Master's thesis},
     address = {Istanbul, Türkiye}
    }

---


