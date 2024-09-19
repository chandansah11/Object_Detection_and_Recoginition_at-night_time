#Overview
The aim of this project was to develop an object detection model using Convolutional Neural Networks (CNNs) to classify and detect objects in real-time video. The workflow involved two primary stages:

#Training and saving a deep learning model capable of object detection.
Applying the trained model to video frames for object detection, drawing bounding boxes, and providing classification labels with confidence scores.

#Part 1: Model Training and Development

Model Architecture
A CNN-based architecture was developed using TensorFlow and Keras libraries. The dataset used for training contained images of various objects (such as bicycles, boats, buses, cats, etc.) labeled with bounding box coordinates and class names. The model comprised several convolutional layers followed by max-pooling and dense layers, allowing it to learn hierarchical features of the images.
The model was compiled using the Adam optimizer and categorical cross-entropy loss due to the multi-class classification nature of the task.

Model Training

The model was trained on the labeled dataset over multiple epochs, adjusting its weights to minimize classification error. The dataset was split into training and validation sets to ensure that the model generalized well to unseen data.

Model Saving

After achieving a satisfactory level of accuracy, the trained model was saved to a file to be reused for object detection tasks in video streams.

#Part 2: Object Detection in Video

Loading the Model
The saved model was loaded for performing object detection on video frames. To ensure efficient use of resources, GPU memory growth was configured, optimizing the performance of the model during video processing.

Class Names

The model was trained to detect and classify the following object classes: bicycle, boat, bottle, bus, car, cat, chair, cup, dog, motorbike, people, and table.

Video Processing Pipeline

A video stream was processed using the OpenCV library, capturing frames from the video file. Each frame was resized to match the input size expected by the model, and the model was used to predict the objects in the frame. After detecting objects, bounding boxes were drawn around the detected objects, along with class labels and confidence scores. These annotated frames were then saved to a new video file.

#Results

Model Accuracy: The model achieved an accuracy of over 85% on the validation set, correctly identifying most of the objects from the dataset.
Video Processing: The object detection model was successfully applied to real-time video. Detected objects, such as cars, bicycles, and people, were labeled with bounding boxes and displayed in the video with their respective confidence scores.

#Future Improvements

Bounding Box Regression: The current implementation displays only class labels and confidence scores. Future improvements could involve implementing bounding box regression for accurate localization of objects.
Multi-object Detection: Enhancements such as YOLO (You Only Look Once) or SSD (Single Shot Multibox Detector) could be implemented to allow detection of multiple objects in a single frame.
Performance Optimization: Optimizing the model's architecture and GPU usage could reduce the processing time for each video frame, enabling faster real-time detection.

#Conclusion
This project demonstrated the successful development and application of an object detection system using CNNs. The system is capable of detecting and classifying objects in real-time video streams, showing its potential for applications in fields such as surveillance, traffic monitoring, and more. Future work could focus on further improving the model's accuracy, efficiency, and ability to detect multiple objects simultaneously.


