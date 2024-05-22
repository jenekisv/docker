# docker

![image](https://github.com/jenekisv/docker/assets/38710485/58037861-7c13-49f7-a894-69d4e8bd5a7e)

Export/Import Docker Image to file
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
docker save image:tag > arch_name.tar
docker load -i arch_name.tar


Import/Export Docker Image to AWS ECR
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
docker build -t evgeniyisv:v1 .
aws ecr get-login --no-include-email --region=ca-central-1 
docker tag  evgeniyisv:v1  12345678.dkr.ecr.ca-central-1.amazonaws.com/myrepo:latest
docker push 12345678.dkr.ecr.ca-central-1.amazonaws.com/myrepo:lastest

docker pull 12345678.dkr.ecr.ca-central-1.amazonaws.com/myrepo:latest



Kill and Delete Containers and Images
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
docker rm -f $(docker ps -aq)        # Delete all Containers
docker rmi -f $(docker images -q)    # Delete all Images
