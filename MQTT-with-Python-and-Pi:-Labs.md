Install the nodered docker container: docker run -it --net="host" -v ~/node-red-data:/data --name nodered iotinafrica/node-red-docker:rpi


    -i = interactive
    -t = assign tty
    -p = bind container-internal port to outside port (in this case, so we can view the webserver on p 1883)
    --name
    --net="host" = use host networking, so the docker container shares the networking stack with the docker host. means we don't need to mess around with bridge networking, port forwarding etc.
     -v ~/node-red-data:/data = binds the containers `data` directory to a `node-red-data` folder on the host so we can save configuration between docker sessions.

 = docker create && docker start

ctrl-p ctrl-q to detach

docker start nodered
docker attach nodered

sudo /etc/init.d/mosquitto start


(create repo in hub.docker.com)
docker pull iotinafrica/nodered
