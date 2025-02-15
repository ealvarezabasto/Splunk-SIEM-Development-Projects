# Installing a Server in AWS EC2 (Ubuntu Linux)

## 1. Create Ubuntu Linux within AWS EC2
* Select EC2

  ![image](https://github.com/user-attachments/assets/c6b84a06-f0b2-4be3-aafe-bce64d2987bc)

* Select 'Launch Instance'

  ![image](https://github.com/user-attachments/assets/33b8b96d-2013-45c9-b477-b218f01a3e86)

* Select 'Ubuntu'> Launch Instance
  ![image](https://github.com/user-attachments/assets/a5c31582-b2f6-42bd-a5c6-e959dec994e7)

*Select 'splunkOS' for Key pair and check 'Allow HTTPS traffic from the internet'
  ![image](https://github.com/user-attachments/assets/4d6c5389-b320-4d78-b80e-6656feb56aba)

*increase to 20 GIB and select 'Launch Instance'
  ![image](https://github.com/user-attachments/assets/51ce77d6-33ec-4ca6-98e0-80daad9253da)

* Should display the 'Splunk-ES-UbuntuLinux' Ubuntu Linux Server
  ![image](https://github.com/user-attachments/assets/bcd55739-91f0-468a-a0f6-aee112125359)

*Select 'Splunk-ES-UbuntuLinux' Linux Sever > Copy the Public IPv4 address (3.145.94.85) and select 'Connect'
  ![image](https://github.com/user-attachments/assets/dbb52d2c-9287-4b41-8f6a-884fdbeecb0e)

## 2. Create Splunk ES Account [Ubuntu Linux]
* Open your Splunk ES account and download LInux > .deb by copying the wget link
  ![image](https://github.com/user-attachments/assets/826ea1c2-eaca-4826-afb0-861440f09d6f)

* Return to Command Line within AWS EC2 Ubuntu Linux. Type **sudo su -**. Now that you're a root user, type the wget link that was copied earlier. installation will begin.
<img width="945" alt="image" src="https://github.com/user-attachments/assets/20c60d06-a329-41de-9ecb-9a991af879be" />


* type **ls -1** to find the .deb file > type **sudo dpkg -i ./<<copy the .deb file>>** > message "COMPLETE" appears > type **ls /opt/** to identfy where "SPLUNK" is stored
  <img width="408" alt="image" src="https://github.com/user-attachments/assets/1f42f1a5-013a-4670-82dd-7e399275efe9" />


* type **sudo /opt/splunk/bin/splunk start** > enter username / password > it appears that your Splunk WEB IP address is: http://ip-172-31-1-61:8000
  ![image](https://github.com/user-attachments/assets/2db78fa8-89d7-46b3-b527-8c33a23a9863)

*type http://ip-172-31-1-61:8000 is a browser, but no page appears.
  <img width="427" alt="image" src="https://github.com/user-attachments/assets/56bb3a1b-9475-4276-8e58-13fd0c28be4a" />

*Return to AWS EC2 instance > 'Security' > select 'launch-wizard'
  ![image](https://github.com/user-attachments/assets/b798ad59-a5e7-4a5c-b9ce-e01788c8c8e6)

*Select 'Security group ID' 
  ![image](https://github.com/user-attachments/assets/3a4d0272-8a75-4fe8-a805-728e36e15cc3)

 * Select 'Edit inbout rules' > 'Add rule' > Custom TCP - 8000 (port #) > Anywhere IPV4 > 'Save Rule'
   <img width="953" alt="image" src="https://github.com/user-attachments/assets/c9819835-fc2c-43f2-a6c7-00794bf3ad8d" />

*Return to AWS EC2 > copy Public IPv4 address and add 80000 > enter username/password previously created
  ![image](https://github.com/user-attachments/assets/f2fc97ee-c114-4efb-9603-b7b21004a217)




