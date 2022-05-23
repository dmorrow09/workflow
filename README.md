workflow short reference:

GIT
https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository
#init new version control on dir


cd /my_project
$:
git init
git commit -m 'Initial project version'
git branch -m master main //change master -> main for github
git status //check state of tracked files
           // -s for short
git add //add file or dir to tracking
        //"add precisely this file to  the next commit"
        //-A add all
git remote add origin git@github.com:username/reponame
git push -u -f origin main
        // -u for set origin as default
        //-f for force if you need to overwrite

GITHUB

$:

VIM

quit without save :q!
save and quit :wq


GO

build and install program
https://www.digitalocean.com/community/tutorials/how-to-build-and-install-go-programs

go mod init github.com/name/repo
go mod tidy         //get dependencies
go build            //create executable
/.name              //run name

DOCKER
build docker image 
https://docs.docker.com/language/golang/build-images/
basic golang Dockerfile : https://github.com/olliefr/docker-gs-ping

EXAMPLE:
# syntax=docker/dockerfile:1

FROM golang:1.16-alpine

WORKDIR /app

COPY go.mod ./
COPY go.sum ./
RUN go mod download

COPY *.go ./

RUN go build -o /docker-gs-ping

EXPOSE 8080

CMD [ "/docker-gs-ping" ]
    
docker image tag docker-gs-ping:latest docker-gs-ping:v1.0. /tag image with additional tab

docker image rm docker-gs-ping:v1.0         //rm docker img

docker run docker-gs-ping                  //run container
(curl localport:8080 will fail)
docker run --publish 8080:8080 docker-gs-ping //expose port 8080 to port 8080 on the host.

docker ps                                   //lists containers running on machine
                                            // -all shows all active and inactive
                                            
k
docker stop "name" or "ID"


A build context is the set of files located in the specified path or URL. The Docker build process can access any of the files located in the context.

The build command optionally takes a --tag flag. This flag is used to label the image with a string value, which is easy for humans to read and recognise. If you do not pass a --tag, Docker will use latest as the default value.

An image is made up of a manifest and a list of layers. In simple terms, a “tag” points to a combination of these artifacts.

multistage builds :https://docs.docker.com/develop/develop-images/multistage-build/


