<ins>Task Optimizer & Priority Scheduler (AI-Powered)<ins>

A comprehensive multi-modal emotion recognition system that analyzes emotions from text, speech, and facial expressions using three different AI models. The project aims to automate task prioritization based on detected emotions, deadline urgency, workload complexity.


<ins>Installation<ins>
-Prerequisites:
-- Python 3.8+
-- pip package manager

-Setup Instructions
--1. Clone the repository
   ```bash
   git clone <repository-url>
   cd zidio-task-optimizer
   ```
--2. Create a virtual environment
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```
--3. Install required packages
   ```bash
   pip install -r requirements.txt
   ```
--If requirements.txt doesn't exist, install these packages:
   ```bash
   pip install streamlit opencv-python deepface tensorflow keras librosa scikit-learn joblib pandas numpy seaborn neattext speech_recognition pydub moviepy
   ```
--4. Download additional dependencies
   - The system will automatically download required model files on first run
   - Ensure internet connection for initial setup

<ins>Usage<ins>

-Running the Application

--1. Start the Streamlit app
   ```bash
   streamlit run finalapp.py
   ```

--2. Access the application
   - Open your browser and go to `http://localhost:8501`
   - Upload a video file containing speech and facial expressions
   - Enter an employee ID for tracking
   - Click "Analyze Emotions" to process the video


<ins>Troubleshooting<ins>

-Common Issues

--1. Model Loading Errors
   --- Ensure all model files are in correct directories
   --- Check file paths in the code

--2. Audio Processing Issues
   --- Verify video has audio track
   --- Check audio format compatibility

--3. Face Detection Issues
   --- Ensure good lighting conditions
   --- Check video quality and resolution

--4. Memory Issues
   --- Reduce video resolution
   --- Process shorter video segments


<ins>License<ins>

-This project is licensed under the MIT License - see the LICENSE file for details.


Note: This system is designed for research and development purposes. Ensure compliance with privacy laws and ethical guidelines when using with real data. Also, just DM me on linkedin in case of any issues :)
