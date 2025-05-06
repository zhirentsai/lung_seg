# lung_seg
> **Folder structure**
>
> ```
> lung_seg/  
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
   * **Images folder**: `data/images/`
   * **Masks folder**:  `data/masks/`
   * File naming must match by index (e.g., `0001.png` in both folders corresponds).

5. **Train**

   ```bash
   python train.py --fileind 0   # to start from COCO weights
   python train.py --fileind 1   # to resume from last checkpoint
   ```
   The `train.py` script supports two modes via the `--fileind` flag:

   * `--fileind 0`
     Load COCO pre‑trained weights, fine‑tune only the heads first.
   * `--fileind 1`
     Resume training from your last checkpoint (`yours.h5`).
   
   ### Example
   
   ```bash
   # First run, start from COCO
   python train.py --fileind 0
   
   # Resume from last
   python train.py --fileind 1
   ```
   
   * **Epochs**: 500 heads, then 500 all-layers
   * **Batch size**: As defined in `ShapesConfig` (`IMAGES_PER_GPU = 32`)
   
   Training outputs:
   
   * Logs & checkpoints in `logs/`
   * Final weights overwritten at `logs/yours.h5`
   * 
6. **Inspect logs**
   Use TensorBoard to visualize losses and metrics:
   * TensorBoard:

     ```bash
     tensorboard --logdir=logs/
     ```
   * Final weights at `logs/yours.h5`





