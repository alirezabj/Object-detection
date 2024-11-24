# Object-Detection
Object detection model to detect sign language gestures.

---

## **Description**
This project involves the development of an object detection model using TensorFlow to recognize four specific sign language gestures: **"like," "dislike," "hello," and "thank you."** 

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
     source tfod/bin/activate # Linux
     .\tfod\Scripts\activate # Windows 
     python -m pip install --upgrade pip
     pip install ipykernel
     python -m ipykernel install --user --name=tfodj
     ```

3. **Image Collection**  
   - Collext images using the Notebook Image collection.ipynb:
   - Ensure your webcam is connected. Detected gestures will be displayed in a window.
   - Manually divide collected images into two folders train and test.
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
---

3. **Training**
 
   - Train the model using Training the model.ipynb

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



