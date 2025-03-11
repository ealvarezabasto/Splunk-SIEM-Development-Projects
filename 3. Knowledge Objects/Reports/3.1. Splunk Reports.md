## Splunk Reports

### Use Case 1
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

### Use Case 1
