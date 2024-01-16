This place is more for theory about object detection.




IOU metric:
Most used Dataset is COCO Dataset. We also have pyccotools package to easily inspect COCO dataset related tasks.

WE see terms like `AP   |  AP50  |  AP75  |  APs   |  APm   |  APl   ` in mesuring Accuracy of this model.
- AP: Average precision
- AP50: how much will be average precision, if threshold is 50%.
- AP75: how much will be average precision, if threshold is 75%.
- APs: AP for small objects.
- APm: AP for medium-sized objects.
- APl: AP for large objects.

As per COCO dataset:
- Small objects: Those with a bounding box area smaller than 32^2 (32x32 pixels).
- Medium objects: Those with a bounding box area between 32^2 and 96^2.
- Large objects: Those with a bounding box area larger than 96^2.

