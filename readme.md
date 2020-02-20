**********************************************************************************
**Docker Basic Commands**
**********************************************************************************

docker info<br/>
docker version<br/>
docker login<br/>
docker run hello-world<br/>
docker system prune -a //Delete all containers, networks, and images.<br/>
________________________________

**Images**
________________________________

docker image ls //list images<br/>
docker image build //build an Image<br/>
docker image push //push an image to a remote repo<br/>
docker image history //intermediate image info<br/>
docker image inspect // detailed info about an image<br/>
docker image rm //delete an image<br/>

________________________________

**Container**
________________________________

docker container create //create a conatiner from an image<br/>
docker container start //start an existing container<br/>
docker container run //create a new conatiner ans start it<br/>
docker container ls //List running containers<br/>
docker container inspect // detailed info about a container<br/>
docker container logs //print logs<br/>
docker container stop //stop running conatiner<br/>
docker container kill // stop main process in container abruptly<br/>
docker container rm // delete a stopped container<br/>

________________________________

**Sample (whalesay)**
________________________________

docker run --rm firecyberice/whalesay Hello Docker<br/>
docker run -it --entrypoint /bin/sh firecyberice/whalesay<br/>
docker container ls -a<br/>
docker rm -f {id]<br/>
________________________________

**Sample (Node)**
________________________________

docker build -t warptec/node-web-app //build from dockerfile<br/>
docker container create my_repo/my_image:my_tag //create and tag container<br/>
docker run -p 49160:8080 -d warptec/node-web-app //create and start container<br/>

________________________________

**Sample (nginx)**
________________________________

docker pull nginx<br/>
docker run -d -P --name web nginx<br/>
docker run --name docker-nginx -p 8080:80 nginx<br/>
docker run --name docker-nginx -p 8080:80 -d -v ~/docker-nginx/html:/usr/share/nginx/html nginx<br/>
docker run --name docker-nginx -p 8080:80 -d -v c:/temp/DockerWorkshop/nginx:/usr/share/nginx/html nginx<br/>

________________________________

**Sample (.net core webapi)**
________________________________

dotnet new webapi -n Warptec.Docker.WebApi<br/>
cd .\Warptec.Docker.WebApi\<br/>
dotnet build --configuration Release<br/>
dotnet publish -c Release<br/>
 
docker build -t warptec/webapi .<br/>
docker run -d -p 8090:80 ImageId<br/>
http://localhost:8090/weatherforecast<br/>
