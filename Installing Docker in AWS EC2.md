# Installing an Ubuntu Linux Server in AWS EC2 for Docker

## 1. Create Ubuntu Linux within AWS EC2
* Select EC2

  ![image](https://github.com/user-attachments/assets/c6b84a06-f0b2-4be3-aafe-bce64d2987bc)

* Select 'Launch Instance'

  ![image](https://github.com/user-attachments/assets/33b8b96d-2013-45c9-b477-b218f01a3e86)

* Select 'Ubuntu'> Launch Instance
  ![image](https://github.com/user-attachments/assets/a5c31582-b2f6-42bd-a5c6-e959dec994e7)

* Select 'splunkOS' for Key pair and check 'Allow HTTPS traffic from the internet'
  ![image](https://github.com/user-attachments/assets/4d6c5389-b320-4d78-b80e-6656feb56aba)

* increase to 20 GIB and select 'Launch Instance'
  ![image](https://github.com/user-attachments/assets/51ce77d6-33ec-4ca6-98e0-80daad9253da)

* Should display the 'Splunk-ES-UbuntuLinux' Ubuntu Linux Server
  ![image](https://github.com/user-attachments/assets/bcd55739-91f0-468a-a0f6-aee112125359)

* Select 'Splunk-ES-UbuntuLinux' Linux Sever > Copy the Public IPv4 address (3.145.94.85) and select 'Connect'
  ![image](https://github.com/user-attachments/assets/dbb52d2c-9287-4b41-8f6a-884fdbeecb0e)

### 2. Once server is up and running, launch 'Splunk-Docker-Ubuntu' container
* Access AWS EC2 'Splunk-Docker-Ubuntu'
  
  ![image](https://github.com/user-attachments/assets/0a363314-ce73-4b8b-a48c-db5320a51be4)

*  Select 'Connect'
  ![image](https://github.com/user-attachments/assets/0bce50b0-b6b8-4a28-9b33-bd1750b2997c)

* Within Command LIne, type **sudo su -**, now that you're a root use type **docker run -d -p 8000:8000 -e SPLUNK_START_ARGS='--accept-license' -e SPLUNK_PASSWORD='type preferred password' splunk/splunk:latest**

* Type **docker ps** > shows the list of containers. Currently we have 1 Splunk container called sharp_proskuriakova
  
  ![image](https://github.com/user-attachments/assets/753871d7-9af3-4352-8d6d-e55203ee9108)

* Type **docker logs sharp_proskuriakova**
  
  <img width="566" alt="image" src="https://github.com/user-attachments/assets/43764da5-165e-4593-82a6-8a9775a12641" />

* Return to AWS EC2 'Splunk-Docker-Ubuntu'
  
  ![image](https://github.com/user-attachments/assets/9f1c7ec7-693d-45ae-adde-5b099dccea7a)

* try to access the Public IPv4 address > page should appear
  
![image](https://github.com/user-attachments/assets/b7610b2e-7986-4e1e-9361-269c46540892)
![image](https://github.com/user-attachments/assets/cd27e366-b097-41e7-b35b-7511b40cfc3a)

## 3. Finding out the Password of your Splunk Container in Docker

* Type **docker ps** > search for Splunk Container within Docker - name: sharp_proskuriakova

* Type docker inspect --name of Splunk Container--

  <img width="935" alt="image" src="https://github.com/user-attachments/assets/6f68b8e7-5693-4f0c-b5a1-41019c9053ba" />


* Scroll to where it shows SPLUNK_PASSWORD=

  ![image](https://github.com/user-attachments/assets/6e87e9de-1a9b-456b-a7ce-5017c6b59c3d)
