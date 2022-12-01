# Cattle Counter Application

The Cattle Counter Application invloves feeding a image or a video of cattle and the application will detect the cattle present in the image/video. The application afte processing the image will return the count of the detected cattle.

## Tech Stacks Used
- OpenCV
- TensorFlow

## Dataset
Collected images from various online sources and merged them into a single dataset.

## Methodology

Using a seqential model to train the data.
The below presented flowchart represents the the model training process.

```mermaid
graph TD;
    Dataset-->Sequential_Model;
    Sequential_Model-->Save_best_model;
```

After training the model, the accuracy of the dataset was realised to be. Along with validation accuracy to be.

After the best model has been saved, a new image is fed into the model where the model detects the cattle present in the new image. Using OpenCV, we draw bounding boxes around the detected cattle. After call the cattle have been detected, a counter is placed to keep a count on the number of bounding boxes present.
The prpcess can be defined by the below presented flowchart.

```mermaid
graph TD;
    Image-->Predict_through_saved_model;
    Predict_through_saved_model-->Detect_cattle;
    Detect_cattle-->Draw_box_around_detected_cattle;
    Draw_box_around_detected_cattle-->Add_counter_according_to_number_of_boxes;
    Add_counter_according_to_number_of_boxes-->Print_Counter;
```
