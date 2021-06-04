   
Commands   



1) Version

    a) C:\Users\echypal>docker --version
       Docker version 19.03.13, build 4484c46d9d
       
    b) C:\Users\echypal>docker version
       Client: Docker Engine - Community
        Cloud integration: 1.0.1
        Version:           19.03.13
        API version:       1.40
        Go version:        go1.13.15
        Git commit:        4484c46d9d
        Built:             Wed Sep 16 17:00:27 2020
        OS/Arch:           windows/amd64
        Experimental:      false
       
       Server: Docker Engine - Community
        Engine:
         Version:          19.03.13
         API version:      1.40 (minimum version 1.12)
         Go version:       go1.13.15
         Git commit:       4484c46d9d
         Built:            Wed Sep 16 17:07:04 2020
         OS/Arch:          linux/amd64
         Experimental:     false
        containerd:
         Version:          v1.3.7
         GitCommit:        8fba4e9a7d01810a393d5d25a3621dc101981175
        runc:
         Version:          1.0.0-rc10
         GitCommit:        dc9208a3303feef5b3839f4323d9beb36df0a9dd
        docker-init:
         Version:          0.18.0
         GitCommit:        fec3683
       
       C:\Users\echypal>

2) Run a docker image 

   docker run docker/whalesay cowsay hello world (executing a command while running the container)
   
           1)Pull: docker pull docker/whalesay
           2)Create container from image : 
                 C:\Users\echypal>docker create docker/whalesay
                 ff02a844536571325e501fcfb2f1151a499ca5eb4c6329e715651ebb60574a97
           
                  C:\Users\echypal>
           3)start it : docker start ff02a844536571325e501fcfb2f1151a499ca5eb4c6329e715651ebb60574a97
           4) and run startup command
           
   

      Unable to find image 'docker/whalesay:latest' locally
      latest: Pulling from docker/whalesay
      Image docker.io/docker/whalesay:latest uses outdated schema1 manifest format. Please upgrade to a schema2 image for better future compatibility. More information at https://docs.docker.com/registry/spec/deprecated-schema-v1/
      e190868d63f8: Pull complete
      909cd34c6fd7: Pull complete
      0b9bfabab7c1: Pull complete
      a3ed95caeb02: Pull complete
      00bf65475aba: Pull complete
      c57b6bcc83e3: Pull complete
      8978f6879e2f: Pull complete
      8eed3712d2cf: Pull complete
      Digest: sha256:178598e51a26abbc958b8a2e48825c90bc22e641de3d31e18aaf55f3258ba93b
      Status: Downloaded newer image for docker/whalesay:latest
       _____________
      < hello world >
       -------------
          \
           \
            \
                          ##        .
                    ## ## ##       ==
                 ## ## ## ##      ===
             /""""""""""""""""___/ ===
        ~~~ {~~ ~~~~ ~~~ ~~~~ ~~ ~ /  ===- ~~~
             \______ o          __/
              \    \        __/
                \____\______/
      
      C:\Users\echypal>
	  
3) list all running container
      C:\Users\echypal>docker ps
      CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES

4) See all the containers
      C:\Users\echypal>docker ps -a

      CONTAINER ID        IMAGE               COMMAND                CREATED             STATUS                     PORTS               NAMES
      26061ad10348        docker/whalesay     "cowsay hello world"   5 minutes ago       Exited (0) 5 minutes ago                   sleepy_varahamihira

      C:\Users\echypal>

5) Stop a container
      C:\Users\echypal>docker stop 26061ad10348 (container id/names)
      26061ad10348
  
6) remove a container
  
  a)   C:\Users\echypal>docker rm sleepy_varahamihira (container id/names)
     sleepy_varahamihira
	 
  b) Check after remove
     C:\Users\echypal>docker ps -a
     CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES

     C:\Users\echypal>
	 
	 -- all container
	 docker rm  $(docker ps -a -q )
	 note: q gives unique id's
	 
7) List available images

   C:\Users\echypal>docker images
   REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
   hello-world         latest              bf756fb1ae65        10 months ago       13.3kB
   docker/whalesay     latest              6b362a9f73eb        5 years ago         247MB

   C:\Users\echypal> docker image ls
   
   --- unique images
   docker images -q
   
8) Remove doker images
   docker rmi docker/whalesay
   
   -- forced
   docker rmi mysql -f   (forced. needed when conflict: unable to delete 6e447ce4863d (must be forced) - image is referenced in multiple repositories)
   
   --remove all images (with forced)
   docker  rmi  -f $(docker images -q)
   
   p.s.: all the dependent containers should be deleted before deleting the docker image
   
9) Run command inside a running container
      C:\Users\echypal>docker exec -it 28f13a42fb72 sh
      /opt # ls
      Dockerfile        app.py            requirements.txt  templates
    /opt #
   
10) Run a container with the nginx:1.14-alpine image and name it webapp

docker run --name webapp nginx:1.14-alpine















docker run ubuntu
docker run -it ubuntu
