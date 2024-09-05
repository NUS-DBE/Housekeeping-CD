


# 
Code for A Change Detection Network and Dataset for Housekeeping in Construction Sites.



 <img src="1.png" width="100%">

 <img src="2.png" width="100%">
 

 



## Install


Please refer [Install](https://github.com/likyoo/open-cd/blob/main/docs/inference.md) doc.
Or refer to [Install opencd](https://github.com/likyoo/open-cd).




## Usage

#### Test
```
# get metrics
python tools/test.py configs/hcdn/hcdn_vit-l14-clip_mit-b2_512x512_40k_levircd.py ./best.pth

# get .png results
python tools/test.py configs/hcdn/hcdn_vit-l14-clip_mit-b2_512x512_40k_levircd.py ./best.pth --show-dir images
```


#### Train
```
python tools/train.py configs/hcdn/hcdn_vit-l14-clip_mit-b2_512x512_40k_levircd.py --work-dir ./hcdn_workdir
```




08/05 20:04:37 - mmengine - INFO - 
+-----------+--------+-----------+--------+-------+-------+
|   Class   | Fscore | Precision | Recall |  IoU  |  Acc  |
+-----------+--------+-----------+--------+-------+-------+
| unchanged | 91.46  |   92.33   | 90.61  | 84.27 | 90.61 |
|  changed  | 81.14  |   79.49   | 82.86  | 68.27 | 82.86 |
+-----------+--------+-----------+--------+-------+-------+
08/05 20:04:37 - mmengine - INFO - Iter(val) [141/141]    aAcc: 88.2500  mFscore: 86.3000  mPrecision: 85.9100  mRecall: 86.7400  mIoU: 76.2700  mAcc: 86.7400  data_time: 0.0051  time: 0.6723
08/05 20:04:37 - mmengine - INFO - The previous best checkpoint /backup/skl2/skl/open-cd/baan_cscd_adamW-1e-3-Cos-new/best_mIoU_iter_8000.pth is removed
08/05 20:04:41 - mmengine - INFO - The best checkpoint with 76.2700 mIoU at 12000 iter is saved to best_mIoU_iter_12000.pth.
09/05 15:10:09 - mmengine - INFO - Iter(test) [50/70]    eta: 0:00:16  time: 0.6893  data_time: 0.0065  memory: 9526
09/05 15:10:23 - mmengine - INFO - per class results:
09/05 15:10:23 - mmengine - INFO -
+-----------+--------+-----------+--------+-------+-------+
|   Class   | Fscore | Precision | Recall |  IoU  |  Acc  |
+-----------+--------+-----------+--------+-------+-------+
| unchanged | 92.61  |   93.84   | 91.41  | 86.24 | 91.41 |
|  changed  | 80.73  |   78.06   | 83.59  | 67.69 | 83.59 |
+-----------+--------+-----------+--------+-------+-------+
09/05 15:10:23 - mmengine - INFO - Iter(test) [70/70]    aAcc: 89.3200  mFscore: 86.6700  mPrecision: 85.9500  mRecall: 87.5000  mIoU: 76.9700  mAcc: 87.5000  data_time: 0.0105  time: 0.7701




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

💥💥💥

## License

Open-CD is released under the Apache 2.0 license.


## Contact Us

If you have other questions❓, please contact us in time 👬
