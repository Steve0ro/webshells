# Command

docker build -t webshells .
- Once built run the following

docker run -p 9005:80 webshells

To gain a docker_shell run:
docker exec -it name_of_container /bin/bash
