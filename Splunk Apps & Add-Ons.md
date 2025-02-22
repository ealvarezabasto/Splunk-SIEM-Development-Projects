## Splunk Apps & Add-Ons

**Purpose:** Add-ons extend the functionality of the Splunk platform and provide required field extractions, lookups, saved searches, and others.

### 1 For Data Parsing

**Description:** For the logs that Splunk does not parse by default, you can install various AddOns from the Splunk marketplace to do the parsing for us.

**EXAMPLE BELOW:**

* Adding Data Source secure.log
**Description:** Data Type: Linux Authentication Logs | Description: Authentication Success & Failure Related Messages such as 'OS loging to your server', 'how many attempts made by an attacker', etc.

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
  
### 2. For Data Input

**Description:** Add-ons can also be used to extract data from a specific destination.

#### * **Example 1** 

![image](https://github.com/user-attachments/assets/442c8556-6803-4e74-ad18-4dc5adecdfea)

* Using AWS Add-On to extract data from AWS. The AWS Add-on has required scripts that connect to your AWS Environment and retrieve the required logs and other information, and add it as part of Splunk environment. 

#### * **Example 1** 
* Using Splunk Add-on for Unix and Linux for:
* Field extraction
* Monitors file and directories
* Has scripts that run and give you the output related to the CPU utility utilization, the overall badwidth and disk space
* 
