# Deploy a Static Website using Docker & Nginx
This project demonstrates how to deploy a static HTML/CSS website using a custom Docker image based on the official Nginx image.

##  How it Works

- The Dockerfile uses the official `nginx` image.
- It copies all files from `website-files/` into Nginx's default HTML directory.
- The container serves your site on port **80** internally.

### Build and Run

# Create a Dockerfile

# Paste the below into the file
'''
FROM nginx:latest
COPY ./Course-Docker/sample-website /usr/share/nginx/html/
EXPOSE 80
''' 
# Build the image from the Dockerfile and run it publishing port 3000 to be mapped to port 80 on the host

$ docker build -t website .
$ docker run -it --rm -d -p 3000:80 --name web website 


#### Create Docker Image from a Running Container 

docker commit web elghandour/new-web 
docker login
docker push elghandour/new-web
docker run -it --rm -d -p 4000:80 --name new-hub elghandour/new-web
