# FaceSort - AI-Powered Face Clustering Web App

An intelligent web application that automatically organizes photos by identifying and grouping faces using machine learning. Built with FastAPI backend and React frontend.

## 🚀 Features

- **Face Detection & Recognition**: Uses advanced face recognition algorithms to identify faces in images
- **Automatic Clustering**: Groups similar faces together using PCA + DBSCAN clustering
- **Web Interface**: Clean, modern React UI for easy image upload and album viewing
- **REST API**: FastAPI backend with automatic documentation
- **Progress Tracking**: Real-time progress updates during processing
- **Album Organization**: Creates organized folders for each person
- **Download Support**: Download individual albums or all albums as ZIP files

## 🛠️ Tech Stack

### Backend
- **FastAPI** - High-performance async web framework
- **face_recognition** - Face detection and encoding
- **scikit-learn** - Machine learning for clustering (PCA + DBSCAN)
- **OpenCV** - Image processing
- **NumPy** - Numerical computations

### Frontend
- **React 18** - Modern UI framework
- **Vite** - Fast build tool and dev server
- **CSS3** - Modern styling

## 📋 Prerequisites

- Python 3.8+
- Node.js 16+
- Git

## 🚀 Quick Start

### 1. Clone the Repository
```bash
git clone https://github.com/Rhythm102/Project-exhibition-2-upd-.git
cd Project-exhibition-2-upd-
```

### 2. Backend Setup
```bash
# Create virtual environment
python -m venv .venv
.venv\Scripts\activate  # Windows
# or
source .venv/bin/activate  # Linux/Mac

# Install dependencies
pip install -r face-clustering/requirements.txt

# Start the backend server
cd face-clustering
uvicorn main:app --host 0.0.0.0 --port 8000 --reload
```

### 3. Frontend Setup
```bash
# In a new terminal
cd facesort
npm install
npm run dev
```

### 4. Access the Application
- **Frontend**: http://localhost:5173
- **Backend API**: http://localhost:8000
- **API Documentation**: http://localhost:8000/docs

## 📖 Usage

1. Open the web app in your browser
2. Click "Choose Files" to select multiple images
3. Click "Upload & Process" to start face clustering
4. Wait for processing to complete (progress shown in backend logs)
5. View organized albums by person
6. Download individual albums or all albums as ZIP

## 🔧 Configuration

### Environment Variables
- `BASE_URL`: Server base URL (default: http://localhost:8000)

### Face Detection Settings
- **Detection Method**: `hog` (CPU) or `cnn` (GPU) - modify in `main.py`
- **Image Resize**: Max 800px width for faster processing
- **Clustering Parameters**: Adjustable in `cluster_encodings()` function

## 📁 Project Structure

```
Project-exhibition-2-upd-/
├── face-clustering/          # FastAPI backend
│   ├── main.py              # Main application
│   ├── encode_faces.py      # Face encoding utilities
│   ├── cluster_faces.ipynb  # Jupyter notebook for testing
│   ├── requirements.txt     # Python dependencies
│   └── dataset/             # Sample images
├── facesort/                # React frontend
│   ├── src/
│   │   ├── App.jsx          # Main React component
│   │   └── FaceSort.jsx     # Face clustering UI
│   ├── package.json         # Node dependencies
│   └── vite.config.js       # Vite configuration
├── outputs/                 # Generated albums (auto-created)
├── .gitignore              # Git ignore rules
└── README.md               # This file
```

## 🎯 Performance Notes

- **CPU Optimization**: Images are automatically resized to 800px max width
- **Progress Logging**: Real-time progress shown in backend terminal
- **Expected Times** (on i5 CPU):
  - 10 images: ~15-20 seconds
  - 30 images: ~45-60 seconds
  - 62+ images: 2-3+ minutes

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🙏 Acknowledgments

- [face_recognition](https://github.com/ageitgey/face_recognition) library
- [FastAPI](https://fastapi.tiangolo.com/) framework
- [React](https://reactjs.org/) ecosystem

---

**Note**: This project uses machine learning models that may require significant computational resources. Processing large numbers of images may take considerable time on slower hardware.