# lung_seg
# Mask‑RCNN Lung Shapes Detector
> **Folder structure**
>
> ```
> mask-rcnn-shapes/  
> ├── data/                  # your images & masks  
> ├── logs/                  # training logs & saved weights  
> │   └── mask_rcnn_coco.h5
> │   └── mask_rcnn_shapes.h5  
> ├── train.py               # the script you posted above  
> ├── test.py               # the script you posted above  
> ├── README.md              # overview & quickstart   
> ```
This repository contains an end‑to‑end pipeline to train Mask‑RCNN on a custom “lung shapes” dataset, and to save the resulting weights (`mask_rcnn_shapes.h5`) for inference.

## Contents

- `train.py` – Training script (based on Mask‑RCNN)  
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
3. **conda_environment**

   Download the py37tf21campp.zip provided on this site ( https://tinyurl.com/27z44nu9 ); after extracting it, place the resulting folder in \anaconda3\envs\.

4. **Prepare data**

   * Place your training images in `data/images/`
   * Place the corresponding masks in `data/masks/`

5. **Train**

   ```bash
   python train.py --fileind 0   # to start from COCO weights
   python train.py --fileind 1   # to resume from last checkpoint
   ```

6. **Inspect logs**

   * TensorBoard:

     ```bash
     tensorboard --logdir=logs/
     ```
   * Final weights at `logs/yours.h5`





