**********************************************************************************
**Docker Basic Commands**
**********************************************************************************

docker info
docker version
docker login
docker run hello-world
docker system prune -a //Delete all containers, networks, and images.
________________________________

**Images**
________________________________

docker image ls //list images
docker image build //build an Image
docker image push //push an image to a remote repo
docker image history //intermediate image info
docker image inspect // detailed info about an image
docker image rm //delete an image

________________________________

**Container**
________________________________

docker container create //create a conatiner from an image
docker container start //start an existing container
docker container run //create a new conatiner ans start it
docker container ls //List running containers
docker container inspect // detailed info about a container
docker container logs //print logs
docker container stop //stop running conatiner
docker container kill // stop main process in container abruptly
docker container rm // delete a stopped container

________________________________

**Sample (whalesay)**
________________________________

docker run --rm firecyberice/whalesay Hello Docker
docker run -it --entrypoint /bin/sh firecyberice/whalesay
docker container ls -a
docker rm -f {id]
________________________________

**Sample (Node)**
________________________________

docker build -t warptec/node-web-app ```diff + text in green build from dockerfile```
docker container create my_repo/my_image:my_tag //create and tag container
docker run -p 49160:8080 -d warptec/node-web-app //create and start container

________________________________

**Sample (nginx)**
________________________________

docker pull nginx
docker run -d -P --name web nginx
docker run --name docker-nginx -p 8080:80 nginx
docker run --name docker-nginx -p 8080:80 -d -v ~/docker-nginx/html:/usr/share/nginx/html nginx
docker run --name docker-nginx -p 8080:80 -d -v c:/temp/DockerWorkshop/nginx:/usr/share/nginx/html nginx

________________________________

**Sample (.net core webapi)**
________________________________

dotnet new webapi -n Warptec.Docker.WebApi
cd .\Warptec.Docker.WebApi\
dotnet build --configuration Release
dotnet publish -c Release
 
docker build -t warptec/webapi .
docker run -d -p 8090:80 ImageId
http://localhost:8090/weatherforecast
