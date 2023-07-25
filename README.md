# Getting Started with Untether tsunAImi tsn200ES Accelerator
To start using the Untether tsunAImi tsn200ES Accelerator, follow these steps:
1. **Download and Install CADPass:**
   Download [CADPass](https://www.cmc.ca/cadpass/) from the provided link and install it on your system.
2. **Login to CADPass:**
   Use your CMC microsystems credentials to log in to CADPass. After logging in, you will see the following window:
   ![Image Alt Text](https://github.com/cmcmicrosystems/Untether-tsunAImi-Accelerator/blob/main/cadpass.JPG)
3. **Obtain AI Jupyter Notebook Shortcut Details:**
   Right-click on AI Jupyter Notebook and select "Shortcut details" as shown in the following figure:
   ![Image Alt Text](https://github.com/cmcmicrosystems/Untether-tsunAImi-Accelerator/blob/main/cadpass1.JPG)
4. **Find the Server IP Address:**
   In the shortcut details window, you will find the IP address of the server.
5. **SSH to the Server:**
   Use the obtained IP address to SSH into the server using the following command:
   ```
   ssh username@ipaddress
   ```
7. **Check Available Accelerators:**
Once connected to the server, type the following command to see available accelerator cards in the system:
  ```
lspci | grep accelerator
```
The output of this command will display the available accelerator cards, such as:
86:00.0 Processing accelerators: Untether AI runAI200 AI Inference Accelerator (rev 01)
8. **Running the Docker Containers:**
Each container has a `spinup.sh` script that launches the container and detects any runAI200 devices on the host. Devices found by the kernel module will appear as `/dev/uai*` both on the host and inside the container.
![Image Alt Text](https://github.com/cmcmicrosystems/Untether-tsunAImi-Accelerator/blob/main/docker.JPG)
To access Jupyter Notebook from outside the container, copy the link from the previous window to your browser and use the token generated by the running Jupyter Notebook session.
![Image Alt Text](https://github.com/cmcmicrosystems/Untether-tsunAImi-Accelerator/blob/main/Jupyter.JPG)
## Resources
- Presentation: Energy-Efficient AI Inference Acceleration with Untether by Gaurav Singh (Untether AI)
- Datasheet and Whitepaper: [https://www.untether.ai/products](https://www.untether.ai/products)
- Getting Started, Tutorials and Demos are available on the Untether AI® Documentation Portal.
## Contact Us
Dr. Yassine Hariri
Senior Staff Scientist
AI/ML and Embedded Systems
Email: [Yassine](mailto:yassine.hariri@example.com)
