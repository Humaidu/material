If you find yourself in a network that requires a proxy server set up, here's some steps to get you going. We started from the [Raspberry Pi documentation](https://www.raspberrypi.org/documentation/configuration/use-a-proxy.md), but tried to switch to as few manual steps as possible so we could run round the classroom to configure everyone!

Replace `http://192.168.32.3:3128` with whatever the appropriate proxy server configuration is for your network. 

Note that in our case the HTTPS proxy deliberately uses HTTP to access the proxy server - we got SSL3 protocol errors when trying to download the Heroku CLI otherwise.

1. Create a file called environment with the following contents

       export http_proxy="http://192.168.32.3:3128"
       export https_proxy="http://192.168.32.3:3128"
       export no_proxy="localhost, 127.0.0.1"

2. Run `sudo cp environment /etc` (in our Raspberry Pis the environment files were empty) 
2. Run `sudo visudo`
3. Add the line below to the file and save

       Defaults    env_keep+="http_proxy https_proxy no_proxy"

4. For some reason Git ignores these, so we need to configure too - run these commands:

       git config --global http.proxy http://192.168.32.3:3128
       git config --global https.proxy http://192.168.32.3:3128
 
5. Run 'sudo reboot' (to restart)