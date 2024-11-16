**Air Canvas**

This project allows users to draw on their screen using hand gestures, leveraging computer vision techniques. Follow the steps below to set up and run the project.

---

## **Table of Contents**
1. [Prerequisites](#prerequisites)
2. [Installation](#installation)
3. [Running the Project](#running-the-project)
4. [Common Issues and Troubleshooting](#common-issues-and-troubleshooting)
5. [Contributing](#contributing)

---

## **1. Prerequisites**
Before running the project, ensure you have:
- A functioning webcam (built-in or external).
- Python 3.7 or higher installed on your system.
- Basic understanding of Python and how to use the command line.

---

## **2. Installation**
Follow these steps to set up the project on your machine:

### a. **Clone the Repository**
```bash
git clone https://github.com/your-username/air-canvas.git
cd air-canvas
```

### b. **Set Up a Virtual Environment**
Create and activate a virtual environment to manage dependencies.
```bash
# On Windows
python -m venv env
env\Scripts\activate

# On macOS/Linux
python3 -m venv env
source env/bin/activate
```

### c. **Install Dependencies**
Install the required Python libraries:
```bash
pip install -r requirements.txt
```

> If `requirements.txt` is missing, the key dependencies are:
> - `opencv-python`
> - `numpy`
> - `mediapipe`

You can install them individually:
```bash
pip install opencv-python numpy mediapipe
```

---

## **3. Running the Project**
1. **Navigate to the Project Directory**:
   ```bash
   cd path/to/air-canvas
   ```

2. **Run the Python Script**:
   ```bash
   python Air-canvas.py
   ```

3. **Grant Camera Access**:
   Ensure you allow the program to access your webcam when prompted.

4. **Use the Air Canvas**:
   - Place your hand in front of the webcam.
   - Use gestures (e.g., pinching or pointing) to draw on the screen.

---

## **4. Common Issues and Troubleshooting**

### **Problem 1: Camera Not Detected**
- **Error Message**:
  ```
  [ERROR:0@0.738] global obsensor_uvc_stream_channel.cpp:158 cv::obsensor::getStreamChannelGroup Camera index out of range
  ```
- **Solution**:
  1. Check if your webcam is connected and working:
     - On Windows: Open the "Camera" app.
     - On macOS/Linux: Use a tool like `Cheese`.
  2. Change the camera index in the script:
     ```python
     cap = cv2.VideoCapture(0)  # Try changing 0 to 1, 2, etc.
     ```

### **Problem 2: Frame Capture Fails**
- **Error Message**:
  ```
  cv2.error: OpenCV(4.10.0) ... error: (-215:Assertion failed) !_src.empty() in function 'cv::cvtColor'
  ```
- **Solution**:
  Add error checks to ensure the camera is capturing frames:
  ```python
  ret, frame = cap.read()
  if not ret:
      print("Error: Failed to capture frame.")
      exit()
  ```

### **Problem 3: Missing Dependencies**
- **Error Message**:
  ```
  ModuleNotFoundError: No module named 'cv2'
  ```
- **Solution**:
  Install the required library:
  ```bash
  pip install opencv-python
  ```

---

## **5. Contributing**
Contributions are welcome! If you'd like to enhance this project:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature-name`).
3. Commit your changes (`git commit -m "Add some feature"`).
4. Push to the branch (`git push origin feature/your-feature-name`).
5. Open a pull request.

---

## **6. License**
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Feel free to copy-paste this structure to your GitHub README. Let me know if you'd like to customize or expand any section!
