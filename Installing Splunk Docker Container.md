## Installing Splunk Docker Container.md

### Once Docker is up and running, launch Splunk Docker container
* Access AWS EC2 'Splunk-Docker-Ubuntu'

* docker run -d -p 8000:8000 -e "SPLUNK_START_ARGS=--accept-license" -e "SPLUNK_PASSWORD=<password>" -- name splunk splunk/splunk:latest
  ![image](https://github.com/user-attachments/assets/0a363314-ce73-4b8b-a48c-db5320a51be4)

*  Select 'Connect'
  ![image](https://github.com/user-attachments/assets/0bce50b0-b6b8-4a28-9b33-bd1750b2997c)

* Within Command LIne, type **sudo su -**, now that you're a root use type **docker run -d -p 8000:8000 -e SPLUNK_START_ARGS='--accept-license' -e SPLUNK_PASSWORD='<password>' splunk/splunk:latest**
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
