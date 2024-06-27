# Plant-Disease-Detection-YOLOv5

## Dataset

The dataset was prepared by manually selecting images from the [PlantVillage](https://arxiv.org/pdf/1511.08060v2) and the [PlantDoc](https://arxiv.org/abs/1911.10317) datasets. The selected images were then annotated using the Computer Vision Annotation Tool ([CVAT](https://www.cvat.ai/)). These images were used to perform a comparative study of different object detection models for plant disease detection. Our results of this study were published at the Computing Conference 2024. If you are interested in using this custom dataset and our annotations, please consider citing our papers-
```
@inproceedings{sadi2024comparative,
  title={A Comparative Study on Plant Diseases Using Object Detection Models},
  author={Sadi, Abu Adnan and Hossain, Ziaul and Ahmed, Ashfaq Uddin and Shad, Md Tazin Morshed},
  booktitle={Science and Information Conference},
  pages={419--438},
  year={2024},
  organization={Springer}
}
```

## Implementation

The YOLOv5 and Scaled-YOLOv4 implementations are cloned from the following repositories-
- <https://github.com/ultralytics/yolov5>
  - Use Command:
    ```
    !git clone https://github.com/ultralytics/yolov5 
    ```
- <https://github.com/roboflow-ai/ScaledYOLOv4.git> (which is also forked from <https://github.com/WongKinYiu/ScaledYOLOv4>)
  - Use Command:
    ```
    !git clone https://github.com/roboflow-ai/ScaledYOLOv4.git
    ```

## How to Run
- First, the 'dataset.yaml' file must be configured appropriately with information such as dataset directory, number of classes, and class names. The 'dataset.yaml' file can be found inside the cloned model implementation folder. For example:
  ```
  YOLOv5/yolov5/dataset.yaml.
  ```
- The models can be trained by using the 'Training_and_Inference' notebooks provided inside the 'YOLOv5' and 'Scaled YOLOv4' folders.
- The models can also be trained by directly running the commands in the console (which I personally prefer). In this case, the repository for the model implementation must be cloned in the local directory beforehand. Some example commands:
  - Command for training:
   ```
   !python train.py --img 256 --batch 16 --epochs 50 --data dataset.yaml --weights yolov5s.pt --cache
   ```
  - Command for inference:
    ```
    !python detect.py --weights best.pt --img 256 --conf 0.25 --source image_name.jpg
    ```
- The results and model weights are saved inside the 'runs' folder (which is located in the cloned model implementation folder) after training is complete.
