# AWSLambda
8. Migrate a website from local server to Cloud using Docker.
Migrate a website from local server to Cloud
==============================================

1) Launch an EC2 Instance : t2.large, Network setting: Add security group: all traffic anywhere, 

2) Connect to EC2 Instance

3) clone the git repos 

backend
============

tinyurl.com/cs1bekmit

git clone https://github.com/procareer3fwd/realgrandebackend.git

frontend
==============

tinyurl.com/cs1fekmit

git clone https://github.com/procareer3fwd/realgrandefrontend.git

4) Update the Ubuntu 

sudo apt update

5) Install the Docker

sudo apt -y install docker.io

6)  Check the docker images

sudo docker images

7) change the directory to backend

cd realgrandebackend/

8) create an .env file

nano .env

9) Copy Paste the lines in .env file

MONGODBURL="mongodb+srv://fsd04.2hxrdca.mongodb.net/realgrande?retryWrites=true&w=majority"
DBUSERNAME=procareer3
DBPASSWORD=ISobjBDohsFqEAqg
FRONTENDURI="http:// 34.202.157.58"

10) Build the docker image for backend

 sudo docker build -t backend_server .

11) Check for any images running in the container 

sudo docker ps

12) Now run the backend_server docker image in the container

sudo docker run -d -p 2001:5000 backend_server

13) Now try to access the backend_server on the browser

<EC2_PUBLIC_IP_ADDRESS>:2001/api

14) Now change the directory to frontend

ubuntu@ip-172-31-1-17:~/realgrandebackend$ cd
ubuntu@ip-172-31-1-17:~$ cd realgrandefrontend/
ubuntu@ip-172-31-1-17:~/realgrandefrontend$

15) Now create a .env file

nano .env

16) Copy paste the line in .env file

REACT_APP_BACKEND_URL="http:// 34.202.157.58:2001/api"

17) Build the docker image for frontend

 sudo docker build -t frontend .

18) Check for any images running in the container 

sudo docker ps

19) Now run the backend_server docker image in the container

sudo docker run -d -p 80:3000 frontend

20) Now try to access the frontend on the browser

<EC2_PUBLIC_IP_ADDRESS>

