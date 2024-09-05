python tools/test.py configs/ban/ban_vit-l14-clip_mit-b2_512x512_40k_levircd.py ./baan_cscd_adamW-1e-3-Cos-new/best_mIoU_iter_12000.pth


# FFO
Code for A Change Detection Network and Dataset for Housekeeping in Construction Sites.



 <img src="ffo.jpg" width="100%">


 
## Environment
- The code is tested on Ubuntu 20.04.2, python 3.8, cuda 11.1.


## Installation
 1. Install pytorch

  ```bash
  pip install torch==1.8.0+cu111 torchvision==0.9.0+cu111 torchaudio==0.8.0 -f https://download.pytorch.org/whl/torch_stable.html
  ```

 2. Clone this repository
  ```bash
  git clone https://github.com/kailaisun/FFO
  ```
  
 3. Install 
  ```bash
  pip install -r requirements.txt
  ```
  

## Test
### SCM ( Scene-based counting method)

```Bash
python people_detect.py --path <video_path>
```
- Result of SCM


![image](https://raw.githubusercontent.com/kailaisun/FFO/main/gif/1.gif)
- You can modify hyperparameters of JointDet module in person_detect.py.
```python 
 result_info = joint_de(head_info, other_info,thresh=0.8,conf=0.6,thresh1=0.8)  #line 50
```
### LCM ( Line-based counting method)
- peopeo_count.py conducts LCM (YOLOX+Deepsort) of indoor view.
- After you obtained the sequences of two-vision LCM:
```Bash
python joint.py
```
- Note that in overhead entrance counting method our video frame rate is downsampled to one-fifth of the original video.
- Result of YOLOX+Deepsort


![image](https://raw.githubusercontent.com/kailaisun/FFO/main/gif/2.gif) 


    label of indoor view LCM
    ```
    frame: i, in/out num: y
    frame: k, in/out num: y
    .
    .
    .
    ```
    label of overhead view LCM
    ```
    frame: i, num: y
    frame: i+1, num: y
    frame: i+2, num: y
    .
    .
    .
    ```

### DBF

```bash 
pytho main.py
```

## Citation

Please refer to the following bibtex to cite.

```
@article{SUN2022109631,
title = {A fusion framework for vision-based indoor occupancy estimation},
        journal = {Building and Environment},
        volume = {225},
        pages = {109631},
        year = {2022},
        issn = {0360-1323},
        doi = {https://doi.org/10.1016/j.buildenv.2022.109631},
        author = {Kailai Sun and Peng Liu and Tian Xing and Qianchuan Zhao and Xinwei Wang}
}
```



## Contact Us

If you have other questions❓, please contact us in time 👬






💥💥💥

## Usage

[Docs](https://github.com/open-mmlab/mmsegmentation/tree/master/docs)

Please refer to [get_started.md](https://github.com/open-mmlab/mmsegmentation/blob/master/docs/en/get_started.md#installation) in mmseg.

A Colab tutorial is also provided. You may directly run on [Colab](https://colab.research.google.com/drive/1puZY5R8fwlL6um6pHbgbM1NTYZUXdK2J?usp=sharing). (thanks to [@Agustin](https://github.com/AgustinNormand) for this demo) [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1puZY5R8fwlL6um6pHbgbM1NTYZUXdK2J?usp=sharing)

#### Install

```
# Install OpenMMLab Toolkits as Python packages
pip install -U openmim
mim install mmengine
mim install "mmcv>=2.0.0"
mim install "mmpretrain>=1.0.0rc7"
pip install "mmsegmentation>=1.2.2"
pip install "mmdet>=3.0.0"
```
```
git clone https://github.com/likyoo/open-cd.git
cd open-cd
pip install -v -e .
```
For more details, please see [here](https://github.com/likyoo/open-cd/blob/main/docs/install.md).

#### Train
```
python tools/train.py configs/changer/changer_ex_r18_512x512_40k_levircd.py --work-dir ./changer_r18_levir_workdir
```

#### Test
```
# get .png results
python tools/test.py configs/changer/changer_ex_r18_512x512_40k_levircd.py changer_r18_levir_workdir/latest.pth --show-dir tmp_infer
# get metrics
python tools/test.py configs/changer/changer_ex_r18_512x512_40k_levircd.py changer_r18_levir_workdir/latest.pth
```

#### Infer
Please refer [inference](https://github.com/likyoo/open-cd/blob/main/docs/inference.md) doc.


## Citation

If you find this project useful in your research, please cite:

```bibtex
@article{opencd,
  title   = {{Open-CD}: A Comprehensive Toolbox for Change Detection},
  author  = {Li, Kaiyu and Jiang, Jiawei and Codegoni, Andrea and Han, Chengxi and Deng, Yupeng and Chen, Keyan and Zheng, Zhuo and
             Chen, Hao and Zou, Zhengxia and Shi, Zhenwei and Fang, Sheng and Meng, Deyu and Wang, Zhi and Cao, Xiangyong},
  journal= {arXiv preprint arXiv:2407.15317},
  year={2024}
}
```
You might also consider citing:

```bibtex
@ARTICLE{10438490,
  author={Li, Kaiyu and Cao, Xiangyong and Meng, Deyu},
  journal={IEEE Transactions on Geoscience and Remote Sensing}, 
  title={A New Learning Paradigm for Foundation Model-based Remote Sensing Change Detection}, 
  year={2024},
  volume={},
  number={},
  pages={1-1},
  keywords={Adaptation models;Task analysis;Data models;Computational modeling;Feature extraction;Transformers;Tuning;Change detection;foundation model;visual tuning;remote sensing image processing;deep learning},
  doi={10.1109/TGRS.2024.3365825}}

@ARTICLE{10129139,
  author={Fang, Sheng and Li, Kaiyu and Li, Zhe},
  journal={IEEE Transactions on Geoscience and Remote Sensing}, 
  title={Changer: Feature Interaction is What You Need for Change Detection}, 
  year={2023},
  volume={61},
  number={},
  pages={1-11},
  doi={10.1109/TGRS.2023.3277496}}
```

## License

Open-CD is released under the Apache 2.0 license.
