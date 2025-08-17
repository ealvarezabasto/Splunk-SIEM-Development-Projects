# Configure Forwarders in Splunk

## Step 1: Loging to the Intermediate Forwarder server
* Login to Intermediate Forwarder server

* Login as a Splunk user
  Command Line -
  ***sudo su - splunk***

## Step 2: Check the Status of the Splunk Forwarder
* For Intermediate Forwarder (IF)
  Command Line -
  ***/opt/splunk/bin/splunk status***

## Step 3: Navigate to the Bin Folder
* Command Prompt - ***cd /opt/splunk/bin***

## Step 4: Connect the Forwarders to the Deployment Server
* Command Prompt - ***./splunk set deploy-poll YOUR_DEPLOYMENT_SERVER_IP:8089***

## Step 5: Restart Splunk to Apply Changes
* Command Prompt - ***./splunk restart***

  <img width="806" height="219" alt="image" src="https://github.com/user-attachments/assets/9943f41a-6306-4194-960d-b84b70c621d8" />
