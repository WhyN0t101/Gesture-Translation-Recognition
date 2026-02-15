# Gesture Translation and Recognition

A Python-based machine learning application that translates sign language gestures into text in real-time. The system uses computer vision and deep learning to recognize hand gestures and convert them into readable text, helping bridge communication gaps for the deaf and hard-of-hearing community.

## Overview

This project implements a gesture recognition system with a client-server architecture. The server handles the machine learning model for gesture recognition, while the client captures video input and displays translated text. The system uses MediaPipe for hand tracking and TensorFlow for gesture classification.

## Features

- **Real-time Gesture Recognition**: Translates sign language gestures to text in real-time
- **Client-Server Architecture**: Distributed processing for better performance
- **Hand Tracking**: Uses MediaPipe for accurate hand landmark detection
- **Deep Learning Model**: TensorFlow-based model for gesture classification
- **User Interface**: Simple client interface for video capture and text display
- **Dataset Training Tools**: Scripts for training custom gesture recognition models

## Technology Stack

- **Python 3.x** - Core programming language
- **TensorFlow 2.5.0** - Deep learning framework
- **OpenCV 4.5.3** - Computer vision and video processing
- **MediaPipe 0.8.6** - Hand tracking and landmark detection
- **NumPy 1.21.1** - Numerical computations
- **Pillow 8.3.1** - Image processing

## Prerequisites

Before you begin, ensure you have the following installed:

- **Python 3.7** or higher
- **pip** - Python package manager
- **Webcam** - For capturing hand gestures

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/WhyN0t101/gesture_translation_recognition.git
   cd Gesture-Translation-Recognition
   ```

2. **Install dependencies**
   ```bash
   pip install -r dependencies.txt
   ```

   Required packages:
   - opencv-python==4.5.3
   - Pillow==8.3.1
   - numpy==1.21.1
   - tensorflow==2.5.0
   - mediapipe==0.8.6

3. **Verify installation**
   ```bash
   python -c "import cv2, tensorflow, mediapipe; print('All dependencies installed successfully')"
   ```

## Usage

The application uses a client-server architecture:

### Starting the Server

1. **Navigate to the Server directory**
   ```bash
   cd Server
   ```

2. **Run the server**
   ```bash
   python server.py
   ```

   The server will:
   - Load the trained gesture recognition model
   - Listen for client connections
   - Process gesture recognition requests

### Running the Client

1. **Open a new terminal**

2. **Navigate to the Client directory**
   ```bash
   cd Client
   ```

3. **Run the client application**
   ```bash
   python client.py
   ```

4. **Using the application**
   - The client will open your webcam
   - Position your hand in front of the camera
   - Perform sign language gestures
   - The recognized text will be displayed on screen


## Training Custom Models

To train your own gesture recognition model:

1. **Prepare your dataset**
   - Organize gesture images in separate folders by class
   - Use the scripts in `DatasetTraining/` for data preparation

2. **Split the dataset**
   ```bash
   cd DatasetTraining
   python splitImages.py
   ```

3. **Train the model**
   ```bash
   python Train.py
   ```

4. **Update the server**
   - Place the trained model in the Server directory
   - Update `server_recognition.py` to use the new model

## Configuration

### Server Configuration
Edit `server.py` to configure:
- Port number (default: 5000)
- Model path
- Processing parameters

### Client Configuration
Edit `client.py` to configure:
- Server IP address
- Port number
- Camera settings
- Display parameters

## Troubleshooting

### Camera Not Detected

**Issue**: Client can't access webcam

**Solutions**:
- Verify webcam is connected and working
- Check camera permissions for Python
- Ensure no other application is using the camera
- Try specifying camera index in client.py (usually 0 or 1)

### Connection Refused

**Issue**: Client can't connect to server

**Solutions**:
- Verify server is running
- Check firewall settings
- Verify IP address and port configuration
- Ensure both client and server are on the same network (if applicable)

### Low Recognition Accuracy

**Issue**: Gestures not recognized correctly

**Solutions**:
- Ensure good lighting conditions
- Position hand clearly in frame
- Perform gestures slowly and distinctly
- Retrain model with more diverse dataset
- Check MediaPipe hand tracking is working properly

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the GNU General Public License - see the [LICENSE](LICENSE) file for details.

**Note**: This project is designed for educational purposes and gesture recognition research. For production use in accessibility applications, consider additional training data and extensive testing with diverse users.
