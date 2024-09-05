


# 
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
  










💥💥💥

## Install


Please refer [Install](https://github.com/likyoo/open-cd/blob/main/docs/inference.md) doc.
Or refer to [Install opencd](https://github.com/likyoo/open-cd).




## Usage

#### Test
```
# get .png results
python tools/test.py configs/ban/ban_vit-l14-clip_mit-b2_512x512_40k_levircd.py ./baan_cscd_adamW-1e-3-Cos-new/best_mIoU_iter_12000.pthh --show-dir images
# get metrics
python tools/test.py configs/ban/ban_vit-l14-clip_mit-b2_512x512_40k_levircd.py ./baan_cscd_adamW-1e-3-Cos-new/best_mIoU_iter_12000.pth
```


#### Train
```
python tools/train.py configs/ban/ban_vit-l14-clip_mit-b2_512x512_40k_levircd.py --work-dir ./changer_r18_levir_workdir
```





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


## License

Open-CD is released under the Apache 2.0 license.


## Contact Us

If you have other questions❓, please contact us in time 👬
