<ins>Task Optimizer & Priority Scheduler (AI-Powered)<ins>

A comprehensive multi-modal emotion recognition system that analyzes emotions from text, speech, and facial expressions using three different AI models. The project aims to automate task prioritization based on detected emotions, deadline urgency, workload complexity. As a discliamer, some dummy data and hard coded credentials are present.

<img width="1163" height="393" alt="Screenshot from 2026-07-27 11-32-20" src="https://github.com/user-attachments/assets/4b3d7e79-1886-4b65-b1af-49707cf32af6" />
<img width="630" height="628" alt="Screenshot from 2026-07-27 12-15-01" src="https://github.com/user-attachments/assets/677c8b29-3c0e-4e19-ab21-73bfab35c8e7" />
<img width="1006" height="625" alt="Screenshot from 2026-07-27 12-08-46" src="https://github.com/user-attachments/assets/30ea93a3-5527-48be-a23d-bd100c475be1" />
<img width="1165" height="643" alt="Screenshot from 2026-07-27 12-06-39" src="https://github.com/user-attachments/assets/c0d01bbc-a11f-4590-8f19-a44cf0859f77" />

<ins>Installation<ins>

Prerequisites: Python 3.8+, pip package manager


Setup Instructions

1. Clone the repository
   ```bash
   git clone <repository-url>
   cd zidio-task-optimizer
   ```

2. Create a virtual environment
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install required packages
   ```bash
   pip install -r requirements.txt
   ```

If requirements.txt doesn't exist, install these packages:
   ```bash
   pip install streamlit opencv-python deepface tensorflow keras librosa scikit-learn joblib pandas numpy seaborn neattext SpeechRecognition pydub moviepy
   ```

4. Download additional dependencies
   - The system will automatically download required model files on first run
   - Ensure internet connection for initial setup



<ins>Usage<ins>

Running the Application

1. Start the Streamlit app
   ```bash
   streamlit run finalapp.py
   ```

2. Access the application
   - Open your browser and go to `http://localhost:8501`
   - Upload a video file containing speech and facial expressions
   - Enter an employee ID for tracking. Credentials for both employee and manager logins have been hardcoded inside finalapp.py
   - Click "Analyze Emotions" to process the video and use other functionalities (employee login)
   - In manager login we can create new tasks, rate them and keep track of employee emotional states.



<ins>Troubleshooting<ins>

Common Issues:

1. Model Loading Errors
   - Ensure all model files are in correct directories
   - Check file paths in the code


2. Audio Processing Issues
   - Verify video has audio track
   - Check audio format compatibility

3. Face Detection Issues
   - Ensure good lighting conditions
   - Check video quality and resolution

4. Memory Issues
   - Reduce video resolution
   - Process shorter video segments



<ins>Note<ins>

This system is designed for research and development purposes. Ensure compliance with privacy laws and ethical guidelines when using with real data. Also, just DM me on linkedin in case of any issues :)
