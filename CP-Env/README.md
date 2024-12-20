# Competitve Coding environment

This container facilitates a quick CP environment to test your Leetcode, or Codeforces algorithms. 
All major libraries for c++, go and python are installed for CP.

Build the docker image : 
> docker build -t cp_env .

Spon up the container : 
> docker run -d -p 9090:8080 -v $(pwd):/worksapce cp_env 
