Task Optimizer & Priority Scheduler (AI-Powered)

A comprehensive multi-modal emotion recognition system that analyzes emotions from text, speech, and facial expressions using three different AI models. The project aims to automate task prioritization based on detected emotions, deadline urgency, workload complexity.


Installation

Prerequisites
- Python 3.8+
- pip package manager

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
   pip install streamlit opencv-python deepface tensorflow keras librosa scikit-learn joblib pandas numpy seaborn neattext speech_recognition pydub moviepy
   ```

4. Download additional dependencies
   - The system will automatically download required model files on first run
   - Ensure internet connection for initial setup

Usage

Running the Application

1. Start the Streamlit app
   ```bash
   streamlit run finalapp.py
   ```

2. Access the application
   - Open your browser and go to `http://localhost:8501`
   - Upload a video file containing speech and facial expressions
   - Enter an employee ID for tracking
   - Click "Analyze Emotions" to process the video



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
