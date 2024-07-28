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

 here,
    -d: Run the container in detached mode.
    -p 5901:5901: Map port 5901 of the container to port 5901 of the host (VNC access).
    -p 6901:6901: Map port 6901 of the container to port 6901 of the host (web-based VNC access).
    
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


I can manually reset the VNC password by attaching to the running container and using the "vncpasswd" command.

    #sudo docker exec -it pratik1 bash
    #vncpasswd

After resetting the password, restart the VNC server within the container.

    # vncserver -kill :1
    # vncserver :1

![image](https://github.com/user-attachments/assets/7373b6c0-08be-4bae-9c53-6a6002dd785c)



now , Agian check on Browser with new saved password (newpassowrd - pratik55)

 public IP of EC2 : port no (http://52.90.226.27:6901/?password=pratik55)

![image](https://github.com/user-attachments/assets/ff95071c-e1d4-4279-a63e-a0788b8526f8)


now check GUI Container by TightVNC viewer:

fill new password 

![Screenshot 2024-07-28 141953](https://github.com/user-attachments/assets/b95063a9-2775-44f1-839e-8d143c3545e3)

    



