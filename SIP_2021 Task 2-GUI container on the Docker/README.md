
## GUI container on the Docker

### Task 2

🔅 Launch a container on docker in GUI mode

🔅 Run any GUI software on the container

### Method 1

1. systemctl status docker

2. systemctl start docker

3. mkdir Dockerfile

4. cd Dockerfile

5. vim DockerFile

FROM centos:latest

RUN yum install python3 -y

RUN pip3 install jupyter

RUN yum install firefox -y

CMD jupyter notebook --allow-root / CMD firefox

6. ocker build -t launchfirefox:v1 . //In case of any changes in the image, update the version to succeeding number.

7. docker run -it --env "DISPLAY " --net "host" --name FirefoxInDocker launchfirefox:v1

### Method 2

1. echo $DISPLAY
2. ls /tmp/.X11-unix/
3. systemctl start docker
4. docker run -it --name gui_on_container -e DISPLAY="$DISPLAY" -v /tmp/.X11-unix/:/tmp/.X11-unix/ centos:latest
5. yum install python3 -y
6. yum install firefox -y
7. pip3 install jupyter
8. jupyter notebook --allow-root


##
- [Video Link](https://nagtodetejaswini.medium.com/running-gui-application-inside-docker-container-706b9076a535)

