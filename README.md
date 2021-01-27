# doker-appliation
manual and FROM Installation
linux instence:
 yum install python-pip -y
 yum install git -y
 yum install docker -y
------------------------------

MANUAL INSTALLING

git clone https://github.com/Naresh240/python-application.git
 cd python-application
     requirements.txt
    pip install requirements.txt

    python home.py
----------------------------------------------------------------------------------


Dokerfile:
---------
FROM python:3.6
COPY . /opt
WORKDIR /opt
RUN pip install -r requirements.txt
ENTRYPOINT ["python","home.py"]
---------------------------

build image: docker build -t python-hello:v1 .

  docker images  TO cheks images in docker.

       python-hello

run the image as container

       doker run --name python-container -p 5000:5000 -d python-hello:v

-------------------------------------
Push the image in dokerhub:

first


   docker login : username/password
   
   docker tag python-hello:v1 faizan240/python-hello:v1
   
    docker push  faizan240/python-hello:v1
