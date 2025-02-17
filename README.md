# Splunk-ES-Personal

## 1. Importing Data
### 1.1 access.log log file
**Description:** Data Type: HTTP Access Logs | Description: Records data of requests processed by Web-Server such as 'canceling a subscription', 'purchasing a product', etc.

* Settings > Add Data
  
  ![image](https://github.com/user-attachments/assets/87c80793-f86a-4cc4-81d0-42581523411d)

* Add Data > Classify Source Type: access_combined > Splunk parser parses information appropiately for specificy sourcetype

  > Source Type: mandatory Splunk field that tells Splunk what kind of data contains the file so that it can format the data intelligently during indexing.
  > access_combined: NCSA combined format HTTP we server logs (can be generated by apache or other web servers)
  
  <img width="953" alt="image" src="https://github.com/user-attachments/assets/2cdbc27b-f5ae-49da-acb1-625f49701d79" />

* Access.log data successfully uploaded
  <img width="943" alt="image" src="https://github.com/user-attachments/assets/55143c4f-7c24-400d-8ef3-1d3b237a3aa4" />

### 1.2 secure.log log file
**Description:** Data Type: Linux Authentication Logs | Description: Authenitcaiton Success & Failure Related Messages such as 'OS loging to your server', 'how many attempts made by an attacker', etc.

* Add Data > Classify Source Type: linux_secure > Splunk parser parses information appropiately for specific sourcetype

  > source type: linux_secure: format for the /var/log/secure file containing all security related messsaged on a Linux machine.
  
  <img width="954" alt="image" src="https://github.com/user-attachments/assets/7a0d9fd1-a556-432e-8b8f-75014bdfc0c9" />

* secure.log data successfully uploaded
* However, some data has not been parsed appropiately.
  ![image](https://github.com/user-attachments/assets/e3fd4bc5-f084-48ea-8b9c-c8a65c34ec79)

* To fix this parsing issue, download 'Splunk Add-on for Unix and LInux' by going to Apps > Find more apps

  ![image](https://github.com/user-attachments/assets/773f211f-adbf-4d96-89f4-65a035034350)

  * Entire secure.log file is entirely getting parsed thanks to the installation of the add-on app.
  <img width="942" alt="image" src="https://github.com/user-attachments/assets/57382911-656a-4015-870a-0d421456bbbe" />

## 2. Use-Case 1: Find Attack Vectors
### Requirements
* **SCOPE:** Compliance auditor requested to find certain attack vectors related to SSH Logins.

### 2.1 Find how many type of logins from every IPs.
![image](https://github.com/user-attachments/assets/02e36151-5504-4244-9d6a-58c1f0680276)

### 2.2 Find List of Countries from which the failed login attempts were made:
* SPL Command: iplocation
* SPL Command: source="secure.log" action=blocked | iplocation src
* Note: Field src showcases the ipaddress of where the attempt is being made from.

### 2.3 Create a visualization of countries in world map based on failed logins.
* SPL Command: source="secure.log" | iplocation src | geostats count by Country
* ![image](https://github.com/user-attachments/assets/ec115e91-9f27-4e21-876f-c7c2533675ef)

## 3. Splunk Reports
### 3.1 Use Case 1
* Requirements: Security Manager should be informed with list of IP address and Country location from which failed SSH attempts are being made at every 24 hours over email.
* SPL Command:

source="secure.log" fail*
| iplocation src
| table src, Country
|  uniq
<img width="941" alt="image" src="https://github.com/user-attachments/assets/863bde37-1839-420a-9f5d-eea32335bd82" />

* To automate the search of this query to run every day, SAVE AS > Report

  ![image](https://github.com/user-attachments/assets/19293797-0339-47ba-af86-ce7ce91b85a0)

* View Report

  <img width="938" alt="image" src="https://github.com/user-attachments/assets/e6b0ab9b-bbbb-4fc9-8d23-4f62a9e11a18" />

* Edit > Edit Schedule
  ![image](https://github.com/user-attachments/assets/87538e6a-3168-4881-bfc2-c5a25676c5a1)
  ![image](https://github.com/user-attachments/assets/1256b133-2dd3-4ae3-b7b9-b67a77a5f81c)


* Go to 'Reports' tab to review list of all reports created
* 
  ![image](https://github.com/user-attachments/assets/dda9807b-0ba9-422f-b8e5-dd66a1b5ddf8)

