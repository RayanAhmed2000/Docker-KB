- install docker
- create app.py and paste below flaskcode in it
```
from flask import Flask
app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello, Flask in Docker!"

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)
```
- Create requirements.txt
```
flask
```
- Now create Dockerfile
```
FROM python:3.10-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
EXPOSE 5000
CMD ['python','app.py'] 
```
- Now build the image from Dockerimage
```
docker build -t flaskapp . 
```
- Now run the container from image exposing port 5000
```
docker run -td --name mycontainer flaskapp -p 5000:5000 
```
- Search Public IP:5000
