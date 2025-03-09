#  Basic Docker project

## **Project overview**
 * Goal: Automate Docker image builds and deployments with CI/CD.
 
## **Prerequisites**

* Python  3.13.1 (Flask 3.1.0) 
* Docker version 27.5.1
* psycopg 2.9.10
 

## **Project Structure**

```bash
SimpleDockerCI-CD-Pipelinene/
├── app.py #   Flask  app
├── docker-compose.yml
├── Dockerfile # Dockerfile  to containerize the flask app
├── docker.yml # Github Action config file 
├── requirements.txt # Dependencies 
```
## **TODO**

### **Clone the repo**
```bash
git clone  https://github.com/sekedoua/SimpleDockerCI-CD-Pipelinene.git
```
### **Build the Docker Image**
```bash
cd SimpleDockerCI-CD-Pipelinene
docker build -t flask-app .
```
### **Push your Dockerized app to GitHub**
```bash
git push origin main

```

### **Create a GitHub Actions Workflow (.github/workflows/docker.yml)**
```bash
name: Docker Build & Push
on:
  push:
    branches:
    - main
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v2
      - name: Login to Docker Hub
        run: echo "${{ secrets.DOCKER_PASSWORD }}" | docker login -u "${{ secrets.DOCKER_USERNAME }}" --password-stdin
      - name: Build Docker Image
        run: docker build -t myusername/myapp:latest .
      - name: Push to Docker Hub
        run: docker push myusername/myapp:latest
```


### **Configure Secrets in GitHub:**
```bash
 Add DOCKER_USERNAME and DOCKER_PASSWORD as repository secrets
```

### **Push to GitHub & Trigger CI/CD Pipeline**
```bash
 Every push to main will build and push the Docker image.
```