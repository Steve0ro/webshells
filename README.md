# Repo used to test php webshells

## Build: 
- ` docker build -t webshells . `

## Once built run the following
- ` docker run -p 9005:80 webshells `

## Visit docker_ip:9005

## Docker_shell
- docker ps -a
- grab dorky name of container
- ` docker exec -it goofy_name /bin/bash `
