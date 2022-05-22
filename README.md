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

GITHUB

$:

VIM

quit without save :q!


DOCKER

FROM node:12.16.3   (base image package )
WORKDIR /basedirectory
ENV PORT 80
COPY package.json /code/package.json   
                    (copy in package and package dependencies)

RUN npm install 
                    (install dependencies with n.. package manager)
COPY ./code         (copy source code into directory)
CMD [ "node", "scr/server.js" ]    
                    (call "node" and pass it in "server.js")