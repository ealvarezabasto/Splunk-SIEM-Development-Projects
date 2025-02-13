# Splunk-ES-Personal

## 1. Importing Data
### 1.1 access.log log file
* Add Data > Classify Source Type: access_combined > Splunk parser parses information appropiately for specificy sourcetype
<img width="953" alt="image" src="https://github.com/user-attachments/assets/2cdbc27b-f5ae-49da-acb1-625f49701d79" />

* Access.log data successfully uploaded
<img width="943" alt="image" src="https://github.com/user-attachments/assets/55143c4f-7c24-400d-8ef3-1d3b237a3aa4" />

### 1.2 secure.log log file
* Add Data > Classify Source Type: linux_secure > Splunk parser parses information appropiately for specific sourcetype
<img width="954" alt="image" src="https://github.com/user-attachments/assets/7a0d9fd1-a556-432e-8b8f-75014bdfc0c9" />

* secure.log data successfully uploaded
* However, some data has not been parsed appropiately.
![image](https://github.com/user-attachments/assets/e3fd4bc5-f084-48ea-8b9c-c8a65c34ec79)

* To fix this parsing issue, download 'Splunk Add-on for Unix and LInux' by going to Apps > Find more apps 
* Entire secure.log file is entirely getting parsed thanks to the installation of the add-on app.
  <img width="942" alt="image" src="https://github.com/user-attachments/assets/57382911-656a-4015-870a-0d421456bbbe" />

## 2. Use-Case 1: Find Attack Vectors
### Requirements
* SCOPE: Compliance auditor requested to find certain attack vectors related to SSH Logins.

### 2.1 Find how many type of logins from every IPs.
![image](https://github.com/user-attachments/assets/02e36151-5504-4244-9d6a-58c1f0680276)

### 2.2 Find List of Countries from which the failed login attempts were made:
* SPL Command: iplocation
* SPL Command: source="secure.log" action=blocked | iplocation src
* Note: Field src showcases the ipaddress of where the attempt is being made from.

### 2.3 Create a visualization of countries in world map based on failed logins.
* SPL Command: source="secure.log" | iplocation src | geostats count by Country
* ![image](https://github.com/user-attachments/assets/ec115e91-9f27-4e21-876f-c7c2533675ef)

