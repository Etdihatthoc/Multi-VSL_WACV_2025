# Multi-VSL-WACV-2025

## Overview
Vision-based sign language recognition is an extensively
researched problem aimed at advancing communication between deaf and hearing individuals. Numerous Sign Language Recognition (SLR) datasets have been introduced to
promote research in this field, spanning multiple languages,
vocabulary sizes, and signers. However, most existing popular datasets focus predominantly on the frontal view of
signers, neglecting visual information from other perspectives. In practice, many sign languages contain words
that have similar hand movements and expressions, making
it challenging to differentiate between them from a single
frontal view. Although a few studies have proposed sign language datasets using multi-view data, these datasets remain
limited in vocabulary size and scale, hindering their generalizability and practicality. To address this issue, we introduce a new large-scale, multi-view sign language recognition dataset spanning 1,000 glosses and 30 signers, resulting in over 84,000 multi-view videos. To the best of our
knowledge, this is the first multi-view sign language recognition dataset of this scale. In conjunction with offering a
comprehensive dataset, we perform extensive experiments
to assess the performance of state-of-the-art Sign Language
Recognition models utilizing on our dataset. The findings indicate that utilizing multi-view data substantially enhances model accuracy across all models, with a maximum
performance improvement of up to 19.75% compared to
models trained on single-view data.

## Data
Video data download link: https://drive.google.com/drive/folders/1yUU1m2hy_CjaXDDoR_6i9Y3T1XL2pD4C?usp=sharing

## Checkpoints
Checkpoints download link: https://drive.google.com/drive/folders/1l820AALsFHOxnFVQiJR82eNkKVTv91mj?usp=sharing

## Setting up
1. Set up envs: pip install -r requirements.txt
2. Download checkpoint from above link and save as /checkpoints
3. Download data from data link and save as /Yolo_dataset/Blur_video
   
## Training and Testing
Run our models using the following commands:

"python main.py --config" + config file (configs/model_name/data_size/.yaml_file)

-Note: Before running, modify the config file parameter such as: device, pretrained, batch_size, etc. All the config file can be found in folder '/config'

#### Example: Model I3D in 1-1000 dataset
##### Training
One-view: python main.py --config configs/i3d/label_1_1000/i3d_one_view_from_AUTSLyaml

Three-view: python main.py --config configs/i3d/label_1_1000/i3d_three_view_finetune_from_one_view.yaml

##### Testing 
One-view: python main.py --config configs/i3d/test_cfg/label_1_1000/i3d_one_view_from_autsl.yaml

Three-view: python main.py --config configs/i3d/test_cfg/label_1_1000/i3d_three_view_finetune_from_one_view.yaml
