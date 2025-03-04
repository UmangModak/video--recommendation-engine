# video--recommendation-engine

# Video Recommendation API

## Overview
The **Video Recommendation API** is a FastAPI-based project that suggests videos based on a user's mood. It utilizes deep neural networks (DNN) and content-based filtering to provide personalized recommendations.

## Features
- Mood-based video recommendations
- Efficient data caching and pagination
- Integration with external APIs
- Fast and scalable using FastAPI

## Installation
1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-repo/video-recommendation-api.git
   cd video-recommendation-api
   ```

2. **Create a Virtual Environment (Optional but Recommended)**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use: venv\Scripts\activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

## Running the API
### Locally
```bash
uvicorn app:app --host 0.0.0.0 --port 8000 --reload
```

### In Google Colab
Run the following in a Colab cell:
```python
!uvicorn video_recommendation_engine.app:app --host 0.0.0.0 --port 8000 --reload
```

## API Endpoints

### 1. **Get Recommended Videos**
   **Endpoint:** `GET /recommend`
   
   **Query Parameters:**
   - `mood` (string) → User's mood (e.g., `happy`, `sad`, `excited`)
   
   **Example Request:**
   ```python
   import requests
   url = "http://0.0.0.0:8000/recommend"
   params = {"mood": "happy"}
   response = requests.get(url, params=params)
   print(response.json())
   ```

   **Example Response:**
   ```json
   {
      "videos": [
         {"title": "Feel Good Music", "url": "https://youtu.be/example1"},
         {"title": "Motivational Talk", "url": "https://youtu.be/example2"}
      ]
   }
   ```

## Troubleshooting
### **Issue: API Not Found (404 Error)**
- Ensure the server is running by checking the logs.
- Confirm that the endpoint is correctly defined in `app.py`.
- Try accessing `http://0.0.0.0:8000/docs` to see the available endpoints.

### **Issue: Server Not Reachable**
- If using Colab, ensure the correct public URL is used.
- Restart the server and try again.

## Future Enhancements
- Improve recommendation accuracy using hybrid models.
- Add user authentication and history tracking.
- Optimize API response times.





