
## Installation from Source

```bash
# Clone the repository
git clone https://github.com/open-mmlab/mmdetection.git
cd mmdetection

# Create and activate a conda environment
conda create -n openmmlab python=3.8 -y
conda activate openmmlab

# Install PyTorch (adjust according to your CUDA version)
pip install torch torchvision torchaudio

# Install MMDetection from source
pip install -v -e .

# Install additional dependencies
pip install mmengine mmcv
```

## Running MAP Challenge Instance Segmentation Experiments

### Project Configuration
You can find and edit experiment configurations in the `projects/mapchallenge` folder. Typical configurations will include:
- Model architectures
- Dataset settings
- Training parameters

### Experiment Script
```bash
# Run the experiments script
bash train.sh
```
## MapChallenge Instance Segmentation Results

| Model            | segm mAP | segm mAP@50 | segm mAP@75 | segm mAP_s | segm mAP_m | segm mAP_l | segm mAR | segm mAR@50 | segm mAR@75 |
|------------------|----------|-------------|-------------|------------|------------|------------|----------|-------------|-------------|
| [SwinS-Mask2former](https://github.com/saidineshpola/MaskDINO-mapchallenge/blob/main/assets/logs/mask2former_swin-s-p4-w7-224_8xb2-lsj-50e_coco.log) | 0.380    | 0.721       | 0.382       | 0.152      | 0.495      | 0.692      | 0.504    | 0.879       | 0.509       |
| [SwinL-Mask2former](https://github.com/saidineshpola/MaskDINO-mapchallenge/blob/main/assets/logs/SWIN-L.log) | 0.3080   | 0.7260      | 0.2360      | 0.1710     | 0.4400     | 0.1310     | 0.453    | 0.855       | 0.464       |
| [RTMdet-M](https://github.com/saidineshpola/MaskDINO-mapchallenge/blob/main/assets/logs/rtmdet-ins_m_8xb32-300e_satellite.log) | 0.403    | 0.726       | 0.452       | 0.186      | 0.523      | 0.737      | 0.527    | 0.888       | 0.586       |
| [RTMdet-X](https://github.com/saidineshpola/MaskDINO-mapchallenge/blob/main/assets/logs/rtmdet-ins_X_8xb16-300e_satellite.log) | 0.418    | 0.743       | 0.472       | 0.194      | 0.536      | 0.769      | 0.529    | 0.897       | 0.586       |
| [QueryInst-r50](https://github.com/saidineshpola/MaskDINO-mapchallenge/blob/main/assets/logs/queryinst_r50_fpn_ms-3x_coco.log) | 0.400   | 0.711      | 0.437      | 0.188     | 0.517     | 0.657     | 0.553    | 0.905       | 0.595       |
| [QueryInst-r101](https://github.com/saidineshpola/MaskDINO-mapchallenge/blob/main/assets/logs/queryinst_r101_fpn_300_proposals_crop_mstrain_3x_coco.log) | 0.406   | 0.689      | 0.44      | 0.184     | 0.524     | 0.665     | 0.581    | 0.914       | 0.655       |
| **[MaskDINO](https://github.com/saidineshpola/MaskDINO-mapchallenge/tree/main/assets/logs)**     | **0.561**| **0.911**   | **0.650**   | **0.351**  | **0.6843** | **0.6851** | **0.617**| **0.949**    | **0.703**   |

<br>
### MapChallenge results at >= @0.50 IOU

| Model            | segm mAP@50 | segm mAR@50 |
|------------------|-------------|-------------|
| [SwinS-Mask2former](https://github.com/saidineshpola/MaskDINO-mapchallenge/blob/main/assets/logs/mask2former_swin-s-p4-w7-224_8xb2-lsj-50e_coco.log) | 0.721       | 0.879       |
| [SwinL-Mask2former](https://github.com/saidineshpola/MaskDINO-mapchallenge/blob/main/assets/logs/SWIN-L.log) | 0.7260      | 0.855       |
| [RTMdet-M](https://github.com/saidineshpola/MaskDINO-mapchallenge/blob/main/assets/logs/rtmdet-ins_m_8xb32-300e_satellite.log) | 0.726       | 0.888       |
| [RTMdet-X](https://github.com/saidineshpola/MaskDINO-mapchallenge/blob/main/assets/logs/rtmdet-ins_X_8xb16-300e_satellite.log) | 0.743       | 0.897       |
| [QueryInst-r50](https://github.com/saidineshpola/MaskDINO-mapchallenge/blob/main/assets/logs/queryinst_r50_fpn_ms-3x_coco.log) | 0.711       | 0.905       |
| [QueryInst-r101](https://github.com/saidineshpola/MaskDINO-mapchallenge/blob/main/assets/logs/queryinst_r101_fpn_300_proposals_crop_mstrain_3x_coco.log) | 0.689       | 0.914       |
| **[MaskDINO](https://github.com/saidineshpola/MaskDINO-mapchallenge/tree/main/assets/logs)**     | **0.911**   | **0.949**   |

<br>

**Note:**
- **mAP@50/mAR@50** refers to average precision/recall at 0.50 and **mAP@75/mAR@75** refers to average precision/recall at 0.75 IOU
- `segm mAP` values are usually averaged over multiple IOUs from 0.5 to 0.95 with interval of 0.05
- In metric columns,
       - `s` = small objects
       - `m` = medium objects
       - `l` = large objects
  
<!-- For the MAP Challenge instance segmentation task, **MaskDINO** got the most robust and high-performing model, especially for small and large objects.
 -->
## Related Repositories

For MaskDINO experiments, you might want to check out:
- [MaskDINO training Repository](https://github.com/saidineshpola/MaskDINO-mapchallenge/blob/main/README.md)

