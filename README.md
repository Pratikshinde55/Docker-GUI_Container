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

now check container logs :

    #sudo docker logs pratik1
    
and we can try to connect container from outside (browser) 

here show error while connecting to container by HTTP (http://52.90.226.27:6901/?password=pratik)

we write password then also unable to connect -

![image](https://github.com/user-attachments/assets/070c9471-cc3c-4b4a-8d72-2ecea5747da7)



Now we can by using TightVNC viewer for GUI container:

Fill public Ip of EC2 and port no. -->> (52.90.226.27:5901)

![image](https://github.com/user-attachments/assets/99d21477-3f4d-4623-a5cd-3ad9783d029a)

while fill pass also unble to connect :

![image](https://github.com/user-attachments/assets/95bf9c5d-c26a-4136-87bd-49982e444545)



Now Fix this :


    




