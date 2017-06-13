Install the nodered docker container: docker run -it -net="host" -p 1883:1883 --name nodered nodered/node-red-docker:rpi


    -i = interactive
    -t = assign tty
    -p = bind container-internal port to outside port (in this case, so we can view the webserver on p 1883)
    --name
    --net="host" = use host networking, so the docker container shares the networking stack with the docker host. means we don't need to mess around with bridge networking, port forwarding etc.

 = docker create && docker start

ctrl-p ctrl-q to detach

docker start nodered
docker attach nodered

sudo /etc/init.d/mosquitto start


