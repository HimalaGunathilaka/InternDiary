# Eval table

| Model           | [[#^mAP50\|mAP50]]  | [[#^mAP50-95\|mAP50-95]] | [[#^precision\|Precision]] | [[#^recall\|Recall]]   |
| --------------- | ------------------- | ------------------------ | -------------------------- | ---------------------- |
| [[#^model1\|1]] | 0.25256805293022916 | 0.2079214979769584       | 0.37777777777777777        | 0.096045197740113      |
| [[#^model5\|5]] | 0.42332040635699253 | 0.11938964926187415      | 0.6585409611165236         | 0.3922725827411971     |
| Mine            | 0.6215909236652978  | 0.36601026054804986      | 0.==6844062398990213==     | ==0.5649717514124294== |
|                 |                     |                          |                            |                        |
|                 |                     |                          |                            |                        |


---
### Model Source
1. https://www.kaggle.com/code/ztrollk/license-plate-detection-with-yolov8/output ^model1
2. https://www.kaggle.com/code/mclikmb4/vehicle-license-plate-detection-vgg16/notebook#Convolutionnal-Neural-Network ^model2
3. https://www.kaggle.com/code/gowrishankarp/license-plate-detection-yolov5-pytesseract/notebook ^model3
4. https://www.kaggle.com/code/aslanahmedov/automatic-number-plate-recognition/notebook ^model4
5. https://github.com/Muhammad-Zeerak-Khan/Automatic-License-Plate-Recognition-using-YOLOv8 ^model5
6. https://github.com/Brahmiraj-Tharmapalan/NumberPlate_Detection ^model6
---
# Model evaluation
- https://mookpreeyanuch.medium.com/a-beginners-guide-to-model-evaluation-in-machine-learning-6e4ad4a844b2

---
# Evaluation criterias
- **Confusion matrix** - `N x N` matrix where N is the number of target classes. Represents number of actual outputs and predicted outputs.
	![[Pasted image 20260304162557.png]]

	![[Pasted image 20260304162640.png]]
- **Accuracy** - Ratio of the number of correct predictions to the number of predictions.$$\text{Accuracy} = \frac{TP + TN}{TP+TN+FP+FN}$$ ^accuracy
	- Accuracy has a drawback. It cannot perform well on an imbalanced dataset.

- **Precision**-----> <span style="color:rgb(255, 0, 0)">Measures the proportion of correct positive predictions out of all the predicted values</span>.$$\text{Precision} = \frac{TP}{TP+FP}$$ ^precision

- **Recall** ----> <span style="color:rgb(255, 0, 0)">Out of all the actual positive cases, how many did the model correctly find</span>.$$\text{Recall} = \frac{TP}{TP+FN}$$ ^recall
	- **TP (True Positives)** = correctly predicted positives
	- **FN (False Negatives)** = positives the model missed

- **F1 score**----> Is the harmonic mean of precision and recall.$$\text{F1 score} = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision}+\text{Recall}}$$ ^f1

- **AUC-ROC curve** -----> Commonly used for evaluating binary classification models. ^auc
---
## YOLO evaluation 

- **Intersection over union** / IOU - A measure that quantifies the overlap between a predicted [bounding box](https://www.ultralytics.com/glossary/bounding-box) and a ground truth bounding box. It plays a fundamental role in evaluating the accuracy of object localization.
- **Average precision** - AP computes the area under the precision-recall curve, providing a single value that encapsulates the model's precision and recall performance.
- **Mean average precision** / mAP - mAP extends the concept of AP by calculating the average AP values across multiple object classes. This is useful in multi-class object detection scenarios to provide a comprehensive evaluation of the model's performance.
- **mAP50** ----- Mean average precision calculated at an intersection over union (IoU) threshold of 0.50. It's a measure of the model's accuracy considering only the "easy" detections. ^mAP50
- **mAP50-95** -------- The average of the mean average precision calculated at varying IoU thresholds, ranging from 0.50 to 0.95. It gives a comprehensive view of the model's performance across different levels of detection difficulty. ^mAP50-95
![[Pasted image 20260311121311.png|302]]

https://youtu.be/oqXDdxF_Wuw

