# Object-detection
Object detection model to detect sign language

## Description
Due to the size of this project (1.5 GB), it has been uploaded to Google Drive. You can download the complete project using the following link:

[Download the Project on Google Drive](https://drive.google.com/file/d/1mVJIFoCkXlw0OVc6PKxUqkixosbZQG1_/view?usp=drive_link)


## **How to Use**
1. **Download the Project**  
   - Visit the (https://drive.google.com/file/d/1mVJIFoCkXlw0OVc6PKxUqkixosbZQG1_/view?usp=drive_link) to download the complete project files.
   - Extract the files to your desired directory.

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
1. **Download the Project Files**: Use the link above to download the base files for this project.
2. **Collect and Label Images**: Use the provided `image_capture.py` script to collect images and annotate them using LabelImg.
3. **Train the Model**: Follow the training instructions in the `README_TRAINING.md` (included in the downloaded files) to train the model with your data.

---

## **Performance and Results**
- **Precision**: 75%
- **Recall**: 75%
- **Accuracy**: 97%

### **Visual Examples**
Here are some examples of the model's performance:

**Example 1: Detecting 'like' gesture**
![Like Gesture](images/like_example.jpg)

**Example 2: Real-time detection of gestures**
![Real-Time Detection](images/realtime_detection.gif)

For more detailed metrics and evaluation, check the TensorBoard graphs included in the downloaded files.

---

## **Key Files**
- `image_capture.py`: Script for collecting images.
- `detect_realtime.py`: Script for running real-time detection.
- `train_model.py`: Script for training the object detection model.
- `export_model.py`: Script for exporting the trained model.

---

