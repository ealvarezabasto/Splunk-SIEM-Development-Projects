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

### 2. Once Docker is up and running, launch 'Splunk-Docker-Ubuntu' container
* Access AWS EC2 'Splunk-Docker-Ubuntu'
  
  ![image](https://github.com/user-attachments/assets/0a363314-ce73-4b8b-a48c-db5320a51be4)

*  Select 'Connect'
  ![image](https://github.com/user-attachments/assets/0bce50b0-b6b8-4a28-9b33-bd1750b2997c)

* Within Command LIne, type **sudo su -**, now that you're a root use type **docker run -d -p 8000:8000 -e SPLUNK_START_ARGS='--accept-license' -e SPLUNK_PASSWORD='type preferred password' splunk/splunk:latest**
  ![image](https://github.com/user-attachments/assets/c3c64c93-6169-4fe6-84a1-e362596c24bc)

* Type **docker ps** > shows the list of containers. Currently we have 1 called Splunk
  ![image](https://github.com/user-attachments/assets/acaf506e-cdc6-4242-af03-7c8808a069a5)

* Return to AWS EC2 'Splunk-Docker-Ubuntu'
![image](https://github.com/user-attachments/assets/0e60bb85-4677-4c1f-9b6d-b73e86730d3b)

* try to access the Public IPv4 address > browser not running
![image](https://github.com/user-attachments/assets/1db5dc5c-bfd8-4dda-9b48-fc79dc09788e)

* Return to AWS EC2 'Splunk-Docker-Ubuntu', select 'launch-wizard-4' > select 'Security group ID'
  ![image](https://github.com/user-attachments/assets/439fbea8-869e-4359-b9aa-f2fe0ca762f8)

* Select 'Edit inbound rules'
![image](https://github.com/user-attachments/assets/8a38a52d-fedf-4f8a-8282-a7350278f8ca)

* Add 'Custom TCP' > 8000 > Anywhere-IPv4
  ![image](https://github.com/user-attachments/assets/35b393d0-e725-4b1b-a66a-e8118925b439)

* Copy the Public IPv4 address:8000 and page should appear
