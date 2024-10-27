# Mental Health Concern Classification

The **Mental Health Concern Classification** project is a Flask-based web application designed to provide users with real-time mental health insights through **Natural Language Processing (NLP)**. Utilizing the **Groq API**, the application analyzes text submitted by users to determine emotional sentiment (positive, negative, or neutral), identify relevant mental health-related keywords, classify concerns into categories like Anxiety, Depression, and Stress, and assign an intensity score for each concern on a 1-10 scale.

Each analysis result, along with a timestamp, is stored in **MongoDB Atlas** for persistent storage and future reference, enabling timeline-based tracking of mental health trends. This allows users to monitor changes in emotional sentiment and mental health concerns over time, providing valuable insights into their well-being.

## Key Components

1. **Groq API for NLP Analysis**: The Groq API powers sentiment analysis, keyword extraction, concern classification, and intensity scoring, processing each user input to return structured mental health data instantly.
   
2. **MongoDB Atlas for Data Storage**: MongoDB Atlas serves as a secure, cloud-based NoSQL database where all processed entries are saved with timestamps. This setup enables the app to retrieve past entries for timeline analysis, helping users visualize trends in mental health.

3. **Containerized Deployment with Docker**: Docker enables easy deployment across cloud platforms such as Google Cloud Run, AWS ECS, and Azure App Service. Docker Hub is used for storing the Docker image, supporting portability and scalability across environments.

## Project Structure

```plaintext
MentalHealthApp/
├── app.py               # Main Flask application
├── config.py            # MongoDB Atlas connection
├── Dockerfile           # Dockerfile for containerizing the app
├── requirements.txt     # Python dependencies
├── README.md            # Project documentation
├── templates/           # HTML templates for frontend
└── functions/           # API functions for NLP tasks


Setup and Installation
Clone the Repository:

```bash
git clone https://github.com/yourusername/mental-health-classification.git
cd mental-health-classification
Configure MongoDB Atlas:

Create a MongoDB Atlas cluster and get the connection URI.
Set the MONGODB_URI environment variable in your terminal:
```bash
export MONGODB_URI="your_mongodb_atlas_uri_here"
Install Dependencies:

```bash

pip install -r requirements.txt
Running the Application Locally
To run the application locally:

```bash
python app.py
Visit http://127.0.0.1:5000 to access the web interface.

Using Docker
Build the Docker Image:

```bash
docker build -t mentalhealthapp .
Run the Docker Container:

```bash
docker run -p 5000:5000 -e MONGODB_URI="your_mongodb_uri_here" mentalhealthapp
Deploying to Docker Hub
Login to Docker Hub:

```bash
docker login
Tag and Push the Image:

```bash
docker tag mentalhealthapp yourdockerhubusername/mentalhealthapp
docker push yourdockerhubusername/mentalhealthapp
API Endpoints
POST /classify: Accepts user text input, analyzes it with the Groq API, and returns analysis data.
GET /timeline-analysis: Retrieves historical data for timeline-based mental health trend analysis.
License
This project is licensed under the MIT License.

## Acknowledgments
Groq API for providing NLP capabilities.
MongoDB Atlas for secure and scalable database solutions.
Docker for containerization support.
yaml


---

This README file is structured to give a comprehensive overview of the project while guiding users through setup, running, and deployment. Replace `yourusername` and `yourdockerhubusername` with your GitHub and Docker Hub usernames, respectively.









## Benefits

The application provides users with immediate, data-driven mental health insights and enables them to monitor emotional patterns over time. By integrating Groq API, MongoDB Atlas, and Docker, the project ensures scalability, security, and ease of deployment, making it an effective tool for tracking mental health and well-being over time.
