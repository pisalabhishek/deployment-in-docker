1️⃣ Prerequisites

Windows PC

Docker Desktop
 installed

Git
 installed (if cloning repo)

Python not required to run via Docker

2️⃣ Clone the Project
git clone https://github.com/your-username/your-repo.git
cd your-repo


Replace your-username/your-repo with the link to this GitHub repository.

3️⃣ Build Docker Image

Open PowerShell in the project folder (where Dockerfile is) and run:

docker build -t my-ml-app:1.0 .


my-ml-app:1.0 → local Docker image name

. → build context is current folder

4️⃣ Run the App Locally
docker run -p 8501:8501 my-ml-app:1.0


Open browser: http://localhost:8501

Your ML/Streamlit app will appear.

Press Ctrl + C in PowerShell to stop the container.

5️⃣ Optional: Push Image to Docker Hub
5a. Login to Docker Hub
docker login


Enter your username and password / access token.

5b. Tag the image for Docker Hub
docker tag my-ml-app:1.0 your-docker-username/my-ml-app:1.0

5c. Push to Docker Hub
docker push your-docker-username/my-ml-app:1.0


The image is now online and can be pulled from anywhere.

6️⃣ Optional: Run on Another PC (No Python Needed)
docker pull your-docker-username/my-ml-app:1.0
docker run -p 8501:8501 your-docker-username/my-ml-app:1.0


Open browser: http://localhost:8501

App runs without installing Python, Streamlit, or dependencies.

7️⃣ Optional: Deploy Online via Streamlit Cloud

Push your project (app.py + requirements.txt) to GitHub.

Go to Streamlit Community Cloud
.

Click “New app”, connect your GitHub repo, select branch and app file.

Streamlit will deploy the app and give you a URL like:

https://your-app-name.streamlit.app


Share this link — anyone can access your app via browser (PC or mobile).

No Docker or Python required for users.

8️⃣ Notes / Tips

Docker image size can be reduced using python:3.11-slim and .dockerignore.

Port mapping: -p local_port:container_port lets you control the browser URL.

For cloud deployment, Streamlit Cloud is free for small apps.
