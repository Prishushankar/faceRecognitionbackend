# Face Recognition Backend API

A FastAPI-based backend service for comparing faces in images using DeepFace library.

## Features

- **Face Comparison**: Compare faces between multiple images using deep learning
- **URL-based Input**: Accepts image URLs for processing
- **REST API**: Simple HTTP endpoints for integration
- **CORS Support**: Cross-origin requests enabled for frontend integration
- **Distance Metrics**: Provides similarity scores and distance matrices

## Tech Stack

- **FastAPI**: Modern, fast web framework for building APIs
- **DeepFace**: Deep learning face recognition and analysis library
- **OpenCV**: Computer vision library for image processing
- **MTCNN**: Multi-task CNN for face detection
- **TensorFlow**: Machine learning framework
- **Uvicorn**: ASGI server for running the application

## Installation

1. Clone the repository:
```bash
git clone https://github.com/Prishushankar/faceRecognitionbackend.git
cd faceRecognitionbackend
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

## Usage

### Running the Server

**Development:**
```bash
python main.py
```

**Production:**
```bash
uvicorn main:app --host 0.0.0.0 --port 8000
```

### API Endpoints

#### Health Check
```
GET /
```
Returns server status.

#### Compare Faces
```
POST /compare
```

**Request Body:**
```json
{
  "urls": [
    "https://example.com/image1.jpg",
    "https://example.com/image2.jpg",
    "https://example.com/image3.jpg"
  ]
}
```

**Response:**
```json
{
  "matrix": [
    [true, false, true],
    [false, true, false],
    [true, false, true]
  ],
  "distances": [
    [0.0, 0.68, 0.23],
    [0.68, 0.0, 0.71],
    [0.23, 0.71, 0.0]
  ],
  "threshold": 0.25
}
```

## Configuration

The application can be configured using environment variables:

- `PORT`: Server port (default: 8001)
- `ALLOWED_ORIGINS`: Comma-separated list of allowed CORS origins

## Deployment

### Local Development
1. Install dependencies from `requirements.txt`
2. Run with `python main.py`

### Cloud Deployment
The application is ready for deployment on platforms like:
- Heroku
- Railway
- Render
- Google Cloud Run
- AWS Lambda

## API Documentation

Once the server is running, visit `/docs` for interactive API documentation provided by FastAPI's built-in Swagger UI.

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

This project is licensed under the MIT License.
