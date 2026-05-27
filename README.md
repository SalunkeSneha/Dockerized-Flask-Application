# Dockerized Flask Application

## Project Overview
This project demonstrates how to containerize a simple Python Flask web application using Docker. The application runs inside a Docker container and is accessible through a web browser using port mapping.

The main goal of this project is to understand:
- Docker basics
- Containerization
- Dockerfile creation
- Building Docker images
- Running containers
- Exposing application ports

---

## Technologies Used
- Python 3
- Flask
- Docker

---

## Project Structure

```bash
dockerized-flask-app/
│
├── app.py
├── requirements.txt
├── Dockerfile
├── README.md
└── screenshots/
````

---

## Application Code

### app.py

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def home():
    return "Hello from Docker Flask App running inside a container!"

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)
```

---

## requirements.txt

```txt
Flask==2.3.3
```

---

## Dockerfile

```dockerfile
FROM python:3.10

WORKDIR /app

COPY requirements.txt .

RUN pip install -r requirements.txt

COPY . .

EXPOSE 5000

CMD ["python", "app.py"]
```

---

## Steps Performed

### 1. Create Project Files

Created:

* app.py
* requirements.txt
* Dockerfile

---

### 2. Build Docker Image

```bash
docker build -t flask-app .
```

Purpose:

* Builds a Docker image from the Dockerfile

---

### 3. Run Docker Container

```bash
docker run -d -p 5000:5000 flask-app
```

Purpose:

* Runs the Flask application inside a container
* Maps container port 5000 to local machine port 5000

---

### 4. Verify Running Container

```bash
docker ps
```

Purpose:

* Displays running Docker containers

---

### 5. Access Application

Open browser:

```bash
http://localhost:5000
```

Output:

```text
Hello from Docker Flask App running inside a container!
```

---

## Screenshots

Add screenshots of:

* Docker image build
* Running container
* docker ps output
* Browser output

Store screenshots inside the `screenshots/` folder.

---

## Learning Outcomes

Through this project, I learned:

* Basic Docker commands
* Creating Docker images
* Running containers
* Port mapping
* Containerizing Python Flask applications
* Managing application dependencies using requirements.txt

---

## Docker Commands Used

| Command                              | Description                  |
| ------------------------------------ | ---------------------------- |
| docker build -t flask-app .          | Build Docker image           |
| docker run -d -p 5000:5000 flask-app | Run Docker container         |
| docker ps                            | View running containers      |
| docker images                        | View available Docker images |
| docker stop container_id             | Stop running container       |

---

## Conclusion

This project helped in understanding the fundamentals of Docker and how applications can be containerized for easier deployment and portability in DevOps environments.

```
```
