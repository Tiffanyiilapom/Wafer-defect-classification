# Wafer-defect-classification
Accurate defect classification in wafer manufacturing is essential for ensuring product quality, production efficiency, and reliability, as defects can adversely impact the functionality of semiconductor chips. Advanced technologies, such as high-resolution imaging and machine learning, are employed to identify and classify defects rapidly, enabling timely actions to improve production outcomes.

## Dataset Description
- Wafer defect type
  ![image](https://github.com/user-attachments/assets/99d937de-755d-4754-9eee-782d4ce4fa0a)
- Sample sizes among categories
  
  - Center : 3462
  - Donut : 409
  - Edge-Loc : 2417
  - Edge-Ring : 8554
  - Loc : 1620
  - Near-full : 54
  - Random : 609
  - Scratch : 500

## Methods
### Undersampling
Due to class imbalance, SMOTE was tested for oversampling with moderate results but nothing particularly outstanding. Given limited computational resources, random undersampling was chosen to reduce the overrepresented classes.
### Augmentation
Use data augmentation techniques to increase the sample size, balancing each class to a similar total amount. The methods used include rotation, horizontal flip, and vertical flip. Random cropping was avoided, as it could lead to misclassification (for example, cropping a "Donut" image could turn it into a "Near-full" class).
### Grayscale
Since the images mainly contain green dots for regular points and yellow dots for defects, grayscale was chosen after several experiments and limited computational resources.
### Normalize
The pixel values of the images were standardized and scaled to a range with a mean of 0 and a standard deviation of 1, which can accelerate model convergence and reduce instability during training caused by large feature value ranges.
### VGG
VGG (Visual Geometry Group) is a convolutional neural network architecture known for its simplicity and depth. This architecture performs exceptionally well in image classification tasks and has been widely used in various computer vision applications.
### Focal Loss
Focal Loss is a loss function designed to address class imbalance and is handy for object detection and imbalanced datasets. It adds a modulating factor to the standard cross-entropy loss, reducing the loss contribution from easily classified examples and focusing more on hard-to-classify samples.
