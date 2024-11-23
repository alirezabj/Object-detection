# Object-Detection
Object detection model to detect sign language gestures.

---

## **Description**
This project involves the development of an object detection model using TensorFlow to recognize four specific sign language gestures: **"like," "dislike," "hello," and "thank you."** The model leverages deep learning to address the challenges of sign language recognition, such as the dynamic nature of hand gestures, and provides real-time detection capabilities.

---

## **How to Use**
1. **Clone the Repository**  
   - Clone this repository to your local machine using the following command:
     ```bash
     git clone https://github.com/alirezabj/Object-detection.git
     cd Object-detection
     ```

2. **Set Up the Environment**  
   - Create a Python virtual environment to isolate dependencies:
     ```bash
     python -m venv tfod
     source tfod/bin/activate  # On Windows: tfod\Scripts\activate
     pip install --upgrade pip
     pip install -r requirements.txt
     ```

3. **Run the Model for Real-Time Detection**  
   - Execute the real-time detection script:
     ```bash
     python detect_realtime.py
     ```
   - Ensure your webcam is connected. Detected gestures will be displayed in a window.

---

## **How to Build the Model with Your Own Data**
1. **Collect and Label Images**  
   - Use the provided `image_capture.py` script to collect images for your custom labels:
     ```bash
     python image_capture.py
     ```
   - Edit the `labels` variable in the script to define your custom gestures:
     ```python
     labels = ['like', 'dislike', 'hello', 'thank_you']
     ```
   - Annotate the images using LabelImg:
     ```bash
     pip install pyqt5 lxml
     git clone https://github.com/tzutalin/labelImg.git
     cd labelImg
     python labelImg.py
     ```

2. **Generate TensorFlow Records**  
   - Convert the labeled images into TensorFlow records using the `generate_tfrecord.py` script:
     ```bash
     python generate_tfrecord.py --label_map=label_map.pbtxt --images_dir=train --output_path=train.record
     python generate_tfrecord.py --label_map=label_map.pbtxt --images_dir=test --output_path=test.record
     ```

3. **Customize the Model Configuration**  
   - Download a pretrained model from the [TensorFlow Model Zoo](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf2_detection_zoo.md) (e.g., **SSD MobileNet V2 FPNLite 320x320**).
   - Update the `pipeline.config` file with your custom configurations:
     - Set `num_classes` to the number of gestures.
     - Update paths for `train.record`, `test.record`, and `label_map.pbtxt`.

4. **Train the Model**  
   - Train the object detection model using the following command:
     ```bash
     python model_main_tf2.py --model_dir=training/ --pipeline_config_path=pipeline.config --num_train_steps=2000
     ```
   - Monitor the training progress with TensorBoard:
     ```bash
     tensorboard --logdir=training/
     ```

5. **Export the Model**  
   - Export the trained model using the `export_model.py` script:
     ```bash
     python export_model.py --pipeline_config_path=pipeline.config --trained_checkpoint_dir=training/ --output_directory=exported_model/
     ```

---

## **Performance and Results**
- **Precision**: 75%
- **Recall**: 75%
- **Accuracy**: 97%

### **Visual Examples**
Here are some examples of the model's performance:

<img width="821" alt="Screenshot 2024-11-23 at 13 24 26" src="https://github.com/user-attachments/assets/e61cdcaf-34c7-49d1-9705-23ed95178d09">
<img width="818" alt="Screenshot 2024-11-23 at 13 24 18" src="https://github.com/user-attachments/assets/b75fd927-9a75-4c32-b69f-718111dc5eb9">
<img width="831" alt="Screenshot 2024-11-23 at 13 24 01" src="https://github.com/user-attachments/assets/56ede57d-f02d-4e21-b736-ebdce9d12dce">
<img width="832" alt="Screenshot 2024-11-23 at 13 23 52" src="https://github.com/user-attachments/assets/15032ead-31cb-42b9-a91c-ec2c3e802d2d">

---



