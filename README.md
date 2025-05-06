# lung_seg
# Mask‑RCNN Lung Shapes Detector
> **Folder structure**
>
> ```
> mask-rcnn-shapes/  
> ├── data/                  # your images & masks  
> ├── logs/                  # training logs & saved weights  
> │   └── mask_rcnn_shapes.h5  
> ├── train.py               # the script you posted above  
> ├── test.py               # the script you posted above  
> ├── README.md              # overview & quickstart   
> ```
This repository contains an end‑to‑end pipeline to train Mask‑RCNN on a custom “lung shapes” dataset, and to save the resulting weights (`mask_rcnn_shapes.h5`) for inference.

## Contents

- `train.py` – Training script (based on Matterport’s Mask‑RCNN)  
- `data/` – Folders for your `images/` and `masks/`  
- `logs/` – Training logs and saved weights  
- `mask_rcnn_shapes.h5` – Final trained weights  
- `README.md` – Overview & quickstart & Detailed setup & usage instructions  

## Quickstart
1. Prerequisites
- **Anaconda**  
- **Git** (command‑line)  
- **CUDA & cuDNN** 
- **Pip**
- 
2. **Clone repo**  
   ```bash
   git clone https://github.com/zhirentsai/lung_seg.git
   cd lung_seg
