# Domain Adaptive Video Segmentation via Temporal Pseudo Supervision

## Abstract
Video semantic segmentation has achieved great progress under the supervision of large amounts of labelled training data. However, domain adaptive video segmentation, which can mitigate data labelling constraint by adapting from a labelled source domain toward an unlabelled target domain, is largely neglected. We design temporal pseudo supervision (TPS), a simple and effective method that explores the idea of consistency training for learning effective representations from unlabelled target videos. Unlike traditional consistency training that builds consistency in spatial space, we explore consistency training in spatiotemporal space by enforcing model consistency across augmented video frames which helps learn from more diverse target data. Specifically, we design cross-frame pseudo labelling to provide pseudo supervision from previous video frames while learning from the augmented current video frames. The cross-frame pseudo labelling encourages the network to produce high-certainty predictions which facilitates consistency training with cross-frame augmentation effectively. Extensive experiments over multiple public datasets show that TPS is simpler to implement, much more stable to train, and achieves superior video segmentation accuracy as compared with the state-of-the-art.

## Main Results
#### SYNTHIA-Seq => Cityscapes-Seq
| Methods       | road | sidewalk | building | pole | light | sign | vegetation | sky | person | rider | car | mIoU |
|---------------|------|----------|----------|------|-------|------|------------|-----|--------|-------|-----|------|
| Source only   | 56.3 | 26.6 | 75.6 | 25.5 |  5.7 | 15.6 | 71.0 | 58.5 | 41.7 | 17.1 | 27.9 | 38.3 |
| DA-VSN        | 89.4 | 31.0 | 77.4 | 26.1 |  9.1 | 20.4 | 75.4 | 74.6 | 42.9 | 16.1 | 82.4 | 49.5 |
| PixMatch      | 90.2 | 49.9 | 75.1 | 23.1 | 17.4 | 34.2 | 67.1 | 49.9 | 55.8 | 14.0 | 84.3 | 51.0 |
| **TPS (ours)**| **91.2**| **53.7** | 74.9 | 24.6 | **17.9** | **39.3** | 68.1 | 59.7 | **57.2** | **20.3** | **84.5** | **53.8** |

#### VIPER => Cityscapes-Seq


## Environment
The code is developed based on PyTorch. The code is developed and trained on a single 2080Ti GPU. Other platforms or multiple GPUs are not tested.

## Installation
1. create conda environment
```bash
conda create -n TPS python=3.6
conda activate TPS
conda install -c menpo opencv
pip install torch==1.2.0 torchvision==0.4.0
```
2. clone the [ADVENT repo](https://github.com/valeoai/ADVENT)
```bash
git clone https://github.com/valeoai/ADVENT
pip install -e ./ADVENT
```

3. clone the repo
```bash
git clone https://github.com/xing0047/TPS.git
pip install -e ./TPS
```

## Preparation

## Train and Test

## Evaluation

## Acknowledgement
This codebase is based on [DA-VSN](https://github.com/Dayan-Guan/DA-VSN).

## Contact
If you have any questions, feel free to contact: xing0047@e.ntu.edu.sg
