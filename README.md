### Image 

1. create .dockerignore

2. build image

        $ docker build -f Dockerfile.dev .

### Container

1. run react app 

        $ docker run -it -p 3000:3000 <cid>

### Volume

1. map target folder to ref of docker container

        $ docker run -p 3000:3000 -v $(pwd):/app <iid>

2. depend on different env (for cmd)

- https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/learn/lecture/18799500#overview

3. for window cmder (cmd) %cd% instead of $(pwd)

        # issues for 'sh: react-scripts: not found'
        $ docker run -p 3000:3000 -v %cd%:/app lasting/frontend

        # solution
        $ docker run -p 3000:3000 -v /app/node_modules -v %cd%:/app lasting/frontend

### Test React

1. npm test at webapp existed

        $ docker exec -it <cid> npm run test

### CICD

1. git init and push new to Github

2. Travis ci integrate with Github

        2.1 add file '.travis.yml'

        2.2 see .travis.yml