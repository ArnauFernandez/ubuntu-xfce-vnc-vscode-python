# Docker: Ubuntu with XFCE, VNC, VSCode, and Python

This Docker container provides a Ubuntu-based graphical environment with XFCE, remote access via VNC, pre-installed VSCode, and Python support.

# 🚀 Building the Image

To build the image, run the following command in the directory where your Dockerfile is located:

docker build -t ubuntu-xfce-vnc-vscode-python -f Dockerfile .

# ▶️ Running the Container

## Option 1: Temporary Container (Removed on Exit)

docker run -it --rm --cap-add=SYS_ADMIN -p 5901:5901 -p 555:22 ubuntu-xfce-vnc-vscode-python

--rm: Removes the container when it stops.

--cap-add=SYS_ADMIN: Grants administrative permissions required for XFCE.

-p 5901:5901: Maps port 5901 for VNC connection.

-p 555:22: Maps port 22 for SSH access.

## Option 2: Persistent Container

docker run -it --cap-add=SYS_ADMIN -p 5901:5901 -p 555:22 ubuntu-xfce-vnc-vscode-python

This container will not be automatically removed and will retain changes made during your session.

# 📱 Connecting to the VNC Server

To access the graphical environment, you need a VNC client. Remmina is recommended on Linux, but any VNC-compatible client will work.

Install Remmina (optional):

sudo apt install remmina -y

Connect using the following address in your VNC client:

localhost:5901

# 🛠️ Additional Notes

Ensure ports 5901 (VNC) and 555 (SSH) are not used by other processes.

To persist data, add volume mappings with -v in the docker run command.

If you have issues connecting to VNC, check that the VNC service is running inside the container.
