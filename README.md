# Bachelor Thesis Project

This repository contains the code and instructions for various components of the Bachelor Thesis project, including training YOLO-v9, image stitching, and 3D object detection using the NuScenes and NuImages datasets.

## Installation

Follow the instructions below to set up the NuScenes Devkit and the required datasets.

### 1. NuScenes Devkit

1. Clone the NuScenes Devkit repository:

    ```sh
    git clone https://github.com/nutonomy/nuscenes-devkit.git
    cd nuscenes-devkit
    ```

2. Install the required dependencies:

    ```sh
    pip install -r setup/requirements.txt
    ```

3. Follow the instructions in the [NuScenes Devkit repository](https://github.com/nutonomy/nuscenes-devkit) to set up NuImages and NuScenes datasets.

## Training YOLO-v9

To train YOLO-v9, first convert the NuImages dataset to a standard YOLO dataset format using the `Nuimage_dataset_to_yolo_dataset.ipynb` notebook.

1. Add the `render_image_2` function from the `nuimages.py` file in the NuScenes Devkit repo to the NuImages package located at `/nuscenes/lib/python3.7/site-packages/nuimages/nuimages.py`.

2. Follow the instructions from the [YOLOv9 repository](https://github.com/WongKinYiu/yolov9) to train, use, and replicate YOLOv9.

3. Our best model's weights can be found [here](https://drive.google.com/drive/folders/12b7a8DV96sZRReExGAgT9hX-nDmjczW8?usp=sharing).

## Image Stitching

For stitching multiple images, we have implemented a method based on [this paper](https://ieeexplore.ieee.org/document/9841307).

1. Add the `get_corresponding_points()` function to the `NuScenes.py` file in the NuScenes Devkit repo located at `/nuscenes/lib/python3.7/site-packages/nuscenes/nuscenes.py`.

## 3D Object Detection

For 3D object detection, use Single Lift Neural Networks and preprocess the data using the `datasetmaker` notebook.

1. Use the `2D-to-3D` trainer provided in the repository. We provide examples for both variants: without LiDAR and with direct LiDAR.

2. Adapt the `datasetmaker` by adding the `make_grid` function, which includes either the 'coloring' (distances) or directly adding the LiDAR points.

3. You can visualize and examine the outputs using the `validate.ipynb` notebook.
