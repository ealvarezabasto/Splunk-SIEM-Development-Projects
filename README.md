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

* Download 'Splunk Add-on for Unix and LInux
* Entire secure.log file is entirely getting parsed thanks to the installation of the add-on app.
  <img width="942" alt="image" src="https://github.com/user-attachments/assets/57382911-656a-4015-870a-0d421456bbbe" />
