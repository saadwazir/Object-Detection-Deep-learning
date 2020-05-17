# Object-Detection-Deep-learning
## Acknowledgment
This repo contains code from several github repos - Thankx to them :)

retinanet : https://github.com/fizyr/keras-retinanet

yolo : https://github.com/experiencor/keras-yolo3

Faster-RCNN : https://github.com/RockyXu66/Faster_RCNN_for_Open_Images_Dataset_Keras

-----------------------------------------------------

## Faster - RCNN
```
Dataset  consist of images of folder and train, test csv file which contain information in the following format 
filename,x1,y1,x2,y2,class_name

```
```
Training and Testing
For training and testing run following jupyter notebook files
frcnn_train_vgg.ipynb
frcnn_test_vgg.ipynb
Change the folder paths and run all the cells
```

```
Faster RCNN Results
Epoch 306/310
Mean number of bounding boxes from RPN overlapping ground truth boxes: 14.390728476821192
Classifier accuracy for bounding boxes from RPN: 0.8433333333333334
Loss RPN classifier: 0.1274503849853871
Loss RPN regression: 0.08873817281487087
Loss Detector classifier: 0.42768263728668293
Loss Detector regression: 0.13990973714273422
Total loss: 0.7837809322296752
mAP: 0.440
```

## Yolo3
```
Dataset must be in the form of PASCL VOC dataset

```
```
Training and Testing

For training and testing run following jupyter notebook file
Yollo3.ipynb
Run the cells respectively and change the paths
```
```
Yolo3 Results

airliner: 0.9178
boat: 0.9566
bus: 0.8522
car: 0.8410
chartered: 0.7598
fighter: 0.0000
helicopter: 0.0000
longvehicle: 0.6364
other: 0.0000
propeller: 1.0000
pushbacktruck: 0.0000
stairtruck: 0.3243
trainer: 0.9667
truck: 0.3535
van: 0.5415
mAP: 0.5433
```
## Retinanet
```
Dataset must be in the form of PASCL VOC dataset

```
```
Training and Testing

Command for training - change the paths
retinanet-train --freeze-backbone --backbone resnet50 --no-resize --compute-val-loss --random-transform --weights C:\Users\saad\simd\keras-retinanet/weights/resnet50_coco_best_v2.h5 --batch-size 8 --steps 100 --epochs 100 --multiprocessing --compute-val-loss --weighted-average --snapshot-path C:\Users\saad\simd\keras-retinanet/snapshots csv annotations.csv classes.csv

Commands for testing - change the paths
retinanet-convert-model C:\Users\saad\simd\keras-retinanet\snapshots\resnet50_csv_40.h5 C:\Users\saad\simd\keras-retinanet\converted_model\out.h5
retinanet-evaluate csv test_data_ratina.csv classes.csv C:\Users\saad\simd\keras-retinanet\converted_model\out.h5
```
```
Retinanet results on Test Set:

3679 instances of class car with average precision: 0.7030
874 instances of class van with average precision: 0.1820
446 instances of class truck with average precision: 0.1681
367 instances of class bus with average precision: 0.2204
85 instances of class others with average precision: 0.0042
161 instances of class airliner with average precision: 0.7445
83 instances of class stair_truck with average precision: 0.0032
55 instances of class pushback_truck with average precision: 0.0001
222 instances of class lang_vehicle with average precision: 0.1297
25 instances of class propeller_aircraft with average precision: 0.1230
103 instances of class charted_aircraft with average precision: 0.2123
9 instances of class helicopter with average precision: 0.0889
49 instances of class trainer_aircraft with average precision: 0.0421
1820 instances of class boat with average precision: 0.6747
8 instances of class fighter_aircraft with average precision: 0.0250
Inference time for 748 images: 0.3295
mAP using the weighted average of precisions among classes: 0.5393
mAP: 0.2214
```
