# Python Development Environment

This container comes preinstalled with Python, and related extensions to get into the development setup ASAP. 


Build the docker image : 
> docker build -t python_dev_env .

Spon up the container : 
> docker run -d -p 7070:8080 -v $(pwd):/worksapce python_dev_env