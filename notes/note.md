RGB-D tum yolo Eample:

```
./Examples/RGB-D/rgbd_tum_yolo Vocabulary/ORBvoc.txt Examples/RGB-D/TUM3.yaml ~/Downloads/datasets/TUM_RGBD/rgbd_dataset_freiburg3_walking_xyz Examples/RGB-D/associations/fr3_walking_xyz.txt
```

对比[ORB_SLAM2](https://github.com/JimGreenJaguar/ORB_SLAM2)与[YOLO-DynaSLAM](https://github.com/JimGreenJaguar/YOLO-DynaSLAM)二者在动态场景下的性能:

使用TUM_RGB-D Dynamic Objects的fr3_walking_xyz数据集进行了实验，并使用TUM [useful tools](https://vision.in.tum.de/data/datasets/rgbd-dataset/tools)进行了评估：

ORB_SLAM2的结果如下：

```bash
python tools/evaluate_ate.py results/CameraTrajectory_fr3_walking_xyz.txt ~/Downloads/datasets/TUM_RGBD/rgbd_dataset_freiburg3_walking_xyz/groundtruth.txt --plot ORB_SLAM2-fr3_walking_xyz.png
0.730144
```

![ORB_SLAM2-fr3_walking_xyz](/home/mate/src/ORB_SLAM2/results/ORB_SLAM2-fr3_walking_xyz.png)

```bash
python tools/evaluate_ate.py results/KeyFrameTrajectory_fr3_walking_xyz.txt ~/Downloads/datasets/TUM_RGBD/rgbd_dataset_freiburg3_walking_xyz/groundtruth.txt --plot ORB_SLAM2-Keyframe-fr3_walking_xyz.png
0.654843
```

![ORB_SLAM2-Keyframe-fr3_walking_xyz](/home/mate/src/ORB_SLAM2/results/ORB_SLAM2-Keyframe-fr3_walking_xyz.png)

YOLO-DynaSLAM的结果如下：

```bash
python tools/evaluate_ate.py results/CameraTrajectory_fr3_walking_xyz.txt ~/Downloads/datasets/TUM_RGBD/rgbd_dataset_freiburg3_walking_xyz/groundtruth.txt --plot YOLO-DynaSLAM-fr3_walking_xyz.png
0.072051
```

![YOLO-DynaSLAM-fr3_walking_xyz](/home/mate/src/YOLO-DynaSLAM/results/YOLO-DynaSLAM-fr3_walking_xyz.png)

```bash
python tools/evaluate_ate.py results/KeyFrameTrajectory_fr3_walking_xyz.txt ~/Downloads/datasets/TUM_RGBD/rgbd_dataset_freiburg3_walking_xyz/groundtruth.txt --plot YOLO-DynaSLAM-Keyframe-fr3_walking_xyz.png
0.093899
```

![YOLO-DynaSLAM-Keyframe-fr3_walking_xyz](/home/mate/src/YOLO-DynaSLAM/results/YOLO-DynaSLAM-Keyframe-fr3_walking_xyz.png)

结论：

在动态场景中（以本数据序列为例），[YOLO-DynaSLAM](https://github.com/JimGreenJaguar/YOLO-DynaSLAM)的性能优于[ORB_SLAM2](https://github.com/JimGreenJaguar/ORB_SLAM2)。