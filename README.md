# Getting Started with Untether tsunAImi tsn200ES Accelerator
To start using the Untether tsunAImi tsn200ES Accelerator, follow these steps:
1. **Download and Install CADPass:**
   Download [CADPass](https://www.cmc.ca/cadpass/) from the provided link and install it on your system.
   
2. **Login to CADPass:**
   Use your CMC microsystems credentials to log in to CADPass. After logging in, you will see the following window:
   ![Image Alt Text](https://github.com/cmcmicrosystems/Untether-tsunAImi-Accelerator/blob/main/cadpass.JPG)
   
3. **Obtain AI Jupyter Notebook Shortcut Details:**
   Right-click on AI Jupyter Notebook and select "Shortcut details" as shown in the following figure: 
<p align="center">
    <img src="https://github.com/cmcmicrosystems/Untether-tsunAImi-Accelerator/blob/main/cadpass1.JPG" alt="Image Alt Text" style="width: 250px; height: 400px;">
</p>

5. **Find the Server IP Address:**
   In the shortcut details window, you will find the IP address of the server. In this case, the IP address of the server is 172.16.60.17:    
6. **SSH to the Server:**
   Use the obtained IP address to SSH into the server using the following command:
   ```
   ssh username@ipaddress                     
   ```
7. **Copy the configuration script and tutorials:**
   ```
   cp -r -a /CMC/* /home/username
   cd /home/username/untether
   ```
8. **Change permission of your directory and files**
   ```
   chmod-R a+rwx /home/username/untether
   ```   
9. **Check Available Accelerators:**
Once connected to the server, type the following command to see available accelerator cards in the system:
   ```
   lspci | grep accelerator
   ```
The output of this command will display the available accelerator cards, such as:
   ```
   86:00.0 Processing accelerators: Untether AI runAI200 AI Inference Accelerator (rev 01)
   ```
10. **Running the Docker Containers:**

Before launching the container, type the following command in a separate terminal to establish a secure shell (SSH) connection to the server with the ipaddress, using your username and port 22.
```
ssh -N -f -L localhost:8888:localhost:8888 username@ipaddress -p 22
```
 The options used in the command are:

-N: Instructs SSH not to execute any remote commands after establishing the connection.
-f: Requests SSH to go into the background just before command execution.
-L localhost:8888:localhost:8888: Sets up local port forwarding, where connections to port 8888 on the local machine are forwarded securely through the SSH tunnel to port 8888 on the remote server.
username@ipaddress: Specifies the username ("username") and the IP address of the remote server.
-p 22: Specifies the port number (22) to use for the SSH connection.

Each container has a `spinup.sh` script that launches the container and detects any runAI200 devices on the host. Devices found by the kernel module will appear as `/dev/uai*` both on the host and inside the container.

Type './spinup.sh' to launch the container as shown in the following image:
![Image Alt Text](https://github.com/cmcmicrosystems/Untether-tsunAImi-Accelerator/blob/main/docker.JPG)

To access Jupyter Notebook from outside the container, type the following command in the terminal:
```
python3 -m notebook --ip 0.0.0.0 --nobrowser $
```
Use the token generated by the running Jupyter Notebook session.
![Image Alt Text](https://github.com/cmcmicrosystems/Untether-tsunAImi-Accelerator/blob/main/Jupyter.JPG)
9. **Access Jupyter notebook tutorials:**
Open your Jupyter Notebook in your web browser and navigate to the "Workspace" tab. Click on "tutorials" to access the available Jupyter Notebook tutorials.
## Resources
- [Presentation: Energy-Efficient AI Inference Acceleration with Untether by Gaurav Singh (Untether AI)](https://www.youtube.com/watch?v=oK7YbOD4TYk&t=2112s)
- [Datasheet and Whitepaper](https://www.untether.ai/products)
- [Getting Started, Tutorials and Demos are available on the Untether AI® Documentation Portal](https://www.untether.ai/)

## Get Access today
Contact Yassine Hariri
Senior Staff Scientist
AI/ML and Embedded Systems
Email: [Yassine](mailto:yassine.hariri@cmc.ca)
