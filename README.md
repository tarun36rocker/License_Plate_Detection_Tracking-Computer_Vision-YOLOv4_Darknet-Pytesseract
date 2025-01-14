
# **License Plate Detection and Tracking**

This project demonstrates a computer vision pipeline for detecting and tracking license plates in images or videos. Using **YOLOv4** for object detection and **Pytesseract** for Optical Character Recognition (OCR), it extracts and tracks license plate text with high accuracy.

---

## **How It Works**

### **1. Detection**
The system uses **YOLOv4** (You Only Look Once, version 4), a state-of-the-art object detection model, to identify license plates in input frames. The model is pre-trained and fine-tuned for detecting license plates with high precision. 

**Process**:
- Each input frame (image or video) is passed through the YOLOv4 network.
- YOLOv4 outputs bounding boxes around detected license plates.

---

### **2. Text Recognition**
After detection, the cropped regions containing license plates are sent to **Pytesseract**, an OCR library. This step extracts text from the license plates.

**Process**:
- Detected regions are cropped from the input frame.
- Pytesseract performs Optical Character Recognition (OCR) on these cropped images.
- Extracted text is stored along with the corresponding bounding box data.

---

### **3. Tracking**
To handle video inputs, the project includes a tracking module. This ensures that the same license plate is consistently identified across multiple frames.

**Process**:
- Detected license plates in consecutive frames are assigned unique IDs.
- The tracker updates these IDs as the plates move through the video, ensuring consistent recognition.

---

### **Key Outputs**
- **Cropped Plate Images**: The project saves detected plates as individual images for further verification.
- **Extracted License Plate Text**: Text from plates is displayed or logged for reference.
- **Annotated Video**: An output video highlights detected and tracked license plates with bounding boxes and extracted text.

---

### **Example Workflow**
1. **Input**:
   - An image or video file is provided as input.
2. **Detection**:
   - YOLOv4 detects the location of license plates in the input.
3. **OCR**:
   - Pytesseract extracts text from the detected license plates.
4. **Tracking**:
   - The system tracks license plates across frames in the video.
5. **Output**:
   - Annotated video with bounding boxes and text.
   - Cropped license plate images and numbers are saved in a directory.
