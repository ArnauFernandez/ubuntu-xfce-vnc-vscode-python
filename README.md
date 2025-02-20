# Build image with docker build

docker build -t ubuntu-xfce-vnc-vscode-python -f Dockerfile .

# run the new container you'll find two commands first one is for kill the container once it's gone second one is persistant which means it doesn't dissapear

docker run -it --rm --cap-add=SYS_ADMIN -p 5901:5901 -p 555:22 ubuntu-xfce-vnc-vscode-python 

docker run -it --cap-add=SYS_ADMIN -p 5901:5901 -p 555:22 ubuntu-xfce-vnc-vscode-python 

# Connect to VNC server

install an vnc client such as remmina which is an GUI of vnc client if you redirect correctly the ports you'll be able to connect to the server by writing localhost:5901
