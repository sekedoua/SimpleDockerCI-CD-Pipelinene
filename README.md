#  Basic Docker project

## **Project overview**
 * Simple app  with a database connection using Docker Compose , Flask + PostgreSQL
 
## **Prerequisites**

* Python  3.13.1 (Flask 3.1.0) 
* Docker version 27.5.1
* psycopg 2.9.10
 

## **Project Structure**

```bash
Multi-Container-Application-with-Docker-Compose/
├── app.py #   Flask  app
├── docker-compose.yml
├── Dockerfile # Dockerfile  to containerize the flask app
├── requirements.txt # Dependencies 
```
## **TODO**

### **Clone the repo**
```bash
git clone  https://github.com/sekedoua/Multi-Container-Application-with-Docker-Compose.git
```
### **Build & Run the Docker Image**
```bash
cd Multi-Container-Application-with-Docker-Compose
docker-compose up --build
```

### **Verify the Application:**
```bash
Open http://localhost:5000 in your browser.
---