---
date: 2025-02-19 
tags: 
    - docker
urls:
    -https://www.youtube.com/watch?v=oiKHGyl8bxo
---

# Deploy a flask app with docker

## Create Docker file
```dockerfile
# use the right python version
FROM python:3.12

# go into a dir
WORKDIR /flask-app

# copy req and istall it with pip
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

# copy all the data of the app
COPY . .

# run the app
CMD ["python3", "app.py"]
```

## Create Docker image

Write the docker image by going into the dir of the docker file and run:
```bash
docker build --tag flaskapp-docker .
```
You can list all images with (but we don't need to bc we set the tag of our image to flaskapp-docker):
```bash
docker images
```
Let's run the image into a local container to test it
```bash
docker run -d -p 5000:5000 flaskapp-docker
```

## Need to debug?
1. stop the running container
```bash
docker ps
docker stop <container_id>
```

2. remove the container 
```bash
docker rm <container_id>
```
3. build again the image
```bash
docker build --tag flaskapp-docker .
```
4. run the image again with a local container  
```bash
docker run -d -p 5000:500 flaskapp-docker
```
5. How to check what is running on port 5000?
```bash
sudo netstat -tulnp | grep 5000
```
## Save the docker image into a .tar file
```bash
docker save -o falskappdocker.tar flaskapp-docker
```

## User scp to send the .tar image to the server (in this case with aws ec2)
-i is for using private key then the path of them
then the name of the file you want to upload
then rootname@publicdns:path_of_where_you_want_to_upload_the_file
```bash
scp -i ~/keys/E-voting-key.pem flaskappdocker.tar ubuntu@ec2-51-20-127-97.eu-north-1.compute.amazonaws.com:/home/ubuntu
```

## load the image (on the vps)
```bash
docker load -i flaskappdocker.tar
```

## run the image (from the vps)
```bash
docker run -d -p 5000:5000 flaskapp-docker
```
