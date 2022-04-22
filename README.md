# bosch
Multi-box detector for Bosch challenge

## The notebook "bosch_challenge.ipynb":

### - Downloads the SVIRO dataset (images and bounding box labels for BMW-I3 – whole sceneries in Grayscale):
#### (i3: 2000 train images and 500 test images)
#### only bmw-i3 for that challenge, but all brands can be used together in the future;
#### whole sceneries: I think it's more realistic than rectangular single seats;
#### grayscale is lighter and it's enough for this challenge.

### - Clones Yolo v5 project from https://github.com/ultralytics/yolov5
#### Yolo achieves state-of-the-art results beating other real-time object detection algorithms by a large margin

### - Creates a new dataset structure

### - Moves 1/5 of train data to validation data

### - Creates 3 description files for training

### - Converts SVIRO dataset to Yolo format
#### convert labels to the correct format to use with yolo v5 and apply normalization
#### SVIRO: [class_label], [x_upper_left_corner], [y_upper_left_corner], [x_lower_right_corner], [y_lower_right_corner]
#### YOLO : [class_label] [x_center] [y_center] [width] [height] --> 'normalized and separated by space'

### - Shows a class distribution analysis through a bars graph visualization

### - Trains using sviro.yaml file that contains the 5 classes:
#### ['Empty', 'Empty infant seat', 'Empty child seat', 'Adult', 'Everyday object']
#### Yolo small architecture (yolov5s.yaml), and weights from the model: yolov5s.pt, using batch-size of 16 and 10 epochs only.

### - Results accuracy of more that 0.90% for some images in test dataset. But it could be better training with more epochs!!

## It was manually saved a "history" directory to shows the results after running this notebook.  
### - "history/detection outputs" directory shows only 50 test images with bounding box predictions and its accuracy
### - "history/train outputs" directory shows the training metrics: precision, recall, F1, loss curve, confusion matrix, etc
### - "history/train outputs/weights" contains the trained models.
