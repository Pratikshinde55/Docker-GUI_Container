# Docker-GUI_Container
Docker GUI Container


For this i use AWS Cloud EC2 instance :

install docker and start docker services

     #sudo apt-get update
     #sudo apt-get install -y docker.io
     #sudo systemctl start docker 


For this i use precreated image :

    #sudo docker pull consol/ubuntu-xfce-vnc

    #  sudo docker run -d --name=pratik1 -p 5901:5901 -p 6901:6901 -e VNC_PASSWORD=pratik consol/ubuntu-xfce-vnc

    




