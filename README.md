# Task Optimizer & Priority Scheduler (AI-Powered)

A comprehensive multi-modal emotion recognition system that analyzes emotions from text, speech, and facial expressions using three different AI models. The project aims to automate task prioritization based on detected emotions, deadline urgency, workload complexity.

# 1. Text Emotion Model (`text_emotion/`)
- **Model Type**: Machine Learning Pipeline
- **Architecture**: 
  - Feature Extraction: CountVectorizer
  - Classifier: Logistic Regression
  - Pipeline: `Pipeline([('cv', CountVectorizer()), ('lr', LogisticRegression())])`
- **File**: `text_emo_model.pkl` (1.9MB)
- **Purpose**: Analyzes transcribed text to detect emotions

# 2. Speech Emotion Model (`speech_emotion/`)
- **Model Type**: Deep Learning Neural Network (Keras/TensorFlow)
- **Architecture**: LSTM-based Sequential Model

- **File**: `my_model.keras` (3.5MB)
- **Feature Extraction**: MFCC (Mel-frequency cepstral coefficients)
- **Purpose**: Analyzes audio features for emotion detection

# 3. Face Emotion Model (`faceemotion/`)
- **Model Type**: Pre-trained Deep Learning Model
- **Architecture**:
  - Face Detection: Haar Cascade Classifier
  - Emotion Recognition: DeepFace's built-in emotion analysis
- **Implementation**: Uses `DeepFace.analyze()` with emotion detection
- **Purpose**: Analyzes facial expressions in video frames



## 🚀 Installation

### Prerequisites
- Python 3.8+
- pip package manager

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd zidio-task-optimizer
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install required packages**
   ```bash
   pip install -r requirements.txt
   ```

   If requirements.txt doesn't exist, install these packages:
   ```bash
   pip install streamlit opencv-python deepface tensorflow keras librosa scikit-learn joblib pandas numpy seaborn neattext speech_recognition pydub moviepy
   ```

4. **Download additional dependencies**
   - The system will automatically download required model files on first run
   - Ensure internet connection for initial setup

## 🎮 Usage

### Running the Application

1. **Start the Streamlit app**
   ```bash
   streamlit run finalapp.py
   ```

2. **Access the application**
   - Open your browser and go to `http://localhost:8501`
   - Upload a video file containing speech and facial expressions
   - Enter an employee ID for tracking
   - Click "Analyze Emotions" to process the video

### Individual Model Usage

#### Text Emotion Analysis
```python
from text_emotion.text_recog import text_recog
text_recog("path/to/video.mp4", "employee_123")
```

#### Speech Emotion Analysis
```python
from speech_emotion.speech__recog import speech_recog
speech_recog("path/to/video.mp4", "employee_123")
```

#### Face Emotion Analysis
```python
from faceemotion.face_emotion import process_video
process_video("path/to/video.mp4", "employee_123")
```

## 📊 Output Format

The system generates results in JSON format:

### Individual Results
```json
{
  "predicted_emotion": "happy",
  "probabilities": [0.1, 0.8, 0.05, 0.02, 0.01, 0.01, 0.01]
}
```

### Central Database
```json
{
  "employee_123": [
    {
      "timestamp": "20241201_143022",
      "results": {
        "predicted_emotion": "happy",
        "probabilities": [...]
      }
    }
  ]
}
```

## 🔧 Configuration

### Model Parameters

#### Text Model
- **Vectorizer**: CountVectorizer (TF-IDF alternative)
- **Classifier**: Logistic Regression
- **Training Data**: Custom emotion dataset

#### Speech Model
- **Input Features**: 40 MFCC coefficients
- **Architecture**: LSTM with dropout layers
- **Training Data**: TESS Toronto emotional speech set
- **Epochs**: 50
- **Batch Size**: 64

#### Face Model
- **Face Detection**: Haar Cascade Classifier
- **Emotion Recognition**: DeepFace pre-trained model
- **Processing**: Frame-by-frame analysis with averaging

## 📈 Performance

### Model Accuracy
- **Text Model**: ~85% accuracy on test set
- **Speech Model**: ~78% accuracy on validation set
- **Face Model**: ~92% accuracy (DeepFace benchmark)

### Processing Time
- **Text Analysis**: ~2-5 seconds per video
- **Speech Analysis**: ~3-7 seconds per video
- **Face Analysis**: ~10-30 seconds per video (depending on length)

## 🛠️ Development

### Training New Models

#### Text Model Training
```python
# See text_emotion/text_emotion.ipynb for training pipeline
from sklearn.pipeline import Pipeline
from sklearn.feature_extraction.text import CountVectorizer
from sklearn.linear_model import LogisticRegression

pipe_lr = Pipeline(steps=[
    ('cv', CountVectorizer()),
    ('lr', LogisticRegression())
])
```

#### Speech Model Training
```python
# See speech_emotion/test.ipynb for training pipeline
from keras.models import Sequential
from keras.layers import Dense, LSTM, Dropout

model = Sequential([
    LSTM(256, return_sequences=False, input_shape=(40,1)),
    Dropout(0.2),
    Dense(128, activation='relu'),
    Dropout(0.2),
    Dense(64, activation='relu'),
    Dropout(0.2),
    Dense(7, activation='softmax')
])
```

### Adding New Features
1. Modify the respective model files
2. Update the main application (`finalapp.py`)
3. Test with sample data
4. Update this README

## 🐛 Troubleshooting

### Common Issues

1. **Model Loading Errors**
   - Ensure all model files are in correct directories
   - Check file paths in the code

2. **Audio Processing Issues**
   - Verify video has audio track
   - Check audio format compatibility

3. **Face Detection Issues**
   - Ensure good lighting conditions
   - Check video quality and resolution

4. **Memory Issues**
   - Reduce video resolution
   - Process shorter video segments

### Error Logs
- Check console output for detailed error messages
- Review JSON result files for processing status

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📞 Support

For issues and questions:
- Check the troubleshooting section
- Review the Jupyter notebooks for implementation details
- Create an issue in the repository

## 🔄 Updates

### Version History
- **v1.0**: Initial release with three emotion recognition models
- **v1.1**: Added Streamlit interface and result storage
- **v1.2**: Improved error handling and performance optimization

### Planned Features
- Real-time emotion detection
- Webcam integration
- Advanced analytics dashboard
- Multi-language support
- API endpoints for integration

---

**Note**: This system is designed for research and development purposes. Ensure compliance with privacy laws and ethical guidelines when using with real data. 
