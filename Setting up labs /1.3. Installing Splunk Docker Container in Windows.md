# Installing Splunk Docker Container in Windows (Personal Laptop).md

## 1. Download Docker App to Windows (Personal Laptop)

* Go to www.docker.com/products/docker-desktop/ and 'Download for Windows -AMD64"
![image](https://github.com/user-attachments/assets/3a839e39-e253-4d84-9238-7dd5798156aa)

* Download the 'Docker.Desktop' app > open an account
![image](https://github.com/user-attachments/assets/eabbe988-a0a8-4414-92b8-17e2f8d08772)

## 2. Open Command Prompt in Windows (Personal Laptop)

* As a normal user (not root), type **docker run -d -p 8000:80000 -e SPLUNK_START_ARGS='--accept-license' -e SPLUNK_PASSWORD=--enter preferred password-- splunk/splunk:late st** > press Enter. After running, type **docker ps**. This will list all Docker containers including the Splunk container just created called **zealous_brattain**

![image](https://github.com/user-attachments/assets/dd9c233f-f33b-45c4-9daa-2dc2eae894a3)

* Type **logs zealous_brattain** to list out all Splunk logs within Docker Splunk Container

## 3. Return to Docker Desktop App in Windows (Personal Laptop)
* The Splunk container called **zealous_brattain** appears

  ![image](https://github.com/user-attachments/assets/a701ff9c-1184-48e5-8f15-907a05f1f4a5)
