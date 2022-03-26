# Neural 3D Video Synthesis Dataset

This repository contains the dataset used for the CVPR paper "Neural 3D Video Synthesis from Multi-View Video".

[Project Page](https://neural-3d-video.github.io/) | [Paper](https://neural-3d-video.github.io/resources/paper.pdf) | [Video](https://neural-3d-video.github.io/) | [License: CC-BY-NC 4.0](LICENSE)

Check the [Release Page](https://github.com/facebookresearch/Neural_3D_Video/releases/tag/v1.0) for all the datase files.

Each of the dataset contains the following files
```
cam00.mp4
cam01.mp4
cam02.mp4
...
cam19.mp4
cam20.mp4
poses_bounds.npy
```

All the *.mp4 files are the processed synchronized videos compressed in mp4 format. The poses_bounds.npy files stores the camera pose information for each video. The details of format can refer to [NeRF dataset pose format](https://github.com/bmild/nerf#generating-poses-for-your-own-scenes).

Notes:
* For all the dataset, cam00.mp4 is the center reference camera which we held out for testing.
* We have already filtered out the camera stream that is either unsynchronized, or have significant inconsistency in observations. If a camera stream ID does not exist in the folder, this is the invalid camera stream that has been filtered.
* The poses_bounds.npy store all the camera poses correspond to their sequential sorted order in the folder. If cam03.mp4 does not exist in the final folder, it does not contain the pose for that. The length of total cameras in the poses_bounds.npy file should be equal to the total number of valid video streams.
