This is the code base of my Bachelor Thesis.

Please follow instructions to install the NuScenes Devkit --> https://github.com/nutonomy/nuscenes-devkit with NuImages and Nuscenes.

# Train YOLO-v9
In order to train YOLOv9 I first converted the NuImages dataset to a standard yolo dataset format using Nuimage_dataset_to_yolo_dataset.ipynb notebook.
To use this add the render_image_2 function from the nuimages.py file in the repo to the nuimages package (/nuscenes/lib/python3.7/site-packages/nuimages/nuimages.py).
Then follow the instructions from their repository. https://github.com/WongKinYiu/yolov9 and you can train/use/replicate it.
Our best model's weight can be found at --> https://drive.google.com/drive/folders/12b7a8DV96sZRReExGAgT9hX-nDmjczW8?usp=sharing

# Image Stitching
For stitching multiple images we have implemented a stitching method based on https://ieeexplore.ieee.org/document/9841307
Add the get_corresponding_points() function to the NuScenes.py file in the NuScenes repo. (/nuscenes/lib/python3.7/site-packages/nuscenes/nuscenes.py).

# 3D object Detection
For 3D object detection, use Single Lift Neural Networks and preprocess the data using the datasetmaker notebook. 
Then use our 2D-to-3D trainer. We provide examples for both variants: without LiDAR and with direct LiDAR.
Ensure to adapt the datasetmaker by adding the make_grid function, which includes either the 'coloring' (distances) or directly adding the LiDAR points.
You can visualize and examine the outputs using the validate.ipynb notebook.
