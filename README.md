# GLAM-to-segment-video
* Writer: Keer Zhang
* Time: 4/6/2024~26/8/2024



install grounding-dino:

```python
import os
HOME = '/path/to/your/root'

%cd {HOME}
!git clone https://github.com/IDEA-Research/GroundingDINO.git
%cd {HOME}/GroundingDINO
!git checkout -q 57535c5a79791cb76e36fdb64975271354f10251
!pip install -q -e .
```

Install segment-anything:

```python
import os
HOME = '/path/to/your/root'

%cd {HOME}

import sys
!{sys.executable} -m pip install 'git+https://github.com/facebookresearch/segment-anything.git'
```

Install segment-anything2:

```python
!git clone https://github.com/facebookresearch/segment-anything-2.git
cd segment-anything-2 
!pip install -e .
```



Introductions for files:

* yolo_dino_sam2.ipynb

  * Using yolo, grounding-ding and segment-anything2 model to segment video
  * Generate video with whole masks

* class_description.json

  * File for yolo_dino_sam2.ipynb

* get_gaze_positions_yolo.ipynb

  * Apply gaze on yolo-segmented video
  * Generate table 'yolo_gazed.csv' include detailed information about gaze

* get_gaze_positions_dino_sam2.ipynb

  * Apply gaze on yolo-segmented video

  * Generate table  'dino_sam2_gazed.csv' include detailed information about gaze

* pgd_attack.ipynb

  * Using PGD algorithm to add noise into video
  * Generate video with noise
  * Compare original video with noise video
  * Generate IoU and Dice to prove whether model is robust

* analyze.ipynd

  * Merge two table ( 'yolo_gazed.csv'  and 'dino_sam2_gazed.csv')

  * Generate table 'merged_gazed.csv'

  * Analyze Saliency, Frequency and Persistency of each object detected

    

